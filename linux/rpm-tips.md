# RPM Tips

## Show files in a rpm package

```
rpm2cpio foo.rpm | cpio -t
```

## Extract files from a rpm package

```
rpm2cpio foo.rpm | cpio -id
```