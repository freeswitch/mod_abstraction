# mod_abstraction

Abstraction

## Table of Contents

* [Table of Contents](#table-of-contents)
* [Build and install mod_abstraction](#build-and-install-mod_abstraction)
* [Build standalone mod_abstraction module using FreeSWITCH devel package](#build-standalone-mod_abstraction-module-using-freeswitch-devel-package)

## Build and install mod_abstraction

Change to a directory where the FreeSWITCH sources will be compiled

```
cd /usr/src
```

Clone the FreeSWITCH repository into the above directory

```
git clone https://github.com/signalwire/freeswitch.git
```

Perform an initial bootstrap of FreeSWITCH so that a `modules.conf` file is created

```
./bootstrap.sh
```

Add the mod_abstraction to `modules.conf` so that an out-of-source build will be performed

```
mod_abstraction|https://github.com/freeswitch/mod_abstraction.git -b main
```

Configure, build and install FreeSWITCH

```
./configure
make
make install
```

The following commands will build and install *only* mod_abstraction

```
make mod_abstraction
make mod_abstraction-install
```

To run mod_abstraction within FreeSWITCH, perform the following two steps
1. Add mod_abstraction to freeswitch/conf/autoload/modules.conf.xml
2. Add conf/autoload_configs/abstraction.conf.xml to freeswitch/conf/autoload_configs

## Build standalone mod_abstraction module using FreeSWITCH devel package

Install FreeSWITCH devel package (assuming you have [FreeSWITCH Debian repository setup](https://github.com/signalwire/freeswitch/tree/master/scripts/packaging))
```
apt-get update
apt-get install -y libfreeswitch-dev
```

Change to a directory where mod_abstraction sources will be compiled
```
cd /usr/src
```

Clone mod_abstraction module
```
git clone https://github.com/freeswitch/mod_abstraction -b main
```

Go to the module's source folder
```
cd mod_abstraction
```

And build normally
```
./bootstrap.sh
./configure
make
make install
```