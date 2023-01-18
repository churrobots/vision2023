# AprilTags Example

Sample AprilTags detector and pose estimator for WPILibPi.

# Install and Run on WPILibPi Vision Application

The WPILibPi framework includes a "Vision Application" that can be manipulated
using the web service.  To set it up requires a few steps:

Attach the pi to the LAN, e.g. with an ethernet switch, or directly to your laptop.

From your laptop browser, browse to http://wpilibpi.local/ and click the "writeable" button on the top.

Now install some software on the pi, by ssh'ing to it (e.g. using PuTTY or whatever
ssh client you want, using username 'pi' and password 'raspberry'), and execute these:

```
sudo date -s '15 Sep 2022 14:25' (use the actual date)
sudo apt update
sudp apt upgrade
python3 -m pip install pupil-apriltags
sudo /sbin/reboot now
```

When the pi finishes restarting, go to http://wpilibpi.local/ again and click the "writeable" button on the top.

Now we're going to install the python code:

Click "Application" on the left side, and in the first box called "Vision Application Configuration," click "Choose File"
and find app.py.  Then click "Upload."

Then navigate to "Vision Settings" and click "Open Stream".  you should see wpilibpi.local:1181/, which
will render a bunch of stuff about the camera, and a little video stream showing what the camera sees,
with tag poses overlaid in text.

The app also publishes the id and pose of any AprilTags it finds to NetworkTables.

# Making changes

You can change app.py here, and re-upload it using the "Choose File" and "Upload" buttons mentioned above.  Each
time you do that, it will restart the python app.  You can see the log in the "Vision Settings" pane, which
is useful for debugging.
