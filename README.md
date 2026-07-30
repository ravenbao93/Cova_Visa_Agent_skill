# COVA Visa Agent

> AI-powered assistant for U.S. residents applying for Chinese visas via COVA (cova.mfa.gov.cn)

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Version](https://img.shields.io/badge/version-2.0.0-green.svg)](#)

## Overview

COVA Visa Agent transforms the Chinese visa application process into a simple conversation. The AI guides you through quick YES/NO questions, validates your information, and helps fill the COVA form step-by-step.

### Features

- Conversational YES/NO interview
- Smart validation (passport, 90-day rule)
- Personalized document checklist
- Step-by-step form filling
- Risk assessment

---

## Quick Start

### Prerequisites

- Valid passport (6+ months validity)
- Chrome or Edge browser
- Know your travel dates

### Installation

Place the `cova-visa-agent` folder into your AI agent's skills directory:

| AI Agent | Skills Directory |
|----------|-----------------|
| **Cursor** | `~/.cursor/skills/` |
| **Claude Code** | `~/.claude/skills/` |

### Usage

Start a new conversation and mention:

- "Chinese visa"
- "COVA form"
- "????"

---

## How It Works

**Step 1: Account** --> **Step 2: Visa Type** --> **Step 3: Personal Info**

Log in or register --> Select L/M/Q1/Q2/F/Z --> YES/NO questions

**Step 4: Travel** --> **Step 5: Checklist** --> **Step 6: Form Fill**

Dates & accommodation --> Required documents --> Browser step-by-step

---

## Supported Visa Types

| Code | Name | Requirement |
|------|------|-------------|
| **L** | Tourism | No invitation needed |
| **M** | Business | Invitation letter |
| **Q1/Q2** | Family | Invitation + relationship proof |
| **S1/S2** | Private | Invitation |
| **F** | Exchange | Invitation letter |
| **Z** | Work | Work permit |

---

## Document Checklist

**All Visas:**
- [ ] Passport (6+ months, 2 blank pages)
- [ ] Photo (354x472px, white bg, ?40KB)
- [ ] US residence proof

**L Visa:** Done!

**M Visa:** + Invitation letter

**Q1/Q2:** + Invitation + Relationship proof

---

## Key Rules

| Rule | Requirement |
|------|-------------|
| Passport | 6+ months beyond exit |
| Entry date | Within 90 days |
| Photo | 354x472px, ?40KB |
| Blank pages | 2+ required |

---

## Data Privacy

- No data storage
- Session only
- You review every field
- Only you submit

---

## License

MIT License
