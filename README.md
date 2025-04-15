## Instruction to get working 3.5 inch TFT on Orange Pi Zero 2W

Tested on Waveshare 3.5 RPI Display and other copy-cat 3.5 TFT Display (need rotated)

```
git clone https://github.com/thanhtantran/orangepizero2w35tft.git && cd orangepizero2w35tft
sudo orangepi-add-overlay ./tft35-overlay.dts
```

It will ask for reboot but don't reboot yet, add more for touch, if you need it

```
sudo cp ./80-calibration.conf /usr/share/X11/xorg.conf.d
sudo cp ./99-fbdev.conf /usr/share/X11/xorg.conf.d
```

final step

```
sudo nano /etc/modules
```

then add `fbtft` into this, Cltr + X then Y to save the file. Now reboot, unplug the HDMI cable if you have.

Note: *If you use other copy-cat 3.5 TFT Display, you need to add into orangepiEnv.txt or armbianEnv.txt `extraargs=fbcon=rotate:2` to rotate the screen to the correct direction*
