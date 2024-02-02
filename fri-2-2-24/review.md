## Horizontal Scaling vs Vertical Scaling
- Because we have customers that will be accessing our resources, we need to be able to meet the demand changes. You need to adopt a dynamic approach to allocating resources to make sure that you can fulfill the requests while not wasting any resources. 

### Horizontal Scaling
Changing the number of resources. For example, if we have 100 VMs up and running to handle shopping requests, we could add 100 more during high traffic. Or we could remove 50 of them when there's less traffic (at night or during the off-season). 

### Vertical Scaling
Changing the power/capabilities of a single resource. Improving the CPU/RAM/Memory of a computer to meet demand. 

### Usually Horizontal Scaling is preferred
- Can only improve a unit so much
- Have to delegate to different units, but cloud providers have built-in services that handles this for us
