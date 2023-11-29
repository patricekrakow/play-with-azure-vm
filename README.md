# Let's Play with Azure Virtual Machines (VMs)

## Create an Ubuntu VM on Azure

Before starting, don't forget to check that you are connected to the right _subscription_:

```text
az account show
```

If needed, you can change the active _subscription_ with the follwoing command:

```text
az account set --subscription [Name or ID of subscription]
```

Afterwards, let's first create a _resource group_ called `pk-rg-test-01` within the _West Europe_ region:

```text
az group create --name pk-rg-test-01 --location westeurope
```

Then, let's create an Ubuntu _virtual machine_ called `pk-vm-test-01` within the `pk-rg-test-01` group:

```text
az vm create \
  --resource-group pk-rg-test-01 \
  --name pk-vm-test-01 \
  --image Canonical:Ubuntu2204 \
  --admin-username radicel \
  --generate-ssh-keys \
  --public-ip-sku Standard
```

Finally, you can test if the creation was successful by connecting to your _virtual machine_:

```text
ssh <publicIpAddress>
```

In order to save resources (and money), you can easility delete your _virtual machine_ and all the associated resources by delete your group:

```text
az group delete --resource-group pk-rg-test-01
```
