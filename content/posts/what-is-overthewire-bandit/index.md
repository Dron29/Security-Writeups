---
title: "What Is OverTheWire Bandit? A Beginner's Guide"
date: 2026-09-01
draft: false
description: "A beginner-friendly introduction to OverTheWire Bandit, what it teaches, how it works, and why it is useful for learning Linux and cybersecurity fundamentals."
categories:
  - CTF
tags:
  - OverTheWire
  - Bandit
  - Linux
  - CTF
---

If you're getting started in cybersecurity, you've probably come across terms like *CTF*, *wargames*, *Linux privilege escalation*, or *penetration testing*.

They can sound complicated at first.

One of the best ways to get comfortable with the fundamentals is to stop reading about them and start solving problems yourself. **OverTheWire Bandit** is a great place to do exactly that.

This post is an introduction to Bandit for anyone who has never used it before. I'll also be documenting my own journey through the levels in the posts that follow.

## What is Bandit?

Bandit is a beginner-friendly **wargame** hosted by [OverTheWire](https://overthewire.org/wargames/bandit/), a platform that provides hands-on security challenges designed to help people develop practical technical skills.

Bandit is specifically focused on **Linux and command-line fundamentals** and is designed for people who are just starting out. You don't need to already be an experienced penetration tester or security researcher to begin.

The concept is simple.

Each level gives you a set of instructions and a target to investigate. You connect to the Bandit server using **SSH**, explore the environment, and find the password required to access the next level.

The password might be hidden inside a file, protected by unusual permissions, exposed through a process, or require you to understand a particular Linux command or concept.

You solve one level, obtain the credentials for the next one, and continue.

Bandit currently contains **34 levels, from Level 0 through Level 33**, with each level gradually introducing new concepts and making you think a little differently.

## Why is Bandit useful?

A common mistake beginners make when learning cybersecurity is jumping straight into exploitation tools without first becoming comfortable with the environment those tools operate in.

You can learn how to run `nmap`, `ffuf`, Metasploit, or other security tools, but if you're uncomfortable with a Linux terminal, file permissions, processes, pipes, or basic networking, you'll eventually hit a wall.

That's where Bandit is useful.

### 1. It builds real terminal fluency

You're not simply reading about Linux commands.

You're using them to solve an actual problem.

Commands such as:

```bash
ls
cd
cat
find
grep
file
```

become tools for investigation rather than commands you memorized from a tutorial.

### 2. It's free and requires almost no setup

You don't need to download a vulnerable virtual machine or spend hours configuring a lab.

All you need is an SSH client and an internet connection.

Linux and macOS already include SSH, while modern versions of Windows provide SSH through PowerShell and Windows Terminal.

### 3. It teaches you to think instead of just following instructions

The most valuable part of Bandit isn't memorizing commands.

It's developing the habit of asking:

> **What do I know, what can I observe, and where could the information I'm looking for be?**

That mindset becomes increasingly important when you move from controlled CTF environments into penetration testing, bug bounty hunting, and security research.

### 4. The difficulty increases gradually

Bandit doesn't throw advanced exploitation techniques at you immediately.

Instead, each challenge builds on concepts introduced earlier. This makes it much easier to identify what you don't understand and learn it along the way.

## What can you learn from Bandit?

Bandit provides hands-on practice with several important Linux and security fundamentals, including:

- Linux filesystem navigation and file manipulation
- Searching for files and information
- File permissions and ownership
- Standard input, output, pipes, and redirection
- Command-line text processing
- Processes and basic process investigation
- SSH and authentication
- SSH keys and related concepts
- Basic networking and network services
- Cron jobs and scheduled tasks
- SUID binaries and privilege boundaries
- Working with different file formats
- Reading and understanding command output
- Combining multiple Linux commands to solve a problem

None of this is "Hollywood hacking."

And that's precisely the point.

These fundamentals might seem boring compared with exploiting a web application or getting a shell on a target, but they're the foundation you'll repeatedly rely on when working with real systems.

You can't effectively investigate a compromised Linux server if you're struggling to navigate its filesystem.

You can't understand privilege escalation if you don't understand permissions.

And you can't troubleshoot a security problem efficiently if you're uncomfortable working from a terminal.

**The fundamentals matter.**

## What are the prerequisites?

Bandit deliberately keeps the barrier to entry low.

You don't need an extensive cybersecurity background to start, but a few things will make the experience easier.

### An SSH client

You'll need SSH to connect to the Bandit server.

Linux and macOS users can use the terminal directly.

Windows users can use PowerShell or Windows Terminal, both of which support SSH on modern Windows installations.

### Basic terminal familiarity

You don't need to be a Linux expert.

In fact, learning Linux is one of the reasons to do Bandit in the first place.

However, knowing what a terminal and command-line interface are will make the first few levels less intimidating.

### Patience

This is probably the most important prerequisite.

Some levels can be solved in a few minutes. Others may require you to stop, research a command, understand how something works, and try a different approach.

**Looking up documentation is part of the learning process.**

The goal isn't to prove that you already know everything. The goal is to understand why the solution works.

### Take notes

Don't just solve a level and immediately forget it.

Keep notes about:

- The problem
- Commands you used
- Why those commands worked
- Concepts you learned
- Anything you initially misunderstood

You'll be surprised how often the same Linux or security concept appears again later.

## Is Bandit enough to learn cybersecurity?

No.

And it's important to be clear about that.

**Completing Bandit does not make you a penetration tester.**

Bandit is primarily a way to build foundational Linux, command-line, and problem-solving skills.

After that, you'll need to expand into areas such as:

- Networking
- Web application security
- Authentication and authorization
- Active Directory
- Privilege escalation
- Vulnerability research
- Cloud security
- Scripting and automation
- Enumeration and reconnaissance
- Secure coding and application architecture

Think of Bandit as **one building block**, not the entire building.

## How I'll be documenting the journey

Rather than putting every solution into one enormous article, I'll be breaking the Bandit journey into individual writeups.

For each level, I'll document:

1. The objective
2. My initial observations
3. The commands I used
4. Why the solution works
5. The important concept behind the challenge
6. What I learned

I'll also avoid simply dumping commands without explanation.

The goal is to document the **reasoning behind the solution**, because understanding *why* something works is much more valuable than copying a command and moving on.

## What's next?

Now that we know what OverTheWire Bandit is, it's time to actually start solving it.

In the next post, we'll begin with **Bandit Level 0 → Level 1** and work through the challenge step by step.

If you're completely new to Linux or cybersecurity, follow along and try solving each level yourself before reading the solution.

That's where the real learning happens.

**Next:** [OverTheWire Bandit — Level 0 → Level 1](#)