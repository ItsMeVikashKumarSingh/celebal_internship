# Changing Console Text Color

We will learn, how to change the color of text in the console using the `tput` command. This can be useful for highlighting important information or making the console output more readable.

## Step-by-Step Guide

1. **Open the terminal.**

2. **Use the `tput` command to set the text color.** The `tput` command initializes the terminal and sets various terminal capabilities, including text color. Below are examples of how to change the text color to different colors.

### Examples of Changing Text Color

- **Red:**

    ```bash
    tput setaf 1
    echo "This is red text"
    tput sgr0
    ```

- **Green:**

    ```bash
    tput setaf 2
    echo "This is green text"
    tput sgr0
    ```

- **Yellow:**

    ```bash
    tput setaf 3
    echo "This is yellow text"
    tput sgr0
    ```

- **Blue:**

    ```bash
    tput setaf 4
    echo "This is blue text"
    tput sgr0
    ```

- **Magenta:**

    ```bash
    tput setaf 5
    echo "This is magenta text"
    tput sgr0
    ```

- **Cyan:**

    ```bash
    tput setaf 6
    echo "This is cyan text"
    tput sgr0
    ```

### Explanation

- `tput setaf [number]`: Sets the foreground (text) color. The number corresponds to the color you want to use.
  - `0` = Black
  - `1` = Red
  - `2` = Green
  - `3` = Yellow
  - `4` = Blue
  - `5` = Magenta
  - `6` = Cyan
  - `7` = White

- We can use as many commands as needed after `tput setaf [number]` to display text in that color. When you want to revert to the default text color, use `tput sgr0`.

### Screenshot

Below is a screenshot demonstrating the commands executed in the terminal:

![Screenshot of Changing Text Color](/images/change_terminal_colour.png)

## Conclusion

By using the `tput` command, We can easily change the color of the text displayed on the console. This can be particularly useful for highlighting important information or organizing output in a more readable format.
