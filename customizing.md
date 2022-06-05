# Customizing EmoTracker


## Pack Overrides

Overrides allow you to change specific files (images, etc) within a pack without having to edit the pack itself.

Overrides are stored in `Documents\EmoTracker\user_overrides\<pack_name>`. You can open this folder in EmoTracker by going to ***![Settings](images/settings.png) Settings** &rarr; Advanced &rarr; Open Override Folder*

To know where to place specific files, you will need to see where they are stored in the pack itself.




## Changing colors used for tracking

The colors used for locations on maps can be changed. Simply create a new JSON file at `Documents\EmoTracker\application_colors.json`, with any of the following keys you want to change:

<ul>
	<li>Accessibility tracking:
		<ul>
			<li><div class="accessibility-dot accessibility-normal"></div> <code>accessibility_normal</code></li>
			<li><div class="accessibility-dot accessibility-sequencebreak"></div> <code>accessibility_sequencebreak</code></li>
			<li><div class="accessibility-dot accessibility-inspect"></div> <code>accessibility_inspect</code></li>
			<li><div class="accessibility-dot accessibility-none"></div> <code>accessibility_none</code></li>
			<li><div class="accessibility-dot accessibility-partial"></div> <code>accessibility_partial</code></li>
			<li><div class="accessibility-dot accessibility-cleared"></div> <code>accessibility_cleared</code></li>
		</ul>
	</li>
	<li>I have no idea what these are used for:
		<ul>
			<li><div class="accessibility-dot status-generic-active"></div> <code>status_generic_active</code></li>
			<li><div class="accessibility-dot status-generic-success"></div> <code>status_generic_success</code></li>
			<li><div class="accessibility-dot status-generic-warning"></div> <code>status_generic_warning</code></li>
			<li><div class="accessibility-dot status-generic-error"></div> <code>status_generic_error</code></li>
		</ul>
	</li>
</ul>

This example file has the default colors for easy editing:
```
{
  "accessibility_normal": "#00ff00",
  "accessibility_sequencebreak": "#ffff00",
  "accessibility_inspect": "#6495ed",
  "accessibility_none": "#ff0000",
  "accessibility_partial": "#ff8c00",
  "accessibility_cleared": "#333333"
}
```
