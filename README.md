# Let's Play with Azure Virtual Machines (VMs)

## Create an Ubuntu VM on Azure

First, let's create a _resource group_ called `pk-rg-azure-01` within the _West Europe_ region:

```text
az group create --name pk-rg-azure-01 --location westeurope
```

Then, let's create an Ubuntu _virtual machine_ called `pk-vm-01` within the `pk-rg-azure-01` group:

```text
az vm create \
  --resource-group pk-rg-azure-01 \
  --name pk-vm-01 \
  --image Canonical:0001-com-ubuntu-minimal-focal:minimal-20_04-lts-gen2:latest \
  --admin-username radicel \
  --generate-ssh-keys \
  --public-ip-sku Standard
```
