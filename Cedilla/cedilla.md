# Simple fix for those who are using a keyboard with the US layout and cannot type the "ç".

1. Create a hidden file in your home directory  (**~**)   called ".XCompose".
```bash
vim .XCompose
```
2. Copy and paste the following:

```bash
<dead_acute> <c>     : "ç"
<dead_acute> <C>     : "Ç"
```

3. **wq** to write and quit

4. Done.

# Optional in order to make it work on KDE

1. Create a hidden file in your home directory  (**~**)   called ".XCompose".
```bash
vim .XCompose
```
2. Copy and paste the following:

```bash
include "%L"

<dead_acute> <c>     : "ç"
<dead_acute> <C>     : "Ç"
```

3. **wq** to write and quit

4. Done.