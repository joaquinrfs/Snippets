# Make your terminal fancy

Sometimes we spend hours a day looking at a terminal, why not give ourselves a treat and make it fancy?

1. Create a new PowerShell profile:
	```
	New-Item $profile -Force -ItemType File
	```
2. Allow the execution of local scripts in PowerShell, you can do this by either:
	- Running `Set-ExecutionPolicy RemoteSigned` as administrator.
	- Enabling the policy in the _For developers_ category, somewhere in Windows settings (depends on Windows version).
3. Install [Oh My Posh](https://ohmyposh.dev/):
	1. Run:
		```
		winget install JanDeDobbeleer.OhMyPosh -s winget
		```
	2. Add the following line to your PowerShell profile:
		```
		oh-my-posh init pwsh --config ~\AppData\Local\Programs\oh-my-posh\themes\default.omp.json | Invoke-Expression
		```
	3. Relaunch the terminal.
	4. Install a _Nerd Font_:
		1. Run as administrator:
			```
			oh-my-posh font install
			```
		2. Change the font in the terminal options to the font you installed, _you might have to restart the terminal_.
		- You can check them out [here](https://www.nerdfonts.com/font-downloads).
	- Run `Get-PoshThemes` to get a list of possible themes.
	- In the line you added to your profile, replace `default` with any profile name you want.
3. Install [Terminal-Icons](https://github.com/devblackops/Terminal-Icons):
	1. Run as administrator:
		```
		Install-Module -Name Terminal-Icons -Repository PSGallery
		```
	2. Add the following line to your PowerShell profile:
		```
		Import-Module -Name Terminal-Icons
		```