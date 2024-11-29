# OS-Lab-Exams
Operating System Lab Exam Questions
## Q1 (CPU, Files) ++++
1. First create a directory with name of ```OS Exam```, Attention that ```space character``` is required between ```OS``` and ```Exam```.
2. In created directory, create a file named ```cpu_info.txt```.
3. With related commands, show your system's CPU information, then look for item ```CPU max Hz``` and write down your cpu frequency inside ```cpu_info.txt``` file.
4. Create another directory named ```Backup Directory```.
5. Copy ```cpu_info.txt``` to ```Backup Directory``` with any name you like.
6. In the main ```cpu_info.txt``` file write your name at the end of file then save it.
7. Show contents of both main and copied files.
#### Solution (Execute each line separately)
```bash
mkdir OS\ Exam                           # or mkdir 'OS Exam'                 # - Step 1
touch cpu_info.txt                                                            # - Step 2
lscpu                                    # look for value of CPU max Hz       # - Step 3
nano cpu_info.txt                        # and write value in it              # - Step 3
mkdir Backup\ Directory                  # or mkdir 'Backup Directory'        # - Step 4
cp cpu_info.txt Backup/copy_file.txt                                          # - Step 5
nano cpu_info.txt                        # then write your name in the end    # - Step 6
cat cpu_info.txt                                                              # - Step 7
cat Backup/copy_file.txt                                                      # - Step 7
```

## Q2 (Storage, Memory, Files) ++++
1. First create a directory with name of ```OS Exam```, Attention that ```space character``` is required between ```OS``` and ```Exam```.
2. In created directory, create a file named ```storage_report.txt```.
3. With related commands, show your system's Storage information in ```human readable mode```, then look for free storage available at ```Root Directory ('/')``` and write down inside ```storage_report.txt``` file.
4. Create another file named ```memory report.txt```, Attention that ```space character``` is required between ```memory``` and ```report.txt```.
5. With related commands, show your system's Memory information in ```human readable mode```, then look for used memory at and write down inside ```memory report.txt``` file.
6. Show contents of both files.
#### Solution (Execute each line separately)
```bash
mkdir OS\ Exam                           # or mkdir 'OS Exam'                 # - Step 1
touch storage_report.txt                                                      # - Step 2
df -h                                    # -h shows numbers in GB or MB       # - Step 3
nano storage_report.txt                  # and write value in it              # - Step 3
touch 'memory report.txt'                                                     # - Step 4
free -h                                  # look for used column               # - Step 5
nano memory\ report.txt                  # and write value in it              # - Step 5
cat storage_report.txt                                                        # - Step 6
cat memory\ report.txt                                                        # - Step 6
```

## Q3 (Network, Secure Shell) +++
1. With related commands, show your system's Network information, then look for information about ```localhost``` or shortly ```lo``` and write down its IP.
2. With related commands, check your system's network connection with wrote down IP.
3. With related commands, show your username.
4. With related commands, establish a secure connection session from your system to that wrote down IP.
5. In established secure connection session, show information and listener ports of your system.
```bash
ifconfig                                 # IP of localhost is 127.0.0.1       # - Step 1
ping 127.0.0.1                           # find text time and write its 'ms'  # - Step 2
whoami                                                                        # - Step 3
ssh user@127.0.0.1                       # write result of step 3 in user     # - Step 4
netstat -tuln                                                                 # - Step 5
```

## Q4 (Network, Fun, Internet Required) ++
1. Connect yoru system to the internet.
2. With related command, show contents of web page with link of ```ascii.live/can-you-hear-me``` in your terminal.
3. Also show contents of ```ascii.live/forrest```.
4. Check your connection quality and speed to both links.
```bash
curl ascii.live/can-you-hear-me          # full screen your terminal          # - Step 2
curl ascii.live/forrest                                                       # - Step 3
ping ascii.live/can-you-hear-me                                               # - Step 4
ping ascii.live/forrest                                                       # - Step 4
```

## Q5 (Network, Gateways, Internet Required) +++
1. Connect your system to the internet.
2. With related command, trace routes of your system's network packets to the ```google.com```.
3. In routes you found, look for route with title of ```gateway``` then wrote down its IP.
4. Check your connection quality of wrote down gateway IP and save it to file named ```pong.txt```.
5. With related command of converting domain to IP and vice versa, show IP of ```google.com```.
6. Do step 4 for step 5 again.
```bash
trace google.com                                                              # - Step 2
# answer is 192.168.1.1                                                       # - Step 3
ping 192.168.1.1 -c 1 > pong.txt         # -c 1 pings only 1 time             # - Step 4
nslookup google.com                                                           # - Step 5
ping google.com -c 1 >> pong.txt         # >> appends, > rewrite              # - Step 6
```

## Q6 (Files, Search, Root Directories) +++
1. Create a directory with any name you like.
2. Copy file with name of ```cpuinfo``` from you system's root directory path ```/proc/cpuinfo``` to your created directory.
3. With related command, look for text ```MHz``` in copied ```cpuinfo``` file.
4. Do step 3 but add related command that saves output of search result into a file named ```results.txt```.
```bash
mkdir directory                                                               # - Step 1
cp /proc/cpuinfo directory/                                                   # - Step 2
cat directory/cpuinfo | grep 'MHz'                                            # - Step 3
cat directory/cpuinfo | grep 'MHz' > results.txt                              # - Step 4
```

## Q7 (Zip, Unzip, Directories, Echo, Files) +++
1. First create a directory named ```Backup```.
2. Inside the directory, create two files: ```file1.txt``` and ```file2.txt```.
3. Write your full name into ```file1.txt``` using the ```echo``` command and ```redirect the output to file```.
4. Write your student id into ```file2.txt``` using the ```echo``` command and ```redirect the output to file```.
5. Compress both files into zip file named ```archive.zip```.
6. Delete ```file1.txt``` and ```file2.txt```.
7. Extract the contents of ```archive.zip``` into created directory with name of ```Backup```.
8. Show contents of both files.
```bash
mkdir Backup                                                                  # - Step 1
touch Backup/file1.txt Backup/file2.txt                                       # - Step 2
echo "Fullname" > Backup/file1.txt       # write your name in Fullname        # - Step 3
echo "12456..." > Backup/file2.txt       # write your student id              # - Step 4
zip Backup/file1.txt Backup/file2.txt archive                                 # - Step 5
rm -rf Backup/*                                                               # - Step 6
unzip archive.zip                                                             # - Step 7
cat file1.txt                                                                 # - Step 8
cat file2.txt                                                                 # - Step 8
```
