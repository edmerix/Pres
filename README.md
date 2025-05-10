# Presentation.js
A class to build interactive presentations, akin to Keynote or PowerPoint, but
entirely browser-based.

### Overview
Slides are built by creating directories, within each is a `manifest.json` file
that explains to Presentation.js where to find anything you want to include for
that slide. See [below](#Slide-manifest-file) for the structure of the manifest
file.

No extra JavaScript coding is necessary to create slides; they can be entirely
HTML-based, with the option to add your own CSS stylesheets. See [below](#Details)
for details.

By default, it includes an interactive menu for your slides, the option to auto-play
by advancing slides at a given interval (by default one per minute), hovering on zoom,
full-screen, looping of slides, and [shortcuts](#Shortcuts).

This was originally created after getting the invitation to present a "dynamic" poster
at the annual meeting for Society for Neuroscience in 2019. That poster is available
as an example presentation [live at my website](https://edmerix.github.io/SfN2019/),
the code for it is in the [Example-presentation](Example-presentation) in this
repository, and a static screenshot of the first slide is [below](#screenshot).

### Screenshot
![Screenshot of a single slide using Presentation.js](screenshot.png?raw=true "Screenshot of a single slide using Presentation.js")

### Details


### Shortcuts


### Advanced options


### Slide manifest file
Each slide should have its own directory that contains a `manifest.json` file. The remainder of the
content can be called whatever you wish, and the `manifest.json` file tells Presentation.js
what items to display and how. Options inside the `manifest.json` file are:

`{
    "name": "aUniqueIDforTheSlide",
    "title": "A title for the slide",
   	"thumbnail": "an image file to act as the thumbnail for the slide",
   	"main": "the HTML page containing the main slide",
    "styles": "the CSS file containing any required extra styling for the slide",
  	"extra": "an HTML page containing any secondary information (toggled with E)"
}`

<small>(Note that the name attribute should be appropriate for a JavaScript fieldname, i.e., cannot
start with a number or have spaces or hyphens, etc., and it must be unique for each slide.

If it is left blank or not included in the manifest, then the Presentation class will
automatically name it based on its position.)</small>


### TODOs

And go through the TODOs in Presentation.js file and enact them or remove

Remember to explain features in the default styling, such as hover to zoom,
and the fact that you can specify which direction the zoom should come from
so that you can make it static in the bottom left and expand out to the top
right, for example.
