# Q.
altERnaTIng cAsE <=> ALTerNAtiNG CaSe
Define String.prototype.toAlternatingCase (or a similar function/method such as to_alternating_case/toAlternatingCase/ToAlternatingCase in your selected language; see the initial solution for details) such that each lowercase letter becomes uppercase and each uppercase letter becomes lowercase. For example:

to_alternating_case("hello world"); // => "HELLO WORLD"
to_alternating_case("HELLO WORLD"); // => "hello world"
to_alternating_case("hello WORLD"); // => "HELLO world"
to_alternating_case("HeLLo WoRLD"); // => "hEllO wOrld"
to_alternating_case("12345"); // => "12345" (Non-alphabetical characters are unaffected)
to_alternating_case("1a2b3c4d5e"); // => "1A2B3C4D5E"
to_alternating_case("String.prototype.toAlternatingCase"); // => "sTRING.PROTOTYPE.TOaLTERNATINGcASE"
As usual, your function/method should be pure, i.e. it should not mutate the original string.

# A)
```c
#include <stdlib.h>

char *to_alternating_case(const char *s) 
{
  int i = 0;
  int length = 0;
  char *strcpy = 0;
  
  while (s[length])
    length++; 
  
  strcpy = malloc(length + 1);
  
  while (s[i])
  {
      if ('a' <= s[i] && s[i] <= 'z')
        strcpy[i] = s[i] - 32;
      else if ('A' <= s[i] && s[i] <= 'Z')
        strcpy[i] = s[i] + 32;
      else
        strcpy[i] = s[i];
    i++;
  }
  strcpy[i] = 0;
  return strcpy;
}
