# What Was I Thinking?

Hello! If you're reading this, thank you for caring about this project! This markdown file is to act as kind of a brain dump, where I can talk about some of the things I've learned, practiced, and struggled with when making this project.

## Motivation

You should be able to learn something from all projects, so that's what I wanted to for this. My goal was to make something that I had no idea how to make. Who makes a python library and makes it available on PyPI? Crazy people... so I had to try.

Besides wanting to learn something new, I wanted to make something that's actually useful. I think one of the biggest use of AI for companies is having it interact with customers and talk to them. In order for the LLM to talk to a customer, it has to have the customer talk to it too. This causes the customer to input text, which gets turned into tokens, which (usually) goes into the pockets of Big AI by using their APIs instead of self-hosting. This can eat away at costs for a business, so I decided to make a solution where they can wrap the customer prompt in this library's main function, `compress()`, and be able to reduce some of the tokens being used. Even if only a little bit gets minimized, that's still something to be saved.

## Practice Makes Perfect

This was a project with a whole lot of learning, so most things I did was a learning experience. The only thing that was somewhat not, was practicing Python. As a result of big data science libraries like scikit-learn, xgboost, pandas, numpy, matplotlib, etc., I don't get a lot of practice with actually doing raw Python. One of the goals of mine for this project was to reinforce the basics of Python, which I feel I did a pretty good job at. I also used Git in the command line a lot, so that helps with practicing good software engineering behavior (I say as someone who is not a software engineer).

## What I Learned

Did I learn? Yes. Was it so much? Also yes. This was a project for real, so things I learned include:

- **Uploading to PyPI:** I have never made a library before, and so I have never uploaded a library on PyPI. It was a good experience learning the requirements for having a library that passes all the checks needed so that other people can install and use my library.
- **Pytest:** I have done unit testing in C before, but I've never had a real reason to do a *formal* unit test in Python, until now! It was interesting learning about how Pytest works, and doing all the things needed for successful tests like creating a tests folder with a file that has "tests_" in the front of the name. It was also interesting making functions that test possible edge cases for the functions within the program, and creating assert statements that raise errors if they don't match correctly. It made sure that I had functions that worked properly under a number of different tests. Plus, I love it when a command in the terminal is only 1 word!
- **Creating a library:** It was interesting needing to have a src folder with a folder in it with the project name, and an `__init.py__` file in it that imports the functions so they're easier to use. I've never needed that kind of file before, so it was an interesting process to learn.
- **pyproject.toml:** I knew of `setup.py` and `requirements.txt`, but this project had me learn that the modern way to set up a project is with a `pyproject.toml` file, which has your project metadata and other helpful information for specific tasks. It was interesting neededing to have the project name the exact same as the project folder in the src folder so that when I built the project with twine it would actually compile correctly. I also like that it makes it easier to install dependencies, such as doing `pip install .` instead of using a requirements file.
- **GitHub Actions:** I used GitHub actions to run Pytest when I release a new version of the library on Github, and then if it passes the tests, it will publish it onto PyPI automatically. That makes it super easy to just worry about what's on the GitHub instead of going back and forth between the two repositories. I have never used GitHub Actions before, but I know how powerful a deployment pipeline is.

## Struggles

This is the first project that I have done where I went for more of a structured setup, so I had to do a lot of research on what exactly is a pyproject file, what is required in it, why should you have a src file, how to set up unit tests, etc. Usually, my projects have their own structures to it, but this time I needed it to be more specific because it was going on PyPI. I really like the idea of the pyproject file, and now because of this whole library experience, I will always do testing, always include a pyproject.toml, and always try to have a standardized file structure.

## For The Future

I would like to make the actual `compress()` function reduce tokens a bit more strategically by changing up what gets removed from the prompt. I would also like to hopefully make it work with prompts that include code and math, where it only focuses on minimizing the tokens of the questions involved, not the math or coding given.

My absolute main goal is to rework this to be built with uv. The library `uv` is exploding like crazy, and I believe it has a build built in, so you don't need twine to do it. Also, you can add dependencies using uv and have it auto-update the dependencies in the pyprojects file, which is nice. Overall, I believe uv will overtake pip at some point, so it would be best to start adopting it now, and this project would be the perfect starting place to do so.
