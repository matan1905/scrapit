# Scrapit
Language for web scraping

# Scrapit examples

Look at the following example 

```
SELECT a['href] FROM "http://github.com" MAP "$text"!="" PRINT "$attr['href']";
```

SELECT <Css selector> - loads the elements according to the css selector

FROM <URL> - the url chosen, multiple urls are possible: FROM "url1","url2",...,"urlN"

MAP - filter elements who doesn't pass the condition

PRINT - For each element found , Prints the following formated text

$attr['href'] - the attribute 'href' of the elements.


# Actions

PRINT "text" - prints the text , per element (used with element information usually)

SAVE "formatted text" "file name" - saves all elements information, formated, in a file

LOAD "any url" "file name" - downloads any url given to it (usually the first string is "$attr['src']" or "$attr['href']")


# Element information

$text - returns the inner text, without html

$html - save as above but including the html

$id - the id of the element(if any)

$class - the class of the element (if any)

$index - the index of the element in the select result (useful for file saving and row counting)

$element - the entire element html

$attr['attribute name'] - value of an attribute


# Map
A map function always comes before a regular action (as seen above), it will filter all unmatching elements

Conditions:

==  - check if two strings are equal

!= - check if two strings are NOT equal

LIKE - check if the first string has the second string contained in it using wildcards (in the begining,end or both)
REGEX - check if the first string matchs the second string regex

