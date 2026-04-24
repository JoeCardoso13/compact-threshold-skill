<div align="center">
  <img src="https://raw.githubusercontent.com/JoeCardoso13/JoeCardoso13/main/assets/under-construction.svg" alt="Under Construction" />
</div>

---

# Compact Threshold Skill

A Claude Code skill that monitors your context window and gets in your way — on purpose — before it becomes a problem.

## The Idea

Heavy Claude Code sessions accumulate context fast. By the time you think to `/compact`, you've already paid the cost. This skill flips that: it watches the threshold and surfaces the nudge proactively, with `AskUser` so it can't be silently ignored.

## How It Works

When context usage crosses a configurable threshold, the skill interrupts with an `AskUser` prompt:

```
⚠️  Context window at 78%. Time to /compact?

Suggested options:
  /compact                          — standard summary
  /compact keep:last-3-decisions    — preserve key decisions
  /compact keep:architecture        — preserve architecture notes

[compact now] [remind me later] [dismiss]
```

You pick an option, the skill passes the appropriate arguments, and your session stays lean.

## Why `AskUser`

Silent notifications get ignored. `AskUser` blocks until you respond — the interruption is the feature. You stay in flow until the moment it actually matters, then you're forced to make a conscious choice.

## Configuration

- Threshold percentage (default: 75%)
- Snooze interval if dismissed
- Preset argument suggestions tailored to your workflow
