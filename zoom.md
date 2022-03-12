/ [Home](index.md)

# Zoom Installation


```
Uninstall Zoom client from snap:
sudo snap remove zoom-client

cd /tmp

wget --no-check-certificate https://zoom.us/client/latest/zoom_amd64.deb
	or
	curl -k -O -L https://zoom.us/client/latest/zoom_amd64.deb
	 
sudo dpkg -i ./zoom_amd64.deb

	or
	sudo apt install gdebi
	sudo gdebi zoom_amd64.deb
	
if any dependency error, use this:
	sudo apt install -f



```

### Ref :

  * [https://linuxize.com/post/how-to-install-deb-packages-on-ubuntu/](https://linuxize.com/post/how-to-install-deb-packages-on-ubuntu/)
