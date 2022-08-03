# fabric_model_example

# HCL (Infrastructure As Code)
- Language used by Terraform 
- Advantages
  - We can use Terraform down the road. 
     - Yaml files can convert easily to terraform files. 
     - Need to implement plugin
  - May actually solve the dependency problem 
  
# Node In A Prgramming language Like Java. 

```
class Resource {
}

class Node extends Resource {
   String image;
   String nicModel;
}

my_node = new Node()
my_node.image = "centos"
my_node.nic_model = "NIC_Basic"

```

# Node in YAML

```
reource:
   - node: 
     - my_node:                       // Note the variable name here.
       - image: "centos"
       - nic_model: "Nic_Basic"
    
// Now another resource can refer to it as '{{ node.my_node }}' and in doing so we can deduce that this  resource
depends on node with name "my_node"
```

# Node in HCL

```
resource "node" "my_node" {
   image       = "centos"
   nic_model   =  "Nic_Basic"
}
```
