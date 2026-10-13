# Tests

The tests are in `test/board.test.js`. This page tells you how to run the tests. It also gives the checks that each test does.

## Run the tests

Run the tests from the root of the repository:

```bash
node --test
```

Node and Google Chrome, as the `google-chrome` command, are necessary. The tests open the page in headless Chrome with a new profile, and delete the profile at the end. Thus, they do not change the board in your browser. They do not install a package or download data from the internet. They were run with Node 22.

## The checks in each test

The list follows the sequence of the tests in the file.

- `a save keeps the parts the page does not know`: it makes sure that, when the page saves a board, it keeps the parts of the board that it does not know.

- `the first load moves the board and leaves a sign`: it makes sure that, when the page loads for the first time, it moves the board from `personal.board.v1` to `personal.board.v2`. It also makes sure that the page puts a sign in `personal.board.v1`.

- `a board card steps in by its tab and edits by its name`: it makes sure that a board card shows only its name and a count, for example `3 of 9 done`. It also makes sure that the tab opens the board, and that you can double-click the name to change the text of the card.

- `a name in backticks shows as code on its card and in the heading`: it makes sure that a name in backticks shows as code on its board card and in the heading.

- `a drop on the middle of a card asks where the card goes`: it makes sure that, when you drop a card on the middle of a different card, the menu shows all three buttons. It also makes sure that each button moves the card correctly, and that Escape keeps the card at its initial position.

- `a drop on the head of a deck adds to it without asking`: it makes sure that, when you drop a card on the head of a deck, the card goes to the top of the deck. It also makes sure that no menu opens.

- `a place button shows only where pin and low rules let a card land`: it makes sure that the two Place buttons show only where pins and levels let the card go directly above or below.

- `a file dropped on a card or a note shows as a chip`: it makes sure that a file that you drop on a card or a note shows as a chip with its name and file size. It also makes sure that a board card shows its files only in its notes window.

- `the card menu and the clip on a note attach a chosen file`: it makes sure that **Attach a file** in the menu of a card attaches a file from the file picker. It also makes sure that the clip on a note does the same.

- `a chip opens or downloads its file and its cross removes it`: it makes sure that, when you click a chip, a text file opens in a new tab and a different file downloads with its name. It also makes sure that the cross removes a file, and that **Undo** puts the file on the card again.

- `export carries the files in a zip and import brings them back`: it downloads a board and one card with files as zips. It then reads each zip with **Import** into a browser that has no files, and opens a file there.

- `send by gmail downloads one zip and names the files`: it makes sure that **Send this card by Gmail** downloads one zip. It also makes sure that the menu of the card tells you to drag the file onto the message. It then makes sure that the message gives the names of the files, and does not tell you that the file is attached.

- `a zip holds a folder for each card and note that has files`: it makes sure that a zip holds a folder for each card and note that has files. It also makes sure that, if two folders or two files have the same name, the second gets a number.

- `a card or a board with no files downloads as plain JSON`: it makes sure that a card or a board with no files downloads as a JSON file, not as a zip.

- `import reads a zip that another program packed again`: it makes the card zip again, as a different program can do, with compressed files in one more folder. It then makes sure that **Import** reads the zip.

- `a card import adds the card without asking`: it makes sure that **Import** of one card puts the card on the board and does not ask first.

- `opening the page clears stored files that no card holds`: it makes sure that, when the page opens, it deletes each file in the database that no card holds. It also makes sure that the page keeps the other files. These include the files on cards, on notes, in boards and in parts of the board that the page does not know.

- `a clean-up in another tab keeps the files that ctrl z can reach`: in tab 1, it removes a file from a card and deletes a different card with a file. It also puts in the database a file that no card holds. It then opens the board in tab 2, and makes sure that tab 2 deletes only that file. It then makes sure that, after two Ctrl+Z in tab 1, the two files are on the board again. Last, it does two Ctrl+Y and reloads tab 1, and makes sure that the two files go.

- `the card menu puts the gmail note under its row and delete last`: it makes sure that, in the menu of a card, the instruction to drag the file is directly below **Send this card by Gmail**. It also makes sure that **Delete** is the last row.

- `a list item moved by its grip stays in its list with the items under it`: it makes sure that, when you drag a list item by its grip, the item and its nested items move in the list. It also makes sure that a nested item stays below its item, and that the card does not move.

