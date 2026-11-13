# Keeping her private

Purpose: tell you what stops other people and other web pages from using Khadijah, and how to see it working.
Owner: Rafiq. Version 0.1.0 (agreed by Rafiq, 2026-11-02). Date: 2026-11-02.

Khadijah is built so that only this laptop can reach her.

## What protects her

1. **She listens on this laptop only.** Other computers on your network cannot reach her.
2. **She answers only to two names.** These are `localhost` and `127.0.0.1`. A web page cannot reach her under any other name.
3. **She refuses requests from other web pages.** Anything that changes something must come from her own page. If it does not, she refuses it with "Forbidden: cross-origin request."
4. **She allows one live page at a time.** If you open a second tab, the first one stops working. Use the newest tab.
5. **Her page cannot be put inside another site's page.**

These rules are on by default. Do not turn them off.

## Your private details

- Your keys are in the Windows credential store, not in a file.
- Your settings file, `data\config.json`, holds private details. Do not paste it into chats or emails.
- Your microphone is off every time the page opens. Only you turn it on.

## How to see it working

Open her page at `http://localhost:8340`. It works.

Open `http://127.0.0.1:8340`. It also works.

Try the same address from another computer on your network. It does not connect.

## If a good request is refused

Open her page at `http://localhost:8340` and try again. If it still fails, read **Problems and fixes**.
