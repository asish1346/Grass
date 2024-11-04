# Grass_Ext

A useful program to help you earn grass points

# Table of Contents

- [GrassXD](#grassxd)
- [Table of Contents](#table-of-contents)
- [Registration](#registration)
- [Warnings and Notes](#warnings-and-notes)
- [About Proxy](#about-proxy)
- [About config.json](#about-configjson)
- [How to Use](#how-to-use)
- [JavaScript Code to Get Data](#javascript-code-to-get-data)
  - [Code to get userid](#code-to-get-userid)
  - [Code to get token](#code-to-get-token)
- [Possible Errors](#possible-errors)

# Registration

If you haven't registered for grass yet, please use the following URL: [Click here](https://app.getgrass.io/register/?referralCode=DnsuPvOL-xfLiy-)

# Warnings and Notes

All risks are borne by the user!

This program only supports one account.

# About Proxy

The format used follows these examples:

Example formats:
```
http://host:port
socks5://host:port
http://user:password@host:port
socks5://user:password@host:port
```

# About config.json

Here's an explanation of the contents of the config.json file:

| key           | value                     | description                                                                                                                 |
| ------------- | ------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| interval_ping | integer / positive number | delay duration between each ping to server, unit: seconds <br> the extension itself has a delay of 2 minutes or 120 seconds |

# How to Use

1. Make sure your computer has Python and Git installed
   
2. Open terminal on your device (CMD/Powershell/Terminal)

3. Clone this repository. You can use the command below:
   ```shell
   git clone https://github.com/asish1346/Grass.git
   ```

4. Enter the grassxd folder:
   ```shell
   cd Grass
   ```

5. Then install the required libraries:
   ```shell
   python -m pip install -r requirements.txt
   ```

6. Fill in your proxies in the proxies.txt file according to the examples I provided in [About Proxy](#about-proxy). If you don't fill in the `proxies.txt` file, it will automatically use your public IP.

7. Run the `setup.py` file first. You will be prompted to enter the email and password of your grass account to get authentication (id and token).
   
   ```shell
   python setup.py
   ```

   If you encounter errors or other issues, please get your userid and token manually. See [JavaScript Code to Get Data](#javascript-code-to-get-data)

8. Run the `main.py` file:
   
   ```shell
   python main.py
   ```

# JavaScript Code to Get Data

## Code to get userid

Make sure you are logged into the grass website.

You can use the JavaScript code below by pasting it in the console menu in the dev tools / dev options in your browser.

Here's the JavaScript code to get userid:

```javascript
copy(JSON.parse(localStorage.getItem("userId")))
```

If you see the warning "Warning: Don't paste code into the DevTools Console that you don't" when pasting the JavaScript code above, type `allow pasting` and press enter first.

The code above automatically copies the userid to your clipboard, so you just need to paste it into the `userid.txt` file.

## Code to get token

Here's the JavaScript code to get the token:

```javascript
copy(JSON.parse(localStorage.getItem("accessToken")))
```

If you see the warning "Warning: Don't paste code into the DevTools Console that you don't" when pasting the JavaScript code above, type `allow pasting` and press enter first.

The code above automatically copies the token to your clipboard, so you just need to paste it into the `token.txt` file.

# Possible Errors

Here are some possible errors and their solutions:

---
Error message: Cannot write to closing transport

Why does it happen? This error message appears when the program wants to send data but the connection to the server has been closed. This might be caused by the proxy you're using or the server has closed your connection.

Solution? Try reducing the ping interval in the `config.json` file. The default is 120 (seconds), try reducing it to 60 (seconds) or less. If it still occurs, your proxy might be poor quality.

What happens if it's not stopped or fixed? This is just my speculation, but you might receive fewer points as a result.
