# Setup a pareviewsh for Drupal module best practices
<https://www.drupal.org/project/pareviewsh>
online version of pareview.sh

## Install Composer
    curl -sS https://getcomposer.org/installer | php
    sudo mv composer.phar /usr/local/bin/composer

## Install Coder (reference: <https://www.drupal.org/node/1419988#coder-composer>)
    $ composer global require drupal/coder
    $ sudo ln -s ~/.composer/vendor/bin/phpcs /usr/local/bin
    $ sudo ln -s ~/.composer/vendor/bin/phpcbf /usr/local/bin
    $ phpcs --config-set installed_paths ~/.composer/vendor/drupal/coder/coder_sniffer
## Install codespell (reference: <https://github.com/lucasdemarchi/codespell>)
    $ sudo apt-get help2man -y
    $ cd /usr/local/src
    $ git clone https://github.com/lucasdemarchi/codespell.git
**$ cd codespell && sudo make install**
**$ sudo cp codespell /usr/local/bin**
# Install DrupalSecure (reference: <https://www.drupal.org/sandbox/coltrane/1921926>)
    $ sudo apt-get update && sudo apt-get install php-pear
    $ sudo pear install PHP_CodeSniffer
    $ cd $(pear config-get php_dir)/PHP/CodeSniffer/Standards/
    $ git clone git://git.drupal.org/sandbox/coltrane/1921926.git secure_cs
    $ sudo ln -sv ./secure_cs/DrupalSecure ./DrupalSecure
# Install ESLint
    $ sudo npm install -g eslint

    On Ubuntu precise, you might encounter the following errors while performing this command
    npm http GET https://registry.npmjs.org/
    npm ERR! Error: failed to fetch from registry:
    This is because the version supplied by Ubuntu 12.04 is no longer supported, updating node (and npm with it) resolved the issue.

    First, uninstall the outdated version (optional, but I think this fixed an issue I was having with global modules not being pathed in).

    sudo apt-get purge nodejs npm

    Then enable nodesource's repo and install:

    curl -sL https://deb.nodesource.com/setup | sudo bash -
    sudo apt-get install -y nodejs

    $ sudo apt-get install nodejs
****$ eslint --init # run for the first time****
# Install pareviewsh
    $ cd /usr/local/src
    $ sudo wget http://ftp.drupal.org/files/projects/pareviewsh-7.x-1.7.tar.gz
    $ sudo tar xzf pareviewsh-7.x-1.7.tar.gz
    $ sudo ln -s /usr/local/src/pareviewsh/pareview.sh /usr/local/bin/pareview

# Test if Pareview is working
    $ pareview /path/to/module or /path/to/git-repos.git