# Behaviour

The full behaviour of the board. The README keeps the short version.

## Cards

**+ add to backlog**, or the same button at the top of another column, writes a new card, above the rest of the stack. Ctrl+Enter saves the card. Enter makes a new line. Escape cancels.

**burst**, at the end of the row inside the box, decides what a saved card leaves behind. Off, the box closes once the card is in. On, it stays open and empty, ready for the next one. The switch is in the box, so it is there only while you are adding. One setting serves every box on the page, including the ones for notes and decks, and the board remembers it. It starts off.

**≡** on a card opens the menu. The menu holds **Pin to top**, **Turn into a board**, **Attach a file**, **Download this card**, **Send this card by Gmail** and, last and in red, **Delete**. Escape or a click outside closes the menu. **Delete** removes the card in one press. A note carries a bin and a clip, with no menu. Files, below, has the clip.

**A double click** on a card opens its text in a box. This is the one way to write the text, and a checkbox is the one thing that a single click changes. The same keys apply. A single click does nothing else, and a double click on a link or a button does what that link or button does. A note behaves in the same way.

**The date** on a card is the day it was written. Hold the pointer on the date and the exact time shows, down to the second. A note and a card in a deck show theirs in the same way.

**Drag** moves a card within a column or to another column. A drop on the middle of another card asks first, in a small menu. On the head of a deck, a drop puts the card in the deck and does not ask. Decks, below, has the rest. A drag that starts on the grip of an item of a list moves the item, not the card. Moving items, below, has the rest.

**Delete** removes a card from the board, and the bin on a note removes the note from its card. On the head of a deck, **Delete** removes the deck and every card in it. None of these asks first. **clear column** empties Accomplished and asks first. All three show a toast with an **Undo**. **Undo** in the toast is the same as Ctrl+Z. Undo, below, has the rest.

## Undo

**Ctrl+Z** takes back the last change to the board. **Ctrl+Y** brings back the last change that Ctrl+Z took back. Each press is one step. A step is each change that the board saves, except a fold: a new card or note, a change of text, a drag, a click on a checkbox, a pin, a level, a deck, a file, a delete, an import or a palette. Ctrl+Z and Ctrl+Y keep each deck folded or open, as it is when you press the key.

- The tab keeps the last 100 steps. Ctrl+Z goes no further back than that.
- A new change after Ctrl+Z removes the steps that Ctrl+Y could bring back.
- If the step is in a different board, Ctrl+Z and Ctrl+Y open that board, so you see the change.
- In a box where you write, Ctrl+Z and Ctrl+Y work on the text in the box, as the browser does. They do not change the board.
- **Undo** in the toast is the same as one Ctrl+Z, so Ctrl+Y brings back the delete. The toast goes when you press Ctrl+Z or make a different change.
- The steps are in the memory of the tab. A reload or a close of the tab removes them.
- When a different tab changes the board, this tab removes its steps. Thus Ctrl+Z cannot remove the work of the other tab.

## What the card text reads

**Backticks** mark inline code. `` `npm test` `` shows as a monospace chip. The card keeps the backticks, so you see them again when you edit the card. A chip must hold text and stay on one line. A single backtick therefore stays a backtick.

**Links**: the board finds links in the text of a card. Two shapes work: a bare `https://...` and `[what it is](https://...)`. The second shape is for an address that is too long to read on a card. It shows the words and keeps the address behind them. In the second shape the address can hold spaces, so `[plan](file:///home/alex/My Docs/plan.pdf)` works. A bare address ends at the first space. A `mailto:` address and a `file://` address are also links. An address that starts with `www.` is a link too, bare or in the second shape, and the board opens it with `https://` in front. A path that starts with `/`, such as `/home/alex/dotfiles`, is a link to that file or folder, bare or in the second shape. A bare path must start the text or follow a space. A link opens in a new tab. A folder opens as a list of what it holds. A file opens in the browser if the browser can show it, and otherwise the browser downloads a copy of it. No link opens a program, because a page cannot start one.

