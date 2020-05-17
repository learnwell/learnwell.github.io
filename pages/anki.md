---  

layout: page
title: Anki
permalink: /anki/  
last_modified_at: May 5, 2020
tags: [anki,filter,filtered,deck,decks]  

--- 

* Filtered Decks:
  * To capture all the cards that were due within last `n` days while excluding any cards with the `chem112` tag. Also excludes things that have been flagged red/1 or orange/1 as I personally use them to indicate cards that seem completely wrong or need  improvements.
```
# Due Today for review
is:due prop:due=0 is:review -flag:1 -flag:2

# Due within last 3 days
is:due prop:ivl<=3 -"tag:chem112" -flag:1 -flag:2

# Due within last 5 days
```





       




> Written with  [StackEdit](https://stackedit.io/).

<!--stackedit_data:
eyJoaXN0b3J5IjpbODMwMzQ3ODA1LC0xMjMwNDY3MzYxXX0=
-->