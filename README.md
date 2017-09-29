# diffkit-boring-work

Testing Diffkit to break boring work :P

## Run

* `diffkit-app.jar` creates sink.diff file

```
$ java -jar ../diffkit-app.jar -planfiles test9.plan.xml
```

* Gem
    * Generate OUTPUT.html, and see this

```
$ jruby -S bundle install --path vendor/bundle
$ jruby -S bundle exec daff.rb diff --output diff.csv test9.lhs.csv test9.rhs.csv
$ jruby -S bundle exec daff.rb render --output OUTPUT.html diff.csv
```

* daff options

```
daff can produce and apply tabular diffs.
Call as:
  daff [--color] [--no-color] [--output OUTPUT.csv] a.csv b.csv
  daff [--output OUTPUT.html] a.csv b.csv
  daff [--output OUTPUT.csv] parent.csv a.csv b.csv
  daff [--output OUTPUT.ndjson] a.ndjson b.ndjson
  daff [--www] a.csv b.csv
  daff patch [--inplace] [--output OUTPUT.csv] a.csv patch.csv
  daff merge [--inplace] [--output OUTPUT.csv] parent.csv a.csv b.csv
  daff trim [--output OUTPUT.csv] source.csv
  daff render [--output OUTPUT.html] diff.csv
  daff copy in.csv out.tsv
  daff in.csv
  daff git
  daff version

The --inplace option to patch and merge will result in modification of a.csv.

If you need more control, here is the full list of flags:
  daff diff [--output OUTPUT.csv] [--context NUM] [--all] [--act ACT] a.csv b.csv
     --act ACT:     show only a certain kind of change (update, insert, delete)
     --all:         do not prune unchanged rows or columns
     --all-rows:    do not prune unchanged rows
     --all-columns: do not prune unchanged columns
     --color:       highlight changes with terminal colors (default in terminals)
     --context NUM: show NUM rows of context
     --id:          specify column to use as primary key (repeat for multi-column key)
     --ignore:      specify column to ignore completely (can repeat)
     --index:       include row/columns numbers from original tables
     --input-format [csv|tsv|ssv|psv|json]: set format to expect for input
     --eol [crlf|lf|cr|auto]: separator between rows of csv output.
     --no-color:    make sure terminal colors are not used
     --ordered:     assume row order is meaningful (default for CSV)
     --output-format [csv|tsv|ssv|psv|json|copy|html]: set format for output
     --padding [dense|sparse|smart]: set padding method for aligning columns
     --table NAME:  compare the named table, used with SQL sources
     --unordered:   assume row order is meaningless (default for json formats)
     -w / --ignore-whitespace: ignore changes in leading/trailing whitespace
     -i / --ignore-case: ignore differences in case

  daff render [--output OUTPUT.html] [--css CSS.css] [--fragment] [--plain] diff.csv
     --css CSS.css: generate a suitable css file to go with the html
     --fragment:    generate just a html fragment rather than a page
     --plain:       do not use fancy utf8 characters to make arrows prettier
     --www:         send output to a browser
```
