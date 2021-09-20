# Ubuntu Errors

## When Ubuntu Login defaults to Terminal Instead of desktop:

### if there is file corrupt error message on some disk:

```
fsck /dev/sda1 -y 
```

replace sda1 with the curroupt disk number

### if it's a login loop:

issue is with shell rc files, i.e bashrc or zshrc

check if default shell is configured properly and not rerouted elsewhere

