---
layout: post
title: "Ruby on Desktop, Part 2: Searching for the \"Right\" Tool"
date: 2026-02-23 8:00:00 +0800
categories: [Ruby, Desktop]
tags: [ruby, desktop, electron, wxruby, glimmer-dsl, libui, gui, software-engineering]
description: "Exploring Ruby desktop GUI options in 2026. A comparison of Glimmer DSL, wxRuby3, and Electron, focusing on the search for the right tool."
---

I’m a firm believer that simple things should stay simple. For a straightforward task, you should be able to use a straightforward tool.

When it comes to building something truly massive and complex, I have my doubts that Ruby or any interpreted language, for that matter can easily win the race. Carrying a whole interpreter with you always feels a bit like a workaround. JavaScript only gets a "hall pass" here because it’s the industry's special child. :D

Honestly, from the outside, writing a GUI in Ruby often feels like another "kludge." Every tool has its purpose; I don’t eat soup with a fork, and I don’t drive nails with a screwdriver.

## The Electron Standard

But then look at Electron. Thousands of apps are built on it, and they do just fine. The logic stays in Node, the UI stays in Web tech. It works.

**Major Examples:**
Discord, Slack, VS Code, Notion, Obsidian, Signal, 1Password, Figma, Postman, and more...

Try to convince the team to write something serious in Ruby when Electron has such a proven track record that something complex is possible and works well. And what about QT?

I'm not crying it's just raining on my face 😭

## The Ruby Niche

However, there is a specific niche where Ruby could be a perfect fit: **Utilities, companions, and bridges for web apps** cases where the browser "sandbox" prevents you from doing what’s needed. Tasks where the UI is simple, but the business logic is specific. Here, a Ruby GUI stops being "exotic" and starts being a justified solution.

I’d be ready to defend Ruby for these tasks if we had a great solution. But do we?

## The Current Landscape

Let’s look at the current landscape:

### Shoes
As I mentioned in my [first post]({% post_url 2026-02-19-is-there-a-place-for-ruby-on-the-desktop %}), it’s [abandoned](https://github.com/shoes/shoes4).

### [Glimmer DSL for libUI](https://github.com/AndyObtiva/glimmer-dsl-libui)
It feels like a great candidate. Minimum dependencies you install the gem, write a few lines, and boom, a window appears! But **libUI** has been in a "mid-alpha" state for a long time and will likely stay there. While the Glimmer DSL and the [libUI gem (by kojix2)](https://github.com/kojix2/libui) are stable, the functionality is limited and bugs are fixed slowly.

### [Glimmer DSL for SWT](https://github.com/AndyObtiva/glimmer-dsl-swt)
Powerful and reliable. But it requires JRuby and the JVM. For a small system utility? No thanks.

### [wxRuby3](https://github.com/mcorino/wxRuby3) + [Glimmer DSL for wx](https://github.com/AndyObtiva/glimmer-dsl-wx)
**wxRuby3** (by mcorino) is built on the solid wxWidgets, and AndyObtiva’s DSL makes it a joy to use. However, as of early 2026, the last commit in the repo was May 25, 2024. It seems Andy is currently more focused on other great projects like [Glimmer DSL for Web](https://github.com/AndyObtiva/glimmer-dsl-web) (congrats to him on the Fukuoka Future IT 2025 award, by the way!).

However, **wxRuby3** itself receives regular updates, the documentation is quite detailed, and mcorino responds promptly to issues. It seems this method of creating desktop GUI applications in Ruby deserves a green light.

![wxRuby3 Hello World Example](/assets/img/posts/hello-world-wxRuby3-example.png)
_Example of a simple "Hello World" application with wxRuby3_

> wxRuby3 is a cross-platform GUI library for Ruby, based on the mature [wxWidgets](https://wxwidgets.org/) GUI toolkit for C++. It uses native widgets wherever possible, providing the correct look, feel and behaviour to GUI applications on Windows, macOS and Linux/GTK. wxRuby aims to provide a comprehensive solution to developing professional-standard desktop applications in Ruby.

## The Missing Piece

So, here we are in 2026. We have the tools to create a GUI, but we still haven’t solved the one important question: **How do we deliver and update these apps without the pain?**

Imagine if we had something like [electron-builder](https://www.electron.build/), but for the Ruby ecosystem:

> "A complete solution to package and build a ready-for-distribution Ruby GUI app for macOS, Windows, and Linux with 'auto-update' support out of the box. 📦"

Sounds good, doesn't it? ;)

That’s exactly what we’ll talk about in the next posts.
