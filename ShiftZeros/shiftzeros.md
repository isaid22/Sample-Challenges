## Shift zero to the end of array

This example uses C programming to solve the it.

Say I have an array of integers {5, 6, 0, 4, 0}, I want to shift zero to the end of the array, such that the array becomes

{5, 6, 4, 0, 0}

The way this example work is by leveraging swap. 
But I need to track two indexes, say, i and j. i always increment, But
j will stop when 0 is encountered.

Since I want to push 0 to end of array, as my i going from one element to next, 
if a  0 is encountered, j should stay there, whereas i will increment and continue
to next element. If next element is non-zero, then I have to swap:

```
int temp = a[i];
a[i] = a[j];
a[j] = temp;
j++;
```

Code above is fundamental swapping mechanism. At the end, j is incremented because we need it to 
catch up to next element. 

If there is no 0 yet, then i and j will increment together, having same value and index the same element.
Insuch case, swapping is merely swapping each value with itself, because a[i] and a[j] points to same
element. 

To make this code snippet work, we need to wrap it in a for loop to loop over i, from the begining 
to the end of array. j is initialized to 0 before this for loop. 
```
int n = length of string;
int j = 0;
for (int i = 0; i < n; i++)
{
    if(a[i] != 0){
        int temp = a[i];
        a[i] = a[j];
        a[j] = temp;
        j++;
    }
}
```