<h1 align="center">
  :green_circle:&nbsp;&nbsp;  DeepWoods Repositories  &nbsp;&nbsp;:green_circle:
</h1>
<h5> This is a centralized location to find information on the various options available to use repositories and packages provided by DeepWoods(me).</h5><br/><br/>


##### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Information on how to access rpm and debian packages from DeepWoods repositories.

# $\color{SeaGreen}{Debian\ Repo}$
Update base repo information and make sure the required base packages are available.
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
Configure NxFilter per the documentation: [NxFilter tutorial](https://nxfilter.org/tutorial.html)

To remove:
```
apt autoremove nxfilter
```
<br/><br/>


# $\color{SeaGreen}{RPM\ Repo}$
Install the DeepWoods repository package:
```
yum install https://rpm.deepwoods.net/deepwoods-release-7-0.noarch.rpm
```
Install NxFilter and answer yes to import the DeepWoods repository GPG key when prompted:
```
yum install nxfilter
```
> [!NOTE]
> The RPM installs NxFilter files to a non-standard location of /nxfilter in the filesystem root directory and enables system services(/etc/systemd/system/nxfilter.service) by default.
> $\color{Orange}{*This\ is\ not\ a\ standard\ practice\ for\ 3rd\ party\ RPM\ packages\ but\ strives\ to\ make\ installation\ of\ NxFilter\ as\ simple\ as\ possible.}$


Check if NxFilter is running.&nbsp;&nbsp;Start it if it isn't.
<br/>
`systemctl status nxfilter` to verify NxFilter is running.  
`systemctl start nxfilter` to start it if it is not already running.

<br/>

Configure NxFilter per the documentation: [NxFilter tutorial](https://nxfilter.org/tutorial.html) 

