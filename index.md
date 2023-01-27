# Part 1
The following the my implementation of StringServer.

![843adda37dfb08cc560172ced02cbd5](https://user-images.githubusercontent.com/77051146/215222009-348ae413-2609-49d2-839b-927aefe5ed2f.png)

The following is an example of using add-message

![092fe0e2250ff94a9f1b56cbe3b0ae3](https://user-images.githubusercontent.com/77051146/215222361-50bc5778-39c1-4485-9b78-daa7e275e81b.png)

-- **Which methods in your code are called?**

I called the handleRequest method.

-- **What are the relevant arguments to those methods, and the values of any relevant fields of the class?**

The input is just a url: http://localhost:4000/add-message?s=Hello

The following is the value of relevant fields:

`parameters` is an array of String ["s", "Hello"]

`str` is the target out that I want to display: "Hello\n"

The following is another example of using add-message

![27fdfffe32b30263a7e6fc8bbfb24eb](https://user-images.githubusercontent.com/77051146/215222431-1454e045-0358-4eba-9bf7-c5f69d20ab95.png)

-- **Which methods in your code are called?**

I called the handleRequest method.

-- **What are the relevant arguments to those methods, and the values of any relevant fields of the class?**

The input is just a url: http://localhost:4000/add-message?s=Bison

The following is the value of relevant fields:

`parameters` is an array of String ["s", "Bison"]

`str` is the target out that I want to display: "Hello\nBison\n"

# Part 2

I will describe bug in the method `averageWithoutLowest`.

-- **A failure-inducing input for the buggy program, as a JUnit test and any associated code**
```
public void testMean() {
    double[] input1 = {1, 1, 2};
    assertEquals(1.5, ArrayExamples.averageWithoutLowest(input1), 0.000001);
}
```
--- **An input that doesn’t induce a failure, as a JUnit test and any associated code**
```
public void testMean() {
    double[] input1 = {1, 3, 2};
    assertEquals(2.5, ArrayExamples.averageWithoutLowest(input1), 0.000001);
}
```
--- **The symptom, as the output of running the tests (provide it as a screenshot of running JUnit with at least the two inputs above)**

The following sceenshot is an example of failure inducing input.

![image](https://user-images.githubusercontent.com/77051146/215225034-0016f758-429c-4370-ba1a-e63ed176c92b.png)

The following sceenshot is an example of input that does not induce failure.

![image](https://user-images.githubusercontent.com/77051146/215225262-2404619d-90f1-4009-a8c4-efb24f6550f6.png)

Since the test pass, there is no output.

-- **The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown)**

The following is the buggy program:
```
static double averageWithoutLowest(double[] arr) {
    if(arr.length < 2) { return 0.0; }
    double lowest = arr[0];
    for(double num: arr) {
      if(num < lowest) { lowest = num; }
    }
    double sum = 0;
    for(double num: arr) {
      if(num != lowest) { sum += num; }
    }
    return sum / (arr.length - 1);
  }
```

The following is the fixed program:
```
static double averageWithoutLowest(double[] arr) {
    if(arr.length < 2) { return 0.0; }
    double lowest = arr[0];
    for(double num: arr) {
      if(num < lowest) { lowest = num; }
    }
    double sum = 0;
    for(double num: arr) {
      sum += num;
    }
    sum-=lowest;
    return sum / (arr.length - 1);
  }
```

-- **Briefly describe why the fix addresses the issue.**
In the buggy program, it first finds the min value of the array. Then it loops through the array, if the value does not equal min, then add it to the running sum, otherwise just skip the value. So, if there are two min values in the array, they will both be removed. So, I changed the code to first find the min value; then I calculate the sum without removing any value. After calculating the running sum, I subtract the min and calculate the average. In this way, I can calculate the average with one min removed.
