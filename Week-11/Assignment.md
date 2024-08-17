## Task 1: Create a File with Specific Ownership

### Step 1: Create a File `new.txt` with User `sarah`

1. **Switch to User `sarah`**:
    - Use the `su` command to switch to the user `sarah`:
    ```bash
    sudo su - sarah
    ```

2. **Create the File `new.txt`**:
    - Create the file `new.txt`:
    ```bash
    touch /home/sarah/new.txt
    ```

3. **Switch Back to Root User**:
    - Exit the `sarah` session to return to the root user:
    ```bash
    exit
    ```

### Step 2: Change Ownership of `new.txt` to User `natasha`

1. **Change Ownership**:
    - Use the `chown` command to change the ownership of `new.txt` to `natasha`:
    ```bash
    sudo chown natasha:natasha /home/sarah/new.txt
    ```

## Task 2: Copy and Restrict Permissions of the File

### Step 1: Copy `new.txt` to `/etc/testing/app`

1. **Create the Directory if it Doesn't Exist**:
    - Ensure the directory `/etc/testing/app` exists:
    ```bash
    sudo mkdir -p /etc/testing/app
    ```

2. **Copy the File**:
    - Copy the `new.txt` file to the `/etc/testing/app` directory:
    ```bash
    sudo cp /home/sarah/new.txt /etc/testing/app/
    ```

### Step 2: Set Permissions to Make the File Readable Only

1. **Set Permissions**:
    - Use the `chmod` command to make the file readable only:
    ```bash
    sudo chmod 444 /etc/testing/app/new.txt
    ```

### Complete

By following these steps, you can create the file `new.txt` as user `sarah`, change its ownership to `natasha`, copy it to the `/etc/testing/app` directory, and make it readable only.
