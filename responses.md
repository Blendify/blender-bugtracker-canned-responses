Bugtracker Replies
------------------

---- DESIGN ISSUE

While its disputable how this should work,
its behaving as intended and not an error in the code.

Closing.

---- SUPPORT REQUEST

This is a general support issue and not a software error we can investigate.

For general issues, check on support sites such as:

- http://blender.stackexchange.com
- https://blenderartists.org/forum/forumdisplay.php?7-Support

If you still think you have found a bug,
please give exact steps to redo the error.

Closing.

---- INVALID MESH

This mesh is corrupt, so the bug is that you managed to make a corrupt mesh in the first place.

Can you re-create this mesh from scratch (or at least by some operations on a valid mesh)?

To check for invalid mesh data, run this Python snippet:

    import bpy
    bpy.context.object.data.validate(True)

Check terminal, for the output.


---- USERPREF WINDOW FAILS TO OPEN

We have had quite a lot of reports about this,
as far as we can tell this is a bug in some graphic card drivers
relating to using the same OpenGL context for multiple windows
(something which seems not to be well supported especially for low-end cards).

All we can suggest if to try update your graphics card drivers,
or possibly buy a better graphics card.

Failing that, you can workaround this by accessing the user preference
from the window-type-selector available on the window headers.

---- MISSING INFO

The report is a complete lack of any information.
Please follow the bug report guidelines and fill in all the requested information.
This isn't a support system, but a bug tracker,
so it's important you include all the steps needed to reproduce the issue so we can investigate it.

---- NOT A BUG REPORT

If you find an error in Blender you need to report exactly what fails and how to redo the bug.

However this is not a bug report we can handle usefully.

closing.

---- SELECTION FSAA

There are known problems with some graphics cards when using Multisampling,
also called FSAA or Fullscreen Anti-Aliasing,

This is a Blender preference you can disable:

  User Preferences -> System -> Window Draw Method -> (Set to 'No Multi-Sample')

Also, this can be set in the graphics cards preferences,
there is often an option to override, or let the application choose.
You should set to let the application choose.

This causes problems with the selection-buffer under some configurations,
Blender disables this via OpenGL API, but some drivers ignore the request.

Could you see if this is causing the problem?


---- OPENGL RANDOM ERROR

Its highly likely that this bug is specific to your hardware/driver configuration.
These kinds of display issues are often caused by OpenGL driver bugs.

While its possible a software error in Blender,
its worth checking if this functions correctly...

- After upgrading graphics card drivers.
- On a different system (with different hardware/drivers).
- Using a Software OpenGL renderer...
  - On Linux, Official releases come with `blender-softwaregl`
  - On MS-Windows: Downloading 'opengl32.dll' from [[ http://download.blender.org/ftp/sergey/softwaregl | download.blender.org/ftp/sergey/softwaregl ]] and copying it so its located in the same directory as 'blender.exe'

If this is a driver bug, or we can't link to this to an error in Blender's code,
the report may be closed as a driver error,
so please help us determine whether this is a bug in Blender or not.


---- CRASH ON STARTUP

Please:
* Give us your exact Blender, OS and GPU (including drivers) versions, as requested in the template!
* Ensure both your OS and drivers are fully up-to-date (and use official GPU drivers, not those provided by windows or tablet/laptop maker).
* Try to disable any running antivirus.
* Ensure you have no python executable available in your %path% envvar.
* Try to re-download and re-install Blender.
* Try the latest build from [our buildbot](https://builder.blender.org/download).
* Try to start Blender in factory settings (`--factory-startup` commandline option) (this will ensure whether this is a userpref or addon issue or not).
* Try to tweak your GPU driver settings (e.g. try different values between 'performance' and 'quality' if you have such slider, etc.).
* Launch Blender from the command line with `-d` option and **attach as text file** here any error printed out in the console (**do not** paste it directly in comment).
* Try to place [this dll](http://download.blender.org/ftp/sergey/softwaregl/win64/opengl32.dll) next to your blender.exe (software OGL, will be slow, but will show whether this is a driver issue or not).
