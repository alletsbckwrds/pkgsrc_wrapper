# pkgsrc wrapper
### Warning: this script assumes you have installed netBSD pkgsrc tree on your system
if you haven't, you can follow these steps:
- ```$ curl https://cdn.netbsd.org/pub/pkgsrc/current/pkgsrc.tar.xz --output ./pkgsrc.tar.xz```
- ```# tar -xvf ./pkgsrc.tar.xz -C /usr```
- ```# pacman -s inetutils```
- ```# cd /usr/pkgsrc/bootsrtap && ./bootstrap --prefix /opt/pkgs --prefer-pkgsrc yes --make-jobs 2```
#### Note, this is my way. It is not the only right way. Refer to netBSD's wiki for more details.
## Using the script
- Clone this repo or download just the pkgsrc file
- ```chmod +x ./pkgsrc```
---
Please do note that this script needs a lot more testing. Feel free to report any issues.
```
Usage: pkgsrc <command> [package name]
Commands are:
	search <pkg>	Search package in pkgsrc tree (offline)
	update		Update local pkgsrc tree
	check		Check pkgsrc tree status and check for upgradeable packages.
	install <pkg>	Compile and install specified package
	remove <pkg>	Remove specified package
	upgrade	<pkg>	Upgrades specified package
	info <pkg>	Show info about a package (offline)
```
You can test the script by installing ```lintkpkgsrc```, an optional dependency of this wrapper: ```# pkgsrc install pkgtools/lintpkgsrc```
### Note:
- bmake needs to be available in the path, even for this script which does NOT source from ```~/.bashrc```
- This is not a bash script, this is a POSIX shell script. So this should work on BSD too.
- This script depends on cvs and gawk. More info inside the script.
