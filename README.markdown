# A Recipe for a Redis RPM on CentOS

Perform the following on a build box as root.

## Create an RPM Build Environment

    yum install rpmdevtools
    rpmdev-setuptree

## Install Prerequisites for RPM Creation

    yum groupinstall 'Development Tools'

## Download Redis

    cd /tmp
    wget http://download.redis.io/releases/redis-2.8.17.tar.gz \
    -O redis-2.8.17.tar.gz ~/rpmbuild/SOURCES/

## Build the RPM

    cd ~/rpmbuild/
    rpmbuild -ba SPECS/redis.spec

The resulting RPM will be:

    ~/rpmbuild/RPMS/x86_64/redis-2.8.17-1.x86_64.rpm

## Credits

Project forked and updated from redis-centos repository, found on [GitHub][gh].

 [gh]: https://github.com/causes/redis-centos
