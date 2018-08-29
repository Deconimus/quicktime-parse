## Quicktime-Parse

This is a fork from [kzahel's quicktime-parse](https://github.com/kzahel/quicktime-parse).

The goals were:

* store the metadata inside a dictionary after parsing instead of just printing the results
* speed up parsing by not reading the actual video data

### How to use

Here's a brief code example that showcases how to use the script:

```python
import quicktimeparse

qt = quicktimeparse.Mov("path/to/file.mov")
qt.parse()

#retrieve the creation date as a string
date = qt.metadata["creation date"]

#traverse all key-value pairs of the metadata
for key in qt.metadata.keys():
  print(key+": "+str(qt.metadata[key]))
```

Note that all metadata key's are converted to lower-case and stripped of leading and trailing spaces.
