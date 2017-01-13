# Redis CheatSheet

## Search

```
KEYS "*"
GET <key>
HGETALL <key>
HGET <key> <field>
```

## Delete

```
# Delete all coincidenes
$ redis-cli -h <server> KEYS "<filter>" | xargs redis-cli -h <server> DEL
```