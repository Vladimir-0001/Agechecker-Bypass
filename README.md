<h1 align="center">
  Agechecker Bypass 🔞 
</h1>

<h2 align="center">
   Bypass AgeChecker.net without ID
</h2>



<p align="center"> 
  <kbd>
<img src="https://doggo.ninja/XADMW5.png"></img>
  </kbd>
</p>

<h4 align="center">
  <a href="https://github.com/Vladimir-0001/Agechecker.net-Bypasss#setup-the-bypass">🔞・Setting up the Bypass</a>
  <a href="https://github.com/Vladimir-0001/Agechecker.net-Bypasss#changelog">📜・ChangeLog</a>
</h4>

<h2 align="center">
  Made by my love of a magical flower

</h2>

---

## Features

✔ Works on all websites using Agechecker.net for verification \
✔ Uses unique uuid each time\
✔ No programming required\
✔ Easy to set up \
✔ No sketchy chrome extentions


> **Warning**: This Bypass only works for PRE-order verification, meaning if it says it will email you after to verify IT WILL NOT WORK (try to check out without the bypass it will look like [this]([this](#post-order-verification)
), dont worry though im wokring on a bypass for post-order verification too ;)

# Setup The Bypass

You'll need [mkCert](https://github.com/FiloSottile/mkcert) to start off!


## 1. From your command line, configure mkcert:

```bash
# install local CA
$ mkcert -install

```
> **Warning**: The `rootCA-key.pem` file that mkcert automatically generates gives complete power to intercept secure requests from your machine. Do not share it.
## 2.  generate the certificate and key 

```bash
# Generate a certificate for api.agechecker.net that also points to the localhost 
$ mkcert api.agechecker.net localhost 127.0.0.1 

#it should return something like this 
Created a new certificate valid for the following names 
 - "api.agechecker.net"
 - "localhost"
 - "127.0.0.1"
```
If this isnt working try to reinstall the local CA

## 3. Hijacking the host file 

Linux machines・```\etc\hosts```\
Windows machines・```C:\Windows\System32\drivers\etc\hosts```
```bash 
#you need to add theese 2 lines in your host file
127.0.0.1 api.agechecker.net
127.0.0.1 localhost
```

> Don't quite understand how to set it up? (Contact me on discord Vladimir#0001)

## 4 . Getting Bypass.py Started
At the bottom of `bypass.py`  file Edit the file paths to it match your key and certficate paths
```py
if __name__ == '__main__':
    context = ('\\mkcert+3.pem','\\mkcert+3-key.pem')
    app.run(port = 443, debug = False, ssl_context = context)
```
> **Warning**: port 443 is a privileged port on linux so you might have to run with `sudo` and `-E` to ignore enviroment varibles a. like this : `sudo -E python bypass.py`
## 5 . Using the Bypass
Go to  [api.agechecker.net](https://api.agechecker.net) to make sure the api has been locally hijacked
```bash
# You should see something like this
API Hijacked by bypass.py
```



Go to any website using Agechecker.net I will be using the [demo](https://agechecker.net/demo) to showcase the 
bypass
<p align=""> 
  <kd>
<img src="https://doggo.ninja/pRPtCk.png"></img>
  </kdb>

You Can Put in any DOB 
<p align=""> 
  <kd>
<img src="https://doggo.ninja/TRAHwF.png"></img>
  </kbd>
</p>
It will always Verify you
<p align=""> 
  <kd>
<img src="https://doggo.ninja/Lnk2PA.png"></img>
  </kbd>
</p>

## Post Order Verification
- this Wont work currently but I'm working on an update so stay tuned and add my discord for updates!
![image](https://github.com/Vladimir-0001/Agechecker-Bypass/assets/71991079/7c9330d6-4d42-47c0-b8d0-f4a0ea932197)


---

## Upcoming/enhancements

- maybe custom popup.js code?

## Inspiration/Credits

- [jeff](https://github.com/JeffTheModder) maked me do it 


## ChangeLog

```diff
v0.0.1⋮ 2022-9-6
+ corrected CORS headers errors
+ Added Random UUID 


```
