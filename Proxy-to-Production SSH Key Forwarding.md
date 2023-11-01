# Copy Public SSH Key from Proxy Server to Production Server

In this guide, we will discuss two methods for copying your public SSH key from a proxy server to a production server. This is a common task in DevOps to set up secure and passwordless SSH access.

## Method 1: Using `ssh-copy-id`

This method involves using the `ssh-copy-id` command to automate the process of copying your public key to the production server.

1. On your proxy server, open a terminal and execute the following command, replacing the placeholders with your actual values:
  ```
   ssh-copy-id -i ~/.ssh/id_rsa.pub new_username@production_server_ip
  ```

## Method 2: Manual Copy and Append

This method involves manually copying your public key and appending it to the ~/.ssh/authorized_keys file on the production server.

1.On your proxy server, open a terminal and display the contents of your public key using the cat command:
```cat ~/.ssh/id_rsa.pub
```

2.Copy the output, which represents your public key.

3.SSH into the production server:
```ssh new_username@production_server_ip
```

4.Once logged in to the production server, use a text editor to open the ~/.ssh/authorized_keys file (create it if it doesn't exist):
```vi ~/.ssh/authorized_keys
```

5.In the text editor, paste the public key you copied from the proxy server into the ~/.ssh/authorized_keys file.

6.Save the file and exit the text editor.
