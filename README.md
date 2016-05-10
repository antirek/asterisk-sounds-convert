# asterisk-sounds-convert

## mp3 to wav 

> lame --decode file.mp3 - | sox -v 0.5 -t wav - -t wav -b 16 -r 8000 -c 1 file.wav

## wav to mp3

> lame -V2 input.wav output.mp3