Nothing else is a link. A `javascript:` address is not a link. An address inside backticks is code, not a link. The card keeps the text you typed, so you see it again when you edit the card.

**Markdown**: the board reads some of the Markdown marks. A mark must hold text and stay on one line. The card keeps the marks you typed, so you see them again when you edit the card.

- Inside a line, `**bold**`, `*italic*` and `~~struck through~~` mark the words between them. Bold and italic need asterisks. The board does not read the underscore as a mark, so a name such as `max_speed` stays as it is.
- At the head of a line, `#` to `######` make a heading, `>` makes a quote, and `-`, `*` or `+` make a list. `1.` or `1)` makes a numbered list, which counts from the first number you write. Three or more of `-`, `*` or `_` alone on a line make a divider across the card.
- An item nests under the item above it when its line starts at least two spaces, or one tab, further in than that item. Lists nest to any depth, and a numbered list and a bulleted list nest in each other. A line that starts with `>` nests in the same way, as a quote under the words of the item, so a callout can sit under an item too. An indented line that is not an item or a quote joins the item that it sits under, as more of its words. A line that starts with `#` or a fence, with fewer than four spaces before it, still starts its own block and closes the list. So does a line that starts with `>` and is not far enough in to nest.
- A blank line closes a paragraph, a quote or a list, with all the lists nested in it. The board reads no other Markdown. There are no tables, and the Markdown mark for a picture is not read. Pictures, below, has the mark that the board reads.

**Callouts**: a quote whose first line is a noun in brackets is a callout. `> [!warning]` opens one, and the lines below it are its text. The head takes the mark and the colour of the noun. Words after the noun on that line become the head instead, so `> [!question] Do we keep the fourth column?` names itself. A word the board does not know is not a callout, and those lines stay the quote that they were.

The nouns are the ones Obsidian has: `note`, `abstract` (`summary`, `tldr`), `info`, `todo`, `tip` (`hint`, `important`), `success` (`check`, `done`), `question` (`help`, `faq`), `warning` (`attention`), `failure` (`fail`, `missing`), `danger` (`caution`, `error`), `bug`, `example` and `quote` (`cite`). A noun in brackets reads in any case. Obsidian reads `caution` as a warning. Here it is a danger, in red.

The text of a callout is card text, so it takes lists, boxes, fences and a heading. Only the first line of a quote can name a callout. The board does not fold a callout, so a `+` or a `-` after the brackets is read and dropped.

**Checkboxes**: at the head of a bulleted item, `- [ ]` makes an open box. `- [x]`, `- [X]`, `- [y]` and `- [Y]` make a box that is done. `- [n]` and `- [N]` make a box with a cross, and that box is not done. A click on a box changes it and writes the change into the text of the card. So the state of a box is text, and it travels with Export and Import as the rest of the card does.

- Only a space, `x`, `X`, `y`, `Y`, `n` or `N` goes between the brackets, and a space follows them. So `- [-] read` is an item with the characters that you typed. A numbered item takes no box.
- `x` or `X` draws a white bar on a clay box. It draws a line through the words of the item, in a lighter grey than the words. The line does not go through the items nested under it. `y` or `Y` draws a tick on a green box, and `n` or `N` a cross on a red box.
- A click on an open box writes `[x]`. A click on an `x` or `X` box writes `[y]`, a click on a `y` or `Y` box writes `[n]`, and a click on a crossed box writes `[ ]`. So four clicks go from open to bar to tick to cross and back to open.
- An item with a box carries no bullet. The box stands where the bullet would be, so one list holds both kinds of item and the words after them line up.
- A box that is done shows its words in grey, and the plain items and quotes nested under it also. A `y` or `Y` box shows them in faint green, and a crossed box in faint red. An open box nested under a done or crossed box keeps its colour, so work that is not finished still shows. A click changes one box only, and never the boxes under it.
- A note takes boxes too. The head of the notes window shows the text of its card, and a box there is the same box as the one on the card.

