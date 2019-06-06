Shuffling Array of String Type in Processing (Fisher Yates shuffle)

This is a Fisher–Yates shuffle used for shuffling string arrays; the algorithm used here is as described: https://en.wikipedia.org/wiki/Fisher%E2%80%93Yates_shuffle#Modern_method  
The great part about this shuffle, is that it doesn't require another array to be substituted into. 
The code simply swaps pairs of numbers in the array in such a way that results in a randomised array. 
The code creates an unbiased permutation, and thus every permutation should be equally as likely. 
I hope this helped! This was coded in Processing 3.5.3 


Lots of love, 
JustinTopiary




Code can be seen below:


void setup () {                      //This is a Fisher–Yates shuffle for string arrays; the algorithm used here is as described: https://en.wikipedia.org/wiki/Fisher%E2%80%93Yates_shuffle#Modern_method

String[] arrColors = {"Red","Blue","Orange","Green","Purple","Pink","Yellow","White"};  //This is simply an example array of string type

shuffle(arrColors);                                                                     //Here we call the shuffle function which can be seen below

printArray(arrColors);                                                                  //This displays the values of the array in the console when run our code

}



void shuffle (String[] Array) {                //We setup the function, 'shuffle'

  String sValue;                               //This variable is later used to swap two values in the array
  
  for (int i=0; i<Array.length-1; i++) {       //We create a loop from 0 to the length of the array - 1. The i++ means we increase the variable, i, by 1 each time a loop is completed in the for loop.
  
  int iUpperLimit = Array.length-i;          //Here we set what the max range of what our random number can go to. In this example, the value will be 8, then 7, then 6, then 5, then 4, then 3, then 2.
    
   int iRandomNumber = int(random(iUpperLimit)); //Here we will get a random number which is from 0 to iUpperlimit -1 (Including both 0 and iUpperlimit -1). The random function in Processing chooses a float value that does not include the number specified. Thus, random(8) will only output numbers from 0 to 7 (including 0 and 7). Luckily, array numbering systems work similairly and range from [0] to [7] in this instance. The length of the array will be 8, and so the random function will range from 0 to 7, which is exactly what we want. I also used int() to translate the float value the random function outputs into an integer. 
    
  sValue = Array[iRandomNumber];             //Here we use a variable to store the array value which is to be swapped first.
    
  Array[iRandomNumber] = Array[iUpperLimit -1]; //We then overwrite the value of that item in the array with the one it is to be swapped with
    
  Array[iUpperLimit-1] =sValue;                //We then overrwrite the other item in the array with the value we stored in sValue.
    
  }
  
}

