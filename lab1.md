# Lab 1
## cd without argument
<img width="298" alt="Screen Shot 2023-10-03 at 11 28 23 AM" src="https://github.com/RunnnnWang/cse15l-lab-reports/assets/130102197/ab17648b-dc02-48b4-b1e6-ba5f4aa2fa49">

* Working directory: ~/lecture1 (lecture1 directory)
* cd changes the directory. My working directory changes to my home directory in this workspace. I got this output because cd without any argument cd will take you back to the home directory. 
* This is not an error. 

## ls without argument
<img width="190" alt="Screen Shot 2023-10-03 at 11 34 07 AM" src="https://github.com/RunnnnWang/cse15l-lab-reports/assets/130102197/011156a5-e3c2-49f6-886f-2ede79368957">

* Working directory: ~ (this workspace's home directory)
* ls prints the items in the current directory. Since I am in my workspace's home directory and there is only the lecture1 folder in it, lecture1 gets printed.
* There is no error.

## cat without argument
<img width="230" alt="Screen Shot 2023-10-03 at 11 40 30 AM" src="https://github.com/RunnnnWang/cse15l-lab-reports/assets/130102197/6f110ccb-22d3-429b-a937-17880c48f201">

* Working directory: ~ (this workspace's home directory)
* cat concatenates files and prints out their contents. In this command, because I don't put any argument after cat, it is waiting for me to put a directory and I stopped it with command+C.
* There is no error.

## cd with a path being a directory
<img width="262" alt="Screen Shot 2023-10-03 at 11 19 14 AM" src="https://github.com/RunnnnWang/cse15l-lab-reports/assets/130102197/6481fda4-7910-4afa-9b3a-67b58f9ddd33">
<br> 
<img width="233" alt="Screen Shot 2023-10-03 at 11 19 34 AM" src="https://github.com/RunnnnWang/cse15l-lab-reports/assets/130102197/a46c7265-c8df-4a18-b1f7-07a75fc86ebf">

* Working directory: this workspace's home directory
* I changed the directory to lecture1 and now in the next line you can see I am in the lecture1 directory.
* No error.

## ls with a path being a directory
<img width="412" alt="Screen Shot 2023-10-03 at 11 21 19 AM" src="https://github.com/RunnnnWang/cse15l-lab-reports/assets/130102197/17339742-4f98-4082-b99e-10464891a114">

* Working directory: lecture1
* I print the files list in this lecture1 directory and there are en-us.txt, es-mx.txt, ko-ko.txt, zh-cn.txt in the file. Thus, those files are printed in the terminal with a space to separate them.
* No error. 

## cat with a path being a directory
<img width="380" alt="Screen Shot 2023-10-03 at 11 21 25 AM" src="https://github.com/RunnnnWang/cse15l-lab-reports/assets/130102197/06ee0080-2055-4996-ae96-52c8ae7f4f2a">

* Working directory: lecture1
* cat messages try to print the content in the messages directory and print it in the terminal. However, cat can only do it for files so the output is saying this is not a file but a directory.
* No error. It is an information message.

## cd with a path being a file
<img width="393" alt="Screen Shot 2023-10-03 at 11 22 02 AM" src="https://github.com/RunnnnWang/cse15l-lab-reports/assets/130102197/5e94cde5-4435-415c-b01a-679034b58312">

* Working directory: ~/lecture1
* We try to change directory into the Hello.java file in this lecture1 folder. But because we can only change directory into another directory, the system prints out a message saying Hello.java is not a directory.
* This is an error because you can't change directory into a file.

## ls with a path being a file
<img width="435" alt="Screen Shot 2023-10-03 at 11 23 25 AM" src="https://github.com/RunnnnWang/cse15l-lab-reports/assets/130102197/d22fa802-9b9d-473d-8ab0-1a5456dca6c9">

* Working directory: ~/lecture1
* When using ls on a file, it will print the name of the file if it exists. In this case, the file en-us.txt exists in messages so messages/en-us.txt is printed to confirm its existence.
* No error.

## cat with a path being a file
<img width="452" alt="Screen Shot 2023-10-03 at 11 24 08 AM" src="https://github.com/RunnnnWang/cse15l-lab-reports/assets/130102197/4cd338e3-a3da-4499-995b-f6d489189bae">

* Working directory: ~/lecture1
* this command tries to print the message in en-us.txt which is in the messages directory. There is such a file so the content of it is printed as "Hello World!" in the terminal.
* No error. 








