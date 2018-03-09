# gcloud-simple-cmdlet

gcloud-simple-cmdlet is a set of bash scripts that intended to speed up routine tasks on Google cloud. It requires latest version of gcloud command line and only support Linux at this moment.

### Getting started

Add the .inc file in your ~/.bashrc file:
```sh
if [ -f '/home/???/gcloud-simple-cmdlet/gcloud-simple.inc' ]; then source '/home/???/gcloud-simple-cmdlet/gcloud-simple.inc'; fi
``` 

Restart terminal

### Usage
```sh
# switch GCP project
gproject <project-id>

# list all GCE instances
gls [gcloud compute options]

# ssh through public IP address (need firewall setting)
gssh <instance-name> [ssh options]

# copying files between local and remote instance
gscp <source-path> <destination-path> [ssh options]

# encode a clear text with base64 and encrypt with CloudKMS (need KMS encryptor permission)
gencrypt <project-id> <keyring> <key> <secret>

# decrypt a base64 encoded and CloudKMS protected message back to clear text (need KMS decryptor permission)
gdecrypt <project-id> <keyring> <key> <cipher-text>

