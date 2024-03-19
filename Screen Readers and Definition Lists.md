# Screen Readers and Definition Lists
#a11y

I created a simple test file  ([Definition List](https://codepen.io/tjameswhite/full/KKBaNaM))  using sample mark up from Mozilla’s mdn web docs ([<dl>: The Description List element - HTML: HyperText Markup Language | MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dl))

Tested three combinations of screen readers and browser: Jaws & Edge; VoiceOver and Safari, and Chrome. All browsers and screen readers used default settings. 

The test consists of four definition list options: 
1. 1 term and 1 definition 
2. 3 terms and 1 definition
3. 1 term and 2 definitions
4. group of 4 consisting of 1 term and 1 definition each

## Jaws & Edge

Tested the four options, in order, Jaws announced the following. Tested used down arrow to progress one by one through each list. 
(Note: I have truncated the full copy for sake of brevity.) 

1. “Definition list of 1 items. Firefox. A free … . List end”
2. “Definition list of 3 items. Firefox. Mozilla Firefox. Fx. A free … . List end.”
3. “Definition list of 1 items. Firefox. A free … . The Red Panda … . List end.”
4. “Definition list of 4 items. Name. Godzilla. Born. 1952. Birthplace. Japan. Color. Green. List end.”

Observation: 
- Jaws announces “items”(plural) even when there is only 1 item.
## Voiceover and Safari

Tested same order and manner as Jaws. Tested by moving through the lists one item at a time. 

1. “Description list 1 item. Firefox 1 of 2. A free … . 2 of 2. End of description list.”
2. “Description list 3 items. Firefox 1 of 4. Mozilla Firefox 2 of 4. FX 3 of 4. A free … . 4 of 4. End of description list.”
3. “Description list 2 items. Firefox 1 of 3. A free … . 2 of 3. The Red Panda … . 3 of 3. End of description list.”
4. “Description list 4 items. Name 1 of 8. Godzilla 2 of 8. Born 3 of 8. 1952 4 of 8. Birthplace 5 of 8. Japan 6 of 8. Color 7 of 8. Green 8 of 8. End of description list”

Observations:
- Voiceover refers to definition lists as “description list”.
- Voiceover considers the ‘length’ of the list based on the number of `dt` (term) elements. 
- Despite the number of items being determined by the number of `dt` elements, all elements end up being counted. 

## Voiceover and Chrome

This was an accidental test. I started testing and realized I was in Chrome. I decided to finish the test anyway. Same test procedure as Safari.

1. “Definition list 2 items. Firefox. A free … . 2 of 2. End of definition list.”
2. “Definition list 4 items. Firefox 1 of 3. Mozilla Firefox 2 of 3. FX. A free … . 4 of 4. End of definition list.”
3. “Definition list 3 items. Firefox. A free … . 2 of 3. The Red Panda … . 3 of 3. End of definition list.”
4. Definition list 8 items. Name 1 of 4. Godzilla 2 of 8. Born 2 of 4. 1952 4 of 8. Birthplace 4 of 8. Japan 6 of 8. Color. Green 8 of 8. End of definition list.”

Observations:
- Voiceover did not enumerate all items, skipping one in each list. In the 1st and 3rd tests, after Firefox VO did not announce “1 of”. Test 2 it did not announce “3 of 4” after FX. And the final test did not announce “4 of 4” after Green 
- VO in Chrome appears to partially distinguish terms (`dt`) from definitions (`dd`). In the second test, for example, while announcing 4 items, VO then announced the terms as “1 of 3” etc. The same can pattern emerges with the final test where there are 4 pairs of terms and definitions. VO announces 8 total items, and counts the terms as “x of 4”. 
