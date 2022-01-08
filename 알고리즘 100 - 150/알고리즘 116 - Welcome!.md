# Q.
Your start-up's BA has told marketing that your website has a large audience in Scandinavia and surrounding countries. Marketing thinks it would be great to welcome visitors to the site in their own language. Luckily you already use an API that detects the user's location, so this is an easy win.

The Task
Think of a way to store the languages as a database (eg an object). The languages are listed below so you can copy and paste!
Write a 'welcome' function that takes a parameter 'language' (always a string), and returns a greeting - if you have it in your database. It should default to English if the language is not in the database, or in the event of an invalid input.
The Database
english: 'Welcome',
czech: 'Vitejte',
danish: 'Velkomst',
dutch: 'Welkom',
estonian: 'Tere tulemast',
finnish: 'Tervetuloa',
flemish: 'Welgekomen',
french: 'Bienvenue',
german: 'Willkommen',
irish: 'Failte',
italian: 'Benvenuto',
latvian: 'Gaidits',
lithuanian: 'Laukiamas',
polish: 'Witamy',
spanish: 'Bienvenido',
swedish: 'Valkommen',
welsh: 'Croeso'
Possible invalid inputs include:

IP_ADDRESS_INVALID - not a valid ipv4 or ipv6 ip address
IP_ADDRESS_NOT_FOUND - ip address not in the database
IP_ADDRESS_REQUIRED - no ip address was supplied

# A)
```c
#define IP_ADDRESS_INVALID   "not a valid ipv4 or ipv6 ip address"
#define IP_ADDRESS_NOT_FOUND "ip address not in the database"
#define IP_ADDRESS_REQUIRED  "no ip address was supplied"

struct row
{
  const char * lang;
  const char * word;
};

struct row table[] = {{"english"   , "Welcome"},
                      {"czech"     , "Vitejte"},
                      {"danish"    , "Velkomst"},
                      {"dutch"     , "Welkom"},
                      {"estonian"  , "Tere tulemast"},
                      {"finnish"   , "Tervetuloa"},
                      {"flemish"   , "Welgekomen"},
                      {"french"    , "Bienvenue"},
                      {"german"    , "Willkommen"},
                      {"irish"     , "Failte"},
                      {"italian"   , "Benvenuto"},
                      {"latvian"   , "Gaidits"},
                      {"lithuanian", "Laukiamas"},
                      {"polish"    , "Witamy"},
                      {"spanish"   , "Bienvenido"},
                      {"swedish"   , "Valkommen"},
                      {"welsh"     , "Croeso"}};
  

const char* greet(char *language) 
{
  if (!language)
    return table[0].word;

  if (strcmp(language, IP_ADDRESS_INVALID) == 0)
    return IP_ADDRESS_INVALID;
  
  if (strcmp(language, IP_ADDRESS_NOT_FOUND) == 0)
    return IP_ADDRESS_NOT_FOUND;
    
  if (strcmp(language, IP_ADDRESS_REQUIRED) == 0)
    return IP_ADDRESS_REQUIRED;

  int nRows = sizeof(table)/sizeof(struct row);
  for (int i = 0; i < nRows; ++i)
  {
    if (strcmp(language, table[i].lang) == 0)
      return table[i].word;
  }
  return table[0].word;
}