- `a moved item leaves the numbers of a numbered list in place`: it makes sure that, when an item moves in a numbered list, the numbers stay in their positions. It also makes sure of this in a callout.

- `only the item under the pointer shows a grip and its words drag the card`: it makes sure that only the item that the pointer is on shows its grip. It also makes sure that the card moves when you drag the words of an item. It then makes sure that a checkbox changes to done when you click it.

- `the lists in the notes window move as they do on a card`: it makes sure that the lists in a note, and in the head of the notes window, move as they do on a card.

- `a box shows a bar for x, ticks green for y, crosses red for n, words too`: it makes sure that `x` and `X` show a flat bar on a clay box, and that `y` and `Y` show a tick on a green box with green words. It also makes sure that `n` and `N` show a cross on a red box with red words, and that an open box under a crossed box keeps its colour.

- `an x box strikes its words with a line fainter than the words`: it makes sure that `x` and `X` draw a line through the words of their item, and that the line is lighter than the words. It also makes sure that `y`, `n`, an open box, and an open box nested under an `x` box show no line.

- `a card with a crossed box is not done in its deck`: it makes sure that a card with `y` or `Y` boxes is done in its deck. It also makes sure that a card with a crossed box is not done, and stays above the done cards.

- `a click turns a box from open to x to y to n and back to open`: it makes sure that four clicks change an open box to `[x]`, then to `[y]`, then to `[n]`, then to `[ ]`. It also makes sure that a click changes `[X]` to `[y]`, `[y]` and `[Y]` to `[n]`, and `[N]` to `[ ]`.

- `a picture pasted in the edit box shows in the card text`: it makes sure that a picture that you paste in the box for the text of a card goes to the position of the cursor. It also makes sure that the picture shows in the card with no chip, and that a second `image.png` becomes `image (2).png`.

- `a picture dropped on a card or in its edit box lands in the text`: it makes sure that a picture that you drop on a card goes to the end of its text. It also makes sure that a different file stays a chip. It then makes sure that a picture that you drop in the box goes where you drop it.

- `a picture pasted in the box for a new card or note comes with it`: it pastes a picture in three boxes: for a new card, for a new note and for the text of a note. It then makes sure that each picture stays with the text when you save it. It also makes sure that Escape discards the picture.

- `an image chip shows as a picture only while the text names it`: it makes sure that an attached picture stays a chip until the text gives its name. It also makes sure that the picture opens when you click it, and that the chip shows again when you remove the mark.

- `ctrl z takes back each change and ctrl y brings it back`: it makes two changes, then makes sure that each Ctrl+Z takes back one change and that each Ctrl+Y brings one back. It also makes sure that a key press with no step left changes nothing. It then makes sure that a new change after Ctrl+Z stops Ctrl+Y.

- `ctrl z reaches back one hundred changes and no further`: it adds 101 cards, then presses Ctrl+Z 101 times. It makes sure that one card stays.

- `ctrl z takes back a palette click and marks the palette it restores`: it makes sure that Ctrl+Z takes back a click on a palette, and that the panel marks the palette that comes back. It also makes sure that Ctrl+Y brings back the click.

- `ctrl z and ctrl y open the board where the change was made`: it changes a card inside a board and goes back to the Mother Board. It then makes sure that Ctrl+Z, and later Ctrl+Y, opens that board and changes the card there.

- `the toast undo and ctrl z take back the same delete`: it makes sure that Ctrl+Z takes back a delete and closes the toast, and that Ctrl+Y deletes the card again. It also makes sure that a different change closes the toast, and that Ctrl+Y brings back a delete that **Undo** took back.

- `ctrl z in a box leaves the board alone`: it makes sure that Ctrl+Z in the box for the text of a card, and in the box for a new card, does not change the board.

- `a change in another tab clears the steps of this tab`: it makes a change in tab 1 and a change in tab 2. It then makes sure that Ctrl+Z in tab 1 changes nothing, and that Ctrl+Z in tab 2 takes back the change of tab 2.

- `a fold is no step and ctrl z leaves the folds alone`: it changes the level of a card and then folds a deck. It makes sure that Ctrl+Z takes back the level and keeps the fold, and that Ctrl+Y does the same. It then unfolds the deck and makes sure that Ctrl+Z keeps the deck open.

The tests examine the checksum of each file that they read from a zip. For more information, refer to [behaviour.md](behaviour.md#storage).
