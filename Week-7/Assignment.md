## Creating the Directory "/home/manager" with Specific Characteristics


Group ownership of "/home/manager" should go to "sysadmin" group.

The directory should have full permission for all members of "sysadmin" group.

but not to the other users except "root".

Files created in future under "/home/manager" should get the same group ownership

### Step 1: Create the Directory "/home/manager"

1. **Create the Directory**:
    - Use the following command to create the directory:
    ```bash
    mkdir /home/manager
    ```

### Step 2: Set Group Ownership to "sysadmin"

1. **Change Group Ownership**:
    - Use the following command to change the group ownership of the directory to "sysadmin":
    ```bash
    chown :sysadmin /home/manager
    ```

### Step 3: Set Permissions for the "sysadmin" Group

1. **Set Permissions**:
    - Use the following command to set full permissions (read, write, execute) for the "sysadmin" group and no permissions for others except "root":
    ```bash
    chmod 770 /home/manager
    ```

### Step 4: Ensure Future Files Inherit Group Ownership

1. **Set Group ID (SGID) on the Directory**:
    - Use the following command to set the SGID (Set Group ID) bit on the directory. This ensures that files created in the future under `/home/manager` inherit the group ownership:
    ```bash
    chmod g+s /home/manager
    ```
