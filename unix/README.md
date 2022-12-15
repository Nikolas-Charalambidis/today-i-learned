# Unix

## Conditions

### Is a program installed
<sup>29-11-2022, source: [StackOverflow](https://unix.stackexchange.com/a/288402/550665)</sup>

```shell
# Node.js for example
if which node > /dev/null
then
    echo "Using Node.js version: $(node -v)"
else
    echo "Node.js not installed"
    exit 1
fi
```

## Directories and files

### List the file types (estimate)
<sup>05-12-2022, source: [StackOverflow](https://superuser.com/a/1490807/776068)</sup>

```shell
find . -type f -exec file -- {} +
```
- `file` determines file type
- `-f namefile`/`--files-from namefile` specifies a particular file

### List the file sizes 
<sup>22-11-2022, source: [StackOverflow](https://stackoverflow.com/a/1019124/3764965)</sup>

```shell
du -hs .
```
- `du` displays disk usage statistics
- `-h` stands for a human readable format.
- `-s` stands for the files only (depth is 0, i. e. `-d 0`).
- By default, the `du` program recursively lists the directories.

## CURL

### Response as beautified JSON
<sup>25-11-2022, source: [StackOverflow](https://stackoverflow.com/a/32246976/3764965)</sup>

```shell
curl https://gorest.co.in/public/v2/users | python -m json.tool
```
```shell
curl https://gorest.co.in/public/v2/users | python3 -m json.tool
```

## Git

### Count changes lines between branches
<sup>25-11-2022, source: self</sup>

```shell
echo $(git diff --shortstat develop)
```
