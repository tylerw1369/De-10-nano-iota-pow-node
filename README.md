# De-10-nano-iota-pow-node

This is instructions to take a de-10 nano fpga with a cyclone V chip and use it as a pow node for iota. This fpga has 2 arm 32 bit cores and 2 gb ram ram and uses the ethernet connection to set up as a pow node. The image file come ready to load onto an SD card and once it is loaded onto the card it will boot ubuntu 18.04. It has been pre loaded with all the necessary files to start your pow node immediately. When the operating system is booted log into it with the user/pass ubuntu/passwd.  You will find the kernel mod cpowdrv.ko in the main folder. In order to load the kernel it needs to be loaded as root with sudo insmod cpowdrv.ko.  Then you can use the dcurl commands from their site to create the libdcurl.so file to use for your pow node.  You will need to copy the file to the main iota.keccak.pow.node.js folder.  Once in the folder you can change the port or any other info in the main.js file. Start main.js file using sudo or it wont read the .so file correctly with the kernel mod.

I want to make thank the following projects that helped me put all of this together in one place. 
This is a conglomerate of the following projects:

Firstly Lampa de10 nano project found here: https://github.com/LampaLab/iota_fpga
I took their image and updated it to work with the node iotapow software. I wasnt able to get it to function correctly with it being linux-gneaubi so i took it and updated it to gneaubihf.  I also updated the kernel to a newer version and got the cpowdrv.ko module updated and compiled to work for the newer kernel.

Secondly DLTcollab and their dcurl project that they have put together to make iota pow much quicker and easier found here: https://github.com/DLTcollab/dcurl

Thirdly SteppoFF for his pow node project called iota.keccak.pow.node written in JS found here: https://github.com/SteppoFF/iota.keccak.pow.node.js

Next Georg Mittendorfer and his piri project that is used as a load balancer to intercept the api call attachToTangle command and send it to the fpga. His project is found here: https://gitlab.com/georg.mittendorfer/piri

