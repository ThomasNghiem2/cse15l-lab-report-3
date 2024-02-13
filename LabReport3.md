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
