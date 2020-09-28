This page is for the APIs we've found as well as the APIs we're looking for.
## Looking for APIs that provide the following:
-Random Excerpts (e.g. books)

-Random Words

-Song Lyrics

-Code

-Audio

## Potential APIs:
### Random Excerpts:

### Random Words:
https://developer.wordnik.com/ -also provides audio pronunciations (not yet tested)

Not an API, but a Python module

URL: https://pypi.org/project/RandomWords/

To download:
pip install RandomWords

To use:
from random_words import RandomWords
rw = RandomWords()
word = rw.random_word()
print(word) # e.g. "asterisk" or "maintainability"

Not an API, but a Python module

URL: https://pypi.org/project/Random-Word-Generator/

To download:
pip install Random-Word-Generator

To use:
from RandomWordGenerator import RandomWord

# Creating a random word object
rw = RandomWord(max_word_size=10,
                constant_word_size=True,
                include_digits=False,
                special_chars=r"@_!#$%^&*()<>?/\|}{~:",
                include_special_chars=False)

print(rw.generate()) # doesn't generate actual words but letter combinations

Could be used when helping users type certain letter combinations that they're weak at

### Song Lyrics:

### Code:

### Quotes:

-Quotes API (from Rapid API, tested using Python module requests)

URL: https://rapidapi.com/martin.svoboda/api/quotes15

It provides random quotes.

It also provides them in various languages such as German, Italian and French.


Random Quotes API: http://api.quotable.io/random
https://github.com/lukePeavey/quotable
-Good if we want to deal with real sentences


https://random-word-api.herokuapp.com/home
-here is a random word api (good if we dont want jibberish

here is an eexample: https://random-word-api.herokuapp.com/word?number=50

Audio:

- WordnikAPI

It's possible to play the audio, but it must be written to a file. Maybe we could let users input words and generating an mp3 file to their computer and then they can play it and type to type it?

### Other:

-Numbers API (from Rapid API, tested using Python module requests)

URL: https://rapidapi.com/divad12/api/numbers-1

We could do a numbers mode maybe? Where the user just types numbers.

-Chuck Norris API (from Rapid API, tested using Python module requests)

URL: https://rapidapi.com/matchilling/api/chuck-norris

It's not specifically just letters, but it provides jokes that the user could potentially type.

-Jokes API (from Rapid API, testing using Python module requests)

URL: https://rapidapi.com/orthosie/api/jokes

Can give users the option of picking a category of joke to type or just randomly select the category for them.

(For the Chuck Norris API and the Jokes API, we could also remove punctuation before giving it to the user to just get the letters and words.)






