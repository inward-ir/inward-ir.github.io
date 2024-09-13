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
- **administration** : 0.0.0.0:32000
- **web**            : 0.0.0.0:8000
- **resources**      : 0.0.0.0:40000

--------------------------------------------------------------------------------

## Gateways

- application gRPC API (application)    : app.inward.ir
- application gRPC Web API (gRPC proxy) : appweb.inward.ir

## Subdomains

- Media : media.inward.ir

--------------------------------------------------------------------------------

## Development Lifecycle


### Run Services:

/inward.ir/constitution   $ make servers_up
/inward.ir/application    $ make run
/inward.ir/web            $ make run
/inward.ir/web-resources  $ run.sh
/inward.ir/administration $ wails dev | VSCode:Ctrl+F9


### Bundle web interface file for "web" project:

/inward.ir/constitution $ make web_interface


### Generate PASETO asymmetric keys for administration authentication token:

/inward.ir/constitution $ make generate_security_key

Set "Asymmetric Secret Key" and "Asymmetric Public Key" in "system:administration=Authentication" key in "etcd.sh".
Save "Asymmetric Public Key" in "resource/authentication_key" file of "administration" project.


### Generate hashed password for register "author"

/inward.ir/constitution $ make generate_password phrase=<password>

Use output to add a new "author"'s passowrd to database.


### Apply "application" configurations:

/inward.ir/constitution/bootstrap $ source etcd.sh


### Setup MinIO server:

- Setup alias
- Create buckets
- Assign anounymous access
- Create user "saleh"
- Create groups

/inward.ir/constitution/bootstrap $ source minio.sh

### Create MinIO user:

/inward.ir/constitution $ make minio_user name=<name> passwd=<password>
