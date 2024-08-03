## Find a String and Save it to a File

### Step 1: Find Lines Containing the String 'ing'

1. **Use `grep` to Find Lines**:
    - Use the `grep` command to search for lines containing the string 'ing' in a specific file (e.g., `input.txt`) and redirect the output to `/root/lines`:
    ```bash
    sudo grep 'ing' /path/to/input.txt > /root/lines
    ```

### Change **/path/to/input.txt** with acutal fine name.

By following this step, we can find all lines containing the string 'ing' in the specified file and save them to the `/root/lines` file.
