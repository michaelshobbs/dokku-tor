Tor plugin for Dokku
=========================

dokku-tor is a plugin for [dokku](https://github.com/dokku/dokku) that runs a [tor+privoxy](https://github.com/rdsubhas/docker-tor-privoxy-alpine) container linked to all deployed apps

Requirements
------------
* Dokku version `0.4.x` or higher

Installation
-----------
```
# installation
dokku plugin:install https://github.com/michaelshobbs/dokku-tor.git

# run tor container
dokku tor:start

# restart or redeploy your Dokku app
dokku ps:restart app
```
Once your app is connected to dokku-tor plugin, you will be able to use **$DOKKU_TOR_PORT_8118_TCP_ADDR** and **$DOKKU_TOR_PORT_8118_TCP_PORT** environment variables inside your Dokku app.

Example
-----------
```
dokku enter test-app web
curl -i --proxy $DOKKU_TOR_PORT_8118_TCP_ADDR:$DOKKU_TOR_PORT_8118_TCP_PORT http://icanhazip.com/

# The output will contain your new IP address which belongs to one of available Tor nodes.
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
