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

### List the sizes 
<sup>22-11-2022, source: [StackOverflow](https://stackoverflow.com/a/1019124/3764965)</sup>

```shell
du -hs .
```
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
