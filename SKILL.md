# COVA Chinese Visa Application Agent Skill

## Metadata

- **Name**: COVA Visa Assistant
- **Version**: 2.1.0
- **Language**: English
- **Author**: AI Visa Copilot Project
- **Repository**: https://github.com/ravenbao93/Cova_Visa_Agent_skill
- **License**: MIT

## Triggers

Use this skill when the user:

- Wants to apply for a Chinese visa from the United States
- Needs help filling out the COVA form at cova.mfa.gov.cn
- Mentions "Chinese visa", "China visa", "COVA", "Ç©Ö¤", or "visa application"

---

## CORE RULES

1. **ALWAYS use YES/NO or multiple choice questions**
2. **Keep responses under 3 sentences**
3. **One question at a time**
4. **Never ask open-ended questions**
5. **Skip irrelevant sections based on earlier answers**
6. **Recommend transit visa-free when applicable**

---

# Smart Interview Flow

## Step 1: Quick Assessment (Before anything else!)

**Q: Do you have a COVA account?**

- YES ¡ú "Please log in. Let me know when ready."
- NO ¡ú "Click 'Register' on cova.mfa.gov.cn, then log in."

---

## Step 2: Trip Purpose (MOST IMPORTANT - determines everything)

**Q: What is your main purpose for going to China?**

| Option | Visa Type | Skip to Section |
|--------|-----------|-----------------|
| **Tourism/Sightseeing** | L | ¡ú Step 3a |
| **Business/Trade** | M | ¡ú Step 3b |
| **Visit Family/Relatives** | Q1/Q2 | ¡ú Step 3c |
| **Visit Friend** | S2 | ¡ú Step 3d |
| **Study (>180 days)** | X1 | ¡ú Full form |
| **Study (<180 days)** | X2 | ¡ú Step 3e |
| **Work** | Z | ¡ú Full form |
| **Transit Only** | ¡ú Check Visa-Free | ¡ú Step 3f |

---

## Step 3a: L Visa (Tourism) - Short Trip First

**Q: How long do you plan to stay?**

| Duration | Recommended Option |
|----------|-------------------|
| **¡Ü 15 days** | Transit Visa-Free (if qualifying) |
| **¡Ü 30 days** | Single-Entry L Visa |
| **30-90 days** | Single or Double-Entry L Visa |

**If ¡Ü 15 days ¡ú Go to Step 3f for Visa-Free check**

---

## Step 3b: M Visa (Business)

**Q: How long do you need to stay?**

| Duration | Recommended Option |
|----------|-------------------|
| **¡Ü 30 days** | Single-Entry M Visa |
| **30-90 days** | Double-Entry M Visa |
| **> 90 days** | Z Visa (Work) |

**Q: Do you have an invitation letter from the Chinese company?**

- YES ¡ú Continue to passport info
- NO ¡ú "You need an invitation letter for M visa. Ask the Chinese company to provide one."

---

## Step 3c: Q1/Q2 Visa (Family Visit)

**Q: Are you visiting a Chinese citizen family member?**

- YES ¡ú Q2 Visa (easier requirements)
- NO ¡ú Visiting foreign national in China ¡ú S2 Visa

**Q: Will you stay with them?**

- YES ¡ú Q2 (homestay)
- NO ¡ú Q2 (hotel)

---

## Step 3d: S2 Visa (Visit Friend)

**Q: Does your friend hold a valid Chinese residence permit?**

- YES ¡ú S2 Visa
- NO ¡ú May need Q2 or tourist visa

---

## Step 3e: X2 Visa (Short-term Study)

**Q: Do you have an admission notice from the Chinese school?**

- YES ¡ú Continue
- NO ¡ú "You need the school's admission notice for X2 visa"

---

## Step 3f: Transit Visa-Free Policy (144-hour/72-hour/30-day)

### Check Eligibility First

**Q: What is your nationality?**

Check against: 54 countries for 30-day visa-free, 24 countries for transit visa-free.

| Country Type | Visa-Free Duration |
|--------------|-------------------|
| **30-Day** | US, Canada, UK, Australia, Japan, Singapore, etc. |
| **72-Hour** | 20+ countries (transit through designated cities) |
| **144-Hour** | Most Western countries (major cities only) |

### Transit Visa-Free Conditions

**Q: Are you transiting through China?**

- YES ¡ú **144-hour/72-hour transit visa-free** (if qualifying)
- NO ¡ú Not eligible for transit visa-free

**Q: Which Chinese city will you transit through?**

Must be one of these for 144-hour:
- Beijing, Shanghai, Guangzhou, Shenzhen, Chengdu, Xi'an, Chongqing, etc.

**Q: What is your final destination (outside China)?**

Must be a different country from origin.

---

## Transit Visa-Free Summary (Display this for eligible users)

### 144-Hour Transit Visa-Free

**You may NOT need a visa if ALL conditions are met:**

| Condition | Requirement |
|-----------|-------------|
| Nationality | From 54 eligible countries |
| Transit city | Must be designated city |
| Duration | ¡Ü 144 hours (6 days) |
| Final destination | Must be different country |
| No leaving the city zone | Must stay within permit area |

**Required for 144-hour:**
- [ ] Passport (6+ months)
- [ ] Onward ticket (confirmed)
- [ ] Hotel booking (if overnight)
- [ ] No exit restrictions from origin country

**Limitation:**
- Cannot leave the transit city zone
- Cannot extend or change
- No work or study allowed

---

## Step 4: Duration & Entry (Only if visa required)

**Q: How many days will you stay in China?**

- < 30 days ¡ú Single entry
- 30-60 days ¡ú Single or double entry
- 60-90 days ¡ú Double entry recommended
- > 90 days ¡ú Check visa type (may need Z, X1)

