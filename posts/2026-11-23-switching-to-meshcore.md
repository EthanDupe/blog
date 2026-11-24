---
title: Why I switched from Meshtastic to MeshCore
date: 2026-11-23
tags: lora, meshcore, hardware
summary: Moving my Heltec V3 off Meshtastic and why MeshCore feels a lot cleaner for what I actually want to do.
---

I've been messing around with LoRa for a while now, and for most of that time I was running Meshtastic on my Heltec V3. It works fine out of the box, but after using it for a bit I decided to switch over to MeshCore and honestly I'm very glad I did.

## What bugged me about Meshtastic

Meshtastic tries to do a lot of stuff at once. Every node is kind of flooding packets around by default, and once a few people are on the same channel or someone sets their hop limit too high, things get noisy pretty fast. The codebase also feels pretty heavy when you just want to poke around and change how something works on an ESP32.

I mostly just wanted reliable text messaging, clean routing, and firmware that didn't feel too bloated.

## Why MeshCore fits better

With MeshCore, client nodes and repeaters are actually separate roles. Your node doesn't waste any battery or airtime repeating everyone else's damn traffic unless you explicitly set up a repeater to do that! Messaging feels way better almost quicker and snappier and the whole thing just makes more sense for a local mesh.

It's also way easier to get my hands dirty on. Because the project is smaller and more focused, I can actually read through the source, strip out stuff I don't need, and customize the OLED UI for my Heltec V3 without fighting a massive build system.

## The trade-offs

It's definitely not as plug-and-play as Meshtastic (yet). Fewer people around my area are on it, so if you're hoping to get a lot more traffic, Meshtastic still has the bigger crowd.

For me though, I think the trade-off is worth it. I'd rather have a smaller, cleaner network I can actually understand and build tools for!
