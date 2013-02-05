Node-SPDXY
===============

spdy/https proxy server based on node-spdy

It can be used as a standalone proxy server
or being embedded and/or extended in another
node.js application.


###How To Use
1. Get the code:
> git clone --recursive https://github.com/rankjie/node-spdxy.git

2. Get an SSL certificate for your domain.
> A self signed certificate is acceptable, but you will have to import that certificate on your localmachine.
I suggest you try **StartSSL** :)

###Command Line Usage

`node server.js [hostname]` will run the
server with the hostname specified in the commandline.

`node local.js [hostname]` will run the
local-listener connect to the hostname specified in the commandline.

###Configurations

`DEBUG`: debug mode, default to true

`log_file`: server log output, default to `proxy.log`

`ip_blacklist`: the IP blacklist file, with one IP address
each line terminated with \n

`host_blacklist`: the host blacklist file, same syntax as the IP blacklist

`user_ca`: will check user certificate against this CA if given

`user_db`: a json file that identifies users against the fingerprints of their certificates

`secure: {`

`key`: tls key file, default to `gfw.key`

`cert`: tls certificate file, default to `gfw.crt`

`},`

`declineHTTP`: if set to true, will decline HTTP connections. Default to `false`

`timeout`: Remote server timeout in milliseconds, the default is 10000ms

`maxConnections`: Maximum number of connections, default to 1000

`noDelay`: Set nodelay for client and remote sockets, default to true

`keepAlive`: Allow HTTP connections to keep-alive

`host`: Specified in the commandline, see Command Line Usage above

`ip`: Auto Detected, you can manually change it, like `127.0.0.1`

`port`: listening port, default to 5555.
