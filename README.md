1) Name and describe the two main operations of a stack (to add and remove data). 

    1. push() - The push() method adds one or more elements to the end of an array and returns the new length of the array. An example of using this method would be ex:
    var arr = ['cat', 'dog', 'fish'];
    arr.push('lizard'); // will be 4 now
    console.log(animals); // [cat, dog, fish, lizard]
 
    2. pop() - The pop method removes the last element from an array and returns that value to the caller. This method will also changes the length of the array. Example :
    var burger = ['tomato', 'pickles', 'lettuce'];
    burger.pop(1);// at index 1 expected output 'lettuce' 
 

2) Name and describe the two main operations of a queue (to add and remove data). 
 
    1. Enqueue() : A method that adds items at one end and dequeue(aka removes ) item at the other, just like a line of people queuing up for tickets to the latest Drake concert.
 
    2. dequeue() : A method that removes from the queue and then executes the function/removes value from the front, returns size 
 
3) Draw the tree resulting from adding the following sequence of numbers to an empty tree: 30, 45, 15, 10, 50, 40, 20, 27 
 
                                    ---30--- 
                    ----15---                  ---45--- 
              ----10----                           ----50---- 
          ----20----                                      ---40---   
      ----27---- 
 
                                            ---30--- 
                    ----15---                               ---45--- 
     ----10----          ---- 20---          ---40---         ----50---- 
                                      ---27--- 
 

 
4) Is this tree balanced? If not, which rotation needs to be done? (Use the following rotation as an example: rightRotation(30), or leftRotation(10)) 
 
 The tree is balance at the root being 30
 
rightRotation(30): 
 
                                          ---30--- 
                    ----15---                               ---45--- 
      ----10----          ---- 20---          ---40---         ----50---- 
                                      ---27--- 
 

Now add 29. Is the tree balanced? If not, which rotation needs to be done? (Use the following rotation as an example: rightRotation(30), or leftRotation(10)) 


The Tree is NOT balanced. Needs to rotate LEFT on 20 so 27 can become the parent with 20 leaf  left and 29 leaf right. 
 
                                           ---30--- 
                    ----15---                               ---45--- 
      ----10----          ---- 20---          ---40---         ----50---- 
                                        ---27----- 
                                               ---29---  
 
 
Consider the following tree: 
------5 
---2-----8 
-1—3 
 
Now add 0 to the tree. Which one is the first node to go out of balance? 
------5 
---2-----8 
1—3 
0 
 
Answer: node 2 is out of balance, node 2 now needs a right rotation

 
 
How do you fix this node? (Use the following rotation as an example: rightRotation(30), or leftRotation(10)) 
 
---------3 
----1--------5 
0-----2---------8 
 
Fix it with: 
leftRotation(3) 
RightRoation(2) 
RightRotation(5) 
 
3 is now the root
 
 
What are the four main steps of mergesort? 
 
1) Divide 
2) Sort 
3) Combine 
4) Return 
 
Say you have a program which handles the login queue to a game server. The game server is able to log in one person every one second. Assume that one second must elapse after a person logs in with an empty queue before they are removed from the queue. Draw the state of the queue at 12:00:06, considering the following sequence of events: 
 
At 12:00:00 Hades logs in                            
At 12:00:00 Ares logs in                                 
At 12:00:00 Zeus logs in 
At 12:00:00 Buzz Light Year logs in 
At 12:00:02 Kanye West logs in 
At 12:00:03 Taylor Swift logs in 
At 12:00:03 Darkwing Duck logs in 
At 12:00:04 Evil Mickey logs in. 
 
ANSWER: At 12:00:06 you'll have two users waiting. 
 
State at 12:00:06  
At 12:00:00  
01 in 
Hades logs in                          
At 12:00:00  
02 in 
Ares logs in                                 
At 12:00:00  
03 in 
Zeus logs in 
At 12:00:00  
04 in 
Buzz Light Year logs in 
At 12:00:02  
05 in 
Kanye West logs in 
At 12:00:03  
06 in 
Taylor Swift logs in 
At 12:00:03  
07 waiting 
Darkwing Duck logs in 
At 12:00:04  
08 waiting 
Evil Mickey logs in. 
 
Solve https://www.hackerrank.com/challenges/compare-the-triplets - be mindful that you are required to print the output to the console in exactly the format that was asked. You are not required to return a value, just print to the console. Also be mindful to use JavaScript. 
  
(function solve(a0, a1, a2, b0, b1, b2) {
    var aa = [a0, a1, a2];
    var bb = [b0, b1, b2];
    var a = 0;
    var b = 0;     
      
    aa.forEach((element, index) => {
      var ax = aa[index];
      var bx = bb[index];    
      if (ax === bx) return; // neither person receives a point
      return ax > bx ? a += 1 : b += 1;
    });
    
    return [a, b];
    
  })(5, 6, 7, 3, 6, 10);
 
 
Solve https://www.hackerrank.com/challenges/mini-max-sum - be mindful that you are required to print the output to the console in exactly the format that was asked. You are not required to return a value, just print to the console. Also be mindful to use JavaScript. 
 
main(['1 2 3 4 5'])



//---Main function
function main(stdin) {
    var arr = stdin[0].split(' ').map(Number);
    var i, j, min, max, temp_sum, sum = 0;

    for (i in arr) {
        temp_sum = 0;
        

        for (j in arr) if (i != j) temp_sum += arr[j];
        

        if (max < temp_sum || !max) max = temp_sum;
        if (min > temp_sum || !min) min = temp_sum;
    }

    console.log(min, max);
}