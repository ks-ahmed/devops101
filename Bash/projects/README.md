<div align="center"> 
<img width="700" src="https://i.ytimg.com/vi/AdNXaI0Qx3A/maxresdefault.jpg" />
</div>

---

## Bash Battle Arena Challenge: 

Bash Battle Arena is a collection of hands-on scripting challenges crafted to test and **strengthen your Bash skills**.

These exercises are designed to reinforce core Bash scripting concepts and help you build a strong foundation for tackling real-world automation tasks.

---

## Level 1: 
### The Mission
Create a directory named **Arena** and then inside it, create three files: **warrior.txt**, **mage.txt**, and **archer.txt**. List the contents of the **Arena** directory.

- `mkdir Arena`: Creates the Arena directory.
- `cd Arena`: Moves into the Arena directory
- `touch warrior.txt mage.txt archer.txt`: Creates three files: warrior.txt, mage.txt, and archer.txt.
- `ls`: Lists the files in the Arena directory.


https://github.com/user-attachments/assets/584c5e20-3b7a-45a5-8e92-c07c22e28e87

---

## Level 2:
### The Mission
Create a script that outputs the numbers 1 to 10, one number per line.


- `for number in {1..10}; do`: This creates a loop that starts at 1 and increments up to 10.
  - `{1..10}`: Defines the range of numbers for the loop.

- `echo "Number: $number"`: Inside the loop, each number (from 1 to 10) is printed on a new line.
  - `$number` holds the current number in the loop.

- `done`: This marks the end of the loop.

https://github.com/user-attachments/assets/3637dea4-2d23-45fe-819d-3079b98098f6

---

## Level 3: 
## The Mission
Write a script that checks if a file named **hero.txt** exists in the **Arena** directory. If it does, print **Hero found!**; else, print **Hero missing!**.

- `if [ -f "./Arena/hero.txt" ]; then`: This checks if the file `hero.txt` exists in the `Arena` directory.
  - `-f` checks if the file exists and is a regular file.

- `echo "Hero found"`: If `hero.txt` is found, the script prints "Hero found".

- `else echo "Hero missing!"`: If `hero.txt` is not found, the script prints "Hero missing!".


https://github.com/user-attachments/assets/0af905f7-a3ac-4409-835d-af37ef64508a

---


## Level 4: 
### The Mission
Create a script that copies all **.txt** files from the **Arena** directory to a new sirectory called **Backup**.

- `mkdir backup`: This creates a new directory called `backup`.
  - This directory will be used to store all `.txt` files copied from the current directory.

- `cp Arena/*.txt ./backup/`: This command copies all `.txt` files from the current directory into the `backup` directory.
  - `./*.txt`: Specifies all `.txt` files in the current directory.
  - `./backup/`: This is the target directory where the `.txt` files will be copied.


https://github.com/user-attachments/assets/8beca4b2-5322-4e9d-9805-a89ed6844bfd


---

## Level 5: 
### The Mission
Combine from above! Write a script that: 

- `mkdir Battlefield`: Creates a `Battlefield` directory for files.
  
- `cd Battle*`: Changes to the `Battlefield` directory using a wildcard.

- `touch knight.txt sorcerer.txt rogue.txt`: Creates `knight.txt`, `sorcerer.txt`, and `rogue.txt`.

- `if [ -f "knight.txt" ]; then`: Checks if `knight.txt` exists.

- `mkdir -p Archive`: Creates an `Archive` directory if `knight.txt` exists.

- `mv knight.txt Archive/`: Moves `knight.txt` to `Archive`.

- `ls`: Lists remaining files in `Battlefield`.

- `ls ./Archive`: Verifies `knight.txt` is now in `Archive`.


https://github.com/user-attachments/assets/1462239c-bd99-443b-9d15-c656401ddff3


---

## Level 6: 
### The Mission
Write a script that accepts a filename as an argument and prints the number of lines in that file. If no filename is provided, display a message saying 'No file provided'.

- `FILE="$1"`: This saves the first argument (the filename) passed to the script into the `FILE` variable.

- `if [[ -n "$1" ]]; then`: This checks if the user provided a filename.
  - `-n` checks if the first argument (the filename) is not empty.
  - If the filename is provided, the script moves on to count the lines.

- `Num=$(wc -l <"$1")`: This counts the number of lines in the file.
  - `wc -l` counts the lines in the file, and `<"$1"` sends the file content to this command.
  - The number of lines is saved in the `Num` variable.

- `echo "The number of lines in this file is : $Num"`: This prints the number of lines in the file.

- `else echo "No file provided"`: If the user didn't provide a filename, the script will print "No file provided".


https://github.com/user-attachments/assets/f52514e0-7865-4f38-9a58-be8e4de761ed


---

## Level 7: 
### The Mission
Write a script that sorts all .txt files in a directory by their size, from smallest to largest, and displays the sorted list.

- `ls -lh`: the file size is displayed in a human-readable format. 
- This option shows sizes in KB, MB, etc., but it **doesn't actually sort the files based on their size.**

- `awk '{print $5, $9}' `: extracts the 5th (file size) and 9th column (file name) ONLY from the ls -l output, which are the file size and file name respectively.


https://github.com/user-attachments/assets/76c44f19-ffc1-48c3-94d6-71ed73e7f6f0


---
