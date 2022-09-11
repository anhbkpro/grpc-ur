# grpc-ur
## Install protoc and protoc-gen-go plugin
- Install the gRPC library:
```
go get -u google.golang.org/grpc
```
- Install the protoc plug-in for Go:
```
go install github.com/golang/protobuf/protoc-gen-go@v1.3
```
- To generate service (server) and client side code:
```
cd productinfo/service //or cd productinfo/client to create client side code
protoc -I ecommerce ecommerce/product_info.proto --go_out=plugins=grpc:ecommerce
```

## Building
- Building a Go Server
```
cd productinfo/service
go build -i -v -o bin/server
```
- Building a Go Client
```
cd productinfo/client
go build -i -v -o bin/client
```
## Running a Go Server and Client
- Let’s run them on separate terminals and make them talk to each other:
```
// Running Server
bin/server

// Running Client
bin/client
```