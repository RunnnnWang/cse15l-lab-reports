# Lab Report 5

## Part 1
### The Post
Hi, I am writing a function called merge that takes two List of String and returns a sorted new list. I am running everything inside a folder called lab report 5. It contains the java file ListExamples.java with the merge method, a junit test file called TestListExamples.java, and a bash file tesh.sh that runs ListExamples.java and TestListExamples.java. The screen shot below shows the bash file, the directory structure of what I just described and the code of my merge method.
<img width="1443" alt="Screen Shot 2023-12-03 at 12 24 46 PM" src="https://github.com/RunnnnWang/cse15l-lab-reports/assets/130102197/411dac58-3d1b-4beb-b9d6-5324411840fd">
This screenshot shows the content of the test.sh bash file. 
<img width="1130" alt="Screen Shot 2023-12-03 at 1 30 17 PM" src="https://github.com/RunnnnWang/cse15l-lab-reports/assets/130102197/3d934402-99d7-4cc7-ae36-04170b92b4d2">

This screenshot shows the failed test. 

<img width="649" alt="Screen Shot 2023-12-03 at 1 34 05 PM" src="https://github.com/RunnnnWang/cse15l-lab-reports/assets/130102197/e63d76a2-97bf-4c56-a981-50e3a49ebf38">

It seems like the first merge test works but not the second one and we have the correct sorted part from the second input String List but not the first one. The symptom is that we are missing the word "cake" in the result List. The failure-inducing input is the String List with the content "a" and "cake". I guess the bug will be related to the way I process list 1. Could you give me some suggestions on how to fix the error? I am a little bit lost. 

### TA's Response
Hi, you are correct about the part where there might be something wrong with how you deal with list1. I suggest you run your test on a longer list for list1 along with a short list2 so you exit the first while loop early and pay attention to the pattern of the output along with what you get this time. Try to figure out which while loop that process list1 is not working. I will also give you a further hint that there is only one bug. 

### Student's reattempt
<img width="1225" alt="Screen Shot 2023-12-03 at 1 53 44 PM" src="https://github.com/RunnnnWang/cse15l-lab-reports/assets/130102197/fa45051f-a77a-4cf0-86e0-b26c0d6fdc6a">

The student tried with a longer list and discovered that the second element of list1 is still missing in the final result but everything also is correct. There are two while loops that deal with list1. She knows that the first while loop ends when "bob" is put into the list, and then because list1 is longer everything will be added one by one in the second while loop. She checks the second while loop that deals with list1 and doesn't see any error. Then she goes to the first while loop starting from line 28 and finds that index1 adds by 2 every time instead of 1. So after "a" is added the index changes from 0 to 2 and then when the program runs the second while loop for list1 it adds to the new list starting from "eye" instead of "cake". After she changes the index1 += 2 into index +=1 in line 31, everything works as expected as shown below. 

<img width="878" alt="Screen Shot 2023-12-03 at 1 14 16 PM" src="https://github.com/RunnnnWang/cse15l-lab-reports/assets/130102197/aa3b0b5f-9e78-4a6a-aae3-e582258478f3">

## Part 2
I learned many cool command shortcuts for vim. Like d$ helps you to delete to the end of the line and a number with "w" helps you move that number of words forward. "G" helps me to move to the bottom of the file and "gg" helps me to move to the top of the file. Those vim commands are all very helpful as I am taking CSE30 right now and it speeds up my work.

