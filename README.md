# De-10-nano-iota-pow-node

These are instructions to take a de-10 nano fpga with a cyclone V chip and use it as a pow node for iota. This fpga has 2 arm 32 bit cores and 2 gb ram ram and uses the ethernet connection to set up as a pow node. The image file comes ready to load onto an SD card and once it is loaded onto the card it will boot ubuntu 18.04. It has been pre loaded with kernel mod that is used to load the pow instructions. You will need to go to DLTcollab and clone dcurl then follow commands to make it for your nano. When the operating system is booted log into it with the user/pass ubuntu/temppwd.  You will find the kernel mod cpowdrv.ko in the main folder. In order to load the kernel it needs to be loaded as root with sudo insmod cpowdrv.ko.  You will need to go to DLTcollab and clone dcurl then clone the keccak pow node to your nano. These files are found in the links below. Then you can use the dcurl commands from their site to create the libdcurl.so file to use for your pow node.  You will need to copy the file to the main iota.keccak.pow.node.js folder.  Once in the folder you can change the port or any other info in the main.js file. Start main.js file using sudo or it wont read the .so file correctly with the kernel mod.

The download to the image file to burn to the sdcard.
https://drive.google.com/file/d/19KkvdSOrfzdIu9nH8WNp0dlvS3eXV10p/view?usp=sharing

You will need to install node.js 10 or newer. 

I want to make thank the following projects that helped me put all of this together in one place. 
This is a conglomerate of the following projects:

Firstly Lampa de10 nano project found here: https://github.com/LampaLab/iota_fpga
I took their image and updated it to work with the node iotapow software. I wasnt able to get it to function correctly with it being linux-gneaubi so i took it and updated it to gneaubihf.  I also updated the kernel to a newer version and got the cpowdrv.ko module updated and compiled to work for the newer kernel.

Secondly DLTcollab and their dcurl project that they have put together to make iota pow much quicker and easier found here: https://github.com/tylerw1369/dcurl


Thirdly SteppoFF for his pow node project called iota.keccak.pow.node written in JS found here: https://github.com/SteppoFF/iota.keccak.pow.node.js

Next Georg Mittendorfer and his piri project that is used as a load balancer to intercept the api call attachToTangle command and send it to the fpga. His project is found here: https://gitlab.com/georg.mittendorfer/piri

Also my node has the de10-nano as pow so its pretty fast if you want to use it.  Nodes address is:
https://www.iotaqubic.us:443

Steps:

Download image file and copy to sd

Start nano and login using ubuntu/temppwd

Install node js 10

Clone dcurl

Clone keccak.pow.node

Enter keccak.pow folder and run npm install

Make sure dip switches on the de10-nano are all set in the on position. 

Go to home folder with kernel mod

sudo insmod cpowdrv.ko 

CD to dcurl folder and run

make BUILD_FPGA_ACCEL=1 BUILD_COMPAT=1

CD to build folder and make sure libdcurl.so is in the directory

cp libdcurl.so /home/ubuntu/iota.keccak.pow.node.js/libccurl.so

Then enter the iota.keccak.pow.node.js and run

sudo node main.js

Enjoy your iota pow node


If you have any questions or anything doesnt work for you let me know and I will look at it.
If you want to donate you can here. Iota Address
UAYLMAJXMWENHKFCNJQZDZWAGAEKWYXFTMPXPQYUKYMOSJIYAJVJUTFMPMYTPKCBXDUCWIEEYOTSYMRFAKLWHKTUWD
