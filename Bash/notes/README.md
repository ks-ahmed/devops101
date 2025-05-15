
https://github.com/user-attachments/assets/c3955692-4fc7-45aa-977c-1e06bb2645fc

---

# Handling Bad Data in Bash:
This project demonstrates how to handle bad or unexpected input using a combination of conditional logic and input sanitization — all within a Bash script. Perfect for CLI tools, automation tasks, or anytime user input could break your workflow.

## What It Does?
Validates input using conditional statements (if, [[ ]], regex)

Sanitizes input using parameter expansion and pattern substitution

Ensures input meets desired formats and constraints

Prevents script failures due to bad or unsafe data

## Why It Matters? 
Handling input properly makes your scripts:

 - More secure
 - Easier to debug
 - Safer to reuse in pipelines ⚙️

## Example: Clean and Validate a Username:

`#!/bin/bash`

`read -p "Enter a username: " user_input`

**Sanitize input: remove spaces and convert to lowercase**

`username="${user_input// /}"`
`username="${username,,}"`

**Validate: only allow lowercase alphanumeric, 3–12 characters**

`if [[ "$username" =~ ^[a-z0-9]{3,12}$ ]]; then` \
   `echo "Username accepted: $username"` \
`else` \
    `echo "Invalid username. Must be 3–12 characters, lowercase letters or numbers only."` \
    `exit 1` \
`fi`

## Tools Used:

  - Bash parameter expansion
  - Regex pattern matching
  - Simple conditionals (if / else)
  - User input handling

## Feel free to fork this or use the pattern in your own scripts!
   PRs welcome if you’ve got tricks to make input handling even more bulletproof.
