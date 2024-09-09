# Specify the extension we'll build
ENV extension=xdebug-3.2.2
SHELL ["/bin/bash", "-c"]
RUN disable_xdebug
# Install the needed development packages
RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y -o Dpkg::Options::="--force-confnew" --no-install-recommends --no-install-suggests build-essential php-pear php${DDEV_PHP_VERSION}-dev
# The "echo" below just forces accepting the "automatic" configuration, the same as hitting <RETURN>
RUN pecl install ${extension}
# Assuming the extension is already installed in web container in php8.2 we can just copy its configuration
