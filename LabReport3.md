## Part 1
* Failure-inducing input
```
@Test
 public void TestReverseOdd() {
   int[] input = {1, 2, 3}; 
   ArrayExamples.reverseInPlace(input);
   assertArrayEquals(new int[]{ 3, 2, 1}, input);
```
* Successful input
```
@Test
 public void TestReverseOdd() {
   int[] input = {1, 2, 1}; 
   ArrayExamples.reverseInPlace(input);
   assertArrayEquals(new int[]{ 1, 2, 1}, input);
```
* Symptoms
1. ![Image](labreport3-failure-input-fixed.png) <br>
2. ![Image](labreport3-successful-input.png) <br>
* Bugs
1. Before
```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```  
2. After
```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length/2; i += 1) {
      int temp = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length - i - 1] = temp;
    }
  }
```
The code is functional until halfway through the array, where it then starts to reverse using the changed values. So, a temporary value is useful in saving the original value before it is changed in order to change the values in the latter half of the array.
## Part 2
*`find` command
1. `-name` <br>
a. `$ find technical/plos -name '*.txt'` <br>
![Image](find-command-name-option1.png) <br>
b. `$ find technical/plos -name 'pmed.*.txt'` <br>
![Image](find-command-name-option2.png) <br>
2. `-type` <br>
a. 

Citation: https://tecadmin.net/linux-find-command-with-examples/
