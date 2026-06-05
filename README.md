# Probability-Distribution-Lab
My Lab work from triAI programme
# Lab: Create Your Own Probability Distribution

## Overview

This lab explores how language models use probability distributions to predict the next word in a sentence. Rather than letting a model do it automatically, I assigned probabilities manually to understand the core intuition behind how LLMs generate text.

## What I Investigated

> *“Jide was hungry so she went looking for…”*

Given a list of candidate words, I assigned probabilities reflecting how likely each word was to follow the prompt — then used Python’s `random.choices()` to sample the next word.

## Tools Used

- Python 3
- Google Colab
- `random` module
- `ai_foundations` custom package (triAI)

## Key Tasks

### Activity 1 — Assigning probabilities for a prompt

Prompt: *“Jide was hungry so she went looking for”*

|Word          |Probability|
|--------------|-----------|
|food          |0.36       |
|snacks        |0.34       |
|leftovers     |0.19       |
|her           |0.02       |
|for           |0.02       |
|water         |0.05       |
|photosynthesis|0.01       |
|pyramid       |0.01       |

**Output:** *“Jide was hungry so she went looking for food…”*

### Activity 2 — The importance of context

Prompt changed to: *“Jide was THIRSTY so she went looking for”*

|Word          |Probability|
|--------------|-----------|
|food          |0.1        |
|snacks        |0.1        |
|leftovers     |0.06       |
|her           |0.04       |
|for           |0.03       |
|water         |0.6        |
|photosynthesis|0.04       |
|pyramid       |0.03       |

**Output:** *“Jide was thirsty so she went looking for water…”*

## Key Findings

- Changing one word in the prompt (*hungry* → *thirsty*) completely shifted the probability distribution
- “Water” jumped from 5% to 60% probability — context drives everything
- This is exactly what large language models do automatically at scale: assign probabilities based on context and sample from them
- Words that are grammatically valid but contextually unlikely (e.g. “photosynthesis”, “pyramid”) received near-zero probabilities

## What I Learned

Language models are fundamentally **probability machines**. Every word they generate is a sample from a distribution shaped by context. This lab made that concrete by doing it manually first.

## Part Of

[triAI Program](https://aisaturdayslagos.github.io) — AI Saturdays Lagos
Course 1: Foundations of Language Modeling | Week 1
