# gct

A git-crypt test.

## HOWTO

- create repo

- add and commit .gitattributes, e.g.
```
secret.json filter=git-crypt diff=git-crypt
```

- set up git-crypt
```
$ git-crypt init
$ git-crypt export-key ~/.gnupg/my-gct-key
```

- add and commit sensitive information
```json
{ "password": "cant_touch_this" }
```

- new cloners will need `my-gct-key` to read the encrypted files
```
$ git-crypt unlock ~/.gnupg/my-gct-key
```
