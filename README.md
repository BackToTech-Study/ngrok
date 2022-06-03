# ngrok

* In computer networks, a [reverse proxy](https://en.wikipedia.org/wiki/Reverse_proxy) is the application that sits in front of back-end applications and forwards client (e.g. browser) requests to those applications.
* [ngrok](https://ngrok.com/) is a globally distributed reverse proxy fronting your web services running in any cloud or private network, or your machine.
* in this example we will use ngrok to expose a an app hosted on a local network

## Prerequisites

* download and install the ngrok agent: https://ngrok.com/download
* create an ngrok account (it's free for non comercial use) https://dashboard.ngrok.com/signup
* register the agent with the config command from your account 
```
    ngrok config add-authtoken YOUR TOKEN HERE
```

## Expose an endpoint

* To expose an endpoint running on https in your local network simply call
```
    ngrok http https://IP_HERE
```
or with port
```
    ngrok http https://IP_HERE:PORT_HERE
```
if all went well you will get a message indicating the address of the proxy server:
```
Forwarding https://84c5df439d74.ngrok.io -> https://IP:443
```

* You can also use ngrok built in file server to expose a local folder
```
    ngrok http --basic-auth="user:password" file:///Users/alan/share
```

* The egent also exposes an web interface on localhost ```http://127.0.0.1:4040```. You can use this to see a list of calls.
