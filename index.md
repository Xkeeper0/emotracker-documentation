
<blockquote class="quotable">
	Throughout this documetation, direct quotes from the program author will appear like this.
</blockquote>

Welcome to the **unofficial EmoTracker documentation**! I guess! [EmoTracker](https://emotracker.net/) is a program mainly focused on tracking *randomizer* playthroughs, helping organize and visualize items, locations, and other things. It relies on *packs* created by other people for most of its functionality.


----

<blockquote class="quotable" style="margin-top: 3em;">
	At this point, if I’m being honest, it is more likely that I remove the [documentation] tab from the website.
	<br><br>
	The Discord serves as the defacto source for documentation and help.
</blockquote>

You know what they say: if you want something done right...


## Contents

@TODO hey can you add a programmatic table of contents to github pages? :')


## Pages

This section is under construction.

* [Customizing](customizing)


## Getting Started

When you first open the program, you will be told you have no installed packages. Good news: That's easy to fix!

### Installing Packages

Packages are installed by clicking the **![Package Manager](images/packages.png) Package Manager** icon at the top right of the window. You can search for a given game or package name and install it.

### Manual Package Management

Installed packages are saved in your `Documents\EmoTracker\packs` folder.

To install a package manually, place its zip file in that folder.

For development, you can place a folder in this directory with the extracted contents of the pack, e.g. `Documents\EmoTracker\packs\cool-new-pack`.


### Choosing A Package

Clicking the **![Settings](images/settings.png) Settings** icon in the top right of the window will allow you to choose a package to use. Some packs also support multiple trackers (e.g. normal, 'keysanity', 'entrance randomizer', etc).


## Tracking

<img src="images/map-example.png" alt="Example of a pack's tracker and map" style="float: right; margin: 0 0 0 1em;">

Most trackers will supply a map with *locations* or *checks* to help keep track of what you have or have not seen yet.

Checks are typically color coded:


<table id="accessibility-key">
	<thead>
		<tr>
			<th colspan="2" style='text-align: center;'>Color</th>
			<th style='text-align: center;'>Meaning</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>
				<div class="accessibility-dot accessibility-normal"></div>
			</td>
			<td>Green</td>
			<td>Fully accessible.</td>
		</tr>
		<tr>
			<td>
				<div class="accessibility-dot accessibility-sequencebreak"></div>
			</td>
			<td>Yellow</td>
			<td><em>Potentially</em> accessible. Might require sequence breaks, glitches, or specific key routing.</td>
		</tr>
		<tr>
			<td>
				<div class="accessibility-dot accessibility-inspect"></div>
			</td>
			<td>Blue</td>
			<td>Can be inspected; visible, but not accessible.</td>
		</tr>
		<tr>
			<td>
				<div class="accessibility-dot accessibility-none"></div>
			</td>
			<td>Red</td>
			<td>Inaccessible.</td>
		</tr>
		<tr>
			<td>
				<div class="accessibility-dot accessibility-partial"></div>
			</td>
			<td>Orange</td>
			<td>Partially accessible; mixture of the above.</td>
		</tr>
		<tr>
			<td>
				<div class="accessibility-dot accessibility-cleared"></div>
			</td>
			<td>Gray</td>
			<td>Cleared.</td>
		</tr>
	</tbody>
</table>

**I'm colorblind and/or these colors are hard to read. Help!**

You can change the colors used for locations. See [Customizing > Changing colors used for tracking](customizing#Changing_colors_used_for_tracking).


### Tracking

By default, only accessible, un-cleared locations are visible; any locations marked as <div class="accessibility-dot accessibility-none"></div> Inaccessible or <div class="accessibility-dot accessibility-cleared"></div> Cleared will not appear on the map. This can be changed by toggling the *⚙️ &rarr; Tracking &rarr; Show All Locations* option (or by pushing F11).


To interact with the tracker:

* *Right* click a location to mark it as <div class="accessibility-dot accessibility-cleared"></div> Cleared.
* *Double click* a location to pin it.
* <img src="images/location-popup.png" alt="Image of a location popup menu" style="float: right; margin: 0 0 0 1em;"> *Left click **and hold*** on a location to open a small popup. (If you release the button while the cursor is in the popup area, it will stay open.)
	* *Left* clicking on a check will mark it as cleared (or increment its counter, depending).
	* *Right* clicking on a check will unmark it. *Note that this is the **opposite** behavior outside of this popup!*
	* Clicking the 📌 icon will pin or unpin the location.
	* Clicking the 📝 icon will open *another* popup that allows you to add notes.
		* Click the (+) button to add a new note.
		* Click the "✏️ Edit Markdown" to be able to enter text. *(This text is only visible if you click the 📝 button again.)*
		* There is an empty square at the right that can be used to add extra marks to a location. (These marks are visible in the tracker when hovering over the location, and can be removed by clicking the small trash icon that appears when hovering over them in this menu.)
		* Notes can be deleted by using the 🗑 Trash icon.

Example of adding and removing notes on a location:
![GIF example of adding a note to a location](images/tedium.gif)

Some trackers or locations may allow you to assign an additional icon to a location, which can be useful for locations that are visible but not accessible, or for tracking which location goes where.

![GIF example of adding marks to track which which entrances go where](images/location-tracking.gif)


You can also disable logic checks by choosing *⚙️ &rarr; Tracking &rarr; Ignore All Logic*, which is ~~how you end up with Discord documentation~~ useful if you need to change a mark that you accidentally set, or if the tracker's logic is incorrect. 

The *⚙️ &rarr; Layout* menu may have additional options for swapping the left and right sides of a tracker, showing or hiding the map, or more.


### Shortcuts and Hotkeys

* **Ctrl-S**: Saves the current tracker state.
* **Ctrl-Shift-S**: Same, but allows you to choose a filename.
* **Ctrl-O**: Opens a saved tracker state.
* **Ctrl-Z**: Undo
* **Ctrl-Mousewheel**: Zoom in/out.
* **Ctrl-0** (zero): Reset zoom level.
* **F1**: Opens the current pack's documentation URL.
* **F2**: Opens the *Broadcast View* window.
* **F5**: Reset tracker to its initial state, including any tracker-specific options.
* **F11**: Toggle showing *all* locations, including inaccessible or cleared ones.

