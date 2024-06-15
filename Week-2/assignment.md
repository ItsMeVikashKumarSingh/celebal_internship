# Creating a User and Logging in via SSH on RHEL

## Steps

1. **Create a New User on RHEL**:
   - Log in as root or a user with sudo privileges.
   - Use the following command to create a new user (replace 'newuser' with your desired username):
     ```
     sudo adduser newuser
     ```
   - Set a password and provide other user information when prompted.

3. **Enable SSH Access on RHEL**:
   - Ensure the SSH service is installed and running by checking its status:
     ```
     sudo systemctl status sshd
     ```
   - If not running, start the service:
     ```
     sudo systemctl start sshd
     ```
   - Enable the service to start automatically on system boot:
     ```
     sudo systemctl enable sshd
     ```
   - Edit the SSH configuration file to disable root login and enable password authentication:
     ```
     sudo nano /etc/ssh/sshd_config
     ```
   - Find the lines `PermitRootLogin` and `PasswordAuthentication`, and set them to:
     ```
     PermitRootLogin no
     PasswordAuthentication yes
     ```
   - Save the changes and exit the editor.
   - Restart the SSH service for the changes to take effect:
     ```
     sudo systemctl restart sshd
     ```

4. **Find the IP address of your Machine**:

      ```
      ip addr show
      ```

5. **Log in through SSH from the Host Machine**:
   - On your host machine, open a terminal (e.g., Command Prompt on Windows, Terminal on macOS/Linux).
   - Use the `ssh` command to connect to the RHEL Machine, replacing 'newuser' with your username and 'vm_ip_address' with the noted IP address:
     ```
     ssh newuser@vm_ip_address
     ```
   - Enter the password for 'newuser' when prompted.

After following these steps, We have successfully logged in to the RHEL virtual machine through SSH from your host machine.