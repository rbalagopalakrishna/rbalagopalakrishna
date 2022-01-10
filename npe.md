Setup NEP environment in windows machine
========================================

Login into VMware Horizon server : https://vdiair.nike.com/appblast/webclient/#/home


To get admin access of windows
------------------------------
 
Go to nike tools and install "promote to administrator" and then restart the system 


Requirements
------------
* Install python & pip

* Install golang

* Install GitBash and Generate the ssh key and add it to https://github.com/settings/keys

* Install awscli using pip ```pip3 install awsebcli --upgrade```

* Install gimme-aws-creds using pip ```pip3 install --upgrade gimme-aws-creds```

**Configure gimme-aws-creds:**

Edit the ~/.okta_aws_login_config file and complete the following actions:

```
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
```

Run
```
gimme-aws-creds --action-configure
gimme-aws-creds
```

**Build & Install npectl ::** Clone core-cli from https://github.com/nike-platform-engine/core-cli 

Set Environment variables: 

```
GO111MODULE="on" 

export PATH="$PATH:$GOBIN" 

export GOPROXY='https://proxy.golang.nike.com' 

export GONOSUMDB='*.nike.com,github.com/nike*,github.com/Nike*,k8s.io.*'
```

Run Build Command: ```go build -o npectl . ```

OR

Download the binary from https://github.com/nike-platform-engine/core-cli  and move to C:\Users\<your_userID> 


**Install kubectl ::** Download binary from https://dl.k8s.io/release/v1.23.0/bin/windows/amd64/kubectl.exe and move it to C:\Users\<your_userID> 


**Install Terraform ::** Download binary from https://releases.hashicorp.com/terraform/1.1.3/terraform_1.1.3_windows_amd64.zip and move it to C:\Users\<your_userID> 


Verify Access to Cluster
------------------------
```# aws eks --region <REGION> update-kubeconfig --name <KUBE_CONFIG> --profile <PROFILE>```
