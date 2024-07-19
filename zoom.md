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



How to create Rooms in Zoom?
1. Check for "Breakout rooms"

It should be either here:
![alt text](image-6.png)

Or here:
![alt text](image-7.png)

2. Choose "Let participants choose room" option

![alt text](image-8.png)

3. Increase rooms count by using + option (check screenshot above)

4. Use Recreate option to increase rooms (sometimes you come across with this)

![alt text](image-9.png)


5. You should be seeing like this:
![alt text](image-10.png)


6. Click "Open All Rooms"
![alt text](image-11.png)

7. You are done!



### Ref :

  * [https://linuxize.com/post/how-to-install-deb-packages-on-ubuntu/](https://linuxize.com/post/how-to-install-deb-packages-on-ubuntu/)
