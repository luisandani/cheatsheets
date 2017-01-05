# CheatSheets

Personal CheatSheets

## Integration together with dotfiles repo

I have in a .extra file this script, so I create an alias for each cheatsheet.

```
## cheatsheets
for file in ~/devel/cheatsheets/{ansible,concourse,docker,git,linux,mysql,redis}.md; do
    if [[ -r "$file" ]] && [[ -f "$file" ]]; then
        filename=$(basename $file | cut -f 1 -d '.')
        alias mal-cs-$filename="cat $file"
    fi
done
unset file
```
