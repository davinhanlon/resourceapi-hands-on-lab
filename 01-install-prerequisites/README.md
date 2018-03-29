# Download and Install Puppet Development Kit (PDK) and the Puppet Agent

## Step 1 Install the PDK
> In this step we will download and install the PDK

Go to [this](https://puppet.com/docs/pdk/1.x/pdk_install.html) URL and download the package corresponding to your operating system. Download and install the package. When this has been done open a terminal or command prompt and type ```pdk --version```. The version of the PDK will be displayed. It must be version 1.4.1 or later. The PDK will install the Ruby environment within it, so a separate Ruby installation is not necessary.

## Step 2 Install the Puppet Agent
> In this we will download and install the Puppet Agent

Go to [this](https://puppet.com/download-puppet-enterprise). You will have to enter some details in order to get to the download page. Ensure you choose the tab entitled "Puppet Enterprise Agents". Find the agent for your operating system, download it and run the installer. When this has been done open a terminal or command prompt and type ```puppet --version```. The version of Puppet will be displayed.

[02. Create Target to Manage](../02-create-target-to-manage)
