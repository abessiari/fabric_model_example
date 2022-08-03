# fabric_model_example

# HCL (Infrastructure As Code)
- Language used by Terraform 
- Advantages
  - We can use Terraform down the road. 
     - Yaml files can convert easily to terraform files. 
     - Need to implement plugin
  - May actually solve the dependency problem 
  
# Node using classic language. 

class Resource {
}

class Node extends Resource {
   String image;
   String nicModel;
}

my_node = new Node()
my_node.image = "centos"
my_node.nic_model = "NIC_Basic"

# Node in yaml

reource:
   - node: 
     - my_node:
       - image: "centos"
       - nic_model: "Nic_Basic"
    
// Now we can refer to it as {{ node.my_node }}

# Node in HCL

resource "node" "my_node" {
   image       = "centos"
    nic_model. =  "Nic_Basic"
}
