# 0x00 Challenge

This repository contains a fixed version of the code challenge from the original [0x00-Fix_My_Code_Challenge](https://github.com/alx-tools/0x00-Fix_My_Code_Challenge) repository.

## Changes Made

**[0-fizzbuzz.py](0-fizzbuzz.py)**

The issue with the original Python code is that the condition for checking if a number is divisible by both 3 and 5 is placed after the condition for checking if it is divisible by 3 only. This means that the code will never reach the condition for "FizzBuzz" because the condition for "Fizz" will always be true first.

To fix this, the condition for "FizzBuzz" should be checked first, followed by "Fizz" and "Buzz".

**[1-print_square.js](1-print_square.js)**

The issue with the original JavaScript code is that the radix value used in the parseInt function is set to 16, which means the code is expecting the input to be in hexadecimal format. However, the desired functionality is to interpret the input as a decimal number.

By changing the radix value to 10, the code will correctly interpret the input as a decimal number and proceed to print the desired number of "#" characters horizontally.

**[2-sort.rb](2-sort.rb)**

The issue with the original Ruby code is that when inserting a value into the "result" array, the incorrect index is used. In the original code, the value is being inserted at index "i - 1", which means it is being inserted one position before the current value at index "i". This results in the inserted value being placed at the wrong position in the array.

To fix this, the corrected code updates the insertion index to simply "i", which means the value will be inserted at the correct position in the array. This ensures that the desired functionality of inserting the value "i_arg" into the "result" array is achieved.

**[3-user.py](3-user.py)**

The issue with the original Python code is that in the password setter method, the condition for assigning the hashed password to `__password` is incorrect. The original code assigns `None` to `__password` if `pwd` is `None` or not a string. However, the desired functionality is to assign the hashed password only if `pwd` is not `None` and is a string.

To fix this, the corrected code updates the condition to check if `pwd` is not `None` and is a string. If this condition is satisfied, the password is hashed using MD5 and assigned to `__password`.

In the `is_valid_password` method, the code correctly checks if `pwd` is `None`, not a string, or if `__password` is `None`. However, the comparison between the hashed password and `__password` is done using `.upper()`, which converts the hashed password to uppercase. The corrected code uses `.lower()` to ensure the comparison is done in lowercase, matching the hashed password stored in `__password`.

**[4-delete_dnodeint/delete_dnodeint_at_index.c](4-delete_dnodeint/delete_dnodeint_at_index.c)**

The issue with the original C code is that in the original code, when removing the first element of a doubly linked list (index 0), the assignment of `*head` to `tmp` is done before freeing the memory. This leads to a memory leak because the memory allocated for the first element is not freed before updating `*head` to the next element.

To fix this, the corrected code updates the order of operations. First, the memory for the first element is freed, and then the `*head` pointer is updated to the next element (`tmp`). This ensures that the memory is properly freed before updating the head pointer.

In the `else` block, the code incorrectly assigns `(*head)->prev->prev` to `(*head)->prev`, which results in a loss of the previous node's information. The corrected code assigns `(*head)->prev->next` to `(*head)->next`, preserving the correct linkage between the nodes.

Additionally, the order of operations for freeing the memory and updating the pointers is adjusted to match the correct flow of the code. The updated code ensures that the memory is freed before updating the pointers and then assigns `*head` to the original head pointer (`saved_head`), as intended.

## Acknowledgements

The original code challenges were part of the [0x00-Fix_My_Code_Challenge](https://github.com/alx-tools/0x00-Fix_My_Code_Challenge) repository.
