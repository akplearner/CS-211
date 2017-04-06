#include <iostream>
#include <cmath>
using namespace std;

// Returns true if the queen in column c is ok
bool ok(int q[], int c) {
   for (int i = 0; i < c; ++i)
      if (q[i] == q[c] || abs(q[i] - q[c]) == c - i)
         return false;
   return true;
}

void print(int q[]) {
   static int numSolutions = 0;
   cout << "Solution #" << ++numSolutions << ": ";
   for (int i = 0; i < 8; i++)
      cout << q[i];
   cout << "\n";
}

int main() {
   int q[8] = {};   // Initialize the array to 0.
   int c = 0;       // Start on the first column
   while (c >= 0) { // End the loop if you backtrack from the first column
      if (c == 7) { // If you are in the last column, print and backtrack
         print(q);
         --c;
      }
      else                  // Otherwise, move to one before the first row of the next column
         q[++c] = -1;
      while (c >= 0) {
         ++q[c];            // Move to the next row
         if (q[c] == 8)     // If you have passed the end of the column, backtrack
            --c;
         else if (ok(q, c)) // Otherwise, if the queen is ok, break (go back to the beginning of the outer loop)
            break;
      }
   }
   return 0;
}
