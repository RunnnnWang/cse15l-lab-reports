# Lab Report 5

## Part 1
### The Post
Hi, I am writing a function called merge that takes two List of String and returns a sorted new list. This is the code for my method. I am running everything inside of a file called lab report 5. It contains the java file containing the method called ListExamples.java, and the junit test file called TestListExamples.java and a bash file tesh.sh that runs ListExamples.java and TestListExamples.java. The screen shot below shows the file and directory structure of what I just described and the code of my merge method.
<img width="1443" alt="Screen Shot 2023-12-03 at 12 24 46 PM" src="https://github.com/RunnnnWang/cse15l-lab-reports/assets/130102197/411dac58-3d1b-4beb-b9d6-5324411840fd">

This screenshot is the test that fails the failure output. 
<img width="1137" alt="Screen Shot 2023-12-03 at 12 29 24 PM" src="https://github.com/RunnnnWang/cse15l-lab-reports/assets/130102197/f780439b-e19e-4df0-b4e1-b2c7775c844a">
It seems like the first merge test works but not the second one and we have the correct sorted part from the second input String List but not the first one. I guess there must be something wrong with how I process list 1. Could you give me some suggestions on how to fix the error? I am a little bit lost. 

### TA's Response
Hi, you are correct about the part where there might be something wrong with how you deal with list1. I suggest you running your test on longer list for list1 with a short list2 so you exit the first while loop early pay attention to the pattern of the output. I will also give you a further hint that there is only one bug. 

### Student's reattempt
<img width="897" alt="Screen Shot 2023-12-03 at 1 05 26 PM" src="https://github.com/RunnnnWang/cse15l-lab-reports/assets/130102197/08ff2edb-d06e-4fd0-97ce-da8176c28dcb">
The student tried with a longer list and discovers that the second element of list1 is missing in the final result but everything also is correct. She knows that the first while loop ends when "bob" is put into the list, and then because list1 is longer everything will be added in one by one. She checks the second while loop and finds doesn't see any error. Then she goes to the first while loop and finds that index1 adds by 2 every time instead of 1. So after after "a" is added the index changes from 0 to 2 and then when she runs the second while loop it adds starts from "eye" instead of "cake". After she changes the index1 += 2 into index +=1 in line 31, everything works as expected as shown below. 
<img width="878" alt="Screen Shot 2023-12-03 at 1 14 16 PM" src="https://github.com/RunnnnWang/cse15l-lab-reports/assets/130102197/aa3b0b5f-9e78-4a6a-aae3-e582258478f3">

## Part 2
I learned many cool command shortcuts for vim. Like d$ helps you to delete to the end of the line and a number with "w" helps you move that number of words forward. "G" helps me to move to the bottom of the file and "gg" helps me to move to the top of the file. Those vim commands are all very helpful as I am taking CSE30 right now and it speeds up my work.

