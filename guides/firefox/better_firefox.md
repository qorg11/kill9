# Fixing firefox

Of course. nothing is perfect. But I can try to be or something. In this guide we're turning 

this  
<img src="https://149366088.v2.pressablecdn.com/wp-content/uploads/2020/04/firefox-75-linux.jpg" width=500px>

Into

this  
<img src="/guides/firefox/result.png" width=500px> 

# Download sidebery

This will add the sidebar where you can manage the tree styled tabs
and bookmarks. It's awesome and way better than the default tabs
management.

<https://addons.mozilla.org/en-US/firefox/addon/sidebery/>. 

Download. Install it and if don't appear. Press C-e, and your tabs will appear.

# Remove tab bar

In newer version of Firefox. You might need to set
toolkit.legacyUserProfileCustomizations.stylesheets to trye in
about:config I'm using firefox 68 so i don't need to.

Go to your Firefox profile location
(~/.mozilla/firefox/xxxxxx-default) and create a folder named "chrome"

Inside that folder. Create a file named userChrome.css with the following contents:

~~~
#TabsToolbar {
  visibility: collapse;
}
~~~

# Remove spyware

Now you might want to disable spyware from your browser (You should). Follow the steps [here](/guides/firefox/spyware)
