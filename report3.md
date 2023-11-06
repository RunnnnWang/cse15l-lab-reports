# Lab Report 3
## Part 1 - Bugs
### Failure Inducing Input as Code
```java
@Test
  public void testReversedInPlace(){
    int[] input = {1, 2, 3, 4, 5};
    int[] output = {5, 4, 3, 2, 1};
    ArrayExamples.reverseInPlace(input);
    assertArrayEquals(output, input);
  }
```

### Non-Failure Inducing Input
```java
 @Test
  public void testReversedInPlaceOK(){
    int[] input = {1, 1, 1};
    int[] output = {1, 1, 1};
    ArrayExamples.reverseInPlace(input);
    assertArrayEquals(output, input);
  }
```
### Symptom

<img width="796" alt="Screen Shot 2023-11-05 at 8 20 15 PM" src="https://github.com/RunnnnWang/cse15l-lab-reports/assets/130102197/7b0b7653-b1b9-4148-99ef-16d47b1b47dd">

### The Bug
Code Before
```java
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```

Code After
```java
 static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length/2; i += 1) {
      int value = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length - i - 1] = value;
    }
  }
```
The issue before is that we only swapped the value from the back to the front without putting the front value to the back and we iterated for the length of the array. The fixes are that I saved the beginning value in a variable called value and assigned it to the variables from the back after we assigned the beginning value with the back value so the values are swapped. I also make it iterate through half of the array so we won't swap the values back. 

## Part 2 - Grep
### Grep -i
```
(base) MacBook-Pro-122:technical outakaratakara$ grep -i "protein" biomed/rr74.txt
        hypoxia from birth and measured NOS mRNA and protein
        NOS protein in the lung as assessed using
          protein and RNA measurement, and the left lung was fixed
          centrifuged twice at 4°C and 14,000 rpm. Protein
          (Bio-Rad Laboratories, Hercules, CA, USA). Protein 10 μg
          lipopolysaccharide-treated mouse spleen protein and
          nNOS-positive control was mouse brain protein.
          As shown in Fig. 2, lung eNOS protein levels were
          However, iNOS protein was below the limit of detection
        The increase in eNOS protein and mRNA levels, and the
        of eNOS protein was increased in hypoxic, hypertensive rat
        protein levels were increased in rats with hypoxic
        transcription factor activator protein-1 during hypoxia may
        was increased but iNOS protein remained below the limit of
        both iNOS mRNA and protein levels in rat lungs following
        protein, using several different antibodies, in mice. This
        iNOS protein levels in adult mice following hypoxia was
        that lung iNOS protein was detectable only after
        redox sensitive nuclear factor-κB or activator protein-1 [
        translation or degradation of iNOS protein. In support of
        and protein levels in the aorta of rats following prolonged
        increase in eNOS protein levels in the lungs. Conversely,
        uptake [ 43], decreased heat shock protein-90 levels [ 44],
```
This is searching the string with the word protein in it. It displaces sentences with "protein" and "Protein" because it's case insensitive. It is helpful because we can quickly identify the sentences with keywords.

```
(base) MacBook-Pro-122:technical outakaratakara$ grep -i Lorazepam  biomed/cc3.txt
            lorazepam 4-5 mg or 10 mg intramuscular morphine, was
            Lorazepam
        midazolam (Figs 4and 5), lorazepam (Fig 6), and fentanyl
```
It searches the word "Lorazepam" in boimed/cc3.txt in the technical directory and displays the sentence that matches it. We can see that even though we didn't put quotation marks around "Lorazepam" it still searches. It is helpful because it might be hard to find a single word in a big essay but this searches for you quickly. 

### Grep -c
```
(base) MacBook-Pro-122:technical outakaratakara$ grep -c protein biomed/rr74.txt
21
```
The -c command option displays the count of the sentence that contains the word "protein". It says 21 which is consistent with the output above. It is helpful because we can tell that protein is mentioned quite a few times in the file. 


```
(base) MacBook-Pro-122:technical outakaratakara$ grep -c "Lorazepam"  biomed/cc3.txt
1
```
The -c command option displays the count of the sentence that contains the word "Lorazepam". It says 1 which is consistent with the output above. It's helpful because we can see the frequency of the specific word.

### Grep -l
```
(base) MacBook-Pro-122:technical outakaratakara$ grep -l "1471" biomed/*.txt
biomed/1471-2202-2-8.txt
biomed/1471-2202-2-9.txt
biomed/1471-2474-2-3.txt
```
The -l command option displays any file with a name containing the string "1471" and with the pattern biomed/*.txt. In this case, the technical directory finds biomed/1471-2202-2-8.txt, biomed/1471-2202-2-9.txt, and biomed/1471-2474-2-3.txt. It is helpful because we can quickly find the files with the name we want.

```
(base) MacBook-Pro-122:technical outakaratakara$ grep -l "CSPGs" biomed/1471-2202-2-8.txt biomed/1471-2202-2-9.txt
biomed/1471-2202-2-8.txt
```
If there are multiple files provided, the -l command will return you the file that contains the string. In this case, only biomed/1471-2202-2-8.txt contains the string "CSPGs" so that is what the command returns. It is helpful because we can quickly know which file is useful by trying to see if it contains the specific word we want. 

### Grep -o
```
(base) MacBook-Pro-122:technical outakaratakara$ grep -o "protein" biomed/1476-4598-1-6.txt
protein
protein
protein
protein
protein
protein
protein
protein
protein
protein
protein
protein
protein
protein
protein
protein
protein
protein
protein
protein
protein
protein
protein
protein
protein
protein
protein
```
The -o command only displays the string we want to search for. In this case, it displays all the word protein the file 1476-4598-1-6.txt has. It is useful because from this we know the article talks about protein a lot. 

```
(base) MacBook-Pro-122:technical outakaratakara$ grep -o "life" biomed/1476-4598-1-6.txt
life
life
```
The -o command only displays the string we want to search for. In this case, it displays all the word life in the file 1476-4598-1-6.txt. It is useful because we can get a general sense of the usage of certain word in an article.

### Reference
URL: https://www.geeksforgeeks.org/grep-command-in-unixlinux/
