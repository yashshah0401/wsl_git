**Author:** Shah, Yash Ketanbhai  
**Student ID:** 8990493  
**Course:** Software Quality Assurance & Test Engineering  
**Date:** January 14, 2025  
**Contact:** yashshah0704@gmail.com
**Professional:** Project Manager and Business Analyst

# Installing WSL on Windows PC

## Step 1: Open Windows PowerShell as Administrator
1. Press `Win + S`, type **PowerShell**, and right-click on **Windows PowerShell**.
2. Select **Run as Administrator**.

## Step 2: Install WSL
1. In the PowerShell window, type the following command and press **Enter**:
   ```
   wsl --install
   ```
2. The installation process will begin. Wait for it to complete.

## Step 3: Restart Your Computer
1. Once the installation is finished, you will be prompted to restart your computer.
2. Restart your PC to finalize the installation.

## Step 4: Launch WSL
1. After rebooting, open **PowerShell** or a terminal and type:
   ```
   wsl
   ```
2. If a Linux distribution (e.g., Ubuntu) is not installed, WSL will prompt you to choose one and begin the installation.

   - If it does not prompt you, re-enter the command:
     ```
     wsl --install
     ```
   - You may see messages like:
     ```
     Ubuntu is already installed.
     Launching Ubuntu...
     Installing, this may take a few minutes...
     ```

## Step 5: Set Up Your Linux Distribution
1. Follow the on-screen instructions to configure your Linux environment.
   - You will be asked to create a default UNIX user account. The username **does not need to match your Windows username**.
   - Enter the required details:
     - **Enter new UNIX username**: Choose a memorable username.
     - **New Password**: When entering the password, it will not be displayed for security reasons. Type it carefully and press **Enter**.
     - **Retype Password**: Re-enter the password to confirm and press **Enter**.

   Example prompts:
   ```
   Please create a default UNIX user account. The username does not need to match your Windows username.
   For more information, visit: https://aka.ms/wslusers
   Enter new UNIX username: <Your Username>
   New Password: <Type Password>
   Retype Password: <Confirm Password>
   ```

---

## Step 6: Verify Installation
1. If all steps are completed successfully, you will see a welcome message:
   ```
   Welcome to Ubuntu <Version Number>
   ```

2. Your WSL is now ready for use. You can start exploring Linux commands and tools from your Windows environment.

---

**For more details and troubleshooting, visit the official WSL documentation: [https://aka.ms/wslusers](https://aka.ms/wslusers).**


# Setting Up Git and SSH with GitHub in WSL

## Step 1: Create a GitHub Account
1. Go to [GitHub](https://github.com).
2. Sign up using:
   - A **simple email address**.
   - A **username**.
   - A **password**.
3. Once registered, log in to your GitHub account.

---

## Step 2: Install Git in WSL
1. Open WSL and enter the following command to install Git:
   ```
   sudo apt-get install git
   ```
2. You will be prompted to enter your **password**. When typing, the characters will not be displayed. Type it carefully and press **Enter**.

---

## Step 3: Configure Git with Your GitHub Username and Email
1. Configure your Git username:
   ```
   git config --global user.name "Your Name"
   ```
2. Configure your Git email:
   ```
   git config --global user.email "youremail@domain.com"
   ```
   - **Best Practice:** Ensure your GitHub email and WSL email are the same for consistency.

---

## Step 4: Generate an SSH Key
1. Generate an SSH key by entering the following command:
   ```
   ssh-keygen -t ed25519 -C "youremail@domain.com"
   ```
2. Example output:
   ```
   Generating public/private ed25519 key pair.
   Enter file in which to save the key (/home/username/.ssh/id_ed25519):
   ```
   - Press **Enter** to accept the default file location.
3. For the passphrase prompts:
   - Leave it empty by pressing **Enter** twice.

4. Example continued output:
   ```
   Enter passphrase (empty for no passphrase):
   Enter same passphrase again:
   Your identification has been saved in /home/username/.ssh/id_ed25519
   Your public key has been saved in /home/username/.ssh/id_ed25519.pub
   The key fingerprint is:
   SHA256:fFNk0aLV10vKZgjntlunbNQL88BXP839OOpkMWIy390 youremail@domain.com
   ```

---

## Step 5: Add SSH Key to ssh-agent
1. Start the ssh-agent:
   ```
   eval "$(ssh-agent -s)"
   ```
2. Add your SSH key to the agent:
   ```
   ssh-add ~/.ssh/id_ed25519
   ```
   - Example output:
     ```
     Identity added: /home/username/.ssh/id_ed25519 (youremail@domain.com)
     ```

--- 

## Step 6: Add SSH Key to GitHub
1. Copy your SSH key to the clipboard:
   ```
   cat ~/.ssh/id_ed25519.pub
   ```
2. Select and copy the entire output of the command.
3. Log in to GitHub.
4. Navigate to **Settings** > **SSH and GPG keys**.
5. Click **New SSH key**.
6. Paste your SSH key into the "Key" field.
7. Add a title (e.g., "WSL Key").
8. Click **Add SSH key**.

---

## Step 7: Test Your Connection
1. Test the SSH connection to GitHub:
   ```
   ssh -T git@github.com
   ```
2. Expected output:
   ```
   Hi <your-username>! You've successfully authenticated, but GitHub does not provide shell access.
   ```

---

Congratulations! You are now ready to clone repositories and interact with GitHub using SSH. If you encounter any issues, feel free to ask for assistance.

---

## Step 8: Handle First-Time SSH Authentication
When you test your SSH connection to GitHub for the first time:

1. Run the command:
   ```
   ssh -T git@github.com
   ```
2. You may see a message like this:
   ```
   The authenticity of host 'github.com (140.82.113.4)' can't be established.
   ED25519 key fingerprint is SHA256:+DiY3wvvV6TuJJhbpZisF/zLDA0zPMSvHdkr4UvCOqU.
   This key is not known by any other names.
   Are you sure you want to continue connecting (yes/no/[fingerprint])?
   ```
3. This message is normal when connecting to a new host for the first time. You can safely type:
   ```
   yes and Press **Enter**
   ```
This message is normal when connecting to a new host for the first time. You can safely type `yes` and press **Enter** to continue. This will add GitHub to your list of known hosts.

After that, you should see a message confirming that you've successfully authenticated with GitHub.

- **Warning:** Permanently added 'github.com' (ED25519) to the list of known hosts.
- **Message:** Hi UserName! You've successfully authenticated, but GitHub does not provide shell access.



# License

This work is licensed under a [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/).  