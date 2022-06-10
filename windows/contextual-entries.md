# Manipulate entries in the Windows context menu

Using the regedit.msc program you can edit the Windows Registry in which these context menu entries are allocated.

`HKEY_CLASSES_ROOT\Directory\shell\` is used for entries in the file context menu (like on a .txt).

`HKEY_CLASSES_ROOT\Directory\Background\shell\` is used for entries in the folder context menu (like in Desktop).

For any key (folder-thing) you can add or delete values:

## String Values

`Extended` hides the entry from the user unless the context menu was opened while holding Shift.

`ProgrammaticAccessOnly` completely hides the entry from the user.

You may also just delete the key, but in some instances that _does not_ remove the entry.