**Moving items**: put the pointer on an item of a list, and a grip of six dots shows to its left. Press the grip and move the mouse, and the item fades and a line shows where it will land. Release the button, and the item goes to that line. The board writes the new order into the text of the card, so the order travels with Export and Import as the rest of the card does.

- Only the grip moves the item. A drag that starts on the words, a link or the box of an item drags the card, as it always did. On a nested item, only the grip of the item under the pointer shows.
- An item moves only among the items of its own list, at its own depth. The items nested under it move with it. A nested item stays under the item that holds it, so a drop above the first item or below the last puts it first or last in its own list.
- In a numbered list the numbers stay in place and the words move. So `1. alpha`, `2. beta`, `3. gamma`, with `gamma` moved to the top, becomes `1. gamma`, `2. alpha`, `3. beta`.
- A list in a callout, in a note or in the head of the notes window moves in the same way.

**Fences** mark a block of code. Three or more backticks alone on a line open the block, and a line of at least as many backticks closes it. The lines between them show as you typed them, in one monospace box. The board reads no mark inside a block, so a `#` or an address there stays as plain characters.

A blank line inside a block closes nothing. A word after the opening fence names a language. The board reads no language and deletes the word. A fence that the card never closes is not a fence. Its backticks stay backticks, and the board reads the lines below it in the usual way.

## Notes

**Notes** open in a small window in the middle of the page. The words next to the date of a card open that window. A card with notes gives their count there. A card with no notes shows **add note** while the pointer is on the card. A click there opens the window, with the box for the first note. Notes are cards themselves. The same editing, backticks, links and dates apply to them, and a drag reorders them. They carry a bin of their own, with an Undo.

The window shows all of its notes at once. It becomes as tall as the notes need, and the page behind it scrolls when the window is taller than the screen. Only the window that opens against a card, for an edit of the card text, keeps its notes in a box that scrolls. The window uses the colour of the column that holds the card. Escape or a click outside closes the window. A click counts as outside only when it starts and ends there, so a selection dragged out of the text leaves the window open.

## Files

A card or a note can carry files. A file shows as a chip under the text, with its name and its size, such as `arm.png 210 KB`. A picture that the text names shows as a picture instead. Pictures, below, has the rest.

- **Drop** a file from your desktop or file manager on a card or a note. While the file is over the card, a ring goes round the card with the word **attach**. One drop can bring more than one file. A picture file becomes a picture at the end of the text. Every other file becomes a chip.
- **Attach a file**, in the menu of a card, opens the file picker. A note has no menu, so the clip next to its bin does the same.
- A click on a chip opens the file in a new tab if the browser can show it: a picture, a PDF, plain text, audio or video. Every other file downloads under its own name. An SVG picture and an HTML page download too, because in a tab of their own they could run code with access to the board.
- The cross on a chip removes the file from the card. The toast says `File removed` and offers **Undo**.
- The notes window shows the files of its card under the text of the card.
- A board card does not show its files. Its notes window shows them. A file that lands on a board card opens that window, so you see where the file went.
- On a low card, the chips fade with the rest of the card.
- A delete takes the files of the card with it, and Undo brings them back.

## Pictures

A picture shows inside the text of a card or a note. The text holds a mark with the name of the picture, such as `![[image.png]]`, and the picture shows where the mark is. The picture is a file on the card, so it travels with Export and Import as the other files do.

- **Paste**: copy a picture, for example with **Copy Image** in the browser, and press Ctrl+V in a box where you write text. These are the box for a new card or a new note, the box that a double click opens, and the box for the text of a card in the notes window. The mark goes where the cursor is. The board keeps a copy of the picture, not a link to the web page.
- **Drop** a picture file from your desktop or file manager on one of these boxes, and the mark goes where you drop it. On a card or a note that is not open for editing, the mark goes at the end of the text, on a line of its own.
- A picture comes with the text when you save it. Escape discards the pictures that you pasted or dropped since the box opened.
- A pasted picture has the name `image.png`. A name that the card already has gets a number, such as `image (2).png`.
- A picture is never wider than the card, and never larger than its own size. A click opens it at full size in a new tab.
- Take the mark out of the text, and the picture shows as a chip again. The cross on the chip removes the file, with Undo. Write the mark of a chip into the text, such as `![[arm.png]]`, and the chip shows as a picture.
- A mark that names no file on the card stays as the characters you typed.
- **Attach a file** attaches a picture as a chip. Pictures that were on cards before this change stay chips until you write their mark.
- A board card shows only its name, so its pictures show in its notes window.

