# Terraform AWS OpenVPN
From Paul Marsicovetere's [terraform-aws-openvpn-ephemeral](https://github.com/paulmarsicloud/terraform-aws-openvpn-ephemeral) repository 

Use [m1-terraform-provider-helper](https://github.com/kreuzwerker/m1-terraform-provider-helper)
A CLI to help with managing the installation and compilation of terraform providers when running a new M1 Mac.

Install the [Session Manager plugin for the AWS CLI](https://docs.aws.amazon.com/systems-manager/latest/userguide/session-manager-working-with-install-plugin.html)


### TF_VAR_(iables)

 * `TF_VAR_instance_type` - ec2 instance type, defaults ec2
 * `TF_VAR_public_ip` - client public ip (use `curl ipaddr.io`)
 * `TF_VAR_region` - VPN region (defaults `ap-south-1`)

### alias commands in .zshrc

 * `alias vpn-ap-south-1-up="export AWS_PROFILE=<YOUR AWS PROFILE NAME>; export AWS_DEFAULT_REGION=ap-south-1; export TF_VAR_region=ap-south-1; cd <FOLDER CONTAINING LOCAL TERRAFORM CODE >; terraform init; terraform apply -auto-approve; open openvpn.ovpn"`


 * `alias vpn-ap-south-1-down="export AWS_PROFILE=<YOUR AWS PROFILE NAME>; export TF_VAR_region=ap-south-1; cd <FOLDER CONTAINING LOCAL TERRAFORM CODE >; terraform destroy -auto-approve; rm -rf openvpn.vpn"`

