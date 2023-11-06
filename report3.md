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
