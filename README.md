inward.ir
=========

--------------------------------------------------------------------------------

## Application Tools Reguirements

- [Protobuf Compiler](https://github.com/protocolbuffers/protobuf)
- [Protobuf Plugin Go Generator](google.golang.org/protobuf/cmd/protoc-gen-go)
- [Protobuf gRPC Go Generator](google.golang.org/grpc/cmd/protoc-gen-go-grpc)
- [gRPC for Web Client](https://github.com/grpc/grpc-web)
- [Database Migrations](https://github.com/golang-migrate/migrate)
- [SQL Compile](https://github.com/kyleconroy/sqlc)

--------------------------------------------------------------------------------

## Gateways

- **gRPC Proxy**     : 0.0.0.0:10000
- **Web Server**     : 0.0.0.0:8080

## Services

- **application**    : 0.0.0.0:50050
- **web**            : 0.0.0.0:8000
- **resources**      : 0.0.0.0:4000
- **media**          : 0.0.0.0:4500
- **administration** : 0.0.0.0:32000

--------------------------------------------------------------------------------

## Gateways

- application gRPC API (application)    : app.inward.ir
- application gRPC Web API (gRPC proxy) : appweb.inward.ir

## Subdomains

- Media : media.inward.ir
