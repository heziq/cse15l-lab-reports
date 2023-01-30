# Lab 3 Report
  This lab report is consist of three parts: 
  1. Creating a web server. 
  2. Example and discussion about bugs and symptoms. 
  3. A short conclusion about what I have learned during last two weeks. 

## Part 1: Web Server

   - This is my code for StringServer, the basic setup is really similar to the NumberServer we have seen before in the lab 2, the only difference is in the specific operation parts. 
   
   - In the code, if the path contain message "/add", then this means we want get the string add. Split the query part by "=". If before "=" is a letter "s", the what after "=" is what we want to add into our string. 
  
  Code for StringServer: 
  ```
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    String keep = "";
    public String handleRequest(URI url) {
            if (url.getPath().contains("/add")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    keep = keep + "\n"+parameters[1];}
                return keep;
            }else{
                return "please add some message";}
    }
}
class StringServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;}
        int port = Integer.parseInt(args[0]);
        Server.start(port, new Handler());
    }
}

  ```

Examples of using "/add-massage"

- Screenshot 1 : page that after request : `/add-message?s=Hello`

![hello server](https://user-images.githubusercontent.com/122570012/215379539-84185f20-4808-4ac8-83ba-6965fc6dc809.png)

- Screenshot 2 : page that after request : `/add-message?s=Hello` and `/add-message?s=How are you`

![hhello how are you server](https://user-images.githubusercontent.com/122570012/215380957-32b1c6ff-86bf-48ce-a0f5-be3e7d2615c4.png)


- The method `handleRequest(url)` is being called on this line: `Server.start(port, new Handler());` in both screenshots. 

- For screenshot 1, argument relevent to the method is the url in this case : http://localhost:4000/add-message?s=Hello (Using 4000 as the port number). 
- For screenshot 2, argument relevent to the method is the url in this case : http://localhost:4000/add-message?s=How%20are%20you (Using 4000 as the port number). 
- Values of relevant fields of the class are `String keep`, `URI url`, `String[] parameters` and `int port`, which is same for both screenshots. 

 For screenshot 1: 
-  `String keep` is changing from "" to "Hello" in the line of `keep = keep + "\n"+parameters[1];` 
- `URI url` is assigned to the value :  http://localhost:4000/add-message?s=Hello when the line `Server.start(port, new Handler());` is called
- `String[] parameters` is got from the query part of the url splitted by the "=", which is [s,Hello]. when the line `String[] parameters = url.getQuery().split("=");` is called. 
- `int port` is assigned to number 4000 in this case. 
 
 For screenshot 2: 
-  `String keep` is changing from "Hello" to "Hello \n How are you " in the line of `keep = keep + "\n"+parameters[1];` 
- `URI url` is assigned to the value :  http://localhost:4000/add-message?s=How%20are%20you when the line `Server.start(port, new Handler());` is called
- `String[] parameters` is got from the query part of the url splitted by the "=", which is [s,How are you]. when the line `String[] parameters = url.getQuery().split("=");` is called. 
- `int port` is assigned to number 4000 in this case. 
 
- Port number is not changed in these two screenshot because we did not re-run the StringServer with different port number. 


## Part 2: Bugs and Symptoms
1. A failure-inducing input for the buggy program 

  ```
  @Test 
	public void testReverseInPlace() {
    int[] input1 = { 1,2,3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3,2,1 }, input1);
	}
  ```
  
2. An input that doesn’t induce a failure

  ```
  @Test 
	public void testReverseInPlace() {
    int[] input1 = { 1 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 1 }, input1);
	}
  ```

3. The symptom, as the output of running the tests 

  ![image](https://user-images.githubusercontent.com/122570012/215396014-1f5ebed1-20c8-45dc-ae7a-e373c1241259.png)
  
4. The bug, as the before-and-after code change required to fix it 

  - code before fixed 
  
    ```
    static void reverseInPlace(int[] arr) {
      for(int i = 0; i < arr.length; i += 1) {
        arr[i] = arr[arr.length - i - 1];
      }
    }
    ```
    
  - code after fixed 
  
   ``` 
   static void reverseInPlace(int[] arr) {
     int[] ori = new int[arr.length];
     for(int i = 0;i <arr.length; i += 1){
    	ori[i] = arr[i];
     }
     for(int i = 0; i<arr.length; i +=1){
    	arr[i] = ori[arr.length -i -1];
     }
   }
   ```
  
5. Discussion 

	The reason why the original code does not work is that it changes all the array in order. For example, the code first tried to assign the last index element to the first index, this is fine forr now. But later, when the code try to assign the original first index element to the last index, the first index element is already changed to the original last element. 
	
	What I did to change the code is that: first copy the original array to a new array, then use the new array to change the original array, i.e assign the new array to original array in reverse order. This can avoid the problem. 
