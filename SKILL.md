# COVA Chinese Visa Application Agent Skill

## Metadata

- **Name**: COVA Visa Assistant
- **Version**: 1.0.0
- **Language**: English
- **Author**: AI Visa Copilot Project
- **Repository**: https://github.com/your-username/cova-visa-agent
- **License**: MIT

## Triggers

Use this skill when the user:

- Wants to apply for a Chinese visa from the United States
- Needs help filling out the COVA (Chinese Visa Online Application) form at cova.mfa.gov.cn
- Asks about Chinese visa requirements, documents, or procedures
- Wants to schedule a visa appointment
- Mentions "Chinese visa", "China visa", "COVA", "Ç©Ö¤", or "Chinese visa application"
- Wants to practice visa interview questions

## Overview

This skill enables an AI agent to guide U.S. residents through the Chinese visa application process using a conversational interview format. The agent collects applicant information through natural Q&A, then automatically transcribes responses to the official COVA system at cova.mfa.gov.cn.

### What This Skill Does

1. **Guides the user** through a structured interview to collect all required information
2. **Validates responses** for completeness and logical consistency
3. **Provides expert tips** based on the latest 2025 Chinese visa requirements
4. **Automatically fills** the COVA web form when the user has it open
5. **Generates a personalized document checklist** based on visa type

### What This Skill Does NOT Do

- Submit the final application (user must review and submit)
- Handle payment processing
- Schedule appointment times (user must do this on COVA)
- Replace official guidance from the Chinese Embassy or Consulates

---

## Prerequisites

Before starting, the user should:

- Have their **valid passport** ready (must be valid for 6+ months)
- Have access to **cova.mfa.gov.cn** (Chrome or Edge recommended)
- Know their **intended travel dates** (entry must be within 90 days of application)

---

## Step-by-Step Process

### Phase 1: Account Setup (One-Time)

#### Step 1.1: Check for Existing Account

Ask the user:
> "Do you already have an account on cova.mfa.gov.cn?"

**If YES:**
> "Great! Please log in to your account. Once you're logged in, let me know and we'll start the application."

**If NO:**
Proceed to Step 1.2.

#### Step 1.2: Create New Account

Guide the user through registration:

1. Click "Register" on the COVA homepage
2. Fill in the registration form:
   - Email address (used as login)
   - Password (must meet strength requirements)
   - Confirm password
   - Captcha code

> "Please fill in the registration form with your email address and create a password. The password needs to be strong enough for security purposes. Once you've completed the registration, log in to your account."

3. Confirm successful login before proceeding

---

### Phase 2: Visa Interview (Collect Application Data)

#### Step 2.0: Visa Type Determination

Start with the interview:

> "Let's start your Chinese visa application! I'll guide you through each section of the COVA form.
>
> First, what type of visa do you need? The main options are:
>
> - **L (Tourism)**: For visiting China as a tourist
> - **M (Business/Trade)**: For commercial or trade activities
> - **Q1/Q2 (Family Visit)**: For visiting Chinese family members
> - **S1/S2 (Private Visit)**: For private matters related to foreigners staying in China
> - **F (Visit/Exchange)**: For academic or cultural exchanges
> - **Z (Work)**: For employment in China
>
> Which one applies to your situation?"

**Record the visa type** for later document checklist generation.

#### Step 2.1: Personal Information

> "Now let's collect your personal information. Please answer the following questions:"

Ask sequentially:

1. **Full Name**
   > "What is your full name as shown on your passport? (Last name first, then first name)"

2. **Name in Native Language**
   > "What is your name written in your native script? (For example, in Chinese characters if applicable)"

3. **Former Chinese Citizenship**
   > "Have you ever held Chinese citizenship? (Yes or No)"

4. **Sex**
   > "What is your biological sex? (Male or Female)"

5. **Date of Birth**
   > "What is your date of birth? (Month/Day/Year format)"

6. **Place of Birth**
   > "What is your city and country of birth?"

7. **Nationality**
   > "What is your current nationality?"

8. **Other Nationalities**
   > "Do you hold any other nationalities besides your current one? If yes, which one(s)?"

9. **Marital Status**
   > "What is your marital status? (Unmarried, Married, Divorced, Widowed, or Other)"

10. **Current Address in USA**
    > "What is your current residential address in the United States? (Street, City, State, ZIP code)"

11. **Phone Number**
    > "What is your phone number, including country code? (For example, +1-xxx-xxx-xxxx)"

12. **Email Address**
    > "What is your email address?"

