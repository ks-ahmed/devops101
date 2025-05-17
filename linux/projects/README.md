![banditOverTheWire](https://github.com/user-attachments/assets/65a6b7fb-c8b5-44ce-b2b0-38194cfa6d63)


- [🛡️ **Bandit Wargame: An Introduction**](#️-bandit-wargame-an-introduction)
    - [**How to Get Started**](#how-to-get-started)
    - [**Connect to the Bandit Server**](#connect-to-the-bandit-server)
---

  - [**Level 0 → 1**](#level-0---1)
    - [📝 Steps:](#-steps)
  - [**Level 1 → 2**](#level-1---2)
    - [📝 Steps:](#-steps-1)
  - [**Level 2 → 3**](#level-2---3)
    - [📝 Steps:](#-steps-2)
  - [**Level 3 → 4**](#level-3---4)
    - [📝 Steps:](#-steps-3)
  - [**Level 4 → 5**](#level-4---5)
    - [📝 Steps:](#-steps-4)
  - [**Level 5 → 6**](#level-5---6)
    - [📝 Steps:](#-steps-5)
  - [**Level 6 → 7**](#level-6---7)
    - [📝 Steps:](#-steps-6)
  - [**Level 7 → 8**](#level-7---8)
    - [📝 Steps:](#-steps-7)
  - [**Level 8 → 9**](#level-8---9)
    - [📝 Steps:](#-steps-8)
  - [**Level 9 →  10**](#level-9---10)
    - [📝 Steps:](#-steps-9)
  - [**Level 10 → 11**](#level-10---11)
    - [📝 Steps:](#-steps-10)
  - [**Level 11 → 12**](#level-11---12)
    - [📝 Steps:](#-steps-11)
  - [**Level 12 → 13**](#level-12---13)




# 🛡️ **Bandit Wargame: An Introduction**

The **Bandit Wargame** is an excellent starting point for anyone looking to sharpen their Linux command-line skills. Designed by OverTheWire, this game teaches beginners how to interact with a shell environment, use commands effectively, and navigate through directories—all while solving a series of fun and engaging challenges. 

Each level presents a new puzzle where the goal is to find a password hidden somewhere in the system, which you’ll use to access the next level.

### **How to Get Started**

To begin the Bandit game, you need to SSH (Secure Shell) into the Bandit server. SSH allows you to remotely connect to the system running the game. Here’s how to get started:

### **Connect to the Bandit Server**
Once you have SSH installed, you can connect to the game using the following command in your terminal or SSH client:

``` bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
```
This connects you to the Bandit server as the user bandit0. You’ll then be prompted to enter the password for the first level.

### **Password for Level 0**
The password for the first level (bandit0) is:

```bash
bandit0
```


## **Level 0 -> 1**
<details>
  <summary>🔑 Password</summary>
  <blockquote>ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If</blockquote>
</details>

### 📝 Steps:
1. `ls` to list files.
2. `cat readme` to read the file.

---

## **Level 1 -> 2**
<details>
  <summary>🔑 Password</summary>
  <blockquote>263JGJPfgU6LtdEvgfWU1XP5yac29mFx</blockquote>
</details>

### 📝 Steps:
1. `ls` to list files.
2. `cat ./-` to read the file named `-`.

---

## **Level 2 -> 3**
<details>
  <summary>🔑 Password</summary>
  <blockquote>MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx</blockquote>
</details>

### 📝 Steps:
1. `ls` to list files.
2. `cat spaces*` to read the file with spaces in its name.

---

## **Level 3 -> 4**
<details>
  <summary>🔑 Password</summary>
  <blockquote>2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ</blockquote>
</details>

### 📝 Steps:
1. `ls -a` to list all files, including hidden ones.
2. `cd inhere` to change directory.
3. `ls -a` to list all hidden files in the new directory.
4. `cat ...*` to read the hidden file.

---

## **Level 4 -> 5**
<details>
  <summary>🔑 Password</summary>
  <blockquote>4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw</blockquote>
</details>

### 📝 Steps:
1. `ls` to list files.
2. `cd inhere` to enter the `inhere` directory.
3. `file ./*` to identify file types.
4. `cat ./-file07` to read the specific file.

---

## **Level 5 -> 6**
<details>
  <summary>🔑 Password</summary>
  <blockquote>HWasnPhtq9AVKe0dmk45nxy20cvUa6EG</blockquote>
</details>

### 📝 Steps:
1. `ls` to list files.
2. `cd inhere` to enter the directory.
3. `find . -type f -size 1033c ! -executable` to find the correct file by size.

---

## **Level 6 -> 7**
<details>
  <summary>🔑 Password</summary>
  <blockquote>morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj</blockquote>
</details>

### 📝 Steps:
1. `ls -a` to list hidden files.
2. `find / -type f -user bandit7 -group bandit6 -size 33c 2> /dev/null` to locate the file.
3. `cat /var/lib/dpkg/info/bandit7.password` to reveal the password.

---

## **Level 7 -> 8**
<details>
  <summary>🔑 Password</summary>
  <blockquote>dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc</blockquote>
</details>

### 📝 Steps:
1. `ls -a` to list files.
2. `cat data.txt` to view the file.
3. `cat data.txt | grep "millionth"` to filter the content and find the correct line.

---

## **Level 8 -> 9**
<details>
  <summary>🔑 Password</summary>
  <blockquote>4CKMh1JI91bUIZZPXDqGanal4xvAg0JM</blockquote>
</details>

### 📝 Steps:
1. `cat data.txt` to view the data.
2. `sort data.txt | uniq -u` to find the unique line.

---

## **Level 9 -> 10**
<details>
  <summary>🔑 Password</summary>
  <blockquote>FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey</blockquote>
</details>

### 📝 Steps:
1. `cat data.txt | strings | grep "=="` to find the specific line with "==".

---

## **Level 10 -> 11**
<details>
  <summary>🔑 Password</summary>
  <blockquote>dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr</blockquote>
</details>

### 📝 Steps:
1. `cat data.txt | base64 -d` to decode the base64 content.

---

## **Level 11 -> 12**
<details>
  <summary>🔑 Password</summary>
  <blockquote>7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4</blockquote>
</details>

### 📝 Steps:
1. `cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'` to decode using the ROT13 cipher.
2. 
---

## **Level 12 -> 13**
<details>
  <summary>🔑 Password</summary>
  <blockquote>7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4</blockquote>
</details>

### 📝 Steps:
1. `xxd -r data.hex data.bin` to reverse the hex dump and create a binary file.
2. `file data.bin` to check the file type.
3. `mv data.bin data.gz`, then `gunzip data.gz` to rename and decompress the file.
4. `file data`, then `tar -xvf data` to identify and extract the contents from the tar archive.

---

## **Level 13 -> 14**

<details>
  <summary>🔑 Password</summary>
  <blockquote>FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn</blockquote>
</details>

































