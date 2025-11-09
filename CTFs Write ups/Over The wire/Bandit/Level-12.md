Level Goal:

The password for the next level is stored in the file **data.txt**, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work. Use mkdir with a hard to guess directory name. Or better, use the command “mktemp -d”. Then copy the datafile using cp, and rename it using mv (read the manpages!)

Steps to solve:

 

step 1 : use `ls` to locate file and after that use `file data.txt` command to see the type of file  and read the file with `cat data.txt` command then we will see the hex dump 

![image alt](https://github.com/SongaPraneeth/CTF/blob/fae3ccfc95a09337a2390be80f1cf34fbe0b90ce/CTFs%20Write%20ups/images/bandit_images/bandit12.png)

step2:  we will now make a temporary directory as said in the level goal, using command `mktemp -d`  . This command will generate directory with a random name.

step3: Then copy the file into the directory using command `cp data.txt /tmp/tmp.xxxxxx`

step4: Now use `cd /tmp/tmp.xxxxxx` to enter the directory

step : Check whether the file is present or not using ls

step6: now as we know that the file’s data is in hex dump so we will retrieve the data into binary format and store it into another file using command `xxd -r data.txt first`

step7: now check the file type using `file first` and it will tell it is gzip compressed. So the data which is retrieved and transformed into binary is compressed in gzip format

![image alt](https://github.com/SongaPraneeth/CTF/blob/fae3ccfc95a09337a2390be80f1cf34fbe0b90ce/CTFs%20Write%20ups/images/bandit_images/bandit12.1.png)

step8: Now change the file name from first to first.gz as we have to decompress the file which is gzip compressed. use `mv first first.gz` to change the name

step9: Use `ls` and see whether the file color and name is changed

step10 : Use `gzip -d first.gz` to decompress and after decompress the file color and the `.gz` will be removed from the file name 

step10 : Check the file type by `file first` , now it will tell it is bzip2 compressed. So the data which is decompressed from gzip format was compressed in bzip2 

![image alt](https://github.com/SongaPraneeth/CTF/blob/fae3ccfc95a09337a2390be80f1cf34fbe0b90ce/CTFs%20Write%20ups/images/bandit_images/bandit12.2.png)

step11: So change the name of the file using `mv first first.bz2`

step12: check for the name and color of the file using ls

step13: decompress by command `bzip2 -d first.bz2` and after decompress use ls to see the color and name `.bz2` will be changed

step14: now check the file  using `file first`, it will the data is gzip compressed, so the data which was decompressed was gzip compressed .

![image alt](https://github.com/SongaPraneeth/CTF/blob/fae3ccfc95a09337a2390be80f1cf34fbe0b90ce/CTFs%20Write%20ups/images/bandit_images/bandit12.3.png)

step15: now change the file name and decompress it using command `mv first first.gz`   `gzip -d first.gz`

step16: Now check the data type in file using `file first` and we will see posix tar archive. So the data which was decompressed was archived by tar.

![image alt](https://github.com/SongaPraneeth/CTF/blob/fae3ccfc95a09337a2390be80f1cf34fbe0b90ce/CTFs%20Write%20ups/images/bandit_images/bandit12.4.png)

step17: change the name using `mv first first.tar`

step18: the color will change 

step19: now using `tar -xf first.tar` , we will extract the data present in the first.tar file,

step20: we will find data5.bin file in the first.tar file, so check for the data type of the data5.bin file, using `file data5.bin`, we will find that it is also tar archived. so repeat the step 17,18 and 19.

step21: Now we will find another file data6.bin in the data5.bin file, 

![image alt](https://github.com/SongaPraneeth/CTF/blob/fae3ccfc95a09337a2390be80f1cf34fbe0b90ce/CTFs%20Write%20ups/images/bandit_images/bandit12.5.png)

step22: now check the data type of the data6.bin file using `file data6.bin` 

step23: It will tell that it is bzip2 compressed. So the file which was extracted from the first.tar was data5.bin, which is also archived and after extracting the data5.bin, we find another file called data6.bin, which the data bzip2 compressed

step24: So change the name using `mv data6.bin data6.bz2` , so the color will be change which you can see using the `ls` command

step25: decompress by `bzip2 -d data6.bz2` and after decompress the color and the name of the file will be changed

step26: Now check the data type of data6 using file data6 and it will tell it is tar archive

step25: So change the name of the file and you will see the color change and extract by using the command `mv data6 data6.tar`    `tar -xf data6.tar` 

step26: And after extracting the data6.tar we will get data8.bin file 

![image alt](https://github.com/SongaPraneeth/CTF/blob/fae3ccfc95a09337a2390be80f1cf34fbe0b90ce/CTFs%20Write%20ups/images/bandit_images/bandit12.6.png)

step27: Check the data type using `file data8.bin` and it will tell you that it is gzip compressed

step28: so change the name by `mv data8.bin data8.gz`

step28: and decompress using `gzip -d data8.gz`

step29: After decompressing check for the data type by `file data8` , it will tell it is ACII text (it means human readable)

step30 : Use `cat data8` to read the file

![image alt](https://github.com/SongaPraneeth/CTF/blob/fae3ccfc95a09337a2390be80f1cf34fbe0b90ce/CTFs%20Write%20ups/images/bandit_images/bandit12.7.png)

To understand how the data was compressed follow the steps in the pictures from last to beginning 

### Command:

```bash
xxd -r data.txt first
```

### What it does:

This command **converts a hex dump back into binary data** using the `xxd` utility.

### Breakdown:

- `xxd`: A tool that can create a hex dump from a binary file or reverse a hex dump back to binary.
- `r`: Stands for **reverse** mode. It tells `xxd` to convert **from hex to binary** (instead of the default binary to hex).
- `data.txt`: The **input file** that contains the hex dump.
- `first`: The **output file** that will store the resulting binary data.

### **Command:**

```bash
mktemp -d

```

### **Breakdown:**

- `mktemp`: A command-line utility used to **create a temporary file or directory** with a unique name.
- `d`: This option tells `mktemp` to **create a directory** instead of a file.