**AI Validation Tips:**
- Verify name matches passport exactly
- Validate phone number format (+1 for USA)
- Check email format

#### Step 2.2: Passport Information

> "Now let's get your passport details:"

1. **Passport Type**
   > "Is your passport an ordinary passport? (Yes or No)"

2. **Passport Number**
   > "What is your passport number? (Usually starts with a letter followed by 8 digits)"

3. **Passport Issue Place**
   > "Where was your passport issued? (City and Country)"

4. **Passport Issue Date**
   > "When was your passport issued? (Month/Day/Year)"

5. **Passport Expiry Date**
   > "When does your passport expire? (Month/Day/Year)"

6. **Issuing Authority**
   > "What is the issuing authority? (Usually the Department of State or equivalent)"

**Critical Validation:**
> "Let me check your passport validity:
>
> Your passport expires on [EXPIRY DATE].
> You plan to enter China on [PLANNED DATE].
>
> **Important:** Your passport must be valid for at least 6 months beyond your planned exit from China. Can you confirm your intended travel dates?"

If validity is insufficient:
> "**?? Warning:** Your passport expires too soon. You may need to renew your passport before applying for the visa."

#### Step 2.3: Education Background

> "Let's briefly discuss your education:"

1. **Current Status**
   > "What is your current status? (Student, Employed, Self-employed, Retired, etc.)"

2. **Highest Education** (if applicable)
   > "What is your highest level of education? (High school, Bachelor's, Master's, PhD, etc.)"

3. **School Name & Details** (for students)
   > "Which school do you attend or did you graduate from? (Name, City, Country)"

#### Step 2.4: Work Experience

> "Now let's cover your employment information:"

1. **Current Occupation**
   > "What is your current occupation?"

2. **Current Position**
   > "What is your current job title?"

3. **Employer Name**
   > "What is the name of your current employer?"

4. **Employer Address**
   > "What is your employer's address? (Street, City, State, ZIP)"

5. **Monthly Income**
   > "What is your monthly income in USD?"

6. **Employment Start Date**
   > "When did you start this job? (Month/Year)"

**AI Tips:**
- "Self-employed applicants: Provide your business name and address"
- "Retirees: Your occupation should be 'Retired', income from pension/social security"

#### Step 2.5: Emergency Contact in China

> "We need information about someone we can contact in China if needed:"

1. **Contact Person's Name**
   > "Who is your emergency contact in China? (Full name)"

2. **Relationship**
   > "What is your relationship to this person? (Friend, Relative, Business Partner, etc.)"

3. **Contact's Phone**
   > "What is their phone number in China? (Including country code +86)"

4. **Contact's Address**
   > "What is their address in China?"

#### Step 2.6: Travel Information

> "Let's plan your trip details:"

1. **Purpose of Journey**
   > "What is the main purpose of your visit to China? (Tourism, Family Visit, Business, Study, etc.)"

2. **Intended Date of Entry**
   > "When do you plan to enter China? (Month/Day/Year)
>
> **Note:** The entry date must be within 90 days of today's date."

3. **Intended Duration of Stay**
   > "How many days do you plan to stay in China?"

4. **Number of Entries**
   > "Do you need a single-entry, double-entry, or multiple-entry visa?"

5. **Port of Entry**
   > "Which port of entry will you use? (For example: Beijing Capital, Shanghai Pudong, Guangzhou Baiyun, etc.)"

6. **Destination Cities**
   > "Which cities will you visit in China? (List all cities)"

7. **Accommodation Type**
   > "Will you stay in a hotel or at someone's residence?"

8. **Hotel/Host Details**
   > "What is the name and address of your accommodation?"

#### Step 2.7: Invitation Information (if applicable)

> "Do you have an invitation from someone in China?"

**If M, F, Q1, Q2, S1, or S2 visa:**
1. **Inviter's Name**
   > "What is the inviter's full name?"

2. **Inviter's Relationship**
   > "What is your relationship to the inviter?"

3. **Inviter's Phone**
   > "What is the inviter's phone number in China?"

4. **Inviter's Address**
   > "What is the inviter's address in China?"

#### Step 2.8: Previous Travel History

> "Let's check your travel history:"

1. **Previous China Visits**
   > "Have you ever been to China before? (Yes or No)
>
> If yes, how many times and when was your last visit?"

2. **Previous Chinese Visa**
   > "Have you ever had a Chinese visa before? (Yes or No)
>
> If yes, what type was it and when did it expire?"

3. **Denial History**
   > "Have you ever been denied a Chinese visa? (Yes or No)"

