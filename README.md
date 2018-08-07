# Exercise 3 - UNIX System Programming 

## This application was created by Yoav Saroya & Amit Shmuel 

## Cover Story

### You write a video control for smart home environment.

 
#### Exercise 1 – canapé (25%)
Start with chapter 7 in the Linux kernel module programming guide and implement a  2 char device with IOCTL read and write.
A user process can provide the kernel with content using one chardev and a second process can read content using the second char dev. 
Use 10 strings  of 1000 bytes (char [10000][10]) as your cameras. 
Support the read/write/lseek commands to read from the current tapes.
Support IOCTLs to change tape and format tape,

#### Exercise 2 – User code - backend  (25%)
Use dranger guide to write a code that communicate with kernel module and sends data to the kernel… send data from one of up to 10 cameras (AVI files) that simulate digital home 

#### Exercise 3 – User code - Frondend  (25%)
Use dranger guide to write a code that communicate with kernel module and displays frame from current camera. Switch cameras using 1234567890 keys (use SDLK_1 etc.) this process does not need to send 

#### Exercise 4 – add locking
Add spin locks or rw locks.

---

Please note that writing 5+ videos to kernel decreases the performence.


Compile + insert the devices:
	
- Compile the project with 'make' command.
	
- sudo insmod write_chardev.ko
	
- sudo insmod read_chardev.ko
	
- sudo mknod /dev/write_char_dev c 101 0
	
- sudo mknod /dev/read_char_dev c 100 0
	

Clean + removing the devices:
	Clean the project and any other cruft with 'make clean' command.
	
- sudo rmmod read_chardev
	
- sudo rmmod write_chardev
	
- sudo rm /dev/write_char_dev
	
- sudo rm /dev/read_char_dev
	

How to run:
	
- run the write_user.out application with up-to 10 arguments of video filenames.
	   
  Usage: .exe <video1> <video2>... <video10>
	   
  Example: ./write_user.out movie.mp4 movie2.mp4
	
- run the read_user.out application.
	

### PLEASE quit first read_user app and only then quit write_user app.
	
	
How to use:

	
- write_user app:
 q - stop writing to kernel and quit the application.

	
- read_user app:
  q- close the video screen and quit the application.
		
- 1,2,....,0 keys - change the video
