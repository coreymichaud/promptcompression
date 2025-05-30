# LLM Prompt Compression

Are LLM's costing you too much in your application? This library will allow your prompts to have the minimum amount of text needed to convey what you want the LLM to do. This is perfect for prompts given by users, where they are constantly eating at your costs.

## Benefits of Minimizing Tokens

- Less tokens means more $$$ saved
- Saving on compute, which helps out the environment
- Faster LLM response time

## Install
This package is available on [PyPI](https://pypi.org/project/promptcompression/):
```
$ pip install promptcompression
```

## Usage
This is very simple to use, because it only requires a library import and a function wrapper.

You use the ```compress()``` function, which has the argument ```text``` for the input prompt, and the optional argument ```savings``` which, when True, returns a tuple of the number of tokens saved, and the ratio of tokens saved by the original tokens.

Example:
```
from promptcompression import compress

prompt, tokens, ratio = compress("Summarize this text while sounding more natural. Please do not use contractions or an em dash to be more human-like.", savings = True)

print("Compressed text:", prompt)
print("Tokens saved:", tokens)
print(f"Compression ratio: {ratio:.2f}")

>>> Compressed text: summar text sound natur pleas dont use contract em dash humanlik
>>> Tokens saved: 13
>>> Compression ratio: 0.50
```

## If you want to learn more...

... please check out the file [`markdown/WHATWASITHINKING.md`](https://github.com/coreymichaud/promptcompression/blob/main/markdown/WHATWASITHINKING.md), where I explain my process throught the project. This is located in the library's [GitHub repo](https://github.com/coreymichaud/prompt-compression).