## Pins

**Pin to top** holds a card at the head of its column. A pinned card shows a pin next to its date, and its menu offers **Unpin**. A card that is not pinned cannot pass a pinned one, so a drag stops at that line and so does the line that shows where the card lands. A new pin goes to the foot of the pinned cards. Taking a pin off puts the card at the head of the rest. Every column takes pins. A note takes none, and a card in a deck takes none. A pin on the head of a deck holds the whole deck.

## Levels

A card in Backlog is **normal** or **low**, and only Backlog has the two. Backlog fills faster than it empties and not everything in it is next, so low is where the rest of it waits. A card is written normal, and the low ones gather at the foot of the column.

- The mark after the date says which, and a press on it turns the card over. The mark is a sun, a ring with eight spokes around it. On a normal card it is in the colour of the column. On a low one it is grey. The colour is the whole of the difference. There is no menu row for this: the mark is the whole of it.
- A low card is drawn flat, on the colour of the column, and everything written on it fades most of the way towards the card. Words, code chips, fenced blocks, callouts, list markers, rules, tick boxes, pictures, the date and the note count all fade together, so the card recedes as one thing. The mark, the menu button and the **board** tab of a board card do not fade, because they are how you act on the card. It is put off, not gone.
- The mark of a low card stays while the pointer is away, because that is why the card is at the foot of the column. On a normal card the mark appears when the pointer is on the card, the way **add note** does. On a screen with no pointer, every card shows its mark.
- Making a card low sends it to the head of the low cards, and making it normal again puts it at the foot of the ones above. A card cannot be pinned and low at once, so making it low takes the pin off, and pinning it brings it up. A pinned card shows the pin and no mark.
- A drag moves a card and never changes its level, except into or out of a deck. A card that joins a deck loses its level, and a card taken out of a low deck arrives normal. The three groups keep their order, so a card stops at the line its own group ends at, and so does the line that shows where it lands.
- A low card dragged to another column arrives normal, because no other column has levels.
- The count at the head of Backlog reads **5+3**: five normal cards and three low ones. The line of counts below the header reads the same way. With nothing low, one number. Every count on the board counts each card of a deck, the head included, so a head with 14 cards under it counts 15, and a low deck adds all 15 to the low number.
- The mark of a normal card takes the colour of the column, darkened as far as it must go to hold 3 to 1 against the fill of that column, and no further. Half of the colours in the book are too pale to be seen on a card as they are, and a little under half need nothing done.

## Decks

A deck is a card with cards of its own under it. The card on top is the head. It keeps its own text, notes and menu, and its text names the deck. The cards of the deck hang under the head at the full width of the column, and a thin line in the margin ties each one to the head. A deck goes one level deep, so a card in a deck cannot hold cards.

