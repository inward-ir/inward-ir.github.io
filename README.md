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
/inward.ir/administration $ wails dev | VSCode: Run Build Task (Ctrl+Shift+F9)

--------------------------------------------------------------------------------

## Development Lifecycle


### Apply "application" configurations:

/inward.ir/constitution/bootstrap $ source etcd.sh


### Setup Database

/inward.ir/constitution $ make db_create

Execute:
/inward.ir/constitution/database/schemas/000001_initialize.up.sql
/inward.ir/constitution/database/schemas/000002_data.up.sql
OR
/inward.ir/constitution $ make migrate_up


### Bundle web interface file for "web" project:

/inward.ir/constitution $ make web_interface

Build and push "web" project.
Push "web-resources" project.


### Generate PASETO asymmetric keys for administration authentication token:

/inward.ir/constitution $ make generate_security_key

Set "Asymmetric Secret Key" and "Asymmetric Public Key" in "system:administration=Authentication" key in "etcd.sh".
Save "Asymmetric Public Key" in "resource/authentication_key" file of "administration" project.


### Generate hashed password for register "author"

/inward.ir/constitution $ make generate_password phrase=<password>

Use output to add a new "author"'s password to database.


### Setup MinIO server:

- Setup alias
- Create buckets
- Assign anounymous access
- Create user "saleh"
- Create groups

/inward.ir/constitution/bootstrap $ source minio.sh


### Create MinIO user:

/inward.ir/constitution $ make minio_user name=<name> passwd=<password>

--------------------------------------------------------------------------------

## Administration Develop Workflow

constitution:

- Create database query at "database/queries/administration/"
- Call `make sqlc`
- Create RPC at "specifications/administration/administration.proto"
- Call `make protoc`

application:

- Implement RPC at "services/administration/"
- Add access privilage at "resource/administration_access.json"

administration (backend):

- Add menu at "main.go#setupMenu" function
- Add Application menu item at "basic/menus/application.go"
- Implement service at "application/services/"
- "Run Task" by VSCode : "Generate Module"

administration (frontend):

- Create view at "views/ParaphraseReview.vue"
- Add router at "src/router/"

--------------------------------------------------------------------------------

## Date and Time Epoch

inward.ir/constitution/database/schema.sql#generate_document_alias
inward.ir/application/infrastructure/datetime.go#CheckDateNotExceed
inward.ir/administration/basic/core/core.go
inward.ir/constitution/development/document_generator/main.go
