# dojo-js_scroll

## About
Exercise for the CodingDojo's Javascript course.  See the learning platform to see how you should improve the codes. There are several bugs with the codes which are intentional. 

## My edits
### fixed last character bug
The last character of each of the fill-in-the-blank words was not appearing. That's because the array of letters was being accessed like letter_array[counter++]. The ++ increments the counter, which means in the subsequent check to see if counter == word length, it was finding thi to be true one letter too early. Simply changing this to letter_array[counter+1] and then later updating the counter fixed this. 

### fixed the space bar bug 
Cursor was not moving to the right when a space should appear. The cursor is simply the right border of the div, so with every new character the div becomes larger and therefore gives the appearance of moving to the right. However, the div does not resize from just white space. You need to use a literal space character &nbsp; to force it to resize.

### added emojis to each phrase
Created a span with id="emoji" element immediately after the fill-in-the-blank work, and changed the cursor to be the the right border of this new span. While the word is being typed, the innerHTML of #emoji is the empty string, and only when the word is finished does the emoji get added. Needed to create a div to contain the whole phrase to make sure the positioning on the page didn't change.

### added a pause once the phrase completes
I want there to be little extra time after the phrase is finished before changing to the next phrase. It doesn't seep easy to implement a sleep() function (see [here](stackoverflow.com/questions/951021/what-is-the-javascript-version-of-sleep)), so instead I relied on the setInterval() function that we already are using. For a few iteration of the function I return early, and this mimics a sleep. The sleep period however, can only be a multiple of the function interval. 

View live page here: https://ampetr89.github.io/dojo-wf-js_scroll
