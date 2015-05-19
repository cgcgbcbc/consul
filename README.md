# consul configuration for labmu

install `gorender` by
```
go get github.com/cgcgbcbc/gorender
```

# example usage
```
gorender -p consul.json.tmpl recursor=166.111.8.28 hostname=$HOSTNAME
export IP=`ifconfig docker0 | grep "inet addr" | awk -F: '{print $2}' | awk '{print $1}'`
gorender -p docker-compose.yml.tmpl IP=$IP advertise=$IP dns=166.111.8.28 dns_search=lab.mu
```