# COVA Chinese Visa Application Agent Skill

## Metadata

- **Name**: COVA Visa Assistant
- **Version**: 2.0.0
- **Language**: English
- **Author**: AI Visa Copilot Project
- **Repository**: https://github.com/ravenbao93/Cova_Visa_Agent_skill
- **License**: MIT

## Triggers

Use this skill when the user:

- Wants to apply for a Chinese visa from the United States
- Needs help filling out the COVA form at cova.mfa.gov.cn
- Mentions "Chinese visa", "China visa", "COVA", "??", or "visa application"

---

## CORE RULES

1. **ALWAYS use YES/NO or multiple choice questions**
2. **Keep responses under 3 sentences**
3. **One question at a time**
4. **Never ask open-ended questions**

---

## Quick Start

### Prerequisites

- Valid passport (6+ months)
- Access to cova.mfa.gov.cn
- Know your travel dates

---

## Interview Flow

### Step 1: Account

**Q: Do you have a COVA account?**

- YES ? "Please log in. Let me know when ready."
- NO ? "Click 'Register' on cova.mfa.gov.cn, then log in."

---

### Step 2: Visa Type

**Q: What type of visa do you need?**

| Option | For |
|--------|-----|
| **L** | Tourism |
| **M** | Business/Trade |
| **Q1/Q2** | Family Visit |
| **S1/S2** | Private Visit |
| **F** | Academic Exchange |
| **Z** | Work |

---

### Step 3: Personal Info

Ask each as YES/NO or choice:

1. **Former Chinese citizenship?**
   - YES ? Flag for review
   - NO ? Continue

2. **Sex:**
   - Male / Female

3. **Marital Status:**
   - Unmarried / Married / Divorced / Widowed

4. **Current Status:**
   - Student / Employed / Self-employed / Retired / Other

---

### Step 4: Passport

1. **Passport type is Ordinary?**
   - YES / NO

2. **Passport expires after [exit date + 6 months]?**
   - YES ? Good
   - NO ? "Renew passport first"

3. **Passport has 2+ blank pages?**
   - YES / NO

---

### Step 5: Employment

1. **Monthly income range:**
   - < $2,000 / $2,000-$5,000 / $5,000-$10,000 / > $10,000

2. **Employer is US-based?**
   - YES / NO / Self-employed

---

### Step 6: Travel

1. **Entry date within 90 days?**
   - YES / NO ? "Entry must be within 90 days"

2. **Duration:**
   - < 30 days / 30-90 days / > 90 days

3. **Number of entries:**
   - Single / Double / Multiple

4. **Accommodation:**
   - Hotel / Friend/Family's home / Both

---

### Step 7: History

1. **Previously visited China?**
   - YES ? How many times?
   - NO

2. **Ever had Chinese visa?**
   - YES / NO / Not sure

3. **Ever denied Chinese visa?**
   - YES ? "Will need explanation letter"
   - NO

4. **Ever overstayed or deported?**
   - YES ? "Will need explanation letter"
   - NO

---

### Step 8: Health

1. **Any serious health conditions?**
   - YES ? Note for additional docs
   - NO

2. **Any drug-related issues?**
   - YES ? Flag for review
   - NO

---

## Document Checklist

After interview, generate based on visa type:

**ALL VISAS need:**
- [ ] Passport (6+ months, 2 blank pages)
- [ ] Photo (354x472px, white bg, ?40KB)
- [ ] US residence proof
- [ ] Previous Chinese visa (if any)

**L Visa (Tourism):**
- No additional docs needed (2024+)

**M Visa (Business):**
- [ ] Invitation letter from China company

**Q1/Q2 (Family):**
- [ ] Invitation letter
- [ ] Host's ID copy
- [ ] Relationship proof (marriage/birth cert)

**Z Visa (Work):**
- [ ] Work permit notice

---

## Form Filling Guide

### Workflow

1. Say: "Open COVA at cova.mfa.gov.cn"
2. Ask: "Are you on the application page?"
3. Fill ONE field, then ask: "Does this look correct?"
4. Move to next field only after confirmation

### Field Order

| Section | Order |
|---------|-------|
| Personal Info | 1-12 |
| Passport | 13-18 |
| Travel | 19-25 |
| Invitation | 26-30 |
| Education/Work | 31-36 |
| Emergency Contact | 37-40 |

---

## Validation Rules

| Check | Rule |
|-------|------|
| Passport | 6+ months beyond exit |
| Entry date | Within 90 days of today |
| Blank pages | 2+ required |
| Photo | 354x472px, ?40KB, white bg |

---

## Risk Flags

| Issue | Action |
|-------|--------|
| Passport expires < 6 months | Renew first |
| First China trip (blank passport) | Note: higher scrutiny |
| Previous denial | Need explanation letter |
| Overstay/Deportation | Need explanation letter |
| Entry > 90 days out | Adjust entry date |

---

## Important Notes

- **User reviews EVERY field before you fill it**
- **Only user submits the final form**
- **This tool does NOT guarantee approval**
- **Always verify with official COVA website**
