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

Afterwards, let's first create a _resource group_ called `pk-rg-nodes-01` within the _West Europe_ region:

```text
az group create --name pk-rg-nodes-01 --location westeurope
```

Then, let's create an Ubuntu _virtual machine_ called `pk-vm-node-01` within the `pk-rg-nodes-01` group:

```text
az vm create \
  --resource-group pk-rg-nodes-01 \
  --name pk-vm-node-01 \
  --image Canonical:0001-com-ubuntu-minimal-focal:minimal-20_04-lts-gen2:latest \
  --admin-username radicel \
  --generate-ssh-keys \
  --public-ip-sku Standard
```
