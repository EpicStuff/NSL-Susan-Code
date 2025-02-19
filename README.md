# NSL-Susan-Code

NSL-Susan-Code is a drive controller for Meltybrain (translational drift) robots, running on the arduino (atmega32) platform.

It's also my first Arduino project, so, brace yourself. This library is not guaranteed fit for any purpose, and may cause your robot to just explode instead of doing anything useful. You Have Been Warned.

This is based incredibly heavily on the fantastic PotatoMelt: https://github.com/skysdottir/PotatoMelt

If you're spinning this up in a VS Code workspace, there's a few things you'll need to do to get everything happy:
- Install the Arduino vs code extension

My development hardware:
- TODO

## Configuration

### Entering config mode
At rest, hold the right stick back for 3s to enter config mode. Once you release the stick, the LED will change from a single fast blink to a double blink to indicate that it's in config mode.

It is important to enter config mode while the bot is at rest- it snapshots the current accelerometer state to get a 0 point when it enters config mode, so if it's moving or spinning, that zero point will be wrong

### Setting accelerometer correction curve
Spin the bot up! You're going to want to record 8 correction points, across a wide range of RPMs.

To set a correction point:
- Pick a RPM, make sure the bot is stable at it
- Adjust the heading LED left and right with the right stick until it does not precess
- Push the save button (toggle channel 6)

You do not need to save correction points in order, the bot will sort them for you

### Setting heading LED offset
At a stable RPM in config mode:

- Push the right stick forwards to see how the bot advances
- Pull the right stick back and then rotate to rotate the LED offset
- Repeat until the LED and the bot direction agree

### Exiting config mode
Spin the bot down to zero, and then hold the right stick back for 3s again to exit config mode. The LED will return to a fast blink when you release the stick.