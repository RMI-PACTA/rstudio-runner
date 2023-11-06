# RStudio Runner

Run a rocker/rstudio container on Azure Container Instances

deploying this requires the [az cli](https://learn.microsoft.com/en-us/cli/azure/install-azure-cli)

To Deploy:

copy `example.parameters.json` to `azure-deploy.parameters.json` and change values as needed, then from a terminal:

```sh
# change this value as needed.
RESOURCEGROUP="pacta-runner"

# run from repo root

az deployment group create --resource-group "$RESOURCEGROUP" --template-file azure-deploy.json --parameters @azure-deploy.parameters.json

```

Then connect to VPN, and connect to the host listed in "Outputs" on port 8787.
So for example, if our container group had an IP of `172.20.1.4`, then you would enter `172.20.1.4:8787` in your URL Bar (after connecting to VPN)
