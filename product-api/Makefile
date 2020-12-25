check_install:
	which swagger || GO111MODULE=off go get -u github.com/go-swagger/go-swagger/cmd/swagger

# if [make swagger] command give errors then delete "GO111MODULE=off" for a try
swagger: check_install
	GO111MODULE=off swagger generate spec -o ./swagger.yaml --scan-models

generate_client:
	cd sdk && swagger generate client -f ../swagger.yaml -A product-api