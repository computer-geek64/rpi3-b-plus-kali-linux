# Raspberry Pi 3 Model B+ Kali Linux Installation
*September 19th, 2018*

## Dependencies
* Linux operating system, preferrably existing Kali Linux OS
* sha256sum
* xzcat
* dd

## Installation
1. **Download the image.** Visit the [Kali Linux ARM Images](https://www.offensive-security.com/kali-linux-arm-images/#1493408272250-e17e9049-9ce8) website and download the correct image. For the Raspberry Pi 3 Model B+, the correct image is labeled [**Kali Linux RaspberryPi 2 and 3**](https://images.offensive-security.com/arm-images/kali-linux-2018.3-rpi3-nexmon.img.xz) (This link is valid for version **2018.3**).
1. **Verify the installation.** Obtain the SHA256 checksum of the file that you downloaded with the `sha256sum` tool. Open Bash and run this command (replace the filename with the correct filename): `sha256sum kali-linux-2018.3-rpi3-nexmon.img.xz` If the computed checksum matches that provided on the [website](https://www.offensive-security.com/kali-linux-arm-images/#1493408272250-e17e9049-9ce8), then you can proceed with installing Kali Linux. The SHA256 checksum for version 2018.3 is **a90717c67cd914e01a2f885a308b06f70cf9276c8760f1fa71a0ae372e341673**.
1. **Determine the correct drive.** Use the *fdisk* utility to find the correct drive for your micro SD card. Run `fdisk -l` to view all drives, and determine the correct one. It should appear as something similar to */dev/sdb*.
1. **Flash the image.** Run the following command on the verified download file (replace the filename with the correct filename and the drive with the correct drive): `xzcat kali-linux-2018.3-rpi3-nexmon.img.xz | dd of=/dev/sdb bs=512k`
1. **Run Kali Linux.** Unmount, eject, and insert the SD card into your Raspberry Pi 3 Model B+. Connect the Raspberry Pi to a 5V DC 1.5A micro USB power supply, and log in with the username *root* and the password *toor*.
1. **Update the Raspberry Pi.** Run the following commands to obtain the latest software and packages after configuring the network connection:
```bash
apt-get update
apt-get dist-upgrade
apt-get autoremove
apt-get autoclean
```

## Authors
* **Ashish D'Souza** - *Sole developer* - [computer-geek64](https://github.com/computer-geek64)

## APA Reference and Citation
* D'Souza, A. (2018, September 19). Raspberry Pi 3 Model B+ Kali Linux Installation. Retrieved from https://github.com/computer-geek64/rpi3-b-plus-kali-linux/blob/master/README.md
* (D'Souza, 2018)

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
