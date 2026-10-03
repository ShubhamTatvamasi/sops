# sops

Install `sops`:
```bash
brew install sops
```

Generate a new key:
```bash
age-keygen -o ~/.config/sops/age/keys.txt
```

Setup a secrets directory:
```bash
mkdir -p ~/secrets
```

store your secrets on a file:
```bash
vim ~/secrets/cloud.env
```
