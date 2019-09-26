# GRPC-dockerfile

### Using PECL install grpc

```sh
pecl install grpc
```

or specific version

```sh
pecl install grpc-1.23.0
```
#### Build and install the gRPC C core library

```sh
$ cd grpc
$ git submodule update --init
$ make
$ make install
```

#### Build and install gRPC PHP extension

Compile the gRPC PHP extension

```sh
$ cd grpc/src/php/ext/grpc
$ phpize
$ ./configure
$ make
$ make install
```
#### Build and install protobuf extension

```sh
$ cd /protobuf 
$ ./autogen.sh 
$ ./configure 
$ make 
$ make install
$ ldconfig
```
### Update php.ini

After installing the gRPC extension or protobuf extension, make sure you add this line 
to your `php.ini` file, (e.g. `/etc/php/7.2/cli/php.ini ` or `/etc/php/7.2/fpm/php.ini).

```sh
extension=grpc.so
extension=protobuf.so
```
### PHP Protoc Plugin
You can also just build the gRPC PHP protoc plugin by running:

```sh
$ cd /grpc
$ git submodule update --init
$ make grpc_php_plugin
```

## Unit Tests

You will need the source code to run tests

```sh
$ cd /grpc
$ git submodule update --init
```

Run unit tests

```sh
$ cd /grpc/src/php/bin
$ ./run_tests.sh
```
