Tor plugin for Dokku
=========================

Project: https://github.com/dokku/dokku & https://github.com/rdsubhas/docker-tor-privoxy-alpine

Requirements
------------
* Dokku version `0.4.x` or higher

Installation
-----------
```
# dokku 0.4.x+
dokku plugin:install https://github.com/michaelshobbs/dokku-tor.git
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
