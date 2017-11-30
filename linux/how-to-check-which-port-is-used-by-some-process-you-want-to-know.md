# How to check which port is used by some process you want to know

Here is the list of useful commands.

refs.

- http://blog.livedoor.jp/sonots/archives/32637678.html (in Japanese)

## `lsof` command

```
$ sudo lsof -n -P -p [PID] | grep TCP
```

## `netstat` command

```
sudo netstat -anp | grep [PID]
```