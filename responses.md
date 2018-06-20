Bugtracker Replies
------------------

---- NOT OUR ADDON

Thanks for the report, but this add-on is not developed by Blender, please report the bug to the original author.

---- DESIGN ISSUE

While its disputable how this should work,
its behaving as intended and not an error in the code.

Closing.

---- SUPPORT REQUEST

This is a general support issue and not a software error we can investigate.

For general issues, check on support sites such as:

- https://blender.stackexchange.com
- https://blenderartists.org/c/support

If you still think you have found a bug, please give exact steps to redo the error.

Closing.

---- FEATURE REQUEST

Hi, while we love to hear these ideas, this is not the right place for them.
This website is mainly used to track bug reports and not feature requests.
But luckly, there are some other nice solutions you can take,
so please use one of the other forms of communication listed below:

- https://rightclickselect.com/
- Fun board mailing list: https://lists.blender.org/mailman/listinfo/bf-funboard

---- INVALID MESH

This mesh is corrupt, so the bug is that you managed to make a corrupt mesh in the first place.

Can you re-create this mesh from scratch (or at least by some operations on a valid mesh)?

To check for invalid mesh data, run this Python snippet:

```
bpy.context.object.data.validate(True)
```

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

Please follow our submission template and guidelines and make a complete, valid bug report,
with required info, precise description of the issue, precise steps to reproduce it,
small and simple .blend and/or other files to do so if needed, etc.

A guideline for making a good bug report can be found here:
https://wiki.blender.org/wiki/Process/Bug_Reports

Marking as "Incomplete" until the requested information/data is provided.

---- MISSING BLEND-FILE

Thanks for the report but it would be helpful if you add a blend-file to the report that demonstrates the issue at hand.

---- NOT A BUG REPORT

If you find an error in Blender you need to report exactly what fails and how to redo the bug.

However this is not a bug report we can handle usefully.

Closing.

---- SELECTION FSAA

There are known problems with some graphics cards when using Multisampling, also called FSAA or Fullscreen Anti-Aliasing.

This can be disabled in the User Preferences:

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

While its possible a software error in Blender, its worth checking if this functions correctly...

- After upgrading graphics card drivers.
- On a different system (with different hardware/drivers).
- Using a Software OpenGL renderer...
  - On Linux/macOS, Official releases come with `blender-softwaregl`
  - On MS-Windows: Download [[ http://download.blender.org/ftp/sergey/softwaregl/win64/opengl32.dll | this dll ]] and copying it so its located in the same directory as 'blender.exe' and run Blender normally.

If this is a driver bug, or we can't link to this to an error in Blender's code, the report may be closed as a driver error,
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
* Try to run Blender through Software OpenGL, this will be much slower however, if everything works then it means that the bug is spefic for your GPU/Driver and you should report the bug to your GPU vendor instead.
  * On Linux/macOS, Official releases come with `blender-softwaregl`
  * On MS-Windows: Download [[ http://download.blender.org/ftp/sergey/softwaregl/win64/opengl32.dll | this dll ]] and copying it so its located in the same directory as 'blender.exe' and run Blender normally.

---- ALREADY FIXED

This is a known issue, and the good news is: it is fixed already! if you need the fix urgently you can grab a build from https://builder.blender.org/download otherwise this fix will be included in the next official update.

---- INCOMPLETE WITHOUT REPLY

Since last asking for information it has been 7 or more days, due to the policy of our bug tracker
we will have to archive the report until the requested information is given.

---- UNSUPPORTED GCN

We only support graphics cards with GCN architecture 2.0 and above). To make sure your GPU is supported checkout this [[ https://en.wikipedia.org/wiki/List_of_AMD_graphics_processing_units | Wikipedia page. ]]

---- 2.8 BUG REPORT

Thank you for the report. Currently we are aware of many issues in 2.8 and actively working to fix them.
But since replying to reports takes time, we have decided to limit bug reports to [[ https://wiki.blender.org/wiki/Process/Module_Owners/List | module team ]] members.

