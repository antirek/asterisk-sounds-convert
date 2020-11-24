# asterisk-sounds-convert

## mp3 to wav 

> lame --decode file.mp3 - | sox -v 0.5 -t wav - -t wav -b 16 -r 8000 -c 1 file.wav

## ffmpeg compatible to wav

> ffmpeg -i file.m4a -ac 1 -ab 128k -ar 8000 -acodec pcm_s16le file.wav

NB: Get a list of supported decoders by running ``` ffmpeg -codecs | grep D[E.]```

## wav to mp3

> lame -V2 input.wav output.mp3

## gsm to wav

> sox input.gsm -r 8000 -c 1 -w -s ouput.wav

## wav to gsm

> sox input.wav -r 8000 -c 1 -t gsm output.gsm


## bulk

```bash
#!/bin/bash

for f in *.mp3; do
    lame --decode $f - | sox -v 0.5 -t wav - -t wav -b 16 -r 8000 -c 1 $(basename -s .mp3 $f).wav
done
```

## bulk ffmpeg

```bash
#!/bin/bash

for f in *.*; do 
    ffmpeg -i "$f" -ac 1 -ab 128k -ar 8000 -acodec pcm_s16le "${f%.*}.wav"
done
```

## wav to g722

http://wiki.innovaphone.com/index.php?title=Howto:Convert_wave_files_in_to_G722_coder_files


## wav to opus

/usr/bin/ffmpeg -i sound.wav -acodec libopus -ar 8000 -ab 8000 sound.ogg 

## opus to wav 

> opusdec --force-wav sound.ogg sound.wav

## wav repair

> sox -t raw -r 8000 -b 16 -c 1 -L -e signed-integer broken.wav fixed.wav


`````
when record to wav was broken
`````

## amr to mp3

> ffmpeg -i input.amr -ar 12000 output.mp3