- A drop on another card can make a deck. While you drag, the board shows which of two things a drop will do. Near the top or bottom edge of a card, a line appears between the cards, and a drop moves the card to that line, as it always did. Over the middle half of a card, a ring goes round that card with the words **make a deck**. A drop there asks first. It opens a small menu below that card, with up to three buttons.
- **Create deck** makes the deck. The card inside the ring becomes the head, and keeps its text, notes, pin and level. The dragged card goes under it.
- **Place above this card** puts the dragged card directly above the card inside the ring, and **Place below this card** puts it directly below. Pinned cards stay at the top of the column, and low cards stay at the foot of Backlog. So the two Place buttons show only when the dragged card can land there. For example, over a pinned card, a card that is not pinned gets **Place below this card** only, and only on the last pinned card. Escape or a click outside closes the menu, and the dragged card stays where it was before the drag.
- Over the head of a deck, everything below its top quarter shows the ring with **add to deck**, and a drop puts the card at the top of the deck.
- **+ add to deck**, right under the head, writes a new card at the top of the deck. It works as the box at the top of a column does, burst included.
- Over the cards of a deck, only the line shows. A drop there puts the card into the deck at that line, and never makes a deck inside a deck. A drag also takes a card out of a deck to any place in a column. A card that joins a deck loses its pin and its level. A drag on the head moves the whole deck. A head never shows the ring, because a deck cannot go into another deck, so a head dropped on the cards of a deck lands in the column next to that deck. When the last card leaves a deck, the head is a plain card again.
- Under its text, the head shows a bar and a count such as `3 of 14 done`. A card in a deck is done when it has at least one box and every box on it is done. A card with no box is never done, and a card with a crossed box is not done.
- Done cards go to the foot of the deck, below a line such as `3 done`. The arrow before the count folds the done cards away, and a second press shows them again. A new deck shows its done cards. The fold is on the head, so it travels with Export and shows in another tab.
- The arrow before the date of the head folds the deck to its head, and a second press unfolds it. The fold is on the head, so it travels with Export and shows in another tab.
- A card in a deck is a full card, with a date, notes and a menu. Its menu holds **Attach a file**, **Download this card**, **Send this card by Gmail** and **Delete**. It takes no pin and no level.
- **Delete** on the head deletes the deck and every card in it, in one press. The toast says how many cards went, and offers **Undo**.
- A pin or a level on the head acts on the whole deck. A low deck in Backlog fades as one and gathers with the low cards.
- Every column takes decks.
- A card that holds a board takes no part in a deck. Boards, below, has the rest.

## Boards

A card can hold a board of its own. Such a card is a board card. The top board is the **Mother Board**. There, the heading of the page and the browser tab read **Mother Board**. Every board is the same as the Mother Board, and boards nest to any depth.

- **Turn into a board** is in the menu of every card in a column, below **Pin to top**. A card in a deck does not have it, and a card that already holds a board does not have it. A press gives the card a board of its own, with the same four columns.
- The text of the card names the board. The name is the first line of the text, cut to 60 letters. The page takes off any heading, quote, bullet, number or checkbox mark at the front of that line. The Gmail subject of a card uses the same rule. Backticks in the name show as a code chip on the card and in the heading, as they do in card text. The browser tab and the Gmail subject show the backticks as you typed them.
- The head of a deck can turn into a board too. The cards of its deck go to Backlog on the new board, in the same order, and the head becomes a plain board card. The card keeps its text, notes, pin and level.
- A board card has a **board** tab on its top edge, at the left, with an arrow after the word. A band in the colours of the four columns of its board goes along the top of the card. The colours come from the palette of that board, so each board looks different from outside. Each part of the band is as wide as the count of its column, and a column with no cards has no part. On a board with no cards, the four parts are equal and pale.
- A board card shows only its name, in the type of the column headings. The rest of the text stays in the card, and shows when you edit the card. A double click on the name opens the card to edit, as on every card. The files of the card do not show on it. Its notes window shows them.
- Under the name, a line such as `3 of 9 done` gives the count of Accomplished against the count of Backlog, Now and Accomplished together. Remember is not in the count, because its cards are not tasks. A board with no cards shows `empty board`.
- On a low card, the band, the name and the line fade with the rest of the card. The tab does not fade.
- The tab steps into the board. The heading becomes a trail, such as `Mother Board / Work / Robot arm`. Each name before the last is a button that steps back out to that board. The Back and Forward buttons of the browser step out and in too. The address keeps the place after `#`, so a reload or a bookmark opens the same board. The browser tab shows the name of the board you are in.
- Inside a board, everything acts on that board. This covers new cards, drags, pins, levels, decks and notes. It also covers the counts at the head of each column and the line of counts below the header. So do **clear column**, the toast and **Undo**, **Export** and **Import**.
- A board card counts as one card in the counts of the board that holds it. The cards inside its board count only inside that board.
- A board card takes no part in a deck. It cannot join a deck and it cannot head one. When you drag a board card over a card, or a card over a board card, no ring shows. The line shows, and a drop moves the card to that line. A board card dropped on the cards of a deck lands in the column next to that deck, as a head does.
- A drop never puts a card into another board. To move a card to another board, use **Download this card**, open the other board and **Import** the file there.
- **Delete** on a board card deletes the card and its whole board in one press. It does not ask first. The toast says how many cards went, such as `Board of 12 cards deleted`, and offers **Undo**. The number is the count of that board, with each board inside it counted as one card.
- **Undo** puts the card back in the board it came from, even if you stepped into another board before you pressed it. It also opens that board. This holds for every delete: **Undo** returns a card, a note, a deck or a cleared column to the board it came from.

