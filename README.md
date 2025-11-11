## 🛠️ Wiki.js Local Setup Guide

Follow these steps to get Wiki.js running on your local machine.

---

## 🚀 Initial Setup

1.  **Clone the Repository:**
    ```bash
    # Use the appropriate git clone command for your repository
    git clone [repository-url]
    ```
2.  **Open the Repository**
3.  **Create Secrets Folder:**
    * Create a folder named `secrets` in the root of the repository.
4.  **Create Password File:**
    * Inside the `secrets` folder, create a file named **`password.txt`**.
    * This file should contain the plain English password for `sermon_db(jtj)`.

---

## 📦 Install Dependencies

5.  In the terminal, run the following command to install dependencies:
    ```bash
    npm install
    ```

### ⚠️ Troubleshooting: `npm install` Error (PowerShell/Execution Policy)

**IF YOU RECEIVE AN ERROR WHILE RUNNING `npm install` in VS Code, follow Step 6.**

6.  **Temporarily Change PowerShell Execution Policy:**
    * **a) Open PowerShell as Administrator:**
        * Close the integrated terminal in VS Code.
        * Search for **"Windows PowerShell"** in your Windows search bar.
        * Right-click on it and select **"Run as administrator."**
    * **b) Set the Policy to `RemoteSigned` for the current session:**
        * Run the command below. The `-Scope Process` is crucial as it only changes the policy for the **current, single PowerShell session**, reverting the change when you close the window.
        ```powershell
        Set-ExecutionPolicy RemoteSigned -Scope Process
        ```
    * **c) Confirm the Change:**
        * PowerShell may ask you to confirm. Press **`Y`** (for Yes) and then **`Enter`**.
    * **d) Re-run `npm install` in VS Code:**
        * Go back to VS Code and open a new terminal.
        * Run the command again:
            ```bash
            npm install
            ```
        * This should now execute without the PSSecurityException.

---

## ☁️ Azure Networking & Database Access

7.  **Allow Your IP Address:**
    * Go to the **Azure Portal**.
    * Navigate to our database resource.
    * Go to the **Networking** tab.
    * Click **'Add current client IP address.'**
    * **⚠️ IMPORTANT:** You **MUST** click **'Save'** at the top left of the window for the change to take effect.

---

## 🐳 Running with Docker

8.  **Ensure Docker Desktop is Running:**
    * Before running the Docker command, you **MUST HAVE DOCKER DESKTOP RUNNING**.
9.  **Build and Run the Container:**
    * In the VS Code terminal, run the following command to build and start the Wiki.js container:
    ```bash
    docker compose up --build
    ```
10. **Access the Wiki:**
    * Navigate to **`http://localhost:3000`** in your web browser. You will be at the website, already signed into the administrator account.