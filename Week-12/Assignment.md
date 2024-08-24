


# Configuring HTTPD Server on RHEL

## Step 1: Install the HTTPD Package

To set up an HTTPD server, first, you need to install the `httpd` package.

```bash
sudo yum install httpd -y
```

## Step 2: Start and Enable the HTTPD Service

After installation, start the HTTPD service and enable it to start automatically on boot.

1. **Start the HTTPD Service:**

    ```bash
    sudo systemctl start httpd
    ```

2. **Enable HTTPD to Start on Boot:**

    ```bash
    sudo systemctl enable httpd
    ```

## Step 3: Configure the Firewall to Allow HTTP Traffic

To allow HTTP and HTTPS traffic through the firewall, use the following commands:

1. **Allow HTTP and HTTPS Traffic:**

    ```bash
    sudo firewall-cmd --permanent --add-service=http
    sudo firewall-cmd --permanent --add-service=https
    ```

2. **Reload the Firewall:**

    ```bash
    sudo firewall-cmd --reload
    ```

## Step 4: Verify HTTPD Configuration

Ensure that your HTTPD configuration is correct by performing the following checks:

1. **Test HTTPD Configuration:**

    ```bash
    sudo apachectl configtest
    ```

2. **Check HTTPD Status:**

    ```bash
    sudo systemctl status httpd
    ```

## Step 5: Configure HTTPD Server (Optional Customization)

You can customize the HTTPD server settings by editing the default configuration file:

1. **Edit the Default Configuration File:**

    ```bash
    sudo vim /etc/httpd/conf/httpd.conf
    ```

2. **Add Custom Content to the Document Root:**

    Create or modify the `index.html` file in the default document root (`/var/www/html/`):

    ```bash
    echo "Welcome to the HTTPD Server on RHEL!" | sudo tee /var/www/html/index.html
    ```

## Step 6: Restart HTTPD Service

To apply any configuration changes, restart the HTTPD service:

```bash
sudo systemctl restart httpd
```

## Step 7: Test HTTPD Server

To verify that the HTTPD server is working correctly:

1. **Open a Web Browser** and go to `http://localhost` or `http://<your-server-ip>`. You should see the content you added to the `index.html` file.
