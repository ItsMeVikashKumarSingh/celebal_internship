## Configuring YUM for RHEL

### Step 1: Add a YUM Repository

1. **Create a Repository File**:
    - Create a new repository configuration file in `/etc/yum.repos.d/`. For example, to create a repository file named `custom.repo`:
    ```bash
    sudo vim /etc/yum.repos.d/custom.repo
    ```

2. **Add Repository Configuration**:
    - Add the following content to the repository file:
```plaintext
    [LocalRepo_BaseOS]
    name=LocalRepo_BaseOS
    metadata_expire=-1
    enabled=1
    gpgcheck=1
    baseurl=file:///local_repo/BaseOS
    gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-redhat-release

    [LocalRepo_AppStream]
    name=LocalRepo_AppStream
    metadata_expire=-1
    enabled=1
    gpgcheck=1
    baseurl=file:///local_repo/AppStream
    gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-redhat-release
```

3. **Save and Exit `vim` Editor**:
    - Press `i` to enter insert mode.
    - Add the above content.
    - Press `Esc` to exit insert mode.
    - Type `:wq` and press `Enter` to save and exit the `vim` editor.

### Step 2: Clear YUM Cache and Update Repositories

1. **Clear YUM Cache**:
    - Use the following command to clear the YUM cache:
    ```bash
    sudo yum clean all
    ```

2. **Update YUM Repositories**:
    - Use the following command to update the YUM repositories:
    ```bash
    sudo yum makecache
    ```

### Step 3: Install a Package to Test the Configuration

1. **Install a Test Package**:
    - Use the following command to install a package, for example, `nano`, to ensure YUM is working correctly:
    ```bash
    sudo yum install nano
    ```
