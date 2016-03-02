# SickRage

This image runs [SickRage](http://sickrage.github.io/), an automatic video library manager for TV shows.

[![](https://badge.imagelayers.io/existenz/sickrage:latest.svg)](https://imagelayers.io/?images=existenz/sickrage:latest 'Get your own badge on imagelayers.io')

It makes use of the `runas` functionality found in [my base image](https://hub.docker.com/r/existenz/base) so SickRage runs as the user you want.

## Usage

To run SickRage as a service under user id 1234 with group id 2345 start like this:

```
docker run -d -P \
-e UID=1234 -e GID=2345 \
-v /configdir:/home \
-v /data/video:/data/video \
existenz/sickrage
```

## Directories

SickRage will write its configuration & (image) caches to /home, so make sure to bind something to it like in the example above.

## Ports

This image exposes SickRage on port 8081 so specificy `-P`, or bind to e.g. port 1234 with `-p1234:8081` if you want.

## Bugs, questions, and improvements

If you found a bug or have a question, please open an issue on the GitHub Issue tracker. Improvements can be sent by a Pull Request against the develop branch and are greatly appreciated!

