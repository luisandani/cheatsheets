# Concourse CheatSheet

### Login (always before execute any command)
```
fly -t <target-name> login --team-name <team-name> --concourse-url <concourse-url>
```

### Set new pipeline

```
fly -t <target-name> sp -p <pipeline-name> -c <pipeline-yml-file-path>
# if there are encrypted vars in a file
fly -t <target-name> sp -p <pipeline-name> -c <pipeline-yml-file-path> -l <(ansible-vault --vault-password-file=<vpass-pass-file> decrypt <vars-encrypted-file> --output=-)
```
### Debug Commands
```
fly -t <target-name> builds
fly -t <target-name> i -b <build-number> /bin/bash
```
