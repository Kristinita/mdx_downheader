# Header Downgrader Extension for Python Markdown.

When working with markdown files, sometimes you need to "downgrade" your headings for stying purposes. A good case scenario for this is using markdown with static site generators, for example, Pelican.

Given a piece of markdown like this:

```md
# This is header 1
## This is header 2
```

This will generate the following HTML:

```html
<h1>This is header 1</h1>
<h2>This is header 2</h2>
```

With this extension enabled we obtain this instead:

```html
<h2>This is header 1</h2>
<h3>This is header 2</h3>
```

Easy!

## How to install

Tested with Python 2.7 and Python 3.5.1

It requires the Python Markdown package, tested with Markdown 2.6.5

## Usage

Directly from python
```python
from markdown import markdown
text = '# hello world'
markdown(text, ['mdx_downheader',]
```

From the command line
```
echo '# hello world' > test.md
python -m markdown -o html5 -x 'mdx_downheader' -f test.html test.md
```

*Note*: Some static site generators, like pelican, can use markdown extensions. You just need to install the pip package and provide the name of the markdown extension (in this case the name is simply 'mdx_downheader'). Follow the instructions for your case.