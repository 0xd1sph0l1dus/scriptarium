---
title: "How i create my homelab"
---

# Installation Backend environnement

## Step 1
* Download the sources
 ```
 wget https://go.dev/dl/go1.22.8.linux-amd64.tar.gz 
 ```
* Extract in the good folder
 ```
 sudo tar -C /usr/local -xzf path/to/file/go1.23.3.linux-amd64.tar.gz 
 ```

## Step 2

Edit your `.gitconfig` file
```
[user]
    email = gitnumber+username@users.noreply.github.com

[url "git@github.com:"]
    insteadOf = https://github.com/

[url "ssh://git@github.com/"]
    insteadOf = https://github.com/
```

## Step 3

Create en environment file, like `.bash_aliases` if his not exists.
```
### GO ###
export GOPATH=$HOME/go
export PATH=$PATH:/usr/local/go/bin:$GOPATH/bin
export GO111MODULE=on
export GOBIN=/home/$USER/go/bin
export GOPRIVATE='github.com/sas-check/libs'
```


## Step 4
Create a folder in the root folder of your GO installation:

/home/USERNAME/go/**src/github.com/sas-check**`

## Step 5
Clone the repos locally
## Step 6

Link de bash env file to the current folder
```
source ~/.bash_aliases
```

## Step 7
Install `golanci-lint`
```
curl -sSfL https://raw.githubusercontent.com/golangci/golangci-lint/master/install.sh | sh -s -- -b $(go env GOPATH)/bin v1.62.0
```

## Step 8
Install all dependencies via Makefile
```
make install-swag
make update
```
## Step 9

***Tadam ! Ready to work !***

