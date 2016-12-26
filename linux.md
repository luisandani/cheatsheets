# Linux CheatSheet

#### check linux distro
`$ cat /etc/*-release`

#### rename files from csv to txt
`$ for f in *.csv; do mv -- "$f" "${f%.csv}.txt"; done`

#### for loop
`$ for NUM in `seq 1 1 1000`; do touch $NUM-file.txt; done`

## TAR
```
  Compress:  tar cvJf compressed-file.tar.xz FILES
  Uncompress: tar xvf compressed-file.tar.xz PATH
```

#### disk usage
```
$ du -hs
$ du -h --max-depth=1
$ df -h
```

#### grep count lines
`$ cat /shop/logs/us/live/bob/reset-start-date-*-cron.log | grep US-1 | wc -l`

## TEXTS

#### find files containing a text (add -l to get only list of files)
`$ grep -rnw '/path/to/somewhere/' -e "pattern"`

#### replace text
`$ sed -i -- 's/var/foo/g' fileToChange`

#### Change permissions
```
sudo find . -type f -exec chmod 664 {} \;
sudo find . -type d -exec chmod 775 {} \;
```
