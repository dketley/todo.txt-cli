# todo.txt filters

Here are a couple of filters for use with [todo.txt](http://todotxt.org/).
* `colorNotes` - colours 'note:' tags green. These tags are expected to be generated by the note extension at (https://github.com/mgarrido/todo.txt-cli/tree/note/todo.actions.d).
* `multiFilter` - use if you want to combine multiple filters at once. I use it with `colorNotes` and [`futureTasks`](https://github.com/FND/todo.txt-cli/blob/extensions/futureTasks).

## How to use

`multiFilter` relies on a new environment variable defined in the `todo.txt` config.

* Set the old `TODOTXT_FINAL_FILTER` to the location of the `multiFilter` filter
* Use `TODOTXT_FINAL_FILTER_LIST` to define the filters you wish to use. They will be called in the order they are defined in the config. See below.
```
export TODOTXT_FINAL_FILTER='~/.todo.actions.d/filters/multiFilter'

# TODOTXT_FINAL_FILTER_LIST will, combined with setting TODOTXT_FINAL_FILTER
# to multiFilter, use multiple filters on the output in the order defined.
TODOTXT_FINAL_FILTER_LIST='~/.todo.actions.d/filters/futureTasks'
TODOTXT_FINAL_FILTER_LIST+='|~/.todo.actions.d/filters/colorNotes'
export TODOTXT_FINAL_FILTER_LIST
```
