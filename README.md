## Dashing on Apple TV

This is a sample project that shows how to hook up [Dashing](TODO) to show as the as screen saver of an Apple TV.

### Setup

Check out this project on a Mac and `bundle install`

Open iPhoto and click on "iCloud" on the side. Sign if if necesssary.

NOTE: this is meant to have total control over this iCloud account. It should be a new account for your dashboard, not your personal one. It may delete you photos.

Import a photo, select "Share...", and share it to the iCloud album(s) you want to use (just to make the album). In the sample, it is called "dashboard."

Go back to the command line and run `bundle exec rake dashing:cron` - it should take the screenshots. You'll likely need to allow some accessibility access to iPhoto from the Applescript. Follow the given instructions.




