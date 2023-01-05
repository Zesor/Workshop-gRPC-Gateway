## 1 - Installation

Pour ce workshop, nous devrons installer les dépendances suivantes:

- [go](https://go.dev/) - Le langage pour ce workshop.
- [protoc](https://developers.google.com/protocol-buffers) - Le protobuf compiler
- [grpc-gateway](https://github.com/grpc-ecosystem/grpc-gateway) - grpc gateway

Pour ce workshop nous utiliserons golang en association avec grpc-gateway, pour ce faire installer golang:

### **go**
```shell
# Le tar.gz pour installer golang sur linux
wget https://go.dev/dl/go1.19.linux-amd64.tar.gz
Pour macos -->
brew install golang

# Will extract and move binaries into GOPATH
sudo rm -rf /usr/local/go && sudo tar -C /usr/local -xzf go1.19.linux-amd64.tar.gz
```

Then, open your `.zshrc` or `.bashrc` file and append the following line at the end:
```shell
export PATH=$PATH:/usr/local/go/bin:$(go env GOPATH)/bin
```

### **protoc**

protoc est le protocol buffer compilateur, il nous sera utile pour créer no protobuf plus tard durant le workshop:
- sur fedora: `sudo dnf install protobuf-compiler`
- sur ubuntu: `sudo apt install protobuf-compiler`
- sur macos: `brew install protoc`

Si vous avez le moindre problème avec protoc, go [here](https://grpc.io/docs/protoc-installation/).

## Init golang project

Créer un dossier pour ce workshop et lancez la commande suivante pour initialiser le projet.
```shell
go mod init grpc-workshop
```

Ensuite lancez --> :
```shell
go install \
    github.com/grpc-ecosystem/grpc-gateway/v2/protoc-gen-grpc-gateway \
    github.com/grpc-ecosystem/grpc-gateway/v2/protoc-gen-openapiv2 \
    google.golang.org/protobuf/cmd/protoc-gen-go \
    google.golang.org/grpc/cmd/protoc-gen-go-grpc```
