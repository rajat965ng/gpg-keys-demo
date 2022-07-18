I. Setup gpg home
---
    

## Set gnupg home directory
```export GNUPGHOME=$PWD/gnupg```

## Resolve permissions issue
``` chmod 700 gnupg```

## list keys
```gpg --list-keys```

## Generate Keys
```gpg --full-generate-key```

## Update key expire
```
gpg --edit-key rajatnigam89@gmail.com
list
key 0
expire
2y
save
```

## Generate revocation key
```
gpg --output revoke-rajatnigam89.asc --gen-revoke rajatnigam89@gmail.com
```

## Revoke the key
```
 gpg --import revoke-rajatnigam89.asc
```

## Verify the revoked key
```
gpg --list-keys

uid           [ revoked] Rajat Nigam <rajatnigam89@gmail.com>
```

## Export public key
```
 gpg --export --armor rajatnigam89@gmail.com
```
## Or output in a file
```
gpg --export --armor --output rajatnigam89.pub
```

## Export private key
```
gpg --output rajatnigam89@gmail --armor --export-secret-key rajatnigam89@gmail.com
```

## Example
```
echo "HEllo World !!" > myfile
```


## Encrypt file
```
gpg --encrypt --sign --armor -r rajatnigam89@gmail.com myfile
```

## Output decrypt text
```
gpg --decrypt myfile.asc
```
## Decrypt file
```
gpg myfile.asc
```


