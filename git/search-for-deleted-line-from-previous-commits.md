# Search for Deleted Line from Previous Commits

refs. https://ja.stackoverflow.com/questions/21361/git%E3%81%A7%E8%A1%8C%E3%81%8C%E5%89%8A%E9%99%A4%E3%81%95%E3%82%8C%E3%81%9F%E3%82%B3%E3%83%9F%E3%83%83%E3%83%88%E7%95%AA%E5%8F%B7%E3%82%92%E7%9F%A5%E3%82%8B%E6%96%B9%E6%B3%95 (in Japanese)

If you want to search for some deleted lines from previous commits in some git repository, one way below may be a good way to do it.

```
git log -p -S '<deleted strings> <file path>'
```

e.g.

```
$ git log --help
...
       -S<string>
           Look for differences that change the number of occurrences of the specified string (i.e. addition/deletion) in a file. Intended for the scripter's use.

           It is useful when you're looking for an exact block of code (like a struct), and want to know the history of that block since it first came into being: use the feature
           iteratively to feed the interesting block in the preimage back into -S, and keep going until you get the very first version of the block.
...
```