**Q: How many entries do you need?**

- Single (most common, cheapest)
- Double (if uncertain return date)
- Multiple (frequent travelers, costs more)

---

## Step 5: Dates & Ports

**Q: When do you plan to enter China?**

**Important:** Must be within 90 days of application date.

- YES ¡ú Date: ___
- NO ¡ú "Adjust entry date to be within 90 days"

**Q: Which port of entry?**

Common options:
- Beijing Capital (PEK/PKX)
- Shanghai Pudong (PVG)
- Guangzhou Baiyun (CAN)
- Los Angeles ¡ú Usually PVG/PEK

**Q: Will you exit from a different port?**

- YES ¡ú Note both entry and exit
- NO ¡ú Same port

---

## Step 6: Accommodation

**Q: Where will you stay?**

| Option | Follow-up |
|--------|-----------|
| **Hotel only** | Hotel name + address |
| **Friend/Family** | Host's name, address, phone |
| **Both** | Hotel for X days, then host for Y days |

---

## Step 7: Personal Info (SKIP if already collected)

Only ask for info not already provided:

1. **Former Chinese citizenship?**
   - YES ¡ú Additional form section required
   - NO ¡ú Skip

2. **Sex:** Male / Female

3. **Marital Status:** Unmarried / Married / Divorced / Widowed

4. **Current Status:** Student / Employed / Self-employed / Retired / Other

---

## Step 8: Passport

1. **Passport type is Ordinary?**
   - YES / NO

2. **Passport expiry date:** ___

   **Check:** Expires after [exit date + 6 months]?
   - YES ¡ú Good
   - NO ¡ú "Renew passport first"

3. **Passport has 2+ blank pages?**
   - YES / NO

---

## Step 9: Employment (Conditional)

**Skip if retired/student without income**

**Q: Monthly income range:**
- < $2,000 / $2,000-$5,000 / $5,000-$10,000 / > $10,000

**Q: Employer is US-based?**
- YES ¡ú Company name + address
- NO ¡ú Note employer details
- Self-employed ¡ú Business name + address

---

## Step 10: Health & History (Quick YES/NO)

1. **Any serious health conditions requiring treatment in China?**
   - YES ¡ú Note (usually OK)
   - NO

2. **Any drug-related convictions?**
   - YES ¡ú May affect application
   - NO

3. **Ever denied Chinese visa?**
   - YES ¡ú Need explanation letter
   - NO

4. **Ever overstayed or deported from any country?**
   - YES ¡ú Need explanation letter
   - NO

---

## Document Checklist (Generated Based on Visa Type)

### L Visa (Tourism)

**Required:**
- [ ] Passport (6+ months, 2 blank pages)
- [ ] Photo (354x472px, white bg, ¡Ý40KB)
- [ ] US residence proof (driver's license, utility bill)
- [ ] Onward ticket (for transit visa-free)

**NOT needed:** No invitation letter, no sponsor letter!

---

### M Visa (Business)

**Required:**
- [ ] Passport
- [ ] Photo
- [ ] US residence proof
- [ ] **Invitation letter from Chinese company** ¡û Required!

**Invitation letter must include:**
- Applicant's passport info
- Visit purpose
- Dates of visit
- Company's seal + signature

---

### Q1/Q2 Visa (Family)

**Required:**
- [ ] Passport
- [ ] Photo
- [ ] US residence proof
- [ ] **Invitation letter** (host writes it)
- [ ] **Host's Chinese ID copy**
- [ ] **Relationship proof** (marriage cert, birth cert, household registration)

---

### Transit Visa-Free

**Required:**
- [ ] Passport (6+ months)
- [ ] Onward ticket (different destination)
- [ ] Visa for final destination (if required)
- [ ] Hotel confirmation (if overnight)

**NOT needed:** No photo, no application form!

---

## Form Filling Guide

### Logic: Only show relevant sections

Based on earlier answers, skip:

| If... | Skip sections... |
|-------|------------------|
| L Visa | Invitation, Sponsor |
| Transit Visa-Free | Entire COVA form! |
| No invitation | M visa section |
| No Chinese family | Q1/Q2 sponsor |

---

### Workflow

1. Say: "Open COVA at cova.mfa.gov.cn"
2. Ask: "Are you on the application page?"
3. Fill ONE field, then: "Does this look correct?"
4. Confirm before next field

---

## Validation Rules

| Check | Rule | Action if Fail |
|-------|------|----------------|
| Passport | 6+ months beyond exit | Renew first |
| Entry date | Within 90 days | Adjust date |
| Duration vs Visa | Match visa type | Recommend correct visa |
| Transit eligible | Check 3 conditions | Suggest visa-free or visa |
| Blank pages | 2+ required | Note it |

---

## Smart Recommendations

### Trip Duration ¡ú Visa Type

| Stay | Best Option |
|------|-------------|
| ¡Ü 15 days transit | 144-hour transit visa-free (if eligible) |
| ¡Ü 30 days tourism | Single-entry L visa |
| ¡Ü 60 days business | Single-entry M visa |
| 30-60 days | Double-entry (safer) |
| Family visit | Q2 visa (easier than Q1) |
| Study < 6 months | X2 visa |

### Skip Unnecessary Steps

| User's situation | Skip asking about... |
|-------------------|---------------------|
| L visa | Invitation letter |
| No Chinese family | Family sponsor info |
| Transit visa-free | Entire form! |
| Already have photo | Photo requirements |
| US citizen | Other nationalities |

---

## Important Notes

- **Transit visa-free does NOT need COVA form**
- **L visa does NOT need invitation letter**
- **User reviews EVERY field**
- **Only user submits**
- **This does NOT guarantee approval**