## Export and Import

**Export** opens a menu with two ways out. **Download the board** writes the board you are in to a JSON file, with every board inside it and every file on their cards and notes. **Send the board by Gmail** writes the same file and opens a new Gmail message in another tab, with a subject and a body that name the file. The file is not attached to the message. No page can hand Gmail a file: the Gmail compose address carries the recipient, the subject and the body and nothing else, and the mail protocols behind a plain mail link carry no attachment either. An attachment would need Google's mail interface, a signed-in account and the board served from a web address, which the board is not. So the message opens beside a downloaded file and you drag the file onto it. The menu says so under the two choices.

If the browser blocks the new tab, the file is downloaded all the same.

A board or a card that carries files downloads as a zip, so an export is still one file. The zip holds the JSON, as `board.json` or `card.json`, and a folder for each card and note that has files. A folder takes the first line of its card or note as its name, cut to 60 letters, and holds the files under their own names. A character that a name cannot hold, such as `/` or `:`, becomes `-`. When two folders, or two files in one folder, have the same name, the second one gets a number, as in `run (2).log`. So someone without a board can open the zip and read the files. A board or a card with no files downloads as the same JSON file as before.

**Import** reads a board or a single card, from a JSON file or from a zip, and puts the files back into the browser. It also reads a zip that you unpacked and packed again with another program. Such a program usually compresses the files, and often puts everything inside one more folder. Import reads the files in either case.

**Download this card** writes one card to a file, with its notes and its files. On the head of a deck it writes the whole deck, with every card and note in it. On a board card it writes the card with its whole board. The file passes the card to someone else. **Send this card by Gmail** writes the same file and opens a message for it, as the board does. The menu of the card says so right under **Send this card by Gmail**, above **Delete**. The message names the files on the card and on its notes, as in `Its files come with it: arm.png, run.log.` The files on the cards of a deck and inside a board are in the zip too, but the message does not name them. The subject carries the first line of the card and then its id, as in `Personal board card: pay the bill (ctest456)`. The first line is the text of the line with any heading, quote, bullet, number or checkbox mark taken off the front, cut to 60 letters. The id is the one the card holds on this board. Import gives an arriving card a fresh id, so the id in the subject names the card here and not the card there. Import adds the card to the board you are in and does not change the other cards. It does not ask first. The card goes to the column that it was in. If there is no such column, the card goes to Backlog. A board card arrives with its board, and the cards inside that board keep their ids. The card arrives as a new card. But if the board you are in already holds a card with the same text and the same date and time, Import skips the card. It looks at the cards in each column and at the cards in each deck. The toast then says `That card is already on the board.` and offers no **Undo**. So if you import the same file twice, you get one card. A card with the same text and a different date still arrives.

