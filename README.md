FixFinder
=========

FixFinder aims to resolve that most annoying bug in Mavericks which extends the file name column beyond the width of the Finder window. Viewing file attributes requires horizontal scrolling skills and a good bit of patience.

![Missing Columns in Finder](http://d.pr/i/iHhQ+ "Finder Screenshot")

Credit goes to Christian Varga who solved this with a bit of Applescript wizardry:
http://christianvarga.com/fix-finder-name-column-width-bug-osx-mavericks/

My only contribution is to convert into an Alfred Workflow for easy use.

Requirements
----
* Alfred 2.0 + Powerpack
* Learn more at: http://www.alfredapp.com/

Usage
----

1. Double-click on the .workflow file
2. Invoke script using **CMD + R** or the keyword "**fixfinder**"
3. Enjoy restored sanity

Applescript command in detail
----

```sh
tell application "Finder"
	tell the front Finder window
		-- get the current bounds of the finder window
		set b to the bounds
		-- create a really wide window
		set the bounds to {item 1 of b, item 2 of b, 3000, item 4 of b}
		-- set window back to its original size
		set the bounds to b
	end tell
end tell
```

Version
----

1.0


License
----

MIT