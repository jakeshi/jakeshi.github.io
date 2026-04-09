---
layout: post
title: "Your Calendar Is Not Your Brain"
date: 2026-04-09 00:00:00 -0700
categories: ai productivity design
author: Jake
---

I have been thinking about a different kind of AI assistant.

Not one that summarizes your meetings.
Not one that rephrases your email.
Not one that gives you a prettier dashboard full of things you already know.

I want one that asks better questions.

That is the core idea.

Most workplace AI tools today are built around passive recap. They ingest your calendar, your chat, your inbox, then generate a summary nobody really wants to read. The problem is not that the models are too weak. The problem is that the interaction model is wrong.

The best assistant for knowledge work should not just replay the past. It should help you surface what matters, notice where you are stuck, and ask the one question that changes how you spend the day.

## The Failure Mode I Keep Seeing

Microsoft Copilot is the clearest example of this. In theory it has access to the raw material of work: meetings, chats, email, documents. In practice the output still feels low-quality.

Why?

Because raw corporate exhaust is not insight.

A calendar tells you where you were supposed to be. It does not tell you what you were avoiding.
An inbox tells you what entered your attention. It does not tell you what deserved it.
A task list tells you what you wrote down. It does not tell you what keeps slipping.

The missing piece is a system that can combine context with dialogue.

## The Product Idea

My current design is a personal AI assistant built around an Obsidian vault.

The vault is the brain.

Not a database hidden behind some SaaS app. Not a productivity dashboard that dies when the startup pivots. Just markdown files on disk, visible and editable at all times.

The assistant sits on top of that vault and does a few things well:

- tracks daily intentions
- records what actually happened
- pulls in relevant context from calendar and Jira
- notices patterns over time
- asks better questions than I would ask myself on a tired Tuesday morning

That last part is the whole product.

## What Makes This Interesting

The exciting part is not "AI plus notes." That framing is too shallow.

The interesting part is using an LLM as a compiler for personal work life.

Karpathy once described a pattern I keep coming back to: raw data gets compiled by an LLM into a growing markdown wiki. That idea clicks immediately for this problem. Your vault becomes a record of intentions, decisions, time spent, recurring blockers, and half-formed thoughts. The assistant's job is to quietly turn that into something queryable and useful.

After three weeks, the value is not that you have more notes.

The value is that the assistant can say something like:

"You have deferred the same kind of roadmap conversation four times. Do you want to talk about what is actually blocking it?"

That is a much more interesting product than "Here is your summary of meetings from this week."

## Design Principles

I am trying to keep the design opinionated.

### 1. Dialogue first

The assistant should lead with questions, not dashboards.

If the interaction starts with charts, I already know how this ends: another tool that makes me feel organized without actually helping me think.

### 2. Local first

Everything should stay on my machine unless I explicitly allow a read-only fetch from somewhere else.

That matters for privacy, but also for durability. I want my notes, task history, and patterns to live in a format I own.

### 3. Tasks and time are inputs, not outputs

The assistant is not there to produce a fancier project plan. It uses tasks and time logs to understand where my intentions and my behavior diverge.

### 4. Intentional use beats passive surveillance

I do not want an always-on watcher. I want something I invoke a few times a day: morning, mid-day, end of day.

That feels more realistic, more humane, and more likely to survive contact with real work.

## Why Obsidian

Obsidian is already the right frontend.

That is the key decision.

The obvious temptation is to build a full web app: chat UI, dashboard, graphs, integrations, maybe a slick React frontend to make it feel like a real product. I think that is the wrong move for v1.

Obsidian already gives me:

- a local-first note system
- markdown as the storage layer
- visibility into everything the assistant writes
- plugins like Dataview for querying structured notes
- a place where the output can compound over time

So instead of building a UI, I can treat the vault as the product surface and a simple CLI as the control plane.

That is a much better trade.

## What v1 Looks Like

The first version is intentionally small.

Commands like:

- `assistant morning`
- `assistant eod`
- `assistant log 90 "deep work on roadmap"`
- `assistant ask "what have I been avoiding lately?"`

The morning flow only needs to ask three questions:

1. What are the 1-3 things you most need to accomplish today?
2. What is worrying you that is not on your task list?
3. If you have meetings today, which one matters most to prepare for?

That is enough to be useful.

Then at the end of the day, the assistant can come back with a harder question:

You said this mattered most. Did you actually get to it? If not, what got in the way?

That simple loop is already more valuable than most productivity software.

## The Real Product

The productivity angle is almost a Trojan horse.

What I actually want is psychological clarity.

Less ambient stress.
Less vague guilt.
Less feeling that the day disappeared into meetings and reactive work.

If the assistant helps me notice my real patterns, name what I am avoiding, and make better decisions with my attention, then it is doing something much more valuable than task management.

That is the bar.

## Why I Want To Build This

I care about tools that do more than optimize output.

The best tools reduce cognitive load. They help you think more clearly. They give you leverage without making you feel managed by the software.

This idea feels like one of those.

It sits at the intersection of a few things I care deeply about: AI, personal systems, work quality, and the gap between what we say matters and what we actually spend time on.

It also feels like the kind of product that only becomes obvious after living with LLMs for a while. Not "AI for notes," but AI as a reflective layer on top of the raw mess of working life.

That is interesting enough for me to build.

If I ship it, I will write about what works and what breaks.