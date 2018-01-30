# RPM Tips

## Official RPM repository

### old versions

- http://vault.centos.org
- https://koji.fedoraproject.org/koji/

## Show files in a rpm package

```
rpm2cpio foo.rpm | cpio -t
```

## Extract files from a rpm package

```
rpm2cpio foo.rpm | cpio -id
```

## Show information of rpm which is installed

```
rpm -qi foo.rpm
```

## Show information of rpm which is not installed

```
rpm -qip foo.rpm
```