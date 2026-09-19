GERMAN VOCABULARY TRAINER
==========================

This version does NOT need hosting or a local web server.

1. Keep this folder structure:

   german_vocab_trainer_no_hosting/
   ├── index.html
   └── lists/
       ├── animals.js
       ├── food.js
       ├── travel.js
       └── school.js

2. Double-click index.html.

3. Choose a list.

4. Each game has 40 questions.

5. Each question has 6 English answers.

6. Correct answer = +1 point.
   Wrong answer = 0 points.

ADDING YOUR OWN LIST
====================

Create a new file inside the "lists" folder, for example:

lists/my_list.js

Put this inside:

window.vocabularyLists = window.vocabularyLists || [];

window.vocabularyLists.push({
  name: "My List",
  words: [
    ["Hund", "Dog"],
    ["Katze", "Cat"],
    ["Haus", "House"],
    ["Buch", "Book"],
    ["Wasser", "Water"],
    ["Auto", "Car"]
  ]
});

Then open index.html and add this line with the other list scripts:

<script src="lists/my_list.js"></script>

Important:
- A list needs at least 6 words so the game can make 6 answer choices.
- You can use 20 words, 50 words, 100 words, etc.
- The game always asks 40 questions.
- Words are selected randomly, so words can repeat during a 40-question game.

WHY JAVASCRIPT FILES INSTEAD OF TXT?
====================================

A normal browser page opened directly with file:// cannot reliably use fetch()
to automatically read neighboring TXT files because of browser security rules.

External JavaScript files work when index.html is opened directly, so this
version gives you separate external files without needing hosting.