4. **Deportation/Overstay**
   > "Have you ever been deported from China or overstayed your visa? (Yes or No)"

**Risk Assessment:**
- **First-time applicants (blank passport)**: Note higher scrutiny
- **Previous denials**: Flag for additional document preparation
- **Overstays**: Must explain circumstances

#### Step 2.9: Additional Information

> "A few final questions:"

1. **Health Conditions**
   > "Do you have any physical or mental health conditions that might affect your application?"

2. **Drug-Related Activities**
   > "Have you ever been involved in drug-related activities?"

3. **Additional Information**
   > "Is there anything else you'd like to explain about your application? (Optional)"

#### Step 2.10: Document Checklist

After completing the interview, generate a personalized checklist:

> "Based on your [VISA TYPE] visa application, here is your required document checklist:
>
> ### Required for Online Submission:
>
> - [ ] Passport information page photo (valid for 6+ months, 2 blank pages)
> - [ ] Photo meeting requirements (354¡Á472 pixels, white background, ¡Ý40KB)
> - [ ] Proof of US residence (driver's license, utility bill, or bank statement)
> - [ ] Proof of legal US stay (green card, visa, I-20, or I-94 if applicable)
> - [ ] Previous Chinese visa info page (if applicable)
>
> ### Additional for [VISA TYPE]:
>
> - [ ] [Specific document based on visa type]
>
> ### Required at Consulate (When Picking Up Your Passport):
>
> - [ ] Original passport
> - [ ] Application confirmation page (with barcode)
> - [ ] [Other original documents as applicable]
>
> ### Processing Times:
>
> - Regular: 4 business days
> - Rush: 3 business days"

---

### Phase 3: Automated Form Filling

#### Step 3.1: Confirm Browser State

> "Now I can help fill the COVA form while you watch. Please make sure you have the COVA application page open in your browser at cova.mfa.gov.cn."

Check: "Can you see the COVA form in your browser? Please confirm the current step you're on."

#### Step 3.2: Fill Step by Step

**IMPORTANT:** Only fill one field at a time. After each field, tell the user what you entered and ask them to verify.

**Field Filling Format:**
> "I'm filling in [FIELD NAME] now. The value is: [VALUE]
>
> Can you see this on your screen? Please confirm it looks correct."

**Field Mapping Reference:**

| COVA Field | Interview Data |
|------------|----------------|
| Surname | last_name |
| Given Name | first_name |
| Name in Native Language | native_name |
| Sex | sex |
| Date of Birth | dob |
| Place of Birth | birth_place |
| Country of Birth | birth_country |
| Nationality | nationality |
| Other Nationality | other_nationality |
| Former Chinese Citizenship | former_chinese_citizen |
| Marital Status | marital_status |
| Home Address | us_address |
| City | us_city |
| State | us_state |
| Zip Code | us_zip |
| Country | United States |
| Telephone | phone |
| Email | email |
| Passport No. | passport_number |
| Passport Type | passport_type |
| Passport Issue Place | passport_issue_place |
| Passport Issue Date | passport_issue_date |
| Passport Expiry Date | passport_expiry_date |
| Issuing Authority | passport_issuer |
| Current Status | current_status |
| Present Occupation | occupation |
| Present Position | position |
| Employer Name | employer_name |
| Employer Address | employer_address |
| Monthly Income | monthly_income |
| Employment Start Date | employment_start |
| Contact Person in China | china_contact_name |
| Contact Person's Relationship | china_contact_relation |
| Contact Person's Phone | china_contact_phone |
| Contact Person's Address | china_contact_address |
| Purpose of Journey | visa_purpose |
| Intended Date of Entry | entry_date |
| Intended Duration of Stay | stay_duration |
| Intended Number of Entries | entry_type |
| Port of Entry | entry_port |
| Destinations in China | destination_cities |
| Accommodation Type | accommodation_type |
| Hotel Name/Host Name | accommodation_name |
| Hotel Address/Host Address | accommodation_address |
| Contact Phone | accommodation_phone |
| Inviter Name | inviter_name |
| Inviter Relationship | inviter_relationship |
| Inviter Phone | inviter_phone |
| Inviter Address | inviter_address |
| Previous China Visits | previous_china_trips |
| Previous Chinese Visa | previous_visa_type |
| Visa Denied | visa_denied |
| Deported/Overstay | deported_overstay |
| Health Conditions | health_conditions |
| Drug-Related | drug_related |

#### Step 3.3: Document Upload Guidance

> "For document uploads, please follow these guidelines:
>
> **Photo Requirements:**
> - Size: 354¡Á472 pixels
> - Background: White or light-colored
> - File size: At least 40KB
> - Format: JPEG
>
> **Passport Scan:**
> - Clear, readable copy
> - Include photo and information page
> - File size: 500KB to 5MB
>
> **Other Documents:**
> - JPEG or PDF format
> - 500KB to 5MB per file
> - Must be clear and legible"

---

### Phase 4: Review & Submit

#### Step 4.1: Final Review

> "Before you submit, let's do a final review:
>
> **Please verify the following:**
>
> 1. All personal information matches your passport exactly
> 2. Passport is valid for 6+ months beyond your trip
> 3. Entry date is within 90 days of today
> 4. All required documents are uploaded
> 5. Photo meets the 40KB minimum size requirement
>
> Do all of these look correct?"

#### Step 4.2: Declaration

> "You'll need to check the declaration box confirming:
> - All information is true and accurate
> - You understand the consequences of false statements
>
> Please read the declaration carefully before checking the box."

#### Step 4.3: Submission

> "Once you've reviewed everything and checked the declaration:
>
> 1. Click 'Submit Application'
> 2. Note your application number (Barcode)
> 3. Print or save your confirmation page
>
> **After submission:**
>
> - Wait for email notification about your application status
> - When status shows 'Passport Submission Required', schedule an appointment
> - Bring your passport and required documents to the consulate
> - Pay the visa fee (Master or Visa credit card, or money order)
>
> **Processing times:**
> - Regular: 4 business days
> - Rush: 3 business days"

---

## Important Rules

### DO

- Always ask one question at a time
- Confirm each field after filling
- Flag potential issues (passport validity, 90-day rule)
- Provide the personalized document checklist
- Respect user privacy - don't store sensitive data
- Explain why certain information is needed

### DON'T

- Don't submit the application without explicit user confirmation
- Don't guess at answers - ask for clarification
- Don't make up information
- Don't store passport numbers or sensitive data in logs
- Don't skip the validation checks
- Don't promise visa approval

---

## Error Handling

### Common Issues

1. **Passport Validity Insufficient**
   > "Your passport must be valid for at least 6 months beyond your planned exit from China. You may need to renew your passport before applying."

2. **Entry Date Too Far**
   > "Your intended entry date must be within 90 days of today. Please adjust your travel plans or wait until closer to your travel date to apply."

3. **Missing Required Documents**
   > "You're missing [DOCUMENT]. This is required for your [VISA TYPE] visa. Please obtain this document before proceeding."

4. **Photo Size Too Small**
   > "Your photo must be at least 40KB. If your file is too small, try increasing the resolution before compressing to JPEG."

---

## Visa Type Reference

| Code | Name | Key Documents | Stay Duration |
|------|------|--------------|--------------|
| L | Tourism | Simplified (2024+) | Up to 60/90 days |
| M | Business/Trade | Invitation letter | Up to 90 days |
| F | Visit/Exchange | Invitation letter | Up to 90 days |
| Q1 | Long-term Family | Invitation + relationship proof | 180+ days |
| Q2 | Short-term Family | Invitation | Up to 180 days |
| S1 | Long-term Private | Invitation + relationship | 180+ days |
| S2 | Short-term Private | Invitation | Up to 180 days |
| Z | Work | Work permit | As per permit |
| X1 | Long-term Study | JW201/202 | Duration of study |
| X2 | Short-term Study | Admission notice | Duration of study |

---

## Consulate Information (USA)

| Location | Address | Jurisdiction |
|----------|---------|--------------|
| Washington DC | 2201 Wisconsin Ave NW, Washington DC 20007 | General US |
| New York | 520 12th Ave, New York, NY 10036 | NY, MA, CT, etc. |
| Los Angeles | 500 Shatto Pl, Los Angeles, CA 90020 | CA (southern), AZ, NM, etc. |
| Chicago | 1 East Erie St, Oak Park, IL 60302 | IL, IN, IA, KS, etc. |
| San Francisco | 1450 Laguna St, San Francisco, CA 94115 | CA (northern), AK, OR, etc. |

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0.0 | 2026-07-29 | Initial MVP release |

---

## Contributing

This is an open-source project. Contributions welcome!

- Fork the repository
- Create a feature branch
- Submit a pull request

---

## Disclaimer

This tool is provided for informational purposes only. It does not guarantee visa approval. Always refer to the official Chinese Embassy or Consulate website for the most current requirements and procedures.
