# Personal board

This is a board for one person in one HTML file, with the four columns Remember, Backlog, Now and Accomplished.

![The board has cards in each column. A pinned card is at the top of Remember, and Remember and Backlog contain callouts. Backlog holds a board card with its band of colours, a checklist with a picture and a card with a file. Two low cards are at the bottom of Backlog. A deck in Now holds three cards below its head, and one of these cards is done. The cards show nested checklists, a code chip, a fenced block and a link.](doc/board.png)

## Start

Open `index.html` in a browser. You can open it from a `file://` address. You do not install or build anything, and the board does not use a server. The board stays in this browser only. To keep a copy, or to move the board to a different machine, use **Export**.

The line below the heading shows `drag cards between columns · double-click a card to edit · hover for more options`. The **tips** button opens a window about callouts and the **burst** switch.

For more information, refer to [doc/behaviour.md](doc/behaviour.md#tips).

## Cards

To write a new card, click **+ add to backlog** or the same button in a different column. Ctrl+Enter saves the card, Enter starts a new line and Escape cancels. When **burst** is on, the box stays open for the next card. Double-click a card to change its text. Drag a card to move it in its column or to a different column.

**≡** on a card opens its menu. The menu holds **Pin to top**, **Turn into a board**, **Attach a file**, **Download this card** and **Send this card by Gmail**. **Delete** is the last item, in red. **Delete** removes the card immediately, and the toast shows an **Undo** button. **clear column** removes all the cards from Accomplished, but first it shows **clear** and **cancel**. To see the accurate time at which you wrote a card, hold the pointer on its date.

For more information, refer to [doc/behaviour.md](doc/behaviour.md#cards).

## Undo

Ctrl+Z takes back the last change to the board, and Ctrl+Y brings it back. A change is anything that the board saves, for example a new card, a drag, a tick, a delete or a palette. The tab keeps the last 100 changes until you reload or close it. If the change is in a different board, the page opens that board. In a box where you write, Ctrl+Z takes back your typing and does not change the board. **Undo** in the toast is the same as one Ctrl+Z.

For more information, refer to [doc/behaviour.md](doc/behaviour.md#undo).

## Card text

The board shows Markdown in the text of a card: inline code, fenced blocks, links, headings, quotes, callouts, nested lists, checkboxes, dividers and pictures. A quote that starts with a callout word in brackets is a callout, for example `> [!warning]`. **tips** shows all the callout words.

Click an open checkbox to fill it, click again to give it a tick, click a third time to cross it, and click a fourth time to make it open. `[x]` fills the box and draws a light grey line through the words. `[y]` shows a tick on green with green words, and `[n]` a cross on red with red words. Capital letters do the same. To move an item in its list, put the pointer on the item. Then drag the grip on the left side of the item.

For more information, refer to [doc/behaviour.md](doc/behaviour.md#what-the-card-text-reads).

## Notes

A card can have notes. The words after the date of a card show the number of notes. Click these words to open the notes window. On a card with no notes, **add note** shows while the pointer is on the card. The window shows all the notes of the card at the same time.

For more information, refer to [doc/behaviour.md](doc/behaviour.md#notes).

## Files

A card or a note can hold files. Drop a file on it from your desktop. You can also use **Attach a file** in the menu of a card, or the clip on a note. A file shows as a chip with its name and its file size, but a picture in the text shows as a picture. When you click the chip, the browser opens the file or downloads it. The cross on the chip removes the file.

For more information, refer to [doc/behaviour.md](doc/behaviour.md#files).

## Pictures

A picture shows in the text of a card or a note. To add a picture, copy it. Then press Ctrl+V in a box where you write. You can also drop a picture file on the box or on a card. The text then gets a mark at the position of the picture, for example `![[image.png]]`. If you remove the mark, the picture shows as a chip again.

For more information, refer to [doc/behaviour.md](doc/behaviour.md#pictures).

## Pins

**Pin to top**, in the menu of a card, holds the card at the top of its column. A pinned card shows a pin before its date, and cards that are not pinned cannot go above it. **Unpin**, in the same menu, removes the pin.

For more information, refer to [doc/behaviour.md](doc/behaviour.md#pins).

## Low cards in Backlog

A card in Backlog has one of two levels, **normal** or **low**. The sun after the date shows the level. On a normal card, the sun shows only while the pointer is on the card. Click the sun to change the level.

Low cards are dim and collect at the bottom of the column. The count at the top of Backlog shows the two levels. For example, `5+3` is five normal cards and three low cards.

For more information, refer to [doc/behaviour.md](doc/behaviour.md#levels).

## Decks

A deck keeps cards together below a head card. If you drop a card on the middle of a different card, a small menu opens. The menu has up to three buttons: **Create deck**, **Place above this card** and **Place below this card**. If you drop the card near the top or bottom edge of a different card, the card moves and the menu does not open.

The arrow before the date of the head folds the deck. A card in a deck is done when it has checkboxes and all of them are done. A crossed box is not done. Done cards go to the bottom of the deck.

For more information, refer to [doc/behaviour.md](doc/behaviour.md#decks).

## Boards

**Turn into a board**, in the menu of a card, gives the card a board with the same four columns. The **board** tab on the card opens that board. Click a name in the heading to go back to that board. The top board is the **Mother Board**.

For more information, refer to [doc/behaviour.md](doc/behaviour.md#boards).

## Palette

**Palette** changes the colours of Backlog, Now and Accomplished on the board that you are in. Each board keeps its palette. If you click the combination of the board again, Backlog and Now interchange their colours. The colours are from Sanzo Wada's *A Dictionary of Color Combinations*.

For more information, refer to [doc/behaviour.md](doc/behaviour.md#palette).

## Export and Import

**Export** opens a menu with two items. **Download the board** writes the board that you are in, with all the boards in it, to a file. The file is JSON, or a zip with the JSON and the files if the board holds files. **Send the board by Gmail** downloads the same file and opens a new message, but it cannot attach the file. Drag the file onto the message. **Import** reads a board, which replaces the board that you are in, or one card, which goes into it.

For more information, refer to [doc/behaviour.md](doc/behaviour.md#export-and-import).

## The Remember column

**Remember** holds cards that are not your tasks, for example a card that a different person must move, or a note for you.

For more information, refer to [doc/behaviour.md](doc/behaviour.md#the-remember-column).

## Hide the head of the page

The small arrow on the left side of the line of counts hides the head of the page. Click the arrow again to show the head. **tips** stays on the line of counts.

For more information, refer to [doc/behaviour.md](doc/behaviour.md#the-head-of-the-page).

## Where the browser keeps your board

The board is in `localStorage`, in the key `personal.board.v2`. The files on its cards are in the IndexedDB database `personal.files.v1`. The two stay in this browser on this machine. With **Export** and **Import**, you can move the board and its files to a different machine.

For more information, refer to [doc/behaviour.md](doc/behaviour.md#storage).

## Development

### Build mark

Below the board is the short hash of the commit of this copy of the page. The hooks in `hooks/` write it. To enable the hooks, clone with this command:

```bash
git clone -c core.hooksPath=hooks https://github.com/li9i/personal-board
```

If you cloned without the hooks, `git config core.hooksPath hooks` enables them. The mark then shows after the next commit, merge or checkout.

For more information, refer to [doc/behaviour.md](doc/behaviour.md#build-mark).

### Tests

Run the tests from the root of the repository:

```bash
node --test
```

Node and Google Chrome, as the `google-chrome` command, are necessary. The tests open the page in headless Chrome with a new profile, and delete the profile at the end. Thus, they do not change the board in your browser. They do not install a package or download data from the internet. They were run with Node 22.

For a list of the tests and their checks, refer to [doc/tests.md](doc/tests.md).

## Disclaimer

`personal-board` was created by li9i and coded by Claude. What a time to be alive.
