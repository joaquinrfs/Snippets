# Remove Curl Alias from PowerShell

It might surprise you to know that `curl` comes preinstalled in Windows; it might surprise you even more to know that you cannot use it in PowerShell.

If you run `curl` in PowerShell, you will get a strange output. This is because in PowerShell, `curl` is an alias for `Invoke-WebRequest`.

To temporarily remove this alias, you can execute:

```
Remove-Item Alias:curl
```

## Want a more permanent solution?

Add the command to your PowerShell profile. You don't have one?

1. Create a new PowerShell profile:
	```
	New-Item $profile -Force -ItemType File
	```
2. Allow the execution of local scripts in PowerShell, you can do this by either:
	- Running `Set-ExecutionPolicy RemoteSigned` as administrator.
	- Enabling the policy in the _For developers_ category, somewhere in Windows settings (depends on Windows version).
3. Add the command to the profile file, which should be in `~\Documents\WindowsPowerShell\`.