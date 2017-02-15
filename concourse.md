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

### Delete a pipeline
```
fly -t <target-name> dp -p <pipeline-name>
```

### Create a team
```
flys set-team -n <team-name> --github-auth-client-id=<a-client-id> --github-auth-client-secret=<a-secret> --github-auth-organization=<organization>
```

### Debug Commands
```
fly -t <target-name> builds
fly -t <target-name> i -b <build-number> /bin/bash
```

### Force Pipeline Resource

```
fly -t <target-name> cr -r <pipeline-name>/<resource-name>
```

### Create version branch for SEMVER

```
git checkout --orphan version
git rm --cached -r .
rm -rf *
rm .gitignore .gitmodules
touch README.md
echo "0.0.1" > version
git add .
git commit -m "new branch"
git push origin version
```
