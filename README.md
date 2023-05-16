# [Docker setting]

install docker
using postgres image 
docker run --name postgres -p 5432:5432 -e POSTGRES_USER=root -e POSTGRES_PASSWORD=secret -d postgres
docker exec -it postgres psql -U root

# [Install go]
wget https://go.dev/dl/go1.20.4.linux-amd64.tar.gz
sudo tar -xvf go1.20.4.linux-amd64.tar.gz
sudo mv go /usr/local

cd ~
explorer.exe .

Add the following three lines to the botom of your .bashrc file and save it.

export GOROOT=/usr/local/go
export GOPATH=$HOME/go
export PATH=$GOPATH/bin:$GOROOT/bin:$PATH

check with command
go version

# [Install go migrate]
curl -s https://packagecloud.io/install/repositories/golang-migrate/migrate/script.deb.sh | sudo bash
apt-get update
apt-get install -y migrate

check with command
migrate

migrate init command
migrate create -ext sql -dir db/migration/ -seq init_schema

# [Install sqlc]
curl -L https://github.com/kyleconroy/sqlc/releases/download/v1.18.0/sqlc_1.18.0_linux_amd64.tar.gz | tar xvz
chmod +x sqlc
sudo mv sqlc /usr/local/bin

check with command
sqlc

# [Install lib pq]
go get github.com/lib/pq

# [Make command]
see make file
make with command just like
init command
make postgres
make createdb
make migrateup

# [sqlc command]
sqlc generate




