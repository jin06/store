
docker run --rm -v $(pwd):/workspace tinygo-wasi tinygo build -o yourfile.wasm -target=wasi yourfile.go
