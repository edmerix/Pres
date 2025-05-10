# Presentation.js
A class to build interactive presentations, akin to Keynote or PowerPoint, but
entirely browser-based.

This was originally created after getting the invitation to present a "dynamic" poster at the annual meeting for _Society for Neuroscience_ in 2019. That poster is available as an example presentation [live at my website](https://edmerix.github.io/SfN2019/), the code for it is in the [Example-presentation](Example-presentation) in this repository, and a static screenshot of the first slide is [below](#screenshot). To get started, you can just download the [blank presentation](Blank-presentation).

### Overview
Slides are built by creating directories, within each is a `manifest.json` file that explains to Presentation.js where to find anything you want to include for that slide. See [below](#Slide-manifest-file) for the structure of the manifest file.

No extra JavaScript coding is necessary to create slides; they can be entirely HTML-based, with the option to add your own CSS stylesheets. All settings are stored in [settings.js](Blank-presentation/js/settings.js).

By default, it includes an interactive menu for your slides, the option to auto-play by advancing slides at a given interval (by default one per minute), hovering on zoom, full-screen, looping of slides, and [shortcuts](#Shortcuts).

For more help, the [Presentation.js class](Blank-presentation/js/Presentation.js) is thoroughly documented in the comments.

### Screenshot
![Screenshot of a single slide using Presentation.js](screenshot.png?raw=true "Screenshot of a single slide using Presentation.js")

### Shortcuts
|Key| Action |
|--|--|
|Arrow keys|Advance (right, down) or go back (left, up) a slide|
|`Space`|Advance the slide|
|Number keys|Go to that slide number|
|`a`|Activate "auto-play", which advances the slide after a specified number of seconds (default: 60)|
|`e`|Toggle between the main slide and its "extra" information|
|`z`|Toggle whether the presentation is zoomed/scaled to the current screen or displayed at original size|
|`Esc`|Stop the "auto-play" feature if it's currently active|

### Advanced options
The default CSS allows for zooming on parts of your presentation when you hover the mouse over them. To turn this on, add `zoomable` to the desired element's class list. If you want it to zoom from a specific anchor point, for example to avoid it zooming beyond the edge of the page, you can tell it where to zoom from with extra classes, e.g., `frombottom` or `fromtopleft`.

Elements can also be made transparent by adding `transparent` to its class list, and default styling already exists for `figure`, `figcaption`, and all table-associated elements. These can, of course, be overridden, or you can completely delete the default styling and create your own.

You can include elements that are permanently on screen around your slide by adding them to the HTML element that will contain the presentation. The presentation will be inserted but will not overwrite anything already present in that tag. In the [example presentation](https://edmerix.github.io/SfN2019/), this is used to keep conclusions, title, references etc., always on the screen regardless of which slide is active.

### Slide manifest file
Each slide should have its own directory that contains a `manifest.json` file. The remainder of the content can be called whatever you wish, and the `manifest.json` file tells Presentation.js what items to display and how. Options inside the `manifest.json` file are:

```
    {
        "name": "aUniqueIDforTheSlide",
        "title": "A title for the slide",
       	"thumbnail": "an image file to act as the thumbnail for the slide",
       	"main": "the HTML page containing the main slide",
        "styles": "the CSS file containing any required extra styling for the slide",
       	"extra": "an HTML page containing any secondary information (toggled with E)"
    }
```

<sub><sup>__N.B.__ the `name` attribute should be appropriate for a JavaScript fieldname, i.e., cannot start with a number or have spaces or hyphens, etc., and it must be unique for each slide.
If it is left blank or not included in the manifest, then the Presentation class will automatically name it based on its position.</sub></sup>
