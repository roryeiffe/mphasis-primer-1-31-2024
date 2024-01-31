## Azure Portal
- Register here [here](https://azure.microsoft.com/en-us/get-started/azure-portal)
  - Make sure to click "start free"
  - Hopefully you won't have to put in card details but either way, we will always explicitly go over how to use services in ways that don't charge anything * (might be a few dollars at most)
- Resource Manager - an interface that lets us manage our resources

### Different Sections
- All Resources - shows all resources that we have created
- All Services - shows all services available in categories
- Create a Resource - takes us to a menu that lets us spin up and allocate new resources
- Free Services - good for us learning, not worrying about money


### Creating a VM
1. Select "Create a Resource" option from the home page.
1. From the list of all services, select "Virtual Machine" (should take you to create screen)
1. Fill out the form
    1. Subscription - has to do with billing (should only have one for now so select that)
    1. Resource Group - Logical Grouping of our resources
        - Ex: name them after the type of service we're using like "rg-vm" 
        - Ex: name them after steps in the development cycle like "rg-prod"
    1. Virtual Machine Name - just give a name for the resource
    1. Region - Pick a physical location for where your VM is hosted
        - In practice, you'd want to pick a region that is close to you or your customers
    1. Availability Options - set up availability zones or other facilities to ensure resources are always available
    1. Security Type - Depending on security needs, can change this option but we can stick with the default
    1. Image - Choose what operating system to use (Linux or Windows)
        - Stick with the default Ubuntu, 20.04
    1. VM Architecture - choose between x64 and Arm64 (trade-off between price and compatibility)
    1. Azure Spot Discount - cost-saving method
    1. Size - Can pick size offered for the instance and can sort by price to pick the cheaper options
    1. Hibernation - cost-saving
    1. Authentication Type - determine how we authenticate ourselves to use the VM
       - Choose public key, it is much more secure
    1. Username - pick any username to authenticate yourself
        - "rory"
    1. Public Key Source, can either create a new one or use an old key that we already generated
    1. Key-Pair-Name - if we are creating a new key, give it a name that you will remember
    1. Inbound Port Rules - configuring what sources are allowed to access your VM
        - Public Inbound Ports - make sure "Allow Selected Ports" is selected so we can specify which ports are allowed
        - Select inbound Ports - Select the ports that we want to allow
          - 100% make sure that SSH is selected because SSH is the method by which we connect to the instance. So if SSH wasn't allowed, we couldn't even access our instance in that way.
          - Could allow HTTP (80) if we wanted to allow HTTP requests
        - This seems like a lot of resources but the important ones that you will usually change/edit are
          - Subscription/Resource Group
          - VM Name
          - Region Settings (Region + Availability Zone)
          - Image
          - Size
          - Authentication Type and Key-Pair Settings
          - Inbound Port Rules
1. For the most part, can click "Review + Create" but can also explore the other tabs
1. After creating it, if you chose to allocate a new key-pair, you should download the private key because you otherwise won't be able to access it again (for security purposes)

### Connecting to the VM
1. Download the private key from Azure and move it to any directory where you will remember where to find it but for Windows users it's best to put it in your users folder so something like C:/Users/Rory/ (for appropriate permissions to access the pem file)
2. Ensure that SSH is installed on your computer: https://learn.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse?tabs=gui
3. Open up command prompt/terminal and navigate to wherever your key file is. (For windows users, should default to your user directory)
4. Run a command of the following format
  - ssh -i path-to-key username@ipaddress
  - ex: ssh -i ./rory-vm-key.pem rory@172.210.181.169
    - username and address can be grabbed from Azure portal when we view the resource (VM)
5. If it prompts "Are you sure you want to continue connecting (yes/no/[fingerprint])?" type "yes"
6. Now you should have access to the instance
  - Some Linux commands to play around with:
    - ls - lists the contents of the directory
    - vim - creates/edits a file
      - i - insert mode
      - type a message
      - hit ESC
      - type ":wq" for write-quit and it should save the file
    - cat file-name - displays the contents of the file

### Deleting Resource
- Navigate to your resource
- Click "Delete"
- Might need to confirm by typing in the name of the resource