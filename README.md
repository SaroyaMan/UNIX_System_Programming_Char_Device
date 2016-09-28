# UNIX_System_Programming_Char_Device
This project is a char device that recieves frames and send them to any process who wants to read from it.
<br>This project made for Exercise 3 - UNIX System Programming course Shenkar semester C (Summer).
<br>Bonus implemented: Bonus date (submitted before Oct 1st).

### Notes:
- Please try to run it at least 2-3 times. the read_user sometimes flies on initializing.
- We assumed that synchronizing the video and playing audio is not important to this exercise.
- We assumed that the resolution of the video is not important to this exercise.
- Please note that writing 5+ videos to kernel - decreases the performence.
	
## Compile + insert the devices:
1. Compile the project with 'make' command.
2. sudo insmod write_chardev.ko
3. sudo insmod read_chardev.ko
4. sudo mknod /dev/write_char_dev c 101 0
5. sudo mknod /dev/read_char_dev c 100 0
	
## Clean + removing the devices:
1. Clean the project and any other cruft with 'make clean' command.
2. sudo rmmod read_chardev
3. sudo rmmod write_chardev
4. sudo rm /dev/write_char_dev
5. sudo rm /dev/read_char_dev
	
## How to run:
1. run the write_user.out application with up-to 10 arguments of video filenames.<br>
   Usage: .exe <video1> <video2>... <video10>
   Example: ./write_user.out movie.mp4 movie2.mp4
2. run the read_user.out application.
<br><br>**PLEASE quit first read_user app and only then quit write_user app.
	
## How to use:

write_user app:
- q - stop writing to kernel and quit the application.

read_user app:
- q- close the video screen and quit the application.
- 1,2,....,0 keys - change the video

## Made By
This application was created by Yoav Saroya (304835887) & Amit Shmuel (305213621) (All rights and etc are reserved!)
