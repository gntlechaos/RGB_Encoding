# FCode
Processing based java application to encode .txt files into .png images and vice-versa

## Initial Ideas
The idea behind this project is to experiment a different way by which data (text in this case) can be shared. Also, it is a way of protecting it from immediate recognition, that makes this useful for those in need of an extra layer of lazyness-proof security (even though it doesn't grant any type of criptography (yet), it makes it harder to decode if you don't already know this specific application). It is also meant to be a different way of storing and sharing large texts in a different format, as some social media have character limits or simply don't let you share .txt's or documents that aren't images.

## How it works
The basic premise of this program is that the Unicode [Basic Latin](https://www.ssec.wisc.edu/~tomw/java/unicode.html#x0000) + [Latin-1-Supplement](https://www.ssec.wisc.edu/~tomw/java/unicode.html#x0080) characters can be represented by the decimal range of 0 - 255, and so are the RGBA colors of the pixels in a PNG image. So basically we encode each character to one of the RGBA channels of a pixel at a time. So an **X** by **Y** pixels image can store up to ```4*(X*Y)``` characters.

![alt text](https://github.com/gntlechaos/FCode/blob/master/ProjectImages/scheme.png?raw=true)

Based on that premise, the characters are encoded in the following order: first all red values in all pixels, then all green values and so on. All the values that aren't used to store any data are set to 255, but this can be changed by altering the ```final int nullCharCode = 255;``` variable in the FCode class.

![alt text](https://github.com/gntlechaos/FCode/blob/master/ProjectImages/scheme2.png?raw=true)
