Basic usage
```
$ docker run --rm --interactive --tty \
  --volume $PWD:/app \
  composer <command>
```
Persist cache / global configuration
You can bind mount the Composer home directory from your host to the container to enable a persistent cache or share global configuration:
```
$ docker run --rm --interactive --tty \
  --volume $PWD:/app \
  --volume ${COMPOSER_HOME:-$HOME/.composer}:/tmp \
  composer <command>
```
Note: this relies on the fact that the COMPOSER_HOME value is set to /tmp in the image by default.

Or if your environment follows the XDG specification:
```
$ docker run --rm --interactive --tty \
  --env COMPOSER_HOME \
  --env COMPOSER_CACHE_DIR \
  --volume ${COMPOSER_HOME:-$HOME/.config/composer}:$COMPOSER_HOME \
  --volume ${COMPOSER_CACHE_DIR:-$HOME/.cache/composer}:$COMPOSER_CACHE_DIR \
  --volume $PWD:/app \
  composer <command>
```
