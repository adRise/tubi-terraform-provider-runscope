default: testacc

testacc:
	TF_ACC=1 go test ./... -v $(TESTARGS) -timeout 120m

release:
	goreleaser release

.PHONY: testacc release