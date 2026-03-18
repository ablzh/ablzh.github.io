---
title: "Introducing Ruby Sandbox: A Web-Based Playground for Beginners"
date: 2026-02-26 9:00:00 +0800
categories: [Programming, Ruby]
tags: [ruby, education, webassembly, tutorial, programming-for-beginners]
description: "Discover Ruby Sandbox, a web-based WASM playground designed to make learning Ruby as accessible as Python's Turtle. No installation required."
---

## About Ruby Sandbox

So, what’s the plan and why am I even doing this?

Originally, I was inspired by the Python sandbox and wanted to build something similar for Ruby. As a teacher, I know all too well: if a tool isn't documented and doesn't have a lesson plan, it basically doesn't exist for schools.

In primary and middle school, "Turtle" graphics are the bread and butter of programming. And, as you know, everyone uses Python for this. Even if a teacher wanted to use Ruby, they’d hit a wall:

- **"Who’s going to let me?"** (Getting Ruby installed on school computers is a mission).
- **"Where’s the curriculum?"** (Okay, I got it installed, but what do I actually teach?).
- **"Wait, does Ruby even have a Turtle?"** Spoiler: Ruby doesn't have a Turtle.

I’ve spent years creating educational materials, and honestly, I have zero desire to write a whole new "Turtle curriculum" right now. I usually find more exciting ways to get students hooked anyway. But I do believe that the more diverse a language's ecosystem is, the better. So, I decided to build it.

## Current State & Future Plans

Just to be clear: I'm just getting started. Right now, there’s only the [Ruby WASM playground](https://ablzh.dev/ruby-sandbox/index.html); everything else is a work in progress (assuming I have the time and energy).

My vision includes 3 modes:

### 1. Free Playground

Just a sandbox to poke at some code. No terminal, no debugger (and I don't plan on adding them—I want to keep it simple). Just use good old `puts` for debugging. It runs on WASM Ruby, so while it doesn't support everything CRuby does, it’s more than enough for the basics.

### 2. The Turtle (WIP)

I want to make it as close to the Python implementation as possible, so you can use the same teaching methods. A quick note: I’m not making a standalone gem or writing lessons myself. I’m building the tool. If any of you want to create a curriculum for it—awesome! I’ll happily link to it right here in the Turtle section.

### 3. Introductory Course (WIP)

I’m planning a beginner course inspired by the book *Learn to Program* by Chris Pine (That book is really good! Thanks, man!). The entire first part will be doable right here in the browser to lower the "barrier to entry" as much as possible.

## Why a Web Sandbox?

Because setting up an environment for a total beginner is a nightmare.

I remember trying to learn C++ in middle school using a 3G modem with speeds measured in kilobytes... downloading Visual Studio, trying to configure everything—it was brutal. Modern students might not be the same kind of "nerds" I was, and I see how even basic things like file systems or ZIP archives can cause panic.

Before we force a student to fight with terminals and dependencies, they need a reason to care about the code itself. **Ruby Sandbox** is a way to try the language without the pain. No downloads, no setup. And if you want offline access, just "install" the site as a PWA (thanks to Vite, it works surprisingly well).

Bottom line: I want to hold your hand through the very first steps, but then let you fly solo once you’re ready for the "real" struggle with local environments.

If you recognized yourself in my description of a scared beginner—don't take it personally. I'm doing this specifically for you, my friend :)

[**Try the Ruby Sandbox now!**](https://ablzh.dev/ruby-sandbox/index.html)
