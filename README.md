Tor plugin for Dokku
=========================

dokku-tor is a plugin for [dokku](https://github.com/dokku/dokku) that runs a [tor+privoxy](https://github.com/rdsubhas/docker-tor-privoxy-alpine) container linked to all deployed apps

Requirements
------------
* Dokku version `0.4.x` or higher

Installation & Example
-----------
```
# installation
$ dokku plugin:install https://github.com/michaelshobbs/dokku-tor.git
```
```
# example
# rebuild or deploy your app
$ dokku ps:restart test-app
...snip...
$ dokku enter test-app web
# use $DOKKU_TOR_PORT_8118_TCP_ADDR and $DOKKU_TOR_PORT_8118_TCP_PORT in your app
$ curl -i --proxy $DOKKU_TOR_PORT_8118_TCP_ADDR:$DOKKU_TOR_PORT_8118_TCP_PORT https://dokku.github.io/
HTTP/1.1 200 Connection established
Proxy-Agent: Privoxy/3.0.23

HTTP/1.1 200 OK
Server: GitHub.com
Content-Type: text/html; charset=utf-8
Last-Modified: Tue, 19 Apr 2016 18:59:11 GMT
Access-Control-Allow-Origin: *
Expires: Wed, 20 Apr 2016 21:20:31 GMT
Cache-Control: max-age=600
X-GitHub-Request-Id: B91F1124:2087:150FB42A:5717F047
Content-Length: 3126
Accept-Ranges: bytes
Date: Wed, 20 Apr 2016 21:10:55 GMT
Via: 1.1 varnish
Age: 24
Connection: keep-alive
X-Served-By: cache-fra1222-FRA
X-Cache: HIT
X-Cache-Hits: 1
X-Timer: S1461186655.352564,VS0,VE0
Vary: Accept-Encoding
X-Fastly-Request-ID: 5ff88c63578f8bc5caf0c83128a4d1c30b455473
```

Commands
--------
```
$ dokku help
    tor:destroy                                destroy tor container
    tor:info                                   show status of running container
    tor:start                                  start tor container
    tor:stop                                   stop tor container
    tor:update                                 updates the tor docker image
```

## Contributing

Feel free to fork and create a Pull Request. (Please add your name to AUTHORS)

## License

MIT
