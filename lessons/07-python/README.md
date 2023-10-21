# Python and the Pandas Library

I got the idea to use Vim to learn Python language.
More specifically data science.

The biggest challenge is how to load the Numpy and Pandas library

## execute simple python from vim

Here are some simple Python one line program.
```python
print('Hello Python');

a = 1; print(a);
```

$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$
$$$$$$$$ Here is the idea:
$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$
- save the line to a file /tmp/pyline.py
- execute the file using python

check the saved python file and execute it.
```bash
# review th file content
cat /tmp/pyline.py

python3 --help

# execute the file.
python3 /tmp/pyline.py
```

Set up a vim map to execute it.
```vim
" \1py means execute current line as python program
nnoremap \1py :.w! /tmp/oneline.py \| exec "!python3 /tmp/oneline.py"<CR>
```

## execute more complex multi lines Python programs

Here is a example.
```python
a = 1
b = 2
c = a + b
print(c)
```

We will use vim virtual mode to setup vim map.
```vim
" \1py means execute current line as python program
vnoremap \py :w! /tmp/simple.py \| exec "!python3 /tmp/simple.py"<CR>
```

