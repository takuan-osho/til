## Error Handling

refs. https://dev.realworldocaml.org/07-error-handling.html

There are two basi approaches for reporting errors in OCaml:

* Error-aware return types
* Exceptions


### Error-Aware Return Types

```
# open Core_kernel;;
# List.find;;
- : 'a list -> f:('a -> bool) -> 'a option = <fun>
```

```
# List.find[1;2;3] ~f:(fun x -> x >= 2);;
- : int option = Some 2

# List.find[1;2;3] ~f:(fun x -> x >= 10);;
- : int option = None
```