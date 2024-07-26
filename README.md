# MTR-MC-PID
A Mini Minecraft Transit Railway PID in Real Life! \
GIF (or image) of PID here.
# Pre-Requisites
## Hardware
- Raspberry Pi (or another similar device) 
- 3.5 Inch SPI Screen 
- SD Card (sufficent enough to store Raspbian) 
- GPIO Pins (if your display is connected via the GPIO pins) 
- Power Cable (for RPI or similar device)
## Software
- Minecraft Server with Web Software (i.e. Nginx, Apache, Jetty etc.)
- Minecraft Transit Railway Mod
- Raspbian (or another linux distro)
- Display Drivers (if required, varies by what screen you have or bought)
## Notice
I am not responsibile for anything that happens to you or your hardware/devices.
# Guide
## Minecraft Server
Step 1. Download the PID.html file and the London Underground Regular.ttf from the Repo.

Step 2. Replace all mentions of YOURIP with Your Server's IP in the PID.html file, if you have SSL on your server replace http with https.

Step 3. Upload your modified PID.html file and the London Underground Regular.ttf to your server's website files using FTP (Click [this](https://www.google.com/search?q=how+to+ftp+into+a+minecraft+server&sca_esv=247eb50602a83f19&sxsrf=ADLYWIJR3kGoJjZTtqZKw94yG_KOqH1T_w%3A1722005115959&source=hp&ei=e7ajZpeQOMi7hbIPgNHZ8QU&iflsig=AL9hbdgAAAAAZqPEi4LPnsZZ_mu6iU6azWEtswprxL18&oq=How+t&gs_lp=Egdnd3Mtd2l6IgVIb3cgdEgAUABYAHAAeACQAQCYAQCgAQCqAQC4AQzIAQCYAgCgAgCYAwCSBwCgBwA&sclient=gws-wiz&ved=0ahUKEwjXufH5-MSHAxXIXUEAHYBoNl4Q4dUDCB8) if you don't know how to FTP into your server) or if you have dynmap installed drop it into the web folder inside of the dynmap folder.
## Raspberry Pi (or other device)
Step 1. Flash Raspbian (or another Linux distro) to your SD Card. 

Step 2. Plug your screen into your Pi (or similar device), install any drivers that your display may need. If your screen has its own Linux Distro or remix of Raspbian you may want to flash that to the SD Card Instead. 

Step 3. Insert your SD Card with the flashed OS into your Pi and then plug in the power and power on the device. 

Step 4. Set up Linux/Raspbian as normal (make sure you've got SSH enabled and know your username and password, by default it may be username: pi password: raspberry).

Step 5. SSHing into your Pi, Use an SSH app like Putty (Windows) or ConnectBot (Android). Once in type or paste: "sudo apt-get update
sudo apt-get install chromium-browser" without the quotations.

Step 6. Unclutter: whilst SSH'd run "sudo apt-get install unclutter" in the terminal.

Step 7. Crontab: whilst SSH'd into your Pi's terminal type "sudo crontab -e" if prompted to select an editor type "1" then press enter, once in nano/crontab add
"@reboot chromium-brower --start-fullscreen http://YOURSERVERIP:PORT/PID.html &
@reboot unclutter -idle 0 &" 
to the bottom of the file (replace YOURSERVERIP with your server ip and PORT with the port your website is on).

Step 8. Restart your Pi (or similar device), once the pi boots after some time you should see the PID.html page.

If you've made it here and done all the steps you should be finished and now have your very own real life Mini Minecraft Transit Railway PID.
