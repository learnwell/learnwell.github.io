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
	is:due prop:ivl<=5 -"tag:chem112" -flag:1 -flag:2
	```
  * Intervals to help setup 3 different decks or filtered decks to study for upcomign tests in a repeatable fashio
	```
	# Deck for graduating cards on a Daily basis
	1m 10m 2h 10h 1d max:3d

	# Deck for graduating cards on a Weekly basis
	10m 1d 3d max:7d

	# Deck for graduating cards on a Bi-weekly basis
	10m 3d 5d 7d max:14d
	```



       




> Written with  [StackEdit](https://stackedit.io/).

<!--stackedit_data:
eyJoaXN0b3J5IjpbMzgxNzg1NDExLC0xMjMwNDY3MzYxXX0=
-->