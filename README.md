# GRPC HELLO WORLD EXAMPLE
This example is copied from the official grpc website. The bazel build system is used in this example.

## How to Build
 * Install protoc and protoc go plugin in the system.(Optional : Its not necessary for bazel as it does it in its sandbox. )
 ```
    apt install -y protobuf-compiler
 ```

* install the go protoc plugin
```
    go get github.com/golang/protobuf/protoc-gen-go
```
```
    export PATH="$PATH:$(go env GOPATH)/bin"
```
* Compile the proto buffer definition to generate grpc code
```
    bazel build //helloworld:go_default_library
```

* To generate only the grpc files for proto
```
    bazel build //helloworld:helloworld_go_proto
```

* Similarly build the server 
```
    bazel build greeter_server:greeter_server
```

* Build the client binary
```
    bazel build greeter_client:greeter_client
```

* Run the server and client binary in two different terminals
```
    ./bazel-bin/greeter_server/greeter_server_/greeter_server
    ./bazel-bin/greeter_client/greeter_client_/greeter_client
```

## Bazel TIPS
* Generate BUILD files in every directy 
```
    bazel run //:gazelle
```
* Use go modules to keep track of the version in bazel.Bazel can generate WORKSPACE and BUILD files using go.mod files
```
    bazel run //:gazelle -- update-repos -from_file=go.mod
 ```



