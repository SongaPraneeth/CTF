**Description**:

The Rust saga continues? I ask you, can I borrow that, pleeeeeaaaasseeeee? Download the Rust code

**Steps to solve:**

step1: we will see that the file is compressed and archived, so first use command `gzip -d fixme2.tar.zip` to decompressed and use second command `tar -xf fixme2.tar` to un archive

step2: After executing the above two commands we will get a directory, now enter the directory, using the command `cd fixme1` and we will find two files and a folder.

step3: To run the rusts file first we have to compile it, so use command `cargo build` and to run use command `cargo run`, but after we have used the cargo build command it will show errors in the `[main.rs](http://main.rs)` file which is present in the `src` directory, so now we should see that in error there is a comment that tells what to do. 

step4: Use any preferred editor and remove the errors, and use commands `cargo build` to compile and `cargo run` to run the file and you will get the flag .

![image alt](https://github.com/SongaPraneeth/CTF/blob/b5e41ef578bfb831de71c691f587fd2c858bd300/CTFs%20Write%20ups/images/picoctf_images/general/Easy/Rust_fixme2_1.png)

![image alt](https://github.com/SongaPraneeth/CTF/blob/b5e41ef578bfb831de71c691f587fd2c858bd300/CTFs%20Write%20ups/images/picoctf_images/general/Easy/Rust_fixme2_2.png)

![image alt](https://github.com/SongaPraneeth/CTF/blob/b5e41ef578bfb831de71c691f587fd2c858bd300/CTFs%20Write%20ups/images/picoctf_images/general/Easy/Rust_fixme2_3.png)

![image alt](https://github.com/SongaPraneeth/CTF/blob/b5e41ef578bfb831de71c691f587fd2c858bd300/CTFs%20Write%20ups/images/picoctf_images/general/Easy/Rust_fixme2_4.png)

Before correcting the errors:

![image alt](https://github.com/SongaPraneeth/CTF/blob/b5e41ef578bfb831de71c691f587fd2c858bd300/CTFs%20Write%20ups/images/picoctf_images/general/Easy/Rust_fixme2_5.png)

After correcting the errors:

![image alt](https://github.com/SongaPraneeth/CTF/blob/b5e41ef578bfb831de71c691f587fd2c858bd300/CTFs%20Write%20ups/images/picoctf_images/general/Easy/Rust_fixme2_6.png)