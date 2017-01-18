# Ansible CheatSheet


```
ansible-vault --vault-password-file=<vpass_path> encrypt <file_to_encrypt> --output=<encrypted_file>
ansible-vault --vault-password-file=<vpass_path> decrypt <encrypted_file> --output=<decrypted_file>
```

```
ansible-vault --vault-password-file=<vpass_path> {edit|view} <encrypted_file>
```
