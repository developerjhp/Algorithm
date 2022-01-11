# Q.
Sentence Smash
Write a function that takes an array of words and smashes them together into a sentence and returns the sentence. You can ignore any need to sanitize words or add punctuation, but you should add spaces between each word. Be careful, there shouldn't be a space at the beginning or the end of the sentence!

Example
['hello', 'world', 'this', 'is', 'great']  =>  'hello world this is great'
# A)
```c
#include <string.h>

char *smash(const char **words, size_t count)
{
  char *sentance = malloc(1000);
  int index = 0;
  
  for (int x = 0; x < count; x++) {
    for (int y = 0; words[x][y] != 0; y++) {
    sentance[index] = words[x][y];
    index++;
    }
    if (x + 1 != count) {
      sentance[index] = ' ';
      index++;
    }
  }
  sentance[index] = 0;
  return (sentance);
}

```
c언어나 자바스크립트나 알고리즘풀때 개똥같은건 같나보다 
