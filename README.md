# De-10-nano-iota-pow-node

This is instructions to take a de-10 nano fpga with a cyclone V chip and use it as a pow node for iota.  
This fpga has 2 arm 32 bit cores and 2 gb ram ram and uses the ethernet connection to set up as a pow node. 
The image file come ready to load onto an SD card and once it is loaded onto the card it will boot ubuntu 18.04.
It has been pre loaded with all the necessary files to start your pow node immediately. 

I want to make thank the following projects that helped me put all of this together in one place. 
This is a conglomerate of the following projects:

Firstly Lampa de10 nano project found here

Secondly DLTcollab and their dcurl project that they have put together to make iota pow much quicker and easier found here

Thirdly SteppoFF for his pow node project called iota.keccak.pow.node written in JS. 

Next Georg Mittendorfer and his piri project that is used as a load balancer to intercept the api call attachToTangle command and send it to the fpga. 

