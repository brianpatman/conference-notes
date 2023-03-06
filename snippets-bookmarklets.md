# Scripting in Firefox/Chrome

## Bookmarklets

Bookmarklets are just bookmarks, but with Javascript code instead of a page to open. To create them, you just create a new bookmark and then embed your Javascript code into that one line. Start off your JavaScript code like so:

	javascript: (() => { 
		// your code here 
	})();

You might want to edit the bookmarklet in another editor before pasting it into the bookmark "URL" field, because that field only lets you write on a single line.


## Snippets
You can run snippets in Chrome and Firefox.

### Chrome
In Chrome, you can find the "Snippets" menu under "Sources > Snippets". Here you can put pieces of JavaScript code, name them, and have them run when you want them to. 

Run them by clicking on the snippet you desire to run and using "Ctrl + Enter" to activate them

### Firefox
Firefox doesn't have the same sort of Snippets behavior as Chrome, but they do have multi-line JavaScript input in their console.

To activate this multi-line JS input, go to your console and, where you can type in a current line, look all hte way to the right of the window for an "split view" icon. Click this and the multi-line JS editor will open to the left of the current console.

Like Chrome, you can run these snippets with "Ctrl+Enter", but you cannot save them to easily run over and over. You can load previous snippets by moving through the history, though.

