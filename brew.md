# Brew Cheatsheet

### Manual
```
man brew
```

### List of installed software with version
```
brew list --versions
```

### Show installed formulae that are not dependencies of another installed formula
```
brew leaves
```

### Update Homebrew and fetch the newest version from GitHub
```
brew update
```

### Show formulae that have an updated version available
```
brew outdated --verbose
```

### Upgrade remaining formulae
```
brew upgrade
```

### Show dependencies for formulae
```
brew deps --installed
```

### Show the dependencies for all installed formulae as a tree
```
brew deps --installed --tree
```

### See what other installed formulae use it as a dependency
```
brew uses --installed formulae
```

### Uninstall formulae and all their older versions
```
brew remove --force formulae
```

### Show what will be removed by cleanup command, but do not actually remove anything
```
brew cleanup -ns
```

### Clean the "Cellar" removing any older versions of installed formulae and clearing old downloads from the Homebrew download-cache. Additionally, scrub the cache, removing downloads for even the latest versions of formula, which are downloaded, but not installed
```
brew cleanup -s
```
