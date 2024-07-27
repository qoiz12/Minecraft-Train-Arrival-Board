# Minecraft Train Arrival Board
A Mini Minecraft Transit Railway PID in Real Life! 

![GIF of the Finished Project in Action!](https://your-file-is-ready-to-download.zip/minecraft/the.gif)
# Pre-Requisites
## Hardware
- Raspberry Pi (or another similar device) 
- 3.5 Inch SPI Screen 
- SD Card (sufficent enough to store Raspbian) 
- GPIO Pins (if your display is connected via the GPIO pins) 
- Power Cable (for RPI or similar device)
- GPIO Pins (if your Screen Needs them)
## Software
- Minecraft Server with Web Software (i.e. Nginx, Apache, Jetty etc)
- Minecraft Transit Railway Mod (on the Minecraft server)
- Raspbian (or another linux distro)
- Display Drivers (if required, varies by what screen you have or bought)
## Notice
I am not responsible for anything that happens to you or your hardware/devices.
# Guide
## Minecraft Server
Step 1. Download the PID.html file and the London Underground Regular.ttf from the Repo.

Step 2. Replace all mentions of YOURIP with Your Server's IP in the PID.html file, if you have SSL on your server replace http with https.

Step 3. Upload your modified PID.html file and the London Underground Regular.ttf to your server's website files using FTP (Click [this](https://www.google.com/search?q=how+to+ftp+into+a+minecraft+server&sca_esv=247eb50602a83f19&sxsrf=ADLYWIJR3kGoJjZTtqZKw94yG_KOqH1T_w%3A1722005115959&source=hp&ei=e7ajZpeQOMi7hbIPgNHZ8QU&iflsig=AL9hbdgAAAAAZqPEi4LPnsZZ_mu6iU6azWEtswprxL18&oq=How+t&gs_lp=Egdnd3Mtd2l6IgVIb3cgdEgAUABYAHAAeACQAQCYAQCgAQCqAQC4AQzIAQCYAgCgAgCYAwCSBwCgBwA&sclient=gws-wiz&ved=0ahUKEwjXufH5-MSHAxXIXUEAHYBoNl4Q4dUDCB8) if you don't know how to FTP into your server) or if you have dynmap installed drop it into the web folder inside of the dynmap folder.
## Raspberry Pi (or other device)
Step 1. Flashing Raspbian (or another Linux distro) to your SD Card, I suggest using the Raspberry Pi Imager or Balena Etcher. 

Step 2. Plug your screen into your Pi (or similar device), install any drivers that your display may need. If your screen has its own Linux Distro or remix of Raspbian you may want to flash that to the SD Card Instead. 

Step 3. Insert your SD Card with the flashed OS into your Pi and then plug in the power and power on the device. 

Step 4. Set up Linux/Raspbian as normal (make sure you've got SSH enabled and know your username and password, by default it may be username: pi password: raspberry).

Step 5. SSHing into your Pi: Use an SSH app like Putty (Windows) or ConnectBot (Android). Once in type or paste: "sudo apt-get update
sudo apt-get install chromium-browser" without the quotations [(How to SSH?)](https://www.google.com/search?q=how+to+ssh+into+a+raspberry+pi&sca_esv=247eb50602a83f19&ei=Db6jZuPbLLLBhbIPx-7gqAg&ved=0ahUKEwijlvSVgMWHAxWyYEEAHUc3GIUQ4dUDCBA&uact=5&oq=how+to+ssh+into+a+raspberry+pi&gs_lp=Egxnd3Mtd2l6LXNlcnAiHmhvdyB0byBzc2ggaW50byBhIHJhc3BiZXJyeSBwaTILEAAYgAQYkQIYigUyCxAAGIAEGJECGIoFMgUQABiABDILEAAYgAQYkQIYigUyBBAAGB4yCxAAGIAEGIYDGIoFMggQABiABBiiBDIIEAAYgAQYogQyCBAAGIAEGKIESJElUPwDWNkbcAJ4ApABAJgBmAGgAeICqgEDMy4xuAEDyAEA-AEBmAIGoAL1AcICBBAAGEfCAgcQABiABBgNwgIGEAAYBxgemAMAiAYBkAYIkgcBNqAHsCQ&sclient=gws-wiz-serp).

Step 6. Unclutter: whilst SSH'd run "sudo apt-get install unclutter" in the terminal.

Step 7. Crontab: whilst SSH'd into your Pi's terminal type "sudo crontab -e" if prompted to select an editor type "1" then press enter, once in nano/crontab add
"@reboot unclutter -idle 0 &" 
to the bottom of the file.

Step 8. Auto-Start: In your Terminal (in ssh) type "sudo nano /etc/xdg/lxsession/LXDE-pi/autostart" and then add "@xset s off @xset -dpms @xset s noblank @chromium-browser --kiosk http://YOURSERVERIP:PORT/PID.html/ # load chromium after boot and open the website in full screen mode" (replace YOURSERVERIP with your server IP and PORT with the port your website is on) once done press CTRL-X and then Y and then press enter (this will save the file in nano).

Step 9. Restart your Pi (or similar device), once the pi boots after some time you should see the PID.html page.

If you've made it here and done all the steps you should be finished and now have your very own real life Mini Minecraft Transit Railway PID.
