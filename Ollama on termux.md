# Ollama on Termux

## Install Dependancies

```bash
pkg update -y && pkg upgrade -y
pkg install git cmake golang
```

## Build Ollama from source

```bash
git clone --depth 1 https://github.com/ollama/ollama.git
cd ollama
go generate ./...
go build .
./ollama serve &
./ollama run phi
```

## Cleanup

You may want to remove the 'go' folder that was just created in your home directory. If so here is how to do it.

```bash
chmod -R 700 ~/go
rm -r ~/go
```

Currently, termux does not have .local/bin in its PATH (though you can add it if you would prefer). If you would like to move the ollama binary to the bin folder you can do the following.

```bash
cp ollama/ollama /data/data/com.termux/files/usr/bin/
```


Now you can just run ollama in your terminal directly!