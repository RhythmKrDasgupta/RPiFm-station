# Raspberry-Pi-Fm-station
The FM Transmitter project uses the general clock output on a Raspberry Pi to produce frequency modulated radio communication. The Raspberry Pi is a very useful computer that can be used for many different things. PiFM station is one of useful device. PiFM Transmitter play the sound over the air. This device normally works like real radio station. We can use this device in real life, suppose in an area where our phone network as well as internet is not working to communicate, in those area we can install this device for communication purpose on the other hand it’s a low-cost device we can used in our daily life to communicate in locality.


How to use it
To compile this project use commands below:

sudo apt-get install make gcc g++
make
Then you can use it by typing:

sudo ./fm_transmitter [-f frequency] [-r] filename
WAVE Files
You can open WAVE (.wav) files or read audio data from stdin, i.e.:

sox star_wars.wav -r 22050 -c 1 -b 16 -t wav - | sudo ./fm_transmitter -f 100.6 -
USB sound-card
To use a USB sound-card type this:

arecord -D hw:1,0 -c1 -d 0 -r 22050 -f S16_LE | sudo ./fm_transmitter -f 100.6 -
Some devices have problems with this command (there is a warning in the terminal like buffer overflow and after a few seconds - the transmitting gets slow and will stop), then you can use the following:

arecord -D plughw:1,0 -c1 -d 0 -r 22050 -f S16_LE | sudo ./fm_transmitter -f 100.6 -
Law
Please keep in mind that transmitting on certain frequencies without special permissions may be illegal in your country.

New features
works on RPi 1, 2 and 3
reads mono and stereo files
reads data from stdin
based on threads
