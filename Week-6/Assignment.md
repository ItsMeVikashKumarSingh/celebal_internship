## Creating User Accounts with Supplementary Group in RHEL

### Step 1: Create the Group "sysadmin"

1. **Create the Group**:
    - Use the following command to create a group named "sysadmin":
    ```bash
    groupadd sysadmin
    ```

### Step 2: Create Users "natasha" and "harry" with "sysadmin" as Supplementary Group

1. **Create User "natasha"**:
    - Use the following command to create a user named "natasha" and add her to the supplementary group "sysadmin":
    ```bash
    useradd -G sysadmin natasha
    ```

2. **Set Password for "natasha"**:
    - Use the following command to set the password for "natasha" to "trootent":
    ```bash
    echo "natasha:trootent" | chpasswd
    ```

3. **Create User "harry"**:
    - Use the following command to create a user named "harry" and add him to the supplementary group "sysadmin":
    ```bash
    useradd -G sysadmin harry
    ```

4. **Set Password for "harry"**:
    - Use the following command to set the password for "harry" to "trootent":
    ```bash
    echo "harry:trootent" | chpasswd
    ```

### Step 3: Create User "sarah" with Non-Interactive Shell and No Membership in "sysadmin"

1. **Create User "sarah"**:
    - Use the following command to create a user named "sarah" with a non-interactive shell (e.g., `/sbin/nologin`):
    ```bash
    useradd -s /sbin/nologin sarah
    ```

2. **Set Password for "sarah"**:
    - Use the following command to set the password for "sarah" to "trootent":
    ```bash
    echo "sarah:trootent" | chpasswd
    ```
