- 👋 Hi, I’m @rbalagopalakrishna
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
rbalagopalakrishna/rbalagopalakrishna is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
To get admin access of VDI: 

Go to nike tools and install "promote to administrator" and then restart the system 

 

Tools required for NPE setup: 

 

Install python & pip 

Install golang 

 

Install GitBash 

Generate ssh key and add it to https://github.com/settings/keys  

 

Install npectl 

Download the binary from and move to C:\Users\<your_userID> 

https://github.com/nike-platform-engine/core-cli 

 

 

Install kubectl 

Download binary from and move it to C:\Users\<your_userID> 

https://dl.k8s.io/release/v1.23.0/bin/windows/amd64/kubectl.exe 

 

 

Install Terraform  

Download binary from and move it to C:\Users\<your_userID> 

https://releases.hashicorp.com/terraform/1.1.3/terraform_1.1.3_windows_amd64.zip 

 

Install awscli using pip  
# pip3 install awsebcli --upgrade 

 

Install gimme-aws-creds using pip 
#  pip3 install --upgrade gimme-aws-creds 

 

 

 

To build npectl binary: 

 

Clone: https://github.com/nike-platform-engine/core-cli 

 

Set Environment variables: 

 

GO111MODULE="on" 

export PATH="$PATH:$GOBIN" 

export GOPROXY='https://proxy.golang.nike.com' 

export GONOSUMDB='*.nike.com,github.com/nike*,github.com/Nike*,k8s.io.*' 

 

Build Command: go build -o npectl . 

 

 

Configure gimme-aws-creds 

 

 

vi ~/.okta_aws_login_config 

 

 

[DEFAULT] 

okta_org_url = https://nike.okta.com 

okta_auth_server = aus27z7p76as9Dz0H1t7 

client_id = 0oa34x20aq50blCCZ1t7 

gimme_creds_server = https://api.sec.nikecloud.com/gimmecreds/accounts 

aws_appname = AWS WaffleIron Multi-Account 

aws_rolename = all 

write_aws_creds = True 

cred_profile = acc-role 

okta_username = <YOUR_NIKE_EMAIL>@nike.com 

app_url = 

resolve_aws_alias = False 

include_path = False 

preferred_mfa_type = push 

remember_device = True 

aws_default_duration = 43200 

device_token = 

output_format = export 

 

# gimme-aws-creds --action-configure 

 # gimme-aws-creds 

 
