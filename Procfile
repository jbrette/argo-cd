controller: go run ./cmd/argocd-application-controller/main.go --app-resync 60
api-server: go run ./cmd/argocd-server/main.go --insecure --disable-auth
repo-server: go run ./cmd/argocd-repo-server/main.go --loglevel debug
dex: sh -c "go run ./cmd/argocd-util/main.go gendexcfg -o `pwd`/dist/dex.yaml && docker run --rm -p 5556:5556 -p 5557:5557 -v `pwd`/dist/dex.yaml:/dex.yaml quay.io/coreos/dex:v2.10.0 serve /dex.yaml"
redis: docker run --rm -p 6379:6379 redis:3.2.11
