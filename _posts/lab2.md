# Part 1: Webserver

# Part 2: A Bug

### Failure inducing input:
```java
    @Test
    public void testReverseInPlace2() {
        int[] input = { 1, 3 };
        ArrayExamples.reverseInPlace(input);
        assertArrayEquals(new int[]{ 3,1 }, input);
    }
```

### Input that doesn't induce a failure: 

```java
    @Test 
	public void testReverseInPlace() {
        int[] input1 = { 3 };
        ArrayExamples.reverseInPlace(input1);
        assertArrayEquals(new int[]{ 3 }, input1);
	}
```

### Symptom: 

### Bug: 

Before: 
```java
    static void reverseInPlace(int[] arr) {
        for(int i = 0; i < arr.length; i += 1) {
        arr[i] = arr[arr.length - i - 1];
        }
    }
```

After: 
```java
    static void reverseInPlace(int[] arr) {
    
        int[] temp = new int[arr.length];
        for (int i=0; i < arr.length; i++) {
        temp[i]=arr[i];
        }

        for(int i = 0; i < arr.length; i += 1) {
        arr[i] = temp[arr.length - i - 1];
        }
    }
```


A failure-inducing input for the buggy program, as a JUnit test and any associated code (write it as a code block in Markdown)
An input that doesn’t induce a failure, as a JUnit test and any associated code (write it as a code block in Markdown)
The symptom, as the output of running the tests (provide it as a screenshot of running JUnit with at least the two inputs above)
The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown)
# Part 3: Something I learned