Export and Import use two shapes. A whole board is `{"cols": ...}` and replaces the board you are in. The boards above it and beside it do not change. One card is `{"card": ..., "col": ...}` and joins the board you are in. A deck is one card, with its cards in the list `cards` of the head. A board card is one card, with its board inside it. Import reads the fields in the file to find which of the two shapes it is. In a zip, the JSON also holds `blobs`, which gives the place of each file in the zip.

## Storage

The board is in `localStorage`, in the key `personal.board.v2`. The Mother Board holds everything, and each board inside it is on its card. The key belongs to one browser on one machine. Export moves a board to another machine. Two tabs on the same board stay in sync.

The palette of each board is on that board. A Mother Board saved before boards kept a palette of their own takes its palette from the old keys `personal.palette.v1` and `personal.palturn.v1`. The page no longer writes those keys.

The board keeps the notes of a card on the card, so a card is whole on its own. Notes travel with Export and Import. A delete removes the notes of the card too. Undo returns the card and the notes. A board saved before notes existed opens with no notes.

The files are not in `localStorage`, which holds about 5 MB for the whole page. They are in the IndexedDB database `personal.files.v1` of the browser, which has room for gigabytes. The card or note keeps a list of its files, with the name, the type and the size of each, and the list travels with the card. When the page opens, it deletes from the database every file that the saved board does not name. So a file that you remove, and the files of a card that you delete, stay until the next time a page opens. A file in a part of the board that the page does not know stays too, because the saved board still names it. While Ctrl+Z or Ctrl+Y in a tab can bring files back, those files stay, whichever tab opens the page. The tab keeps a note of them in `localStorage`, under a key that starts with `personal.undo.v1.`. While it is open, the tab also holds a browser lock with the same name. When a page opens, it removes each note that has no lock, because the tab of that note is closed. A board saved before files existed opens with no files.

The cards of a deck are on its head in the same way, so a deck travels whole. A delete of the head removes its cards too, and Undo returns them. A board saved before decks existed opens with no decks.

A pin is on the card too, so it travels with Export and Import as the notes do. A board saved before pins existed opens with none.

The level is on the card in the same way, and travels with it. A board saved before levels existed opens with every card normal. A card that arrives both pinned and low keeps the pin, and a card that arrives low in a column with no levels arrives normal.

Low was called swept, when a card was put under a carpet in the footer of Backlog instead of being made low. A board saved then opens with those cards low, in the same order, at the same foot of the same column.

The page keeps every part of a board that it does not know, and saves that part back as it found it. This covers an unknown field on a card, a note, a card in a deck or a board, and a whole unknown column. The page also keeps cards that hang under a card in a deck. It keeps a board under a note or under a card in a deck too. It does not show the cards under a card in a deck, or a board under a note or under a card in a deck. So a copy of the page never drops what a newer copy wrote.

What the page knows, it treats by its own rules. For example, a card that joins a deck still loses its pin.

A copy of the page from before this rule drops what it does not know. For example, a copy from before decks drops the cards of every deck the next time it saves. That is why the board moved from `personal.board.v1` to `personal.board.v2`. Such a copy reads only the old key, so it never sees the board in the new key and cannot overwrite it.

At the first load, the page moves the board from `personal.board.v1`, or from the older `todo.board.v1` or `backlog.board.v1`, into `personal.board.v2`, and deletes the older keys. It then writes a sign into `personal.board.v1`: a board with one card in Remember that reads `This copy of the page is out of date. Your board is safe. Open the newest copy of the page to see it. What you add here stays in this copy.` A copy that still calls that column Waiting for shows the same card there. What you add in an old copy stays in the old key, and the page does not read that key again. Import also reads older JSON exports.

The Remember column was called Waiting for and was stored under `waiting`. A board saved under that name opens with those cards in Remember.

## Palette

**Palette** changes the colours of Backlog, Now and Accomplished on the board you are in. You select a family, then a combination from that family. The panel stays open while you try the combinations. A click outside or Escape closes the panel.

Click the combination that is on the board again and Backlog and Now swap their colours. Accomplished keeps its green. A second click gives the order in the book again. The bars in the panel show the order that the board has.

