# Force a specific Windows edition on install
*This method shows people how to force the Windows installer to install a specific edition, **the reader still needs a valid Windows Licence** for the installed edition as this snippet **does not** teach them how to pirate it in any way.*

Do you have a notebook? Does it refuse to install Windows Pro? Are you stuck with a OEM key? With a simple trick you can force the Windows installer to actually do what you want.

1. Prepare your bootable installer using the [Media Creation Tool](https://go.microsoft.com/fwlink/?LinkId=691209) or [Rufus](https://rufus.ie/en/).
2. Go to your bootable installer and create a file named `ei.cfg` inside the `sources/` folder.
3. Write the following text in `ei.cfg`:
```
[EditionID]
Professional
[Channel]
Retail
```

## Notes
- I haven't tested it myself, but it should work with Windows 11.
- If you want to install the Enterprise edition, write `Enterprise` instead of `Professional`.