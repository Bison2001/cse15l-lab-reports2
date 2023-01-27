# Part 1
The following the my implementation of StringServer.
![843adda37dfb08cc560172ced02cbd5](https://user-images.githubusercontent.com/77051146/215222009-348ae413-2609-49d2-839b-927aefe5ed2f.png)
The following is an example of using add-message
![092fe0e2250ff94a9f1b56cbe3b0ae3](https://user-images.githubusercontent.com/77051146/215222361-50bc5778-39c1-4485-9b78-daa7e275e81b.png)

-- Which methods in your code are called?

I called the handleRequest method.

-- What are the relevant arguments to those methods, and the values of any relevant fields of the class?

The input is just a url: http://localhost:4000/add-message?s=Hello

The following is the value of relevant fields:

`parameters` is an array of String ["s", "Hello"]

`str` is the target out that I want to display: "Hello\n"

The following is another example of using add-message
![27fdfffe32b30263a7e6fc8bbfb24eb](https://user-images.githubusercontent.com/77051146/215222431-1454e045-0358-4eba-9bf7-c5f69d20ab95.png)

-- Which methods in your code are called?

I called the handleRequest method.

-- What are the relevant arguments to those methods, and the values of any relevant fields of the class?

The input is just a url: http://localhost:4000/add-message?s=Bison

The following is the value of relevant fields:

`parameters` is an array of String ["s", "Bison"]

`str` is the target out that I want to display: "Hello\nBison\n"