Each board keeps its own palette and its own swap of Backlog and Now. A new board starts with the palette of the board it is made in. The palette is on the board, so it travels with Export. **Download this card** on a board card carries the palette of its board. When you import a whole board, a file that holds a palette brings it. A file that holds none keeps the palette of the board that it replaces. The icon of the browser tab shows the palette of the board you are in.

The colour combinations come from Sanzo Wada's *A Dictionary of Color Combinations*. The board groups the combinations into families by their main colour, and keeps three colours from each combination. Backlog, Now and Accomplished get one colour each. The palette gives no colour to Remember.

Green is the colour of Accomplished, so a combination is here only if one of its colours is a green. That green goes to Accomplished and stays there. Where a combination holds more than one green, the deepest of them goes there.

The book holds 108 combinations of four colours. 24 of them are here, in eight families. The rest are not, either because they hold no green, or because no three of their colours stay apart at the strength the columns use, so two columns would read as one.

## The Remember column

**Remember** holds what you must keep in mind: a card that someone else has to move, and a note to yourself that is not work at all. A hairline separates this column from the other three. No palette gives this column a colour. It uses the page background. Its cards are white and its text is grey.

## The head of the page

The small arrow on the left side of the line of counts hides the head of the page. The line of counts is the line below the header, for example `5 to remember · 4+3 in backlog · 6 going on now · 5 accomplished`. The arrow hides the small label `personal / board`, the heading, the hint line, **Palette**, and the **Import** and **Export** buttons. **tips** does not hide. It moves onto the line of counts.

The arrow points up while the head shows, and down while the head is hidden. When you click it again, the head of the page shows again. The page records your selection in `localStorage`, in the key `personal.fold.v1`.

In a board, the names in the heading let you go back to the boards above. While the head of the page is hidden, use the Back button of the browser, or show the head again.

## tips

**tips**, the button above **Palette** on the right of the header, opens a window with what the board does and what it reads. It holds two sections so far. The callouts come first: every noun, the mark it draws and the colour it takes, with the nouns that share a colour on one bar. Burst comes below a short rule: the switch as the add box shows it, off and on, next to what each state leaves behind. The window takes no colour from the palette, because tips belong to the board and not to a column. Escape or a click outside closes it.

## Build mark

Under the board, on the right, is the short hash of the commit this copy of the page came from. It links to that commit on GitHub. The page ships with a plain link to the repository in its place, and `build.js` puts the hash there once it is written.

The hooks in `hooks/` write `build.js` after the fact, because a commit cannot hold its own hash. It is not in the repository. A copy kept there could only ever name the commit before the one you are reading, and it would leave the page changed in the working tree after every commit. `.gitignore` keeps it out, so the tree stays clean.

All the hooks run the same script, `hooks/write-build-mark`, which reads HEAD and writes `build.js`. `post-commit` covers a commit, `post-merge` a merge and so a pull that merges, `post-rewrite` a rebase and an amend, and `post-checkout` a clone, a checkout and a switch. Nothing has to stand aside any more. The file the hooks touch is not one git is watching, so writing it in the middle of a rebase or a checkout of single files disturbs neither.

The page loads `build.js` with a plain script tag. It cannot be a module. A module is fetched under the rules for cross origin requests, which a browser refuses on a `file://` address, and that is how the page is usually opened.

A download of the repository as a zip carries no history, so the hooks have nothing to read. GitHub writes those zips with `git archive`, which fills in the commit hash where `.gitattributes` asks for it, so `stamp.js` comes out of the zip already naming the commit the zip was cut from. In a clone `stamp.js` still holds the placeholder and steps aside, and `build.js` speaks for the working tree instead. A copy of the page with neither shows the plain link, and `index.html` on its own is still the whole board.

A clone can only write the mark if the hooks are already on when the working tree is written, which means `git clone -c core.hooksPath=hooks`. A plain clone shows the link to the repository until the next commit, merge or checkout after `git config core.hooksPath hooks`.
