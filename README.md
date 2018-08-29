## Quicktime-Parse

This is a fork from [kzahel's quicktime-parse](https://github.com/kzahel/quicktime-parse).

The goals were:

* store the metadata inside a dictionary after parsing instead of just printing the results
* speed up parsing by only reading relevant data (the original script used read() instead of seek() _a lot_)

Additional features:

* dynamically parse quicktime meta-tables in mdta format

### How to use

Here's a brief code example that showcases how to use the script:

```python
import quicktimeparse.parse as qtparse

qt = qtparse.Mov("path/to/file.mov")
qt.parse()

#retrieve the creation-time as a string (the actual creation time, not the file-system creation time)
date = qt.metadata["creation time"]

#traverse all key-value pairs of the metadata
for key in qt.metadata.keys():
  print(key+": "+str(qt.metadata[key]))
```

Note that all metadata key's are converted to lower-case and stripped of leading and trailing spaces.

### Installation

You can install this tool as a package via PIP:

`pip install git+"https://github.com/Deconimus/quicktime-parse.git"`
