# Example Control Plane Function

Example function showcasing how you can use Crossplane Composition Functions to orchestrate your IDP's Control Plane

```shell
# Run code generation - see input/generate.go
$ go generate ./...

# Run tests - see fn_test.go
$ go test ./...

# Build the function's runtime image - see Dockerfile
$ docker build . --tag=runtime

# Build a function package - see package/crossplane.yaml
$ crossplane xpkg build -f package --embed-runtime-image=runtime
```

```shell
crossplane beta render ./example/xr.yaml ./example/composition.yaml ./example/functions.yaml
```

```shell
idpbuilder create -p ./local/localstack
```

```shell
kubectl apply -f example/claims/s3bucket.yaml
```