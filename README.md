# Distributed Computing (DC) Lab Manual

This repository contains practical implementations for the Distributed Computing (DC) Laboratory.

## 📌 Prerequisites
- **Python 3.8+** installed.
- No external packages needed! All practicals use Python's standard built-in libraries (`socket`, `threading`, `xmlrpc`, `argparse`).
- A virtual environment (`venv`) is **not required**.

---

## 🚀 How to Run Each Practical

Clone the repository and open the project directory in VS Code:
```bash
git clone <YOUR_REPO_URL>
cd "DC Lab Manual"
```

---

### Practical 1: Concurrent TCP Echo Server & Client
Demonstrates socket programming with a multi-threaded concurrent echo server and interactive client.

- **Option A (Single Terminal - Fastest):**
  ```bash
  cd "Practical 1"
  python run_echo.py
  ```

- **Option B (Two Separate Terminals):**
  - **Terminal 1 (Server):**
    ```bash
    cd "Practical 1"
    python echo_server.py
    ```
  - **Terminal 2 (Client):**
    ```bash
    cd "Practical 1"
    python echo_client.py
    ```

---

### Practical 2: Inter-Process Communication (IPC Swap)
Demonstrates thread synchronization and communication using `threading.Condition` to safely swap shared variables.

- **Run command:**
  ```bash
  cd "Practical 2"
  python ipc_swap.py
  ```

---

### Practical 3: RPC Chat Application (XML-RPC)
Demonstrates Remote Procedure Call (RPC) for sending and retrieving chat messages across client and server.

- **Step 1 - Terminal 1 (Start Server First):**
  ```bash
  cd "Practical 3"
  python server.py
  ```
- **Step 2 - Terminal 2 (Run Client):**
  ```bash
  cd "Practical 3"
  python client.py
  ```

---

### Practical 4: Remote Method Invocation (RMI Simulation)
Demonstrates invoking remote methods (`say_hello`, `add_numbers`) on a remote object instance over the network.

- **Step 1 - Terminal 1 (Start Server First):**
  ```bash
  cd "Practical 4"
  python server.py
  ```
- **Step 2 - Terminal 2 (Run Client):**
  ```bash
  cd "Practical 4"
  python client.py
  ```

---

### Practical 5: Thread Synchronization (Mutex Lock)
Demonstrates mutual exclusion and prevention of race conditions on a shared counter using `threading.Lock`.

- **Run command:**
  ```bash
  cd "Practical 5"
  python counter.py
  ```

---

## 🛠 Troubleshooting
- **`ConnectionRefusedError: [WinError 10061]`**:
  In Practical 3 and 4, always start `server.py` in Terminal 1 first before running `client.py` in Terminal 2.
- **Port 8000 Conflict**:
  If Practical 3's server is still holding port 8000 when starting Practical 4, terminate the background process in PowerShell:
  ```powershell
  Stop-Process -Id (Get-NetTCPConnection -LocalPort 8000).OwningProcess -Force -ErrorAction SilentlyContinue
  ```
