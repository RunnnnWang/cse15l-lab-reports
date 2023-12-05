# Lab Report 5

## Part 1
### The Post
Hi, I am writing a function called merge that takes two List of String and returns a sorted new list. I am running everything inside a folder called lab report 5. It contains the java file ListExamples.java with the merge method, a junit test file called TestListExamples.java, and a bash file tesh.sh that runs ListExamples.java and TestListExamples.java. The screen shot below shows the bash file, the directory structure of what I just described and the code of my merge method.
<img width="1443" alt="Screen Shot 2023-12-03 at 12 24 46 PM" src="https://github.com/RunnnnWang/cse15l-lab-reports/assets/130102197/411dac58-3d1b-4beb-b9d6-5324411840fd">
This screenshot shows the content of the test.sh bash file. 
<img width="1130" alt="Screen Shot 2023-12-03 at 1 30 17 PM" src="https://github.com/RunnnnWang/cse15l-lab-reports/assets/130102197/3d934402-99d7-4cc7-ae36-04170b92b4d2">

This screenshot shows the failed test. 

<img width="649" alt="Screen Shot 2023-12-03 at 1 34 05 PM" src="https://github.com/RunnnnWang/cse15l-lab-reports/assets/130102197/e63d76a2-97bf-4c56-a981-50e3a49ebf38">

This is the actual code in code block. 

```java
import java.util.ArrayList;
import java.util.List;

interface StringChecker { boolean checkString(String s); }

class ListExamples {

  // Returns a new list that has all the elements of the input list for which
  // the StringChecker returns true, and not the elements that return false, in
  // the same order they appeared in the input list;
  static List<String> filter(List<String> list, StringChecker sc) {
    List<String> result = new ArrayList<>();
    for(String s: list) {
      if(sc.checkString(s)) {
        result.add(s);
      }
    }
    return result;
  }


  // Takes two sorted list of strings (so "a" appears before "b" and so on),
  // and return a new list that has all the strings in both list in sorted order.
  static List<String> merge(List<String> list1, List<String> list2) {
    List<String> result = new ArrayList<>();
    int index1 = 0;
    int index2 = 0;
    while(index1 < list1.size() && index2 < list2.size()) {
      if(list1.get(index1).compareTo(list2.get(index2)) < 0) {
        result.add(list1.get(index1));
        index1 += 2;
      }
      else {
        result.add(list2.get(index2));
        index2 += 1;
      }
    }
    while(index1 < list1.size()) {
      result.add(list1.get(index1));
      index1 += 1;
    }
    while(index2 < list2.size()) {
      result.add(list2.get(index2));
      index2 += 1;
    }
    return result;
  }  
}
```

It seems like the first merge test works but not the second one and we have the correct sorted part from the second input String List but not the first one. The symptom is that we are missing the word "cake" in the result List. The failure-inducing input is the String List with the content "a" and "cake". I guess the bug will be related to the way I process list 1. Could you give me some suggestions on how to fix the error? I am a little bit lost. 

### TA's Response
Hi, you are correct about the part where there might be something wrong with how you deal with list1. I suggest you run your test on a longer list for list1 along with a short list2 so you exit the first while loop early and pay attention to the pattern of the output along with what you get this time. Try to figure out which while loop that process list1 is not working. I will also give you a further hint that there is only one bug. 

### Student's reattempt
<img width="1225" alt="Screen Shot 2023-12-03 at 1 53 44 PM" src="https://github.com/RunnnnWang/cse15l-lab-reports/assets/130102197/fa45051f-a77a-4cf0-86e0-b26c0d6fdc6a">

I tried with a longer list and discovered that the second element of list1 is still missing in the final result but everything also is correct. There are two while loops that deal with list1. I then realized that the first while loop ends when "bob" is put into the list, and  because list1 is longer everything will be added one by one in the second while loop. I then looked at the second while loop that deals with list1 and didn't see any error. Then I went to the first while loop starting from line 28 and found that index1 adds by 2 every time instead of 1. So after "a" is added the index changes from 0 to 2 and then when the program runs the second while loop for list1 it adds to the new list starting from "eye" instead of "cake". After I changed index1 += 2 into index +=1 in line 31, everything worked as expected as shown below. 


<img width="878" alt="Screen Shot 2023-12-03 at 1 14 16 PM" src="https://github.com/RunnnnWang/cse15l-lab-reports/assets/130102197/aa3b0b5f-9e78-4a6a-aae3-e582258478f3">

This is the re-edited code in the code block. 

```java
import java.util.ArrayList;
import java.util.List;

interface StringChecker { boolean checkString(String s); }

class ListExamples {

  // Returns a new list that has all the elements of the input list for which
  // the StringChecker returns true, and not the elements that return false, in
  // the same order they appeared in the input list;
  static List<String> filter(List<String> list, StringChecker sc) {
    List<String> result = new ArrayList<>();
    for(String s: list) {
      if(sc.checkString(s)) {
        result.add(s);
      }
    }
    return result;
  }


  // Takes two sorted list of strings (so "a" appears before "b" and so on),
  // and return a new list that has all the strings in both list in sorted order.
  static List<String> merge(List<String> list1, List<String> list2) {
    List<String> result = new ArrayList<>();
    int index1 = 0;
    int index2 = 0;
    while(index1 < list1.size() && index2 < list2.size()) {
      if(list1.get(index1).compareTo(list2.get(index2)) < 0) {
        result.add(list1.get(index1));
        index1 += 1;
      }
      else {
        result.add(list2.get(index2));
        index2 += 1;
      }
    }
    while(index1 < list1.size()) {
      result.add(list1.get(index1));
      index1 += 1;
    }
    while(index2 < list2.size()) {
      result.add(list2.get(index2));
      index2 += 1;
    }
    return result;
  }  
}
```


## Part 2
I learned many cool command shortcuts for vim. Like d$ helps you to delete to the end of the line and a number with "w" helps you move that number of words forward. "G" helps me to move to the bottom of the file and "gg" helps me to move to the top of the file. Those vim commands are all very helpful as I am taking CSE30 right now and it speeds up my work.

