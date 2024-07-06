## Changing the Root Password When the Root Password is Not Known

To change the root password in Red Hat Enterprise Linux (RHEL) when we don't know the current root password, we can follow these steps:

### Step 1: Enter GRUB Edit Mode

1. **Reboot the System**:
    - Restart your RHEL system.

2. **Access GRUB Menu**:
    - When you see the GRUB 2 screen, press the `e` key to interrupt the boot process.

3. **Kernel Boot Parameters**:
    - Once you press `e`, it will show you the kernel boot parameters.


### Step 2: Edit Kernel Boot Parameters

1. **Navigate to Kernel Line**:
    - Go to the end of the line that starts with `linux`. You can do this by selecting the line and pressing `Ctrl + e` to jump to the end of the line.

2. **Add `rd.break`**:
    - At the end of the line, add `rd.break` and press `Ctrl + x` to start the system with the changed parameters.


### Step 3: Reset Forgotten Root Password

1. **Enter Emergency Mode**:
    - You will be given an emergency mode prompt. Press Enter to proceed to the `sh-5.1` prompt.

2. **Remount Filesystem**:
    - By default, the filesystem is mounted as read-only under the `/sysroot` directory. Remount it as read-write using the following command:
    ```bash
    mount -o remount,rw /sysroot
    ```

3. **Enter Chroot Environment**:
    - Enter into the chroot environment, which allows you to make changes directly to system files:
    ```bash
    chroot /sysroot
    ```

4. **Change Root Password**:
    - Use the `passwd` command to change the root password:
    ```bash
    passwd
    ```


5. **Enable SELinux Relabeling**:
    - Enable SELinux relabeling process on the next system boot:
    ```bash
    touch /.autorelabel
    ```

    **Important**: Ensure you use `/.autorelabel` correctly as you are not running any scripts here.

6. **Exit Chroot Environment**:
    - Exit the chroot environment:
    ```bash
    exit
    ```

7. **Exit Emergency Mode**:
    - Exit from the `sh-5.1` prompt:
    ```bash
    exit
    ```

By following these steps, we can reset the root password on our RHEL system even if we do not know the current root password.
