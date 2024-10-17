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

- **gRPC Web Proxy** = 127.0.0.1:10000
- **Web Server**     = 127.0.0.1:8000

## Services

- **application**    = :50050
- **administration** = :32000
- **web**            = :18000
- **resources**      = :40000

--------------------------------------------------------------------------------

## Gateways

- application gRPC API     : app.inward.ir    -> **application**
- application gRPC Web API : appweb.inward.ir -> **gRPC Web Proxy**

## Subdomains

- Media : media.inward.ir -> 0.0.0.0:9000 (minio)

--------------------------------------------------------------------------------

## Run Services:

/inward.ir/constitution   $ make servers_up
/inward.ir/application    $ make run
/inward.ir/web            $ make run
/inward.ir/web-resources  $ run.sh
/inward.ir/administration $ wails dev | VSCode:Ctrl+F9

--------------------------------------------------------------------------------

## Development Lifecycle


### Setup Database

/inward.ir/constitution $ make db_create

Execute:
/inward.ir/constitution/database/schemas/000001_initialize.up.sql
/inward.ir/constitution/database/schemas/000002_data.up.sql
OR
/inward.ir/constitution $ make migrate_up


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
