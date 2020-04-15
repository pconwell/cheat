# Google Cloud Platform

## Google Compute Engine (VMs)

1. Select or Create Project
2. Compute Engine -> VM instances
3. SSH Button
4. Settings ⚙️ -> Change Linux Username -> USERNAME
5. Metadata -> Metadata -> Key: enable-oslogin; Value: FALSE
6. Metadata -> SSH Keys -> Edit -> Add Key
7. Copy/Paste id_rsa.pub

> Make sure that the email adress at the end of the key matches the username set in step 4. For example, if the username was set as jsmith, add the following key:
>
> `ssh-rsa AAAAB3NzaC ... a+t9I/uMRQ== jsmith@gmail.com`
>
> it doesn't matter if you actually own jsmith@gmail.com, you just need the username to match.
