# COVA Visa Agent

> An AI-powered assistant that guides U.S. residents through the Chinese visa application process via conversational interview, then auto-fills the official COVA form.

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Version](https://img.shields.io/badge/version-1.0.0-green.svg)](#)

## Overview

COVA Visa Agent is a Claude Code Agent Skill that transforms the complex Chinese visa application process into a simple conversation. The AI interviews the applicant, validates their information, generates a personalized document checklist, and assists with filling the official COVA (Chinese Visa Online Application) form at [cova.mfa.gov.cn](https://cova.mfa.gov.cn).

### Features

- **Conversational Interview**: Natural Q&A format to collect all required information
- **Smart Validation**: Passport expiry checks, 90-day rule enforcement, logical consistency
- **Document Checklist**: Personalized checklist based on visa type and personal situation
- **Form Auto-Fill**: Step-by-step assistance filling the COVA web form
- **Risk Assessment**: Flags potential issues (blank passport, previous denials, etc.)
- **Multi-Visa Support**: L, M, F, Q1/Q2, S1/S2, Z, X1/X2, and more

## Quick Start

### Prerequisites

- An AI coding agent installed:
  - [Cursor](https://cursor.com) (recommended)
  - [Claude Code](https://claude.ai/code)
  - [VS Code with Copilot](https://code.visualstudio.com/)
  - Other AI agents with skill loading capability
- Access to [cova.mfa.gov.cn](https://cova.mfa.gov.cn)
- A valid passport (6+ months validity)
- Chrome or Edge browser recommended

### Installation

1. Download or clone this repository
2. Place the `cova-visa-agent` folder into your AI agent's skills directory:

   | AI Agent | Skills Directory |
   |----------|-----------------|
   | **Cursor** | `~/.cursor/skills/` |
   | **Claude Code** | `~/.claude/skills/` |
   | **VS Code + Copilot** | Not supported (no skill system) |
   | **Other** | Check your agent's documentation |

   Example for Cursor:
   ```bash
   cp -r cova-visa-agent ~/.cursor/skills/
   ```

3. Restart your AI agent

### Usage

Start a new conversation with Claude Code and the skill will automatically activate when you mention:

- "Chinese visa"
- "China visa application"
- "COVA form"
- "??" (Chinese for visa)

Or simply describe your need:
> "I want to apply for a Chinese visa from the United States"

## How It Works

**Step 1: Interview** --> **Step 2: Validation** --> **Step 3: Checklist**

Conversational Q&A --> Smart checks & risk flags --> Personalized document list

**Step 6: Guidance** <-- **Step 5: Document** <-- **Step 4: Form Fill**

Submit help & next steps <-- Photo tips & uploads <-- Step-by-step browser fill

## Supported Visa Types

| Code | Name | Key Requirement |
|------|------|----------------|
| **L** | Tourism | Simplified (2024+) - No invitation needed |
| **M** | Business/Trade | Invitation letter from China |
| **F** | Visit/Exchange | Invitation letter from China |
| **Q1** | Long-term Family | Invitation + relationship proof |
| **Q2** | Short-term Family | Invitation from family member |
| **S1** | Long-term Private | Invitation + relationship proof |
| **S2** | Short-term Private | Invitation from resident foreigner |
| **Z** | Work | Valid work permit notice |
| **X1** | Long-term Study | JW201/202 + admission notice |
| **X2** | Short-term Study | Admission notice |

## Key Features in Detail

### 1. Conversational Interview

The agent asks one question at a time, covering:

- Personal information (name, DOB, nationality, address)
- Passport details
- Education and employment
- Travel plans and itinerary
- Emergency contact in China
- Previous China travel and visa history
- Health and background questions

### 2. Smart Validation

**Passport Validity Check:**
```
Your passport expires on [DATE]
You plan to exit China on [DATE]
-> Must be valid 6+ months beyond exit date
```

**90-Day Rule Enforcement:**
```
COVA requires entry date within 90 days of application
-> Warning if planned entry is too far in the future
```

### 3. Personalized Document Checklist

Generated based on your specific visa type and situation:

**L Visa Example:**
- [ ] Passport (6+ months validity, 2 blank pages)
- [ ] Photo (354×472px, white background, ?40KB)
- [ ] US residence proof (driver's license, utility bill)
- [ ] Previous Chinese visa page (if applicable)

**Q1/Q2 Family Visa Add:**
- [ ] Invitation letter from Chinese host
- [ ] Host's Chinese ID or passport
- [ ] Relationship proof (marriage certificate, birth certificate)

### 4. Form Auto-Fill

The agent fills the COVA form field by field while you watch:

1. You confirm browser is open at cova.mfa.gov.cn
2. Agent fills one field at a time
3. You verify each entry
4. Agent moves to next field

### 5. Document Upload Guidance

Photo tips:
- **Size**: 354¡Á472 pixels
- **Background**: White or light-colored
- **File size**: At least 40KB
- **Tip**: If file is too small, increase resolution before compressing to JPEG

## Important Rules

### Key Requirements

| Rule | Details |
|------|---------|
| **Passport Validity** | Must be valid for 6+ months beyond planned China exit |
| **90-Day Rule** | Entry date must be within 90 days of application date |
| **Photo Size** | Minimum 40KB, 354¡Á472 pixels |
| **Blank Pages** | At least 2 blank visa pages required |

### Processing Times (2025)

| Service | Time |
|---------|------|
| Regular | 4 business days |
| Rush | 3 business days |

### Fees (USD)

| Visa Type | Regular | Rush |
|-----------|---------|------|
| Single Entry | $185 | $185 + $30 |
| Double Entry | $185 | $185 + $30 |
| Multiple Entry | $185 | $185 + $30 |

*Fees may vary. Check official consulate website for current rates.*

## U.S. Consulates

| City | Address | Phone |
|------|---------|-------|
| Washington DC | 2201 Wisconsin Ave NW | 202-495-2071 |
| New York | 520 12th Ave | - |
| Los Angeles | 500 Shatto Pl | 213-807-8088 |
| Chicago | 1 East Erie St | - |
| San Francisco | 1450 Laguna St | - |

## Workflow Example

```
You: "I want to apply for a Chinese tourist visa"

Agent: "Great! Let's start your L (Tourism) visa application.
        I'll guide you through each step.
        
        First, what is your full name as shown on your passport?"

You: "John Michael Smith"

Agent: "Thank you. Now, do you have your passport handy?
        What is your passport number?"

[Continues interview...]

Agent: "Based on your L visa application, here's your checklist:

        REQUIRED FOR ONLINE SUBMISSION:
        - [ ] Passport info page photo
        - [ ] Photo (354×472px, white background, ?40KB)
        - [ ] US residence proof
        
        REQUIRED AT CONSULATE:
        - [ ] Original passport
        - [ ] Application confirmation (with barcode)
        
        Your passport is valid through [DATE] - perfect!
        Let's start filling the form. Please open cova.mfa.gov.cn
        in your browser and let me know when you're ready."
```

## Data Privacy

- **No Data Storage**: The agent does not store passport numbers or personal information
- **Session Only**: All data remains in your conversation session
- **User Control**: You review and confirm every field before it's used
- **Manual Submission**: Only you can submit the final application

## Troubleshooting

### Common Issues

**"My passport expires in 5 months"**
> You need to renew your passport first. Most countries require 6+ months validity beyond your trip.

**"I don't have an invitation letter"**
> For L (Tourism) visas, no invitation is needed (simplified process since 2024).

**"My photo is too small"**
> Try increasing the image resolution first, then export as JPEG with lower compression.

**"I was denied a Chinese visa before"**
> Previous denials are noted but don't automatically disqualify you. Provide additional documentation.

## Contributing

Contributions welcome! Please:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Disclaimer

This tool is for informational and educational purposes only. It does not guarantee visa approval. Always refer to the official [Chinese Embassy](https://us.china-embassy.gov.cn) or [COVA](https://cova.mfa.gov.cn) websites for the most current requirements and procedures.

---

*COVA Visa Agent is not affiliated with the Chinese government or any official consulate. Use at your own discretion.*
