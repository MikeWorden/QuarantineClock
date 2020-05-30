# QuarantineClock

An update of the QuarantineClock developed by mwfisher3 (found at https://github.com/mwfisher3/QuarantineClock)
Changes include:
1) Disable screen blankcing explicitly if you are not using the phue library
2) A "vacation" set of messages keeping you apprised of how close to happy-hour you are.

Quarantine Clock is a Raspberry Pi that displays the day of the week and an approx time of day. The screen backlight is linked to a Hue Motion Sensor (via the "phue" python library) so that it turns on for 5 minutes at a time then turns off when there is no motion. The clock is a webpage in Chromium in kiosk mode and uses Javascript to get the day and hour.

For setting up phue, visit: https://github.com/studioimaginaire/phue

Add the following to "/etc/xdg/lxsession/LXDE-pi/autostart"

@lxterminal -e /home/pi/QuarantineClock/BackLight.py

@/home/pi/QuarantineClock/noblank.sh

@chromium-browser --incognito  --noerrdialogs --disable-desktop-notifications -update-kiosk --check-for-update-interval=1 --simulate-critical-update /home/pi/QuarantineClock/today.html


