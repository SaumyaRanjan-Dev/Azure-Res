
# How to Deploy a Virtual Network (VNet) in Azure

## Deploy a VNet via Azure Portal

### Steps:
1. **Sign in to Azure Portal**:
   - Go to [portal.azure.com](https://portal.azure.com) and log in with your Azure credentials.

2. **Create a Virtual Network**:
   - In the search bar at the top, type "Virtual Network" and select it from the drop-down list.
   - Click the "Create" button to start creating a new VNet.

3. **Basic Settings**:
   - **Subscription**: Choose the Azure subscription you want to use.
   - **Resource Group**: Select an existing resource group or create a new one.
   - **Name**: Give your VNet a name (e.g., `MyVNet`).
   - **Region**: Choose the Azure region where you want your VNet to be deployed (e.g., East US).

4. **Configure the Address Space**:
   - In the "IP Addresses" section, define the address space for your VNet. For example, you might use `10.0.0.0/16`.
   - Add subnets by specifying a name and a subnet address range (e.g., `10.0.1.0/24`).

5. **Security and Connectivity**:
   - You can add a **Network Security Group (NSG)** to control traffic to and from your VNet.
   - You can configure **DDoS Protection** and **Firewall** settings if needed.

6. **Tags (Optional)**:
   - Tags help you organize your resources. Add any tags you need for managing your VNet.

7. **Review and Create**:
   - Review all your settings. Once everything looks good, click "Create" to deploy the VNet.

8. **Deployment**:
   - Azure will take a few moments to deploy your VNet. You can monitor the deployment status on the portal.

9. **Access and Manage Your VNet**:
   - Once deployed, you can access your VNet from the "Virtual Network" service in the Azure portal. From there, you can manage subnets, NSGs, and other settings.

---

## Deploy a VNet via Azure CLI

### Prerequisites:
- Ensure that you have the Azure CLI installed. If not, you can install it from [here](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli).
- Sign in to your Azure account using:
   ```bash
   az login
   ```

### Step-by-Step Guide:

1. **Create a Resource Group**:
   First, create a resource group to hold your VNet. You can skip this step if you want to use an existing resource group.
   ```bash
   az group create --name MyResourceGroup --location eastus
   ```

2. **Create a Virtual Network (VNet)**:
   Now, create the VNet with a specified address space.
   ```bash
   az network vnet create \
     --name MyVNet \
     --resource-group MyResourceGroup \
     --address-prefix 10.0.0.0/16 \
     --subnet-name MySubnet \
     --subnet-prefix 10.0.1.0/24
   ```

   - `--name MyVNet`: Specifies the name of the VNet.
   - `--resource-group MyResourceGroup`: Specifies the resource group to which the VNet belongs.
   - `--address-prefix 10.0.0.0/16`: Defines the address space for the VNet.
   - `--subnet-name MySubnet`: Creates a default subnet within the VNet.
   - `--subnet-prefix 10.0.1.0/24`: Defines the address range for the subnet.

3. **Verify the VNet**:
   After creating the VNet, you can verify it by listing all the VNets in the resource group:
   ```bash
   az network vnet list --resource-group MyResourceGroup --output table
   ```

4. **Add Additional Subnets (Optional)**:
   If you want to add more subnets to the VNet, use the following command:
   ```bash
   az network vnet subnet create \
     --resource-group MyResourceGroup \
     --vnet-name MyVNet \
     --name AnotherSubnet \
     --address-prefix 10.0.2.0/24
   ```

This command adds a new subnet named `AnotherSubnet` to the existing VNet `MyVNet`.
