Code of Backend master class Series' Articles

https://dev.to/techschoolguru/series/7172

# Tools & Libraries
- migration `paru migrate`
- sqlc `paru sqlc`


## sqlc
- init sqlc.yaml

## Generate code
- create account.sql
- run `make sqlc`

## Testing
- create main_test.go for init var testQueries *Queries
- create account_test.go for test feature
- test by `go test --timeout 30s github.com/techschool/simplebank/db/sqlc --run ^TestMain$`
- found `cannot connect to db:sql: unknown driver "postgres" (forgotten import?)`
- need to install lib `go get github.com/lib/pq` for postgres
- and import `_ "github.com/lib/pq"`
- use `context.Background()` and arg for run
- use `go get github.com/stretchr/testify` for easer to assert test result
- run test `go test -timeout 30s -run ^TestCreateAccount$ github.com/techschool/simplebank/db/sqlc`