inward.ir
=========

--------------------------------------------------------------------------------

## Application Tools Reguirements

- Go 1.20
- PostgreSQL 15

- [Protobuf Compiler](https://github.com/protocolbuffers/protobuf)
- [Protobuf Plugin Go Generator](google.golang.org/protobuf/cmd/protoc-gen-go)
- [Protobuf gRPC Go Generator](google.golang.org/grpc/cmd/protoc-gen-go-grpc)
- [gRPC for Web Client](https://github.com/grpc/grpc-web)
- [Database Migrations](https://github.com/golang-migrate/migrate)
- [SQL Compile](https://github.com/kyleconroy/sqlc)

## Web Tools Reguirements

- [Vue Language Features (Volar)](https://marketplace.visualstudio.com/items?itemName=johnsoncodehk.volar)
- [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
- [Debugger for Firefox](https://marketplace.visualstudio.com/items?itemName=firefox-devtools.vscode-firefox-debug)
- [Vue.js devtools Firefox](https://addons.mozilla.org/en-US/firefox/addon/vue-js-devtools/)

--------------------------------------------------------------------------------

## Services

- **application** : 0.0.0.0:50050
- **gRPC proxy**  : 0.0.0.0:10000
- **web-app**     : 127.0.0.1:8000

--------------------------------------------------------------------------------

## Gateways

- application gRPC API                  : app.inward.ir
- application gRPC Web API (gRPC proxy) : appweb.inward.ir
