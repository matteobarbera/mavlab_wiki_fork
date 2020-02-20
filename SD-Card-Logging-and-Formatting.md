## Downloading logs from Micro SD card

- the logging only works with <=2GB cards
- due to a [bug](https://github.com/paparazzi/paparazzi/issues/2092) only 43 logs can be written, than ALL the logs become unreadable, so keep this in mind and erase the card once in a while by formatting it via a PC card reader 
- to download the data via a card reader, use [this tool](https://github.com/tudelft/highspeedlogger/)
- download the code from github (e.g. 'download the zip'), build it with 'make' command, then go to /tools/bin/
- download the log from SD card by running 'sudo ./pprz_downloader /dev/sdb' or 'sudo ./pprz_downloader /dev/mmcblk0' (if none of the two work, check the device name with 'll /dev' after inserting the SD card into the reader)
- this creates binary 'sd_log_00000.bin','sd_log_00001.bin', etc. log files
- [this tool](https://github.com/paparazzi/paparazzi/blob/master/sw/logalizer/sd2log.ml) (part of your PPRZ installation) will convert the binaries into paparazzi logs
- go to 'paparazzi/sw/logalizer' and run './sd2log ~[path to the binaries]/sd_log_00000.bin'
- if you get errors, make sure your [environment variables](https://wiki.paparazziuav.org/wiki/Installation#Environment_Variables) are set correctly
  - The environment variables need to be changed in the .bashrc file. Go to the home directory and use command 'gedit ~/.bashrc'.
  - Add the lines described in the link at the bottom of the file.
  - Use command line 'source ~/.bashrc' in the home directory. To apply the changes made in the .bashrc file. The changes in the .bashrc file have to be done only once. 
  - If there are still errors, check if there are no spelling errors in the environment variables. If not, restart the computer.
- the paparazzi logs will be stored in 'paparazzi/var/logs' and can be viewed with the [paparazzi log plotter](https://wiki.paparazziuav.org/wiki/Plotter)
- [Matlab script](https://github.com/tudelft/mavlab/raw/master/scripts/read_pprz_MXS.m ] that loads the log into Matlab (if not working update according to messages.xml)

## Formatting the Micro SD card

When the maximum number of logs has been reached, the Micro SD card needs to be formatted. This can't be done with the formatting option in Windows or Mac or Linux, but needs to be done with an application.
- For Windows, this can be done using the SD Card Formatter application. Go to go to https://www.sdcard.org/downloads/formatter/eula_windows/, sroll to the bottom of the page and click 'accept' to download the ZIP-file.
- Extract the file and double click on 'SD Card Formatter 5.0.1 Setup'.
- Insert the SD Card. Make sure it is visible to your computer.
- Launch the program. Make sure the right SD-card is selected when multiple are connected to your computer in the tab 'Select Card'.
- Under Formatting options, select 'Overwrite format'.
- In the bar 'Volume Label' you can rename the SD-card if preferred.
- Click on 'Format' in the bottom right corner. 
- Check if the logs are removed using the procedure to Download Logs from the SD-card described above.