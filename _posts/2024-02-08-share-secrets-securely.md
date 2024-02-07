---
layout: post
title:  How to share secrets over the Internet?
date:   2024-02-08 01:20:21 +0530
categories: idea app
---

Recently, we've been collaborating with a couple of teams, helping them work on their Rails apps.

The thing with Rails (and actually any framework/app) is that it relies on secret `ENV` variables a lot.

In Rails, there's an encrypted file for secrets that's committed to your version control system (like git) which requires a key to decode.

Once decoded, we can access the values in our code.

So, whoever has access to this key can cause harm (by using the secrets like AWS keys, DB password, session secrets, etc).

Whenever we have to share the secret values, we share them over some kind of a messenger and then delete it once the other person has copied it.

This is a bit dangerous as we don't know whether messenger actually deleted it, or whether it was a soft delete.

To overcome this, I envision an app where I can enter a secret message (like YML, JSON, or just a simple value) and set a password and expiry for it. The app then gives me a URL to share, that I can share with the concerned person, and let them know of the password. With password, the person will be able to decode the secret, and then delete it.

To make it trustable, the code should be open source.

Seems like a small weekend project that I should be able to build with enough motivation!

Here's to hoping that I do.