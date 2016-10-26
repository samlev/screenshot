# Screenshot

Pretty basic script for uploading screenshots on ubuntu. Options are: FTP, imgur, local folder, and clipboard.

## Required programs:

* [`shutter`](http://shutter-project.org/) - the screen shot tool (used to actually take screenshots)
* [`zenity`](https://help.gnome.org/users/zenity/stable/) - Basic GTK dialogs (used to ask where to upload)
* [`lftp`](https://lftp.yar.ru/) - basic program for one-line FTP uploads (used if 'FTP' is selected)
* [`curl`](https://curl.haxx.se/) - calls URLs (used for uploading to imgur)
* [`jq`](https://stedolan.github.io/jq/) - sed for json data (used to read responses from imgur)
* [`xclip`](https://linux.die.net/man/1/xclip) - used to add things to the clipboard

All of these should be available through `apt` or `yum`. Note that I haven't tested any of this on anything other than Ubuntu 16.04, but they all work when configured correctly.

## To install:

I'm not a fancy man, and this isn't a fancy script. Get a copy of it, change the config up the top, and throw it in `/usr/local/bin/screenshot` or wherever else. I'm not going to tell you how to do your job.

If you want to make it more fancy, do it on your own time.

## To use:

```
$ screenshot
```

Or bind a key to run that. Whatever.

You will then be able to select an area of your screen to capture. Press enter, and you'll be given the opportunity to edit the image. Once that's done, it'll ask you where you want to upload. Pick one, and it will copy something into your clipboard:

* **Imgur**: the imgur image url (`https://i.imgur.com/SoMetH1ng.png`)
* **FTP**: the URL based on FTP settings (`http://example.com/uploads/2016-10-26_120320_sam_I9dU5QZZ.png`)
* **Picture**: the full path to the image on your harddrive (`/home/sam/Pictures/2016-10-26_120320_sam_I9dU5QZZ.png`)
* **Clipboard**: the actual image data.

## Known issues:

* imgur uploading is set to anonymous uploading only. I couldn't be bothered dealing with OAuth.
* `zenity` makes some complaint about `"Gtk-Message: GtkDialog mapped without a transient parent. This is discouraged."` - I don't see this as my problem.
* My code is really bad because I don't really care too much, and it works for me.
* `shutter` is pretty slow to boot up. If you want to capture something that moves fast... don't use this.
* My right shoulder hurts sometimes when I run a lot.
* I can be a bit abrasive.
* My speling adn grammer arnt to good.

## License:

Released under the [DILLIGASPL](https://github.com/samlev/DILLIGASPL).

                DO I LOOK LIKE I GIVE A SHIT PUBLIC LICENSE 
                          Version 1, July 2013 
      
      Copyright (C) 2013 Sam Levy <sam@samuellevy.com> 
  
      Everyone is permitted to copy and distribute verbatim or modified 
      copies of this license document, and changing it is allowed as long 
      as the name is changed. 
  
                 DO I LOOK LIKE I GIVE A SHIT PUBLIC LICENSE 
        TERMS AND CONDITIONS FOR COPYING, DISTRIBUTION AND MODIFICATION 
      
       0. I don't give a shit what you do, just don't bother me with it.
  
       1. I'm done with this shit, maintain it yourself.
