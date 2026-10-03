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

Store your secrets on a file:
```bash
vim ~/secrets/cloud.env
```

```
DIGITALOCEAN_TOKEN=dop_v1_xxxxxxxxx
```

---

Get your public Key:
```bash
AGE_PUBLIC_KEY=$(age-keygen -y ~/.config/sops/age/keys.txt)
```

Encrypt your secret:
```bash
sops encrypt \
  --age "$AGE_PUBLIC_KEY" \
  ~/secrets/cloud.env > ~/secrets/cloud.env.enc
```


