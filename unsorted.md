# Unsorted garbage from Discord

Notes on things that might be useful and aren't yet split into different sections.

<blockquote class="quotable">Hi folks - sorry for the ping, but a friendly reminder has become necessary. When you have a question, check faq first, then at least make a cursory attempt at searching the support channels. <strong>The number of times recently that somebody has asked a question directly answered by faq AND answered 5 minutes prior by somebody in a support channel is out of control.</strong>  If it continues to get worse, I’m going to have start doing something more direct to keep the channels clean and useful, and I’d rather not do that.</blockquote>

no way to prevent this, says every discord where this happens

----

## Development

You are *expected* to reverse-engineer the way that EmoTracker works via looking at the [ALTTPR tracker source](https://github.com/emosaru/alttpr_emotracker_emosaru).

<blockquote class="quotable">This package source is provided for use as reference by all EmoTracker pack developers. <strong>I do not provide any support for working with this source beyond discussions in the EmoTracker Discord</strong>, and I do not accept merge requests.</blockquote>

in what is likely a shocking surprise to nobody on the planet, this package does **not** implement the "Package Documentation" feature of EmoTracker. lol. of course.


### Random stuff

Undocumented command line option: `-dev`
<blockquote class="quotable">
If you create your own shortcut for EmoTracker, you can add the -dev command line argument. That will cause the entire app to use <code>&lt;user&gt;/EmoTracker/dev</code> instead of <code>/EmoTracker</code> for all relevant directories (edited)
</blockquote>

----

something regarding location accessibility updates
<blockquote class="quotable">
There is caching within a single logic update now if you set <code>"enable_accessibility_rule_caching": true</code> in your pack's settings, but you are correct that each user operation minimally results in one full re-evaluation. (edited)
</blockquote>

----

rather than actually providing documentation, let's get mad at people trying to figure out how things work

<blockquote>Here's what I believe to be the full extent of the accessibility rule syntax:

<pre>rule = baseRule | inspectable
inspectable = "{", baseRule, "}"
baseRule = [clause], { ",", clause }
clause = [whitespace], (sequenceBreakable | glitchable | counted), [whitespace]
sequenceBreakable = "[", counted, "]"
glitchable = "[", "[", counted, "]", "]"
counted = code, [ ":", integer ]
code = item | lua | location
item = identifier
lua = "$", identifier, { "|", identifier }
location = "@", identifier, ["/", identifier]
identifier = <any character>
integer = &lt;you know what this is&gt;
whitespace = " " | "\t" | "\n"</pre>
</blockquote>

wow, thanks. anyway,

<blockquote class="quotable">EmoSaru 2021-11-28 21:42
<br>
Okay, I’m really not particularly interested in defining a formal grammar here. It’s an ad hoc parser implementation, and this really isn’t relevant to what more or less anybody here is doing.</quote>

knowing how things work is not relevant to what anybody is doing 👍


## Pinned Messages

All of the notes in this section are copied from pinned messages.


* `#faq` has several messages, but the most useful ones are, naturally, the oldest. in rough order:
	* download location
	* no, it will not be ported to non-windows
	* no, it is not open source
	* "if you see unicode boxes, install this font"
	* what the various location colors mean **(re-documented)**
	* keyboard shortcuts **(re-documented)**
	* enabling chathud
	* chathud command reference
	* location color accessibility **(re-documented)**
	* troubleshooting: it's probably a virus scanner problem
	* "new package": contact the developer directly
		* <blockquote class="quotable">If you have a pack you want to distribute via the package manager which is complete and that you are prepared to provide ongoing support for, please DM @EmoSaru to request the pack developer role. Please note that this role does not gate any of the information necessary to build a pack - only distribution information. <strong>Everything that’s available for building packs is already available in customization-support</strong></blockquote>
		* lol
	* saving and loading, why your saves are invalid, etc.
	* a very long list of game-specific discords *(personally this seems like a weird place to put it but, hey, you do you)*
	* customizing the tracker **(in-progress)**
	* troubleshooting 2: it's probably still a virus scanner problem
	* how to use voice control
	* 32-bit windows support considered optional
	* autotracker requires internet support (*note: what. why*)
	* troubleshooting "the package community server is down": it's probably their fault
	* how do i uninstall a pack?
		* <blockquote class="quotable">Delete the package zip file from your Documents/EmoTracker/packs folder and restart the application.</blockquote>
		* lol
	* "when will there be a pack for *(insert game here)*"

outside of those channels:

* `#general` and `#suggestions` have no pins
* `#general-support` has no useful pins (0/3)
* `#pack-support` has no pins at all
* `#customization-support` has five pins, all of which are below
* `#autotracker-support` mostly involves setup and configuring ALTTPR, nothing useful
* `#chathud-support` has no useful pins (0/2)
* `#voice-tracking-support` has one pin which is a [youtube video](https://www.youtube.com/watch?v=ECZ9AYHSVGg)
* `#core-bugs` has no pins

### Customizations load order

Overrides replace the original file when loading, and need to be complete. Variants work the same, are still loaded by the variant path (relative to the override directory) and must be overridden independently from the default.

The loading priority order is:
1. Variant Override
2. Variant
3. Override
4. Default


## Layouts and arrangement


<blockquote class="quotable">[12:08 PM] Dorkmaster Flek: Mmm is vertical orientation like that a core app feature?  I thought I recall seeing something like that in one of the menus...
<br>[12:08 PM] Dorkmaster Flek: I could be misremembering that.
<br>
<br>[12:08 PM] EmoSaru: Look at my pack.
<br>[12:08 PM] EmoSaru: It's based on the layout names you provide.</blockquote>


## Reserved names

The reserved layout names are:

	tracker_broadcast
	tracker_default
	tracker_horizontal
	tracker_vertical
	tracker_capture_item


## Image Filters and Mods

<blockquote class="quotable">
[10:08 AM] EmoSaru: I thought I had it listed somewhere in the schemas, but apparently I don't. I will figure out a place to put it, but here is the current list... 
</blockquote>

if only there was somewhere it could go


* `grayscale` - makes things grayscale
* `brightness|<percentage>` - Multiplies brightness by a specified factor. Ex. `brightness|0.25` reduces brightness by 75%
* `overlay|<image_path>` - Applies the specified image path as an overlay. Overlay image must be same size as base image. Ex. `overlay|images/checkmark.png`
* `saturation|<percentage>[|mode]` - Adjusts the saturation of the image to a percentage between [0,1]. An *optional* luminance mode can be specified. Valid values are [`avg`, `max`, `red`, `blue`, `green`, `bt601`, `bt709`]. The default is `avg`.
* `@disabled` - Applies the default image filter for "disabled" states in the current context
* Legacy filters:
	* `dim` - reduces brightness by 50%
	* `halfdim` - reduces brightness by 25%
	* `quarterdim` - reduces brightness by 12.5%


Filters can be applied in sequence by using a comma-separated list, and they apply in the order specified. Ex. "`grayscale,brightness|0.5`"


## Custom Items

> As of the latest EmoTracker version 2.3.5.0, it is now possible to implement custom items in Lua. This can be very powerful for certain advanced types of trackers.
> 
> You can find reference/example code here: 
> https://emotracker.net/developers/sdk/emotracker_sdk.zip



## whatever this is

> To help address issues like this, I've added JSON schemas for the most critical JSON formats used by EmoTracker. You can find them on the web here...

* https://emotracker.net/developers/schemas/items.json
* https://emotracker.net/developers/schemas/layouts.json
* https://emotracker.net/developers/schemas/locations.json

> There is also a composite schema available at https://emotracker.net/developers/schemas/all.json but it requires a certain amount of context to exist in the file before it can reliably determine which type of data you are editing.
> 
> If you are using VS Code and have organized your json files sensibly, you may find that this addition to your workspace's settings.json will work for you. Feel free to adapt it to your directory structure.

    "json.schemas": [
        {
            "fileMatch": [
                "*/items/*.json",
                "*/*.items.json",
            ],
            "url": "https://emotracker.net/developers/schemas/items.json"
        },
        {
            "fileMatch": [
                "*/layouts/*.json",
                "*/*.layouts.json",
            ],
            "url": "https://emotracker.net/developers/schemas/layouts.json"
        },
        {
            "fileMatch": [
                "*/locations/*.json",
                "*/*.locations.json"
            ],
            "url": "https://emotracker.net/developers/schemas/locations.json"
        }                                   
    ]

> I can't guarantee that these are 100% perfect right now, but I will attempt to keep them updated as changes happen.