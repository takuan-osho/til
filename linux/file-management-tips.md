# File Management Tips

## Delete files whose date are older than some date

Make use of `find`'s `-newer` option, negative operand (`\!`) and xargs

```
find ./*.buffer \! -newer ./some-file.buffer | xargs rm
```

### Reference

- http://mikio.github.io/article/2014/03/15_find-date-del.html (in Japanese)