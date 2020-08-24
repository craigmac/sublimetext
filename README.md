# User Files for Sublime Text 4+

## Notes for ST4 beta releases

If using Sublime Text < 4, check the user preferences (Ctrl+Alt+, keybind),
to see what options you need to disable that are v4000+.

While v4+ is beta, you only get zipped folder (portable) versions. So I keep them
in e.g., C:/Users/cmaceachern/Apps/sublime-text-4 and I keep unzipping new releases
to that folder. I then add that folder to my \$PATH (%PATH% on windows) so that
`subl` works even between updates as long as I keep the folder name the same.

Eventually v4 will be released and this process will change; it will probably
install to %APPDATA%/Roaming/Sublime Text like it does now with version 3:
%APPDATA%/Roaming/Sublime Text 3 (on Windows).

## Cloning

Windows:

```bash
cd C:/Users/cmaceachern/Apps/sublime-text-4/Data/Packages
git clone https://github.com/craigmac/sublimetext User
```

## Package Overrides (Safely modifying packages files)

See also: https://www.youtube.com/watch?v=VmyjGEdO2uE

If fixing a bug/altering a default/package control package, use Overrideaudit
package from package control and use "OverrideAudi: Create Override" command.

How ST works is that for every foo.sublime-package (just a zip file renamed)
inside of the 'Installed Packages' folder, ST will look for a folder of the same
name in 'Packages/' folder (one above 'User', i.e., 'Packages/User') and use any
code from in there instead of the .sublime-package code.

For instance to override some code in goto_commands.py inside
'SublimeLinter.sublime-package', you can (or automatically done with
OverrideAudit) create a 'Packages/SublimeLinter' folder and put a copy of the
'goto_commands.py' file inside of there and edit it.
