## Dashing on Apple TV

This is a sample project that shows how to hook up [Dashing](http://dashing.io/) to show as the as screen saver of an Apple TV.

This was a good idea for us to do because we already had conference rooms and common areas with Apple TVs for use in AirPlay. This gives something helpful to look at automatically when not in use.

### Mac

Check out this project on a Mac and `bundle install`

Open iPhoto and click on "iCloud" on the side. Sign if if necesssary.

NOTE: this is meant to have total control over this iCloud account. It should be a new account for your dashboard, not your personal one. It may delete you photos.

Import a photo, select "Share...", and share it to the iCloud album(s) you want to use (just to make the album). In the sample, it is called "dashboard."

Go back to the command line and run `bundle exec rake dashing:cron` - it should take the screenshots. You'll likely need to allow some accessibility access to iPhoto from the Applescript. Follow the given instructions.

You should see it succeed after a few times of that. When iPhoto closes itself, that means it worked.

### Apple TV

Just a few notes on the settings I used when configuring the Apple TV

*Restore to newest software*

_General_

* Set up keyboard
* Set name
* Sleep after: never
* Software updates - Update automatically: on

_Screensaver_

* Start after: 2 minutes
* Photos - iCloud photos - Login - Pick "dashboard" album
* Classic  - Fade through black - 20 seconds

_AirPlay_

* Conference room display - off
* Play iTunes from the cloud - off


The "Classic" screensaver will show one image at a time. This works pretty well if you are taking a picture of the whole dashboard. I've also had success making a "dashboard" out of each widget and taking several screenshots and uploading all of them. In this case, I would use the "Shifting Tiles." This ends up looking like the original dashboard but it moves around a bit.

### Repeat

Once this is all working you can go back to the project and run `bundle exec whenever -w` - this will set it up to update every 10 minutes or so.

You'll want to make sure the computer does not go to sleep.

### Troubleshooting

One issue that I had was that if there was ever a time when there were no images in the iCloud album, then the Apple TV would default back to National Geographic photos. I'm not sure how this is possible other than some sort of lag in iCloud. Regardless, I ended up going with the "Shifting Tiles" solution noted above and always made sure to always have 1 image that never got removed in the album. I set up the iCloud gem so that if you make "hold" the image's name, it will leave it alone. So try that if you keep seeing beautiful whale pictures instead of your dashboard.
