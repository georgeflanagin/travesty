# travesty
A very simple, one file, pure-Python travesty generator, with no
external dependencies. 

### About
This is a one file, simple, travesty generator. It takes a text file and 
generates a travesty that has the same statistical properties as the
input: same vocabulary, same average sentence length. Whatever you want
to measure about the input will be the same in the output. 
Outside of entertainment, the only purpose might be testing.

Note that this program is unaware of grammar, parts of speech, sentence
patterns, nor any of the other attributes of textual analysis that make 
for higher quality travesties. It is a good example of the 80/20 rule, in
that it usually produces coherent output, and the improvements that can be
made would swell the code size by more than one order of magnitude.

### Execution
```bash
python travesty.py [--size {percentage}] [--depth {int}] --input {filename}
```

The `--size` parameter defaults to `100`, meaning the travesty will be the
same size as the original. 

The `--depth` sets the chunk size for analysis/synthesis. For most texts,
something around `11` gives realistic results, `8` gets humorous, and `13+`
begins to resemble the original a little too faithfully.

The output will be a file with the same name as the input file, but with the
suffix `.new` tacked on the end.

### Testing

Feed it some input and see what happens. It is only designed to work with 
text, and makes no attempt to verify that the input file _is_ text. 

### Performance

It is a single threaded program, so the performance is entirely the domain 
of your processor's clock speed. It does not do any math, and it only does
I/O at the beginning and end to read the input and write the output. 

For the 1.2 million bytes of the copy of _Moby Dick_ at Project Gutenberg,
the total execution time was 3.29 seconds.

