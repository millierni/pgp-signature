# PGP-Signature
## VERIFY PGP SIGNATURE & ADD IT TO PACMAN KEY
  - Import the key  
    - If the public key is known  
      Replace `{public_key}` with the public key
      ```
      PUBLIC_KEY={public_key}
      ```
      ```
      gpg --keyserver hkp://pgp.mit.edu --recv-keys $PUBLIC_KEY
      ```
    - If the public key is not known  
      Replace `Magic Unicorn` and `magic@unicorn.pw` with the name and email associated with the signature
      ```
      gpg --keyserver hkp://pgp.mit.edu --search-keys "Magic Unicorn <magic@unicorn.pw>
      ```
      Replace `{public_key}` with the public key
      ```
      PUBLIC_KEY={public_key}
      ```
  
  
  >```
  >gpg --export -a $PUBLIC_KEY > $PUBLIC_KEY.asc
  >sudo pacman-key --add ./$PUBLIC_KEY.asc
  >sudo pacman-key --lsign-key $PUBLIC_KEY
  >sudo pacman-key --refresh-keys
  >```
