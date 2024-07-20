# Simple fix for those who are using a keyboard with the US layout and cannot type the "ç".

1. Create a hidden file in your home directory (~/) called ".XCompose.
```bash
sudo nano .XCompose
```
2. Copy and paste the following:

```bash
<dead_acute> <c>     : "ç"
<dead_acute> <C>     : "Ç"
```

3. Ctrl + O to save it and ctrl + X to close nano.

4. Done.