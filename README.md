# BallTrix_Reverse_Engineering
![IDA Screenshot](/pic.gif)
## About:
This project was doing some trick by reverse engineering BallTriX, a game from 1997 'Yeah too old :)'.
You can find the ``.exe` file available [here]` (https://archive.org/details/BallTriX_1020) freely.
### <mark>Note</mark>
this project originally from the book 'Reverse Engineering for Beginners'.
## Methodology:
 - When open the `balltrix.exe`, IDA recongize the standard `_rand` function at address `0x00403DA0`.
 - This function called by anthor function in three places but the most interesting oneis the third.
 - Overall, the function generates a random board of size n x n and the range of colors is 0 to n − 1 and n is passed as the sole argument of the function.
 - So let's replace the third call by a code will always return zero.
 - Replace the three instructions `PUSH/CALL/ADD` by `NOP`s
 - Finally, we'll add the instruction `XOR EAX, EAX` to clear the `EAX` register.
 ### That's it, thank you for reading :)
