# asterisk-sounds-convert

## mp3 to wav 

> lame --decode file.mp3 - | sox -v 0.5 -t wav - -t wav -b 16 -r 8000 -c 1 file.wav

## wav to mp3

> lame -V2 input.wav output.mp3

## gsm to wav

> sox input.gsm -r 8000 -c 1 -w -s ouput.wav

## wav to gsm

> sox input.wav -r 8000 output.gsm resample -q1
