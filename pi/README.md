# Software for a Raspberry PI and 2065-Z80-programmer

To compile the flash tool, install:
```
sudo apt install libi2c-dev
```
Copy these files onto a PI and type `make`

To verify that your FLASH programmer board is recognized by the Raspberry PI,
use the `i2cdetect` application like this:

```
sudo apt install i2c-tools
pi@bot1:~/2065-Z80-programmer/pi$ i2cdetect -y 1
     0  1  2  3  4  5  6  7  8  9  a  b  c  d  e  f
00:          -- -- -- -- -- -- -- -- -- -- -- -- -- 
10: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- 
20: -- -- -- -- 24 -- 26 -- -- -- -- -- -- -- -- -- 
30: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- 
40: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- 
50: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- 
60: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- 
70: -- -- -- -- -- -- -- --                         
pi@bot1:~/2065-Z80-programmer/pi$ 
```

To program the FLASH, compile your code into a binary file
that begins at absolute address zero and run the flash app:

	flash < mycode.bin

If you cloned and built the test apps for the [2063-Z80](https://github.com/johnwinans/2063-Z80) Retro
project in your home directory then you can program and run blinky like this:

	./flash < ~/2063-Z80/tests/blinky1.bin

