## tf-aws-benchmark


### Config github secrets
1. AWS_ACCESS_KEY_ID
2. AWS_SECRET_ACCESS_KEY
3. EMQX_LIC
4. SSH_PRIVATE_KEY


### Terraform arguments
```bash
terraform apply -auto-approve -var="key_name=aws-west-bench" -var="os=ubuntu" -var="region=us-west-2" -var="emqx_lic=${{ secrets.EMQX_LIC }}"  -var="access_key=${{ secrets.AWS_ACCESS_KEY_ID }}" -var="secret_key=${{ secrets.AWS_SECRET_ACCESS_KEY }}" -var="private_key=${{ secrets.SSH_PRIVATE_KEY }}" -var="emqx_package=/tmp/emqx.zip"
```

**Note: You have to apply the key pair in your region first**

- key_name: the key pair of aws
- os: the os of emqx hosted (`ubuntu` for ubuntu 20.04, `centos` for cenos 7)
- region: aws region
- emqx_lic: the license of emqx
- access_key & secret_key: the access key and secret key of aws you applied
- private_key: ssh private key
- emqx_package: the path of emqx package


