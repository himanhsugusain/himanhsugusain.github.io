+++
date = '2026-07-12T10:03:32+05:30'
draft = true
title = 'From 800s to 100s with half memory'
description = "Using async to boost performance of python script"
tags = [ 'threads', 'coroutines', 'perf' ]
+++

First of all if your simple api calls are taking 100s, that is bad. But given we started from 800s with should be appreciated.All that with minimum effort.

Bit of context, we use simple api calls to make config change across more than 1000 deployments, with each call we fetch current config modify it and put it back. For 1 or 2 deployment this works fine for day to day changes. But when you have to it everywhere and that too in the middle of outage , this becomes a nagging problem.

As always my first thought was to rewrite it in go, I am fan of go's concurrency model and having worked at linkedin's traffic stack and our system in go have performed very well at very high scale with just std go modules. But then asking a good engineering question "Surely I am not the only one with this problem in python".

I admit I am a python noob, never really put effort into learning or understanding it deeply ( because thats the whole selling point of python , isn't it ? ). I knew how fastapi utilize httpx and asyncio to boost your api server performance, but I was using mutli threading, will it really help that much ? So I aksed my pi-agent to swtich everything to Async & httpx.

What gpt-5-6 did "created a async client with httpx" and replaced my threading model with it.
Now one improvement you may immediately note with it is the shared client. Earlier I was using python/request library so every request had to go through entire TLS cycle, now with shared client that overhead is reduced very much.

Second improvement that comes with it is the asyncio event loop, that shared the same idea as go coroutines. Let you program handle the context switches and rather than OS doing the switches and that bring down CPU wait cycles due to less interrupts.

Results

 ![Async_vs_threading](/images/before_and_after_async.png)
