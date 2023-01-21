# firefox-css_use-multiple-userchrome-files
Firefox chrome CSS to easily allow using multiple userChrome.css files.  This makes it much easier to keep individual userChrome.css files up-to-date.

## Installation
Copy the `chrome/userChrome.css` file and the example `chrome/tab-busy-circle-spinning` folder into your Firefox profile folder:
* Start Firefox.
* Open the address `about:profiles` .
* If there is more than one profile then use the one labelled as `This is the profile in use`.
* Click the "Open Directory" button next to Root Directory path.
* Create a `chrome` folder & then inside it save the files.
* Restart Firefox.

## If doesn't work
* Open the address `about:config` .
* Search for `toolkit.legacyUserProfileCustomizations.stylesheets` (and create it as a **Boolean** if it doesn't exist).
* Set it to **true**.
* Restart Firefox.

## Usage
Usage should hopefully be fairly self-explanatory to anyone with a little CSS experience, but just in case it's not...

The main `chrome/userChrome.css` file contains links to other userChrome.css files that you've downloaded to their own folders inside the main `chrome` folder.  

As an example I have provided `chrome/tab-busy-circle-spinning/userChrome.css`.  It will only be used if the following line is present in the main `chrome/userChrome.css` file:
~~~
@import url("tab-busy-circle-spinning/userChrome.css");
~~~

And you can easily disable a line by commenting it out, for example:
~~~
/*@import url("simple-curved-tabs/userChrome.css");*/
/*@import url("status-bar/userChrome.css");*/
~~~

Once you've finished making changes to main `chrome/userChrome.css` file, you need to restart Firefox for the changes to take effect.

As a tip, if you want to quickly *test* some CSS changes, without having to close & restart Firefox, then you can use `about:profiles` to create a dummy new FF profile, and then click on `Launch profile in new browser` to preview the changes.
