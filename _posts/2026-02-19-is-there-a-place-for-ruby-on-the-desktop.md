---
layout: post
title: "Is there a place for Ruby on the Desktop?"
date: 2026-02-19 12:00:00 +0000
categories: [Ruby, Desktop]
tags: [ruby, desktop, electron, tauri, tebako, glimmer-dsl, shoes, gui, software-engineering]
description: "Exploring the state of Ruby desktop application development in 2026. A look at Glimmer DSL, Tebako, and the challenges of packaging and updates compared to Electron and Tauri."
---

Recently, I faced a challenge: one of the projects I'm working on needed to develop a **desktop application**. It required a simple UI but had some specific backend logic. Now, here is the kicker: the team I’m working with is entirely JS-focused. For them, a JS-based solution is the obvious, perfect choice. But as someone who loves Ruby, I really wanted to find a modern, "cool" **Ruby-native way** to build this. I wanted to see if I could bring that Ruby productivity to the desktop.

I looked, and honestly? I was disappointed.

Usually, you pick the stack your team is using and go. But I was hoping to find a reason to advocate for Ruby. Instead, I hit a wall.

## What about Ruby-native desktop frameworks?

[Shoes](http://shoesrb.com/) is long gone.

[Glimmer DSL](https://github.com/AndyObtiva/glimmer-dsl-libui) is impressive work. Massive respect to Andy Maleh for the incredible work there but it’s far from being a standard practice. Convincing a team of JS developers to adopt it for a commercial project is an impossible sell.

## The Packaging Struggle

Even if I built the app, how would I package it? I checked out [Tebako](https://github.com/tamatebako/tebako). It’s probably the most modern bundler we have, but it’s still tricky. For example, building for older OS versions from a newer machine is a major headache. If I’m on the latest macOS, I still need to support users on older versions. In Ruby, this is a critical hurdle.

## The Update Problem

And then there's the "day two" problem: Updates. In a JS environment ([Electron](https://www.electronjs.org/)/[Tauri](https://tauri.app/)), there are battle-tested ways to push updates. In Ruby? There isn’t a "plug-and-play" solution. You have to build the entire update infrastructure yourself.

## The Bottom Line

It’s frustrating. I wanted to prove that Ruby could be a great tool for this, but the infrastructure just isn't there. When you compare it to the JS ecosystem, the gap is massive. Writing in JS might not feel as "pleasant" as Ruby, but the tools, the packaging, and the delivery are all solved problems.

Can we build serious desktop apps in Ruby? Maybe. But is it a viable choice for a professional team today? I'm not so sure. We need better tools and a much stronger ecosystem to even make it a conversation.

I want to ask the community: Am I the only one frustrated by this? Is there a genuine need for a Ruby-native desktop infrastructure, or should we just accept that the desktop belongs to other stacks?

I’m thinking of doing a series of posts on this. This is part one—just some honest reflections. What do you think?

We can discuss here on the bottom comments section or under my original linkedin post: [Link to post](https://www.linkedin.com/posts/artem-blazhievskii_ruby-desktopdevelopment-softwareengineering-activity-7430217384738594816-6HHq?utm_source=share&utm_medium=member_desktop&rcm=ACoAAD6olY8BDiOU5Ou2r5IWYBi5tDC_KOgHrC4)
