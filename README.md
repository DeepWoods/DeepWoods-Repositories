# DeepWoods Repositories
This is a centralized location to find information on the various options available to use images and packages provided by DeepWoods(me).

##### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Information on how to access DeepWoods repositories for docker, debian and rpm packages.
## Docker Repos
[NxFilter](https://github.com/DeepWoods/nxfilter-docker)

[NxCloud](https://github.com/DeepWoods/nxcloud-docker)

## Debian Repo
Update repo information and make sure the required base packages are available.
```
sudo apt update && sudo apt install -y curl gnupg
```
Download the DeepWoods GPG signing key:
```
curl -fsSL https://debian.deepwoods.net/deepwoods.key | gpg --dearmor | sudo tee /usr/share/keyrings/deepwoods.gpg > /dev/null
```
Setup apt source list for the DeepWoods repository:
```
echo "deb [ arch=all signed-by=/usr/share/keyrings/deepwoods.gpg ] https://debian.deepwoods.net stable main" | sudo tee /etc/apt/sources.list.d/deepwoods.list
```
Install NxFilter and dependencies with apt:
```
apt install nxfilter
```
To remove:
```
apt autoremove nxfilter
```

## RPM Repo
1. Install the DeepWoods repository package:
```
yum install https://rpm.deepwoods.net/deepwoods-release-7-0.noarch.rpm
```
2. Install NxFilter and answer yes to import the DeepWoods repository GPG key when prompted:
```
yum install nxfilter
```
3. Check if NxFilter is running.  Start it if it isn't.

`systemctl status nxfilter` to verify NxFilter is running.  `systemctl start nxfilter` to start it if it is not already running.

4. Configure NxFilter per the documentation: [NxFilter tutorial](https://nxfilter.org/tutorial.html)

> [!NOTE]
> The RPM installs NxFilter files to a non-standard location of /nxfilter in the filesystem root directory and enables system services(/etc/systemd/system/nxfilter.service) by default.
> $\color{Orange}{*This\ is\ not\ a\ standard\ practice\ for\ 3rd\ party\ RPM\ packages\ but\ strives\ to\ make\ installation\ of\ NxFilter\ as\ simple\ as\ possible.}$
