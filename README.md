# JavaScript--Daily-coding-problem-4
/*Good morning! Here's your coding interview problem for today.

This problem was asked by Stripe.

Given an array of integers, find the first missing positive integer in linear time and constant space. In other words, find the lowest positive integer that does not exist in the array. The array can contain duplicates and negative numbers as well.*/
//worst-case performance of this algorithm is that it traverses the array n * n times (n for the outer loop, and n for the inner loop) so //it looks like O(n**2) rather than O(n) (linear).
--------------------------------------------------------------------------------------------------------------------------------------

function findSmallestMissingInt(arr) {
  let min = 1;
  let prevLoopMin;
  while (min !== prevLoopMin) { // Exit once no increment has occurred in the previous loop
    prevLoopMin = min;
    for (const num of arr) { 
      if (num === min) min++; // Increment min if its current value is found in the array
    }
  }
  return min;
}
