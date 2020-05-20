# NightlyFox
a pretty Firefox customization

based and build on top of [Humble New Tab Page](https://github.com/quodroc/HumbleNewTabPage) and [Tree Style Tab](https://piro.sakura.ne.jp/xul/_treestyletab.html.en#download) addons.

I went for a clean dark mode-ish look. 
Replaced traditional horizontal tabs with a vertical sidebar where the current tab is highlighted in a gradient color. 
For the hntp Home Page I used some hover and transition effects.
The colors are kinda based on Firefox Nightly Build icon, thus the name.

<i>idea originated from <b>[akshat46/FlyingFox](https://github.com/akshat46/FlyingFox)</b>, take a look!</i>

## Color Palette & Theme Preview
![NightlyFox Color Palette](https://github.com/Burakbo/NightlyFox/blob/master/images/NightlyFoxColors.png)
![NightlyFox Tabs Screen](https://github.com/Burakbo/NightlyFox/blob/master/images/tabs-animation.gif)
![NightlyFox Home Page](https://github.com/Burakbo/NightlyFox/blob/master/images/bookmark-animation.gif)

## Installation

### Prerequisites
* type and enter ```about:config``` on the searchbar and set ```toolkit.legacyUserProfileCustomizations.stylesheets``` to ```true```
* go to ```about:support```, find the profile folder section and click open folder next to it
* create a new directory called chrome in your profile folder
* add [```./userChrome.css```](https://github.com/Burakbo/NightlyFox/blob/master/userChrome.css) into that folder.

### Addon Setup
Download and add the following addons to your browser:
1. [Humble New Tab Page](https://github.com/quodroc/HumbleNewTabPage)
2. [Tree Style Tabs](https://piro.sakura.ne.jp/xul/_treestyletab.html.en)
3. [Firefox Color](https://addons.mozilla.org/de/firefox/addon/firefox-color/)

you can also get the above on: https://addons.mozilla.org/en-US/firefox/ 

### Add NightlyFox customizations
1. hit <i>```[ctrl]+[shift]+[a]```</i> to open the addon menu
2. on <b>Tree Style Tab</b> click on <i>options</i> and scroll down to <i>Advanced</i> and add the styles from [```./NightlyFoxTabs.css```](https://github.com/Burakbo/NightlyFox/blob/master/NightlyFoxTabs.css) into that input box
3. on <b>HNTP</b>, <i>options</i> will open the extensions tab. go to <i>Advanced</i> and under <i>Custom CSS</i> paste the [```./NightlyFoxPage.css```](https://github.com/Burakbo/NightlyFox/blob/master/NightlyFoxPage.css) styles in it
4. under <i>Settings -> Content</i> you can choose the Bookmark location you want to show up with your new styles. (for me that's <i>Bookmars menu</i>, simply add your bookmarks there without subfolders if you want to see them all in one place.   
5. for <b>Firefox Color</b> you can use my customt settings: [NightlyFox](https://color.firefox.com/?theme=XQAAAAIrAQAAAAAAAABBqYhm849SCia2CaaEGccwS-xNKlhT0Sf61H-l2kuFQ7JmIThKEJYbO6BYtL_2lkWfb8tWnwcgdYSjnzerfQXprVIy-d0f6VvN1vWntbZYYsiR-2QeYnnbNWzid6cnV_vGc4Qq0wSsrF0LyZvwu_JqKCOjIK3UBrwW8fBR-9p1MvVeQS3O6XWATJK7ywwSgXleAP5BuJOguN768KrgxH-lg1bIZfQy_lpu84lCy5_CKsoo2a_xgSMM_7xxMAA)

I also had to go to ```about:preferences#home``` and make the extensions page my new Homepage and new tab url in order to make my customized page load on Firefox Home Page sessions and during new tab sessions. You can bookmark your extension and point to there or just drag and drop from the search bar to your custom url for it to be like: ```moz-extension://..../newtab.html```

### Custom Fonts
Your Browser will open System Fonts in the extension. I used Google's [Montserrat](https://fonts.google.com/specimen/Montserrat), which is as close I could get to Firefox lockup typo: https://mozilla.design/firefox/typography/  
Simply add it into the css with your preferred weight.


## Notes
I had a weird bug(?) showing a white square on the very top left of the window. In ```userChrome.css``` I simply put every gap inbetween the components to zero even if I made sure they are turned off already. Its probably not a rendering but coloring issue, tweak around with the css file a little.

<i>```userChrome.css```</i>
```
  --toolbar-height          : 0;
  --menubar-height          : 0;
  --toolmenubar-height      : 0; 
  
  ```
  
  removing the toolbar and menubar also removed my window controls. I simply use custom made addons for minimizing, maximizing and closing the window now (you can go without controls, simply use [ctrl]+[shift]+[q] to quit and [alt]+[space]+[n] to minimize if you like keyboard based window management).
  
I also had to invert colors of the GitHub icon from the Favicon Kit in order to see it on my dark background.

<i>```NightlyFoxPage.css```</i>
  ```CSS
  /* inverted the github icon color here (n=2 in my case)
   so it becomes visible on dark bg */
   
#main li:nth-of-type(2) a .icon {
filter: invert(100%) 
}
```
  
  