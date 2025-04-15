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


![z6506530914643_1c04a1ab2b3cc415c5a6ba0378110fed](https://github.com/user-attachments/assets/f225cab7-e509-414a-996a-bf150365dca0)
![z6506530928516_65be7e0fcc2e1f1c8192e38af1063141](https://github.com/user-attachments/assets/b1d750cc-561d-4d52-b6a6-e0a6ba8505d2)
![z6506530914409_d24a184392dd60ac50f3587694f7b38e](https://github.com/user-attachments/assets/3307d79a-a2d6-4ebe-ab30-4a0a6185ba42)
![z6506530912370_e5b43f08ce25550f3cca35585af400f2](https://github.com/user-attachments/assets/a749e7c7-7b33-4397-89a0-4ec1f601add4)
