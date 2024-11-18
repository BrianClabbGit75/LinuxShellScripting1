# LinuxShellScripting1
Capstone Project - Multiplication Table using Bash Scripting,For and For C loop
#!/bin/bash

# This script generates a multiplication table for a number entered by the user.
# The user can choose to see a full table from 1 to 10 or a partial table within a specified range.

# Ask the user for a number.
read -p "Enter a number: " number

# Check if the number is valid.
if [[ ! $number =~ ^[0-9]+$ ]]; then
  echo "Invalid input. Please enter a positive integer."
  exit 1
fi

# Ask the user if they want a full or partial table.
echo "Do you want a full multiplication table (1-10) or a partial table?"
echo "Enter 'full' for a full table or 'partial' for a partial table."
read table_type

# If the user wants a full table, print the full table.
if [[ $table_type == "full" ]]; then
  echo "Multiplication table for $number:"
  for i in {1..10}; do
    result=$((number * i))
    echo "$number x $i = $result"
  done

# If the user wants a partial table, ask for the range.
elif [[ $table_type == "partial" ]]; then
  read -p "Enter the starting number: " start
  read -p "Enter the ending number: " end

  # Check if the range is valid.
  if [[ ! $start =~ ^[0-9]+$ ]] || [[ ! $end =~ ^[0-9]+$ ]]; then
    echo "Invalid input. Please enter positive integers."
    exit 1
  fi

  if [[ $start -gt $end ]]; then
    echo "The starting number must be less than or equal to the ending number."
    exit 1
  fi

  echo "Multiplication table for $number from $start to $end:"
  for ((i = start; i <= end; i++)); do
    result=$((number * i))
    echo "$number x $i = $result"
  done

else
  echo "Invalid input. Please enter 'full' or 'partial'."
  exit 1
fi



This script combines aspects of For loop and C-style For loop:

The script uses both a for loop and a C-style for loop to demonstrate different looping techniques.
The for loop is used for the full table, and the C-style for loop is used for the partial table.
Input validation:

The script validates the user's input to ensure that it is a positive integer.
It also validates the start and end numbers for the partial table to ensure that the start number is less than or equal to the end number.
Readable output and comments:

The script prints the multiplication table in a clear and concise format.
Comments are added to explain the purpose of each code block.


