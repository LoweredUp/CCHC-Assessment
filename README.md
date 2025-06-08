## Programmer Assessment Q4

# Clinical Analytics Dashboard

This is an interactive dashboard for exploring clinical patient volume, wait times, and care scores.

## Setup and Installation on Linux

These instructions are for a fresh, minimal Debian/Ubuntu-based Linux installation.

### 1. Update System
First, update your package manager and system packages.
```bash
sudo apt update && sudo apt upgrade -y
```

### 2. Install Python
This project requires Python 3.12 or newer. Install Python and the `venv` module for creating virtual environments.
```bash
sudo apt install python3.12 python3.12-venv -y
```

### 3. Get the Project Code
Clone the repository to your machine.
```bash
# Replace with your repository URL
git clone [https://github.com/your-username/your-repo-name.git](https://github.com/your-username/your-repo-name.git)
cd your-repo-name
```

### 4. Setup Virtual Environment
Create and activate a virtual environment to isolate project dependencies.
```bash
# Create the environment
python3.12 -m venv venv

# Activate the environment
source venv/bin/activate
```
Your terminal prompt should now be prefixed with `(venv)`.

### 5. Install Dependencies
Use `pip` to install all the required packages from the `pyproject.toml` file.
```bash
pip install .
```

## How to Run the Application

With the virtual environment still active, run the main application script.
```bash
python main.py
```
You will see output indicating that the Dash app is running, similar to this:
```
Dash is running on [http://0.0.0.0:10030/](http://0.0.0.0:10030/)

 * Serving Flask app 'main'
 * Debug mode: on
...
```

## How to Access the Dashboard

The application is running on port **10030**.

To access it, you do not need to use port forwarding if you are on the same local network as the Linux machine.

1.  **Find your Linux machine's IP Address:**
    Open a new terminal on the Linux machine and run:
    ```bash
    ip addr show
    ```
    Look for an IPv4 address under your primary network interface (e.g., `eth0` or `wlan0`), which will look something like `192.168.1.15` or `10.0.0.5`.

2.  **Access from another computer:**
    On another computer connected to the **same Wi-Fi or local network**, open a web browser and navigate to:
    ```
    http://<LINUX_MACHINE_IP_ADDRESS>:10030
    ```
    For example: `http://192.168.1.15:10030`

This works because the app is configured to run on `host='0.0.0.0'`, making it accessible from other devices on your local network.