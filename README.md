# Smart Mirror

## members
Sion, Brenda Dzanja,Benjamin Tutemi Manyunya, Yire yoon
## Background & objective of research
Nowadays many people spend much time on the mirror perfecting their looks. As a result they end up being late to do other stuff. The Smart Mirror helps to solve this problem by offering information which gives a head start towards the day. Many people use smartphone or computer to check their daily information. However, it is not easy to check various inforamtion at once. This mirror will help the users to check information while doing any other job. Smart mirror is a small computer with Raspberry Pi. As it is easily modifialbe, we can display our necessary infomation for users.

## Step-by-step tutorial
1. install Raspberry Pi
download the Raspbian from the website and start the Raspberry Pi. It is recommended to download the latest full version.
  https://www.raspberrypi.org/
2. intall Smart mirror.
Automatic installation
```
bash -c "$(curl -sL https://raw.githubusercontent.com/MichMich/MagicMirror/master/installers/raspberry.sh)"
Manual Installation
```
Then following modules will be installed automatically. You can refer to these links to change options of each module such as positions, colors, images, size and so on.  
- [Clock](https://github.com/MichMich/MagicMirror/tree/master/modules/default/clock)
- [Calendar](https://github.com/MichMich/MagicMirror/tree/master/modules/default/calendar)
- [Current Weather](https://github.com/MichMich/MagicMirror/tree/master/modules/default/currentweather)
- [Weather Forecast](https://github.com/MichMich/MagicMirror/tree/master/modules/default/weatherforecast)
- [News Feed](https://github.com/MichMich/MagicMirror/tree/master/modules/default/newsfeed)
- [Compliments](https://github.com/MichMich/MagicMirror/tree/master/modules/default/compliments)
- [Hello World](https://github.com/MichMich/MagicMirror/tree/master/modules/default/helloworld)
- [Alert](https://github.com/MichMich/MagicMirror/tree/master/modules/default/alert)
3. Change settings
 - Installation of korean font 
 ```sudo apt-get --yes install fonts-nanum fonts-symbola```
 - Sound output
 check the speacker icon at the top right corner. choose either analog or HDMI.
 - Automatic start of Mirror
 ```
sudo npm install -g pm2
pm2 startup
sudo env PATH=$PATH:/usr/bin /usr/lib/node_modules/pm2/bin/pm2 startup systemd -u pi --hp /home/pi
pm2 start ~/MagicMirror/installers/pm2_MagicMirror.json
pm2 save
#### to mimimize the mirror --> ctrl + m
#### to start mirror --> pm2 start MagicMirror
#### to stop mirror --> pm2 stop MagicMirror
#### to restart mirror --> pm2 restart MagicMirror
```
4. weather and weather forecast module

5. google calendar
6. install google photo
3. install google assistant
MMM-Hotword and MMM-AssistantMk2 are required for google assistant>>
>> step1. installation of related programs
```
sudo apt-get --yes install libmagic-dev libatlas-base-dev sox libsox-fmt-all mpg321
cd ~/MagicMirror/modules/
git clone https://github.com/eouia/MMM-Hotword.git
git clone https://github.com/eouia/MMM-AssistantMk2.git
```
>> step2. installation of MMM-Hotword
 ```
cd ~/MagicMirror/modules/MMM-Hotword/
npm install
```
>> step3. installation of MMM-AssistantMk2
 ```
cd ~/MagicMirror/modules/MMM-AssistantMk2/
npm install
npm install --save-dev electron-rebuild
./node_modules/.bin/electron-rebuild
chmod +x ~/MagicMirror/modules/MMM-AssistantMk2/scripts/*.sh
 ```
>> step4. google API<br>
   Create a new project. https://console.actions.google.com/
   search for Google Assistant API from https://console.cloud.google.com/ and create a credentials.json.
   place the file into the "/home/pi/MagicMirror/modules/MMM-AssistantMk2/"
   then, type the following code:
   ```
cd ~/MagicMirror/modules/MMM-AssistantMk2/
node auth_and_test.js

# internet explore will open soon, then log in to the google and copy the code that appear on the screen and paste on the terminal.
# if you see "Type your request" on the screen, type

Hello

# if the response is working well, exit with typing [Ctrl+C]

mv token.json ./profiles/default.json
```
4. install remote controller

## Source code
1. installing Raspberry Pi and Smart Mirror 

  https://www.magicmirrorcentral.com/complete-raspberry-pi-magic-mirror-tutorial/

2. installing google assistant

  https://www.youtube.com/watch?v=UBgH5hejYtM&feature=youtu.be

## details


## Photos & videos
### Low fidelity(Paper prototyping)



## References

