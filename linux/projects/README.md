<div align="center">
<img width="600" src="https://github.com/user-attachments/assets/94c3a93a-bae8-4141-ae3b-156f3f8dfd50" />
</div>

---

# **Bandit Wargame - An Introduction:**

Bandit Wargame is a great way to dive into the Linux command line, especially if you're just getting started. Created by OverTheWire, it’s a hands-on, challenge-based game that guides you through the basics of working in a shell environment. You’ll learn how to run commands, move around directories, and pick up essential skills—all by solving a series of clever puzzles.

Each level gives you a task: find a hidden password somewhere in the system. Once you uncover it, you’ll use that password to move on to the next level, gradually building your knowledge as you go.

## **How to Get Started:**

To jump into Bandit, you’ll need to connect to their server using SSH (Secure Shell), which lets you securely access the remote system where the game is hosted.

Here’s what you need to do:

### **Connect to the Bandit Server:**
First, make sure SSH is installed on your computer. Then, open up your terminal (or use an SSH client) and run this command to connect:

``` bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
```
This command logs you into the Bandit server as the user bandit0. Once you're connected, you'll be asked to enter the password for level 0 to get started.

### **Password for Level 0**
The password for the first level (bandit0) is:

```bash
bandit0
```

---

## **Bandit Level 0 → 1**

### 💻 Steps:
1. `ls` to list files.
2. `cat readme` to read the file.

![bandit0-1](https://github.com/user-attachments/assets/2c60da19-d64a-4f7b-8b86-01b57c966ec2)


---

## **Bandit Level 1 → 2**

### 💻 Steps:
1. `ls` to list files.
2. `cat ./-` to read the file named `-`.

![band1-2](https://github.com/user-attachments/assets/69947957-487d-4df4-829b-0fba8fc53e80)


---

## **Bandit Level 2 → 3**

### 💻 Steps:
1. `ls` to list files.
2. `cat "spaces in the file name"` ("") to read the file with spaces in its name.

![band2-3](https://github.com/user-attachments/assets/c03a8c83-478e-4cc2-b9f7-67093a370d0a)

---

## **Bandit Level 3 → 4**

### 💻 Steps:
1. `ls` to list all files.
2. `ls -a` to list all hidden files including hidden files.
3. `cat ...*` to read the hidden file.

![3-4](https://github.com/user-attachments/assets/e8feb46d-4eda-4567-ab89-581d76cbfd45)


---

## **Bandit Level 4 → 5**

### 💻 Steps:
1. `ls` to list files.
2. `cd inhere` to enter the `inhere` directory.
3. `file ./*` to identify file types.
4. `cat ./-file07` to read the specific file.

![band4-5](https://github.com/user-attachments/assets/cce4a0e7-bbdd-4167-ba96-93ac3da2af81)


---

## **Bandit Level 5 → 6**

### 💻 Steps:
1. `ls` to list files.
2. `cd inhere` to enter the directory.
3. `find . -type f -size 1033c ! -executable` to find the correct file by size.
4. `cat ..` to open the file

![band5-6](https://github.com/user-attachments/assets/a757f61b-1cb0-4be1-a91c-3a614879b5d8)


---

## **Bandit Level 6 → 7**

### 💻 Steps:
1. `ls -a` to list hidden files.
2. `find / -type f -user bandit7 -group bandit6 -size 33c 2> /dev/null` to locate the file.
3. `cat /var/lib/dpkg/info/bandit7.password` to reveal the password.

![band6-7](https://github.com/user-attachments/assets/1c3347f0-0796-4278-a9c0-349e204cfa9c)


---

## **Bandit Level 7 → 8**

### 💻 Steps:
1. `ls -a` to list files.
2. `cat data.txt` to view the file.
3. `grep "millionth" data.txt` to filter the content and find the correct line.


![band 7-8](https://github.com/user-attachments/assets/cc6f04f0-08dd-42dd-90f0-9c17629f2b4a)


---

## **Bandit Level 8 → 9**

### 💻 Steps:
1. `ls` to list files.
2. `cat data.txt` to view the data.
3. `sort data.txt | uniq -u` to find the unique line.

![band8-9](https://github.com/user-attachments/assets/2c5986bf-97f1-479f-844f-26eb4fbc6298)


---

## **Bandit Level 9 → 10**

### 💻 Steps:
1. `ls` to list files.
2. `strings data.txt | grep "=="` to find the specific line with "==".

![band9-10](https://github.com/user-attachments/assets/7247f705-25a3-4377-b7f4-984dde8cd9a9)


---

## **Bandit Level 10 → 11**

### 💻 Steps:
1. `ls` to list files.
2. `cat data.txt | base64 -d` to decode the base64 content.

![band 1-011](https://github.com/user-attachments/assets/ccea4d43-0dbe-41b1-920f-e808e2e09c0c)


---

## **Bandit Level 11 → 12**

### 💻 Steps:
1. `ls` to list files.
2. `cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'` to decode using the ROT13 cipher.

![band 11-12](https://github.com/user-attachments/assets/15ea14b0-dec7-484e-8354-4ca0102ec443)

---


































