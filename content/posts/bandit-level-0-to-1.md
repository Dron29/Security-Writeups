---
title: "OverTheWire Bandit Level 0 → Level 1 Writeup"
date: 2026-09-06
draft: false
description: "A beginner-friendly walkthrough of OverTheWire Bandit Level 0 to Level 1 using basic Linux commands to locate and read the password file."
tags:
  - overthewire
  - bandit
  - linux
  - ssh
  - ctf
categories:
  - CTF
  - OverTheWire
---

# OverTheWire Bandit Level 0 → Level 1

## Introduction

In this writeup, I'll walk through how I solved **OverTheWire Bandit Level 0 → Level 1**.

The Bandit wargame is designed to teach the basics of Linux, command-line usage, file manipulation, permissions, SSH, and other concepts that are useful when working in cybersecurity.

This first level is intentionally simple, but it introduces an important habit:

> **Don't blindly run commands. Understand what you're looking for and why a command helps you find it.**

---

## Level Goal

The goal of this level is straightforward:

> The password for the next level is stored in a file called `readme` located in the home directory.

Once the password is obtained, it can be used to log into the next account, `bandit1`, over SSH on port `2220`.

The challenge also recommends keeping personal notes of the passwords because the passwords are not saved automatically.

---

## Step 1 — Check the Current Directory

After connecting to the Bandit server, I first wanted to know where I was.

I used:

```bash
pwd
```

The output was:

```text
/home/bandit0
```

### What does `pwd` do?

`pwd` stands for **Print Working Directory**.

It displays the absolute path of the directory I'm currently working in.

In this case:

```text
/home/bandit0
```

This is important because the level tells us that the `readme` file is located in the **home directory**.

So I'm already in the correct location.

---

## Step 2 — List the Files

Next, I needed to see what files were present in the directory.

I used:

```bash
ls
```

The output showed:

```text
readme
```

This immediately tells us that the file we're looking for exists in the current directory.

### What does `ls` do?

`ls` lists the files and directories contained within the current directory.

So the process so far is:

```text
pwd
 ↓
/home/bandit0

ls
 ↓
readme
```

We have found the target file.

---

## Step 3 — Read the `readme` File

Now that I know the file exists, I need to read its contents.

I used:

```bash
cat readme
```

The terminal displayed:

```text
Congratulations on your first steps into the bandit game!!

Please make sure you have read the rules at https://overthewire.org/rules/
If you are following a course, workshop, walkthrough or other educational activity,
please inform the instructor about the rules as well and encourage them to
contribute to the OverTheWire community so we can keep these games free.

The password you are looking for is:
```

The password itself is intentionally **not shown in this writeup**.

I copied the password and stored it securely in my personal notes so that I could use it for the next level.

---

## Understanding the Commands

Although this level is very easy, it introduces three fundamental Linux commands.

| Command | Purpose |
| --- | --- |
| `pwd` | Shows the current working directory |
| `ls` | Lists files and directories |
| `cat` | Displays the contents of a file |

The complete process was:

```bash
pwd
ls
cat readme
```

That's all that was required to solve Level 0 → Level 1.

---

## Why This Approach Works

The challenge description already gives us the most important piece of information:

```text
The password is stored in a file called readme
```

Instead of searching the entire filesystem, we can use the information provided by the challenge.

First:

```bash
pwd
```

confirms our current location.

Then:

```bash
ls
```

shows us the files in that directory.

Finally:

```bash
cat readme
```

reads the contents of the target file.

This is a simple example of **enumeration**:

1. Identify where you are.
2. Identify what is available.
3. Inspect the relevant resource.
4. Extract the required information.

This same mindset becomes much more important in later Bandit levels and in real-world security testing.

---

## Step 4 — Log Into the Next Level

After obtaining the password, the next step is to connect to the `bandit1` account.

The Bandit server uses SSH on port `2220`.

The command is:

```bash
ssh bandit1@bandit.labs.overthewire.org -p 2220
```

When prompted for the password, enter the password obtained from the `readme` file.

> **Note:** I am intentionally not publishing the password here. Bandit passwords can change, and exposing credentials in a public writeup defeats the purpose of the exercise.

If the password is correct, I will be logged into the next level:

```text
bandit1@bandit:~$
```

At this point, Level 0 → Level 1 is complete.

---

## What I Learned

Even though this was the easiest Bandit level, it introduced several Linux fundamentals that are worth remembering.

### 1. `pwd` — Know Where You Are

Before interacting with files, it helps to know your current location.

```bash
pwd
```

This prevents unnecessary confusion when working with files and directories.

### 2. `ls` — Enumerate Your Environment

When entering an unfamiliar directory, `ls` is one of the first commands worth running.

```bash
ls
```

It gives a quick overview of the files and directories available in the current location.

### 3. `cat` — Read Files

When you know the file you want to inspect, `cat` can display its contents directly.

```bash
cat readme
```

### 4. Read the Challenge Carefully

The challenge itself told us exactly where the password was located.

There was no need for complicated tools or automated enumeration.

The key was simply to understand the instructions and use the appropriate Linux commands.

---

## Commands Used

For this level, I only needed three Linux commands:

```bash
pwd
ls
cat readme
```

And to connect to the next level:

```bash
ssh bandit1@bandit.labs.overthewire.org -p 2220
```

---

## Key Takeaways

The first Bandit level is simple, but it establishes the basic methodology that will be useful throughout the game:

- Understand the objective before running commands.
- Check your current directory with `pwd`.
- Enumerate files with `ls`.
- Read files with `cat`.
- Save passwords and notes locally.
- Don't expose challenge passwords in public writeups.
- Use SSH to move between Bandit levels.
- Start with the simplest approach before reaching for complex tools.

The real lesson isn't the command itself. It's developing the habit of **observing the environment first and then choosing the simplest command that answers the question.**

---

## Conclusion

Bandit Level 0 → Level 1 was a straightforward introduction to the Linux command line.

The password was stored in the `readme` file inside `/home/bandit0`. By confirming my location with `pwd`, listing the directory with `ls`, and reading the file with `cat`, I was able to retrieve the password and move on to the next level.

This level may be simple, but the methodology is important:

**Understand → Enumerate → Inspect → Extract → Move Forward**

As the Bandit levels become more difficult, the same process of understanding the environment and reasoning about the available information becomes increasingly important.

Next up: **Bandit Level 1 → Level 2**, where things get slightly more interesting.

---

## Resources

- [OverTheWire Bandit](https://overthewire.org/wargames/bandit/)
- [OverTheWire Rules](https://overthewire.org/rules/)
- [Ubuntu `pwd` Manual](https://manpages.ubuntu.com/manpages/noble/man1/pwd.1.html)
- [Ubuntu `ls` Manual](https://manpages.ubuntu.com/manpages/noble/man1/ls.1.html)
- [Ubuntu `cat` Manual](https://manpages.ubuntu.com/manpages/noble/man1/cat.1.html)