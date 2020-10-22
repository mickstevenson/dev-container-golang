Remote-Containers: Add Development Container Configuration Files ...
From a predefined container configuration definition ...
Show All Definitions ...
Go ...
1.15 ...
Node JS not selected ...

reopen vscode : open folder
reopen in container

$ ./scripts/build.sh
$ make build
$ make install 


* different launch configurations

ensure that that the golang plugin is installed
ensure that all tolls are updated via

Ctrl + SHIFT + P
Go: Install/Update Tools
select all

the following components will be installed or updated

```
gocode
gopkgs
go-outline
go-symbols
guru
gorename
gotests
gomodifytags
impl
fillstruct
goplay
godoctor
dlv
gocode-gomod
godef
goimports
golint
gopls
```

* test sym link

touch .env



launch configurations

main.go

attached

test
```
```

```
```




AZDO_ORG_SERVICE_URL="https://dev.azure.com/mickstevenson"
AZDO_PERSONAL_ACCESS_TOKEN="u2cx6ilvkbeh2chvjwyk2oqegz7ovxus4gx6rhy27mtswytnjrra"


export AZDO_PERSONAL_ACCESS_TOKEN=u2cx6ilvkbeh2chvjwyk2oqegz7ovxus4gx6rhy27mtswytnjrra
export AZDO_ORG_SERVICE_URL=https://dev.azure.com/mickstevenson
export AZDO_DOCKERREGISTRY_SERVICE_CONNECTION_EMAIL="dummy@dummy.com"
export AZDO_DOCKERREGISTRY_SERVICE_CONNECTION_PASSWORD="password1234"
export AZDO_DOCKERREGISTRY_SERVICE_CONNECTION_USERNAME="dummy"
export AZDO_GITHUB_SERVICE_CONNECTION_PAT="pat123"
export AZDO_TEST_AAD_USER_EMAIL="dummy@dummy.com"


running all the acceptance tests


how to debug code by adding folder to work space

```
./create-env-vars.sh \
https://dev.azure.com/mickstevenson \
u2cx6ilvkbeh2chvjwyk2oqegz7ovxus4gx6rhy27mtswytnjrra \
dummy@dummy.com \
password1234 \
dummy \
pat123 \
dummy@dummy.com

make testacc
```

```
cat <<EOF > .env
AZDO_PERSONAL_ACCESS_TOKEN=u2cx6ilvkbeh2chvjwyk2oqegz7ovxus4gx6rhy27mtswytnjrra
AZDO_ORG_SERVICE_URL=https://dev.azure.com/mickstevenson
AZDO_DOCKERREGISTRY_SERVICE_CONNECTION_EMAIL="dummy@dummy.com"
AZDO_DOCKERREGISTRY_SERVICE_CONNECTION_PASSWORD="password1234"
AZDO_DOCKERREGISTRY_SERVICE_CONNECTION_USERNAME="dummy"
AZDO_GITHUB_SERVICE_CONNECTION_PAT="pat123"
AZDO_TEST_AAD_USER_EMAIL="dummy@dummy.com"
EOF

make testacc
```



output

```
==> Checking that code complies with gofmt requirements...
==> Sourcing .env file if avaliable
if [ -f .env ]; then set -o allexport; . ./.env; set +o allexport; fi; \
TF_ACC=1 go test -tags "all" $(go list ./azuredevops/internal/acceptancetests |grep -v 'vendor') -v  -timeout 120m
=== RUN   TestAccAgentPool_DataSource
--- PASS: TestAccAgentPool_DataSource (6.40s)
=== RUN   TestAccAgentPools_DataSource
--- PASS: TestAccAgentPools_DataSource (6.23s)
=== RUN   TestAccAreaDataSource_Read
--- PASS: TestAccAreaDataSource_Read (12.38s)
=== RUN   TestAccAreaDataSource_ReadNoChildren
--- PASS: TestAccAreaDataSource_ReadNoChildren (22.24s)
=== RUN   TestAccClientConfig_LoadsCorrectProperties
--- PASS: TestAccClientConfig_LoadsCorrectProperties (2.76s)
=== RUN   TestAccAzureTfsGitRepositories_DataSource
--- PASS: TestAccAzureTfsGitRepositories_DataSource (19.62s)
=== RUN   TestAccGitRepository_DataSource
--- PASS: TestAccGitRepository_DataSource (15.38s)
=== RUN   TestAccGroupDataSource_Read_HappyPath
--- PASS: TestAccGroupDataSource_Read_HappyPath (13.93s)
=== RUN   TestAccIterationDataSource_Read
--- PASS: TestAccIterationDataSource_Read (10.33s)
=== RUN   TestAccIterationDataSource_ReadNoChildren
--- PASS: TestAccIterationDataSource_ReadNoChildren (11.25s)
=== RUN   TestAccProject_DataSource
--- PASS: TestAccProject_DataSource (12.43s)
=== RUN   TestAccProject_DataSource_IncorrectParameters
.........
```