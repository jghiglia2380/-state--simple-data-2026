# PFL Academy — COMPLETE State Corrections Master Document

**Date:** February 17, 2026
**For:** Denis / Antigravity Team + Sebastian
**From:** Justin

---

## PART 1: Master L-Chapter Reference (Canonical Titles)

Every L-chapter has ONE correct title. When a chapter appears in a state's CHAPTERS listing, it MUST use the title that matches its L-chapter number. No exceptions.

### Core Chapters (L-1 to L-45)

| L-Chapter | Canonical Title |
|-----------|----------------|
| L-1 | Jobs vs. Careers |
| L-2 | Paying for Post-Secondary Education |
| L-3 | Income and Taxes |
| L-4 | Financial Goal Setting |
| L-5 | Managing Your Income Effectively |
| L-6 | Understanding Federal and State Taxes |
| L-7 | Understanding Tax Brackets and Tax Rates |
| L-8 | Understanding Tax Filing Requirements |
| L-9 | Understanding Tax Deductions and Credits |
| L-10 | Tax Planning and Compliance |
| L-11 | Understanding Financial Service Providers |
| L-12 | Choosing and Evaluating Financial Service Providers |
| L-13 | Understanding and Using Banking Tools |
| L-14 | Getting Started Saving and Investing |
| L-15 | Understanding the Power of Compound Interest and the Rule of 72 |
| L-16 | Evaluating Saving and Investment Strategies |
| L-17 | Time is Money — Developing a Savings and Investment Strategy |
| L-18 | Understanding Monetary Risks in Saving and Investing |
| L-19 | Planning for Retirement |
| L-20 | Longevity and Retirement Planning |
| L-21 | Understanding the Cost of Borrowing |
| L-22 | Choosing the Right Source of Credit |
| L-23 | Understanding Your Credit Score and Its Impact |
| L-24 | Consumer Credit Legislation |
| L-25 | Understanding Student Loans |
| L-26 | Credit Card Use and Management |
| L-27 | Online Shopping — Convenience at a Cost |
| L-28 | Protecting Yourself from Consumer Fraud |
| L-29 | Identity Theft Prevention and Recovery |
| L-30 | Renting vs. Owning — Making Informed Housing Decisions |
| L-31 | Understanding the Costs and Responsibilities of Renting |
| L-32 | Understanding Home Buying |
| L-33 | Understanding and Managing Risk |
| L-34 | Insurance as a Risk Management Tool |
| L-35 | Managing Insurance Costs |
| L-36 | Understanding the Risks of Gambling |
| L-37 | The Costs and Benefits of Gambling |
| L-38 | Strategies for Managing High Levels of Debt |
| L-39 | Charitable Giving and Financial Planning |
| L-40 | Checking Out Charitable Groups |
| L-41 | Career Exploration and Goal Setting |
| L-42 | Resume Building and Personal Branding |
| L-43 | Job Application Process |
| L-44 | Interview Skills and Workplace Readiness |
| L-45 | Entrepreneurship and Side Hustles |

### Extended Chapters (L-46+)

| L-Chapter | Canonical Title |
|-----------|----------------|
| L-46 | Automobile Finance — Buying vs. Leasing |
| L-47 | Introduction to Investment Types |
| L-48 | Risk and Return in Investing |
| L-49 | Investment Portfolio Diversification |
| L-50 | Financial Markets and Institutions |
| L-51 | Investment Technology and Tools |
| L-52 | Government and the Economy |
| L-53 | Fiscal and Monetary Policy |
| L-54 | Inflation, Unemployment, and Personal Finance |
| L-55 | International Trade and Economic Development |

### Combined Chapters

| ID | Merges | Title | Content File |
|----|--------|-------|-------------|
| LC-36 | L-36 + L-37 | Understanding the Risks of Gambling | `LC-36-combined-gambling-slides.html` |
| LC-39 | L-39 + L-40 | Charitable Giving and Financial Planning | `LC-39-combined-philanthropy-slides.html` |

**In mapping files, combined chapters appear as:** `L-36+L-37→X.X` and `L-39+L-40→X.X`

**30 states use combined** (see Part 2). **5 states use separate** (CA, IL, IN, NC, RI). Georgia is hybrid (L-36/L-37 separate, L-39+L-40 combined).

---

## PART 2: SYSTEMIC Issue — Career Chapter Title Cascade (ALL 36 States)

### The Problem

During the AI-generated corrections, the career chapter titles (L-41 through L-46) were systematically shifted. **This affects ALL 36 states.** The pattern:

| L-Chapter | Correct Title | Wrong Title Applied |
|-----------|--------------|-------------------|
| L-41 | Career Exploration and Goal Setting | "Career Planning & Development" (close but wrong) |
| L-42 | Resume Building and Personal Branding | "Job Search Strategies" or "Job Application Process" |
| L-43 | Job Application Process | "Workplace Skills" or "Interview Skills" |
| L-44 | Interview Skills and Workplace Readiness | **"Professional Development" (HALLUCINATED)** |
| L-45 | Entrepreneurship and Side Hustles | "Professional Development" or "Resume Building" |
| L-46 | Automobile Finance — Buying vs. Leasing | "Entrepreneurship and Side Hustles" |

### The Fix

**"Professional Development" does not exist as a PFL Academy chapter. It must be removed from every state file.**

For EVERY state, scan all `_CHAPTERS:` lines and replace career chapter titles to match the L-chapter they're mapped to:

1. Find each position's L-chapter number from the `L_CHAPTER_MAPPINGS` line
2. Replace the title in the CHAPTERS line with the canonical title from Part 1

**Critical:** The L_CHAPTER_MAPPINGS numbers (L-42→2.5, etc.) are generally CORRECT. The chapter TITLES in the CHAPTERS lines are what's wrong. Don't change the mapping numbers — change the display titles to match.

### States Where This ALSO Creates Duplicates

In these 3 states, L-45 was mapped to TWO positions (one correct, one labeled "Professional Development"):

| State | Remove This Mapping | Keep This Mapping | Also Fix |
|-------|-------------------|------------------|----------|
| **Delaware** | `L-44→3.9` | `L-44→1.7` | Change 3.9 to `L-31→3.9` titled "Understanding the Costs and Responsibilities of Renting" |
| **Kentucky** | `L-45→1.10` (remove position entirely) | `L-45→6.8` | Reduce Strand 1 from 10 to 9 chapters |
| **Pennsylvania** | `L-45→5.5` (remove position entirely) | `L-45→2.8` | Reduce Area 5 from 6 to 5 chapters |

**Delaware special case:** Delaware is missing L-31 (Renting). Position 3.9 (currently duplicate L-44 with fake "Professional Development" title) should become L-31. This puts L-31 next to L-32 (Home Buying at 3.10), which is logical. Remove the `OMITTED_CHAPTERS` line about L-31.

---

## PART 3: Texas-PFL Complete Rebuild

### Overview
- **Course:** Standalone Personal Financial Literacy (§113.49, HB 27)
- **For:** Class of 2030+ (9th graders entering 2025-26)
- **Standards:** 8 Standards
- **Total Chapters:** 45 (all core content covered)
- **Uses Combined Chapters:** Yes — LC-36 (L-36+L-37) and LC-39 (L-39+L-40)
- **Extended Chapters:** L-46 (Auto Finance), L-47 (Investment Types)

### Complete Chapter Listings

```
STANDARD_1_CHAPTERS: 1.1 Jobs vs. Careers|1.2 Paying for Post-Secondary Education|1.3 Income and Taxes|1.4 Career Exploration and Goal Setting|1.5 Resume Building and Personal Branding|1.6 Job Application Process|1.7 Interview Skills and Workplace Readiness|1.8 Entrepreneurship and Side Hustles

STANDARD_2_CHAPTERS: 2.1 Understanding Federal and State Taxes|2.2 Understanding Tax Brackets and Tax Rates|2.3 Understanding Tax Filing Requirements|2.4 Understanding Tax Deductions and Credits|2.5 Tax Planning and Compliance

STANDARD_3_CHAPTERS: 3.1 Financial Goal Setting|3.2 Managing Your Income Effectively|3.3 Understanding and Using Banking Tools|3.4 Understanding Financial Service Providers|3.5 Choosing and Evaluating Financial Service Providers

STANDARD_4_CHAPTERS: 4.1 Understanding the Cost of Borrowing|4.2 Choosing the Right Source of Credit|4.3 Understanding Your Credit Score and Its Impact|4.4 Consumer Credit Legislation|4.5 Understanding Student Loans|4.6 Credit Card Use and Management|4.7 Strategies for Managing High Levels of Debt

STANDARD_5_CHAPTERS: 5.1 Getting Started Saving and Investing|5.2 Understanding the Power of Compound Interest and the Rule of 72|5.3 Evaluating Saving and Investment Strategies|5.4 Time is Money — Developing a Savings and Investment Strategy|5.5 Understanding Monetary Risks in Saving and Investing|5.6 Introduction to Investment Types

STANDARD_6_CHAPTERS: 6.1 Planning for Retirement|6.2 Longevity and Retirement Planning|6.3 Understanding and Managing Risk|6.4 Insurance as a Risk Management Tool|6.5 Managing Insurance Costs

STANDARD_7_CHAPTERS: 7.1 Renting vs. Owning — Making Informed Housing Decisions|7.2 Understanding the Costs and Responsibilities of Renting|7.3 Understanding Home Buying|7.4 Automobile Finance — Buying vs. Leasing|7.5 Online Shopping — Convenience at a Cost|7.6 Protecting Yourself from Consumer Fraud|7.7 Identity Theft Prevention and Recovery

STANDARD_8_CHAPTERS: 8.1 Understanding the Risks of Gambling (combines L-36 and L-37)|8.2 Charitable Giving and Financial Planning (combines L-39 and L-40)
```

### Complete L_CHAPTER_MAPPINGS Line

```
L_CHAPTER_MAPPINGS: L-1→1.1|L-2→1.2|L-3→1.3|L-41→1.4|L-42→1.5|L-43→1.6|L-44→1.7|L-45→1.8|L-6→2.1|L-7→2.2|L-8→2.3|L-9→2.4|L-10→2.5|L-4→3.1|L-5→3.2|L-13→3.3|L-11→3.4|L-12→3.5|L-21→4.1|L-22→4.2|L-23→4.3|L-24→4.4|L-25→4.5|L-26→4.6|L-38→4.7|L-14→5.1|L-15→5.2|L-16→5.3|L-17→5.4|L-18→5.5|L-47→5.6|L-19→6.1|L-20→6.2|L-33→6.3|L-34→6.4|L-35→6.5|L-30→7.1|L-31→7.2|L-32→7.3|L-46→7.4|L-27→7.5|L-28→7.6|L-29→7.7|L-36+L-37→8.1|L-39+L-40→8.2
```

### Verification
- **Total mapping entries:** 45 (43 individual + 2 combined)
- **Core chapters covered:** ALL L-1 through L-45 ✓
- **Extended chapters:** L-46, L-47 ✓
- **Combined chapters:** LC-36 (8.1), LC-39 (8.2) ✓
- **Duplicates:** NONE ✓
- **Missing chapters:** NONE ✓

### OMITTED_CHAPTERS Line
```
OMITTED_CHAPTERS: L-48 through L-55 (Economics-focused chapters — covered in Texas-PFLE combined course instead)
```

---

## PART 4: Texas-PFLE Complete Rebuild

### Overview
- **Course:** Personal Financial Literacy and Economics (§113.76, SB 1063)
- **For:** 2022-2025 implementation, still active for current students
- **Knowledge and Skills Statements:** 10 (per TEKS §113.76)
- **TEKS Requirement:** Two-thirds instructional time in PFL, one-third in economics
- **Total Chapters:** 45
- **Uses Combined Chapters:** Yes — LC-36 and LC-39
- **Extended Chapters:** L-46, L-47, L-48, L-49, L-50, L-51, L-52, L-53, L-54, L-55

### TEKS §113.76 Knowledge and Skills → L-Chapter Mapping

| K&S | TEKS Topic | L-Chapters |
|-----|-----------|------------|
| 1 | Economics fundamentals (scarcity, supply/demand, circular flow) | L-48, L-49, L-50, L-51, L-52 |
| 2 | Macroeconomics and taxation (taxes, fiscal/monetary policy) | L-6, L-7, L-53, L-54, L-55 |
| 3 | Education and career (postsecondary, FAFSA, loans, career) | L-1, L-2, L-3, L-41, L-42, L-44 |
| 4 | Earning income (sources, benefits, gross/net/taxable) | L-8, L-25 |
| 5 | Entrepreneurship | L-45 |
| 6 | Spending (goals, budgeting, exchange, housing, vehicle) | L-4, L-5, L-13, L-26, L-30, L-46 |
| 7 | Credit and debt (borrowing, credit types/reports, predatory) | L-21, L-22, L-23, L-24, L-38 |
| 8 | Saving and investing (compound interest, investments, retirement) | L-14, L-15, L-16, L-17, L-18, L-19, L-47 |
| 9 | Protecting and insuring (risk, insurance, fraud, identity theft) | L-28, L-29, L-32, L-33, L-34, L-35, LC-36, LC-39 |
| 10 | Financial literacy skills (problem-solving, budgeting) | Integrated across all |

### Complete Chapter Listings

```
K_AND_S_1_CHAPTERS: 1.1 Risk and Return in Investing|1.2 Investment Portfolio Diversification|1.3 Financial Markets and Institutions|1.4 Investment Technology and Tools|1.5 Government and the Economy

K_AND_S_2_CHAPTERS: 2.1 Understanding Federal and State Taxes|2.2 Understanding Tax Brackets and Tax Rates|2.3 Fiscal and Monetary Policy|2.4 Inflation, Unemployment, and Personal Finance|2.5 International Trade and Economic Development

K_AND_S_3_CHAPTERS: 3.1 Jobs vs. Careers|3.2 Paying for Post-Secondary Education|3.3 Income and Taxes|3.4 Career Exploration and Goal Setting|3.5 Resume Building and Personal Branding|3.6 Interview Skills and Workplace Readiness|3.7 Entrepreneurship and Side Hustles

K_AND_S_4_CHAPTERS: 4.1 Understanding Tax Filing Requirements|4.2 Understanding Student Loans

K_AND_S_5_CHAPTERS: 5.1 Financial Goal Setting|5.2 Managing Your Income Effectively|5.3 Understanding and Using Banking Tools|5.4 Credit Card Use and Management|5.5 Renting vs. Owning — Making Informed Housing Decisions|5.6 Automobile Finance — Buying vs. Leasing

K_AND_S_6_CHAPTERS: 6.1 Understanding the Cost of Borrowing|6.2 Choosing the Right Source of Credit|6.3 Understanding Your Credit Score and Its Impact|6.4 Consumer Credit Legislation|6.5 Strategies for Managing High Levels of Debt

K_AND_S_7_CHAPTERS: 7.1 Getting Started Saving and Investing|7.2 Understanding the Power of Compound Interest and the Rule of 72|7.3 Evaluating Saving and Investment Strategies|7.4 Time is Money — Developing a Savings and Investment Strategy|7.5 Understanding Monetary Risks in Saving and Investing|7.6 Planning for Retirement|7.7 Introduction to Investment Types

K_AND_S_8_CHAPTERS: 8.1 Understanding and Managing Risk|8.2 Insurance as a Risk Management Tool|8.3 Managing Insurance Costs|8.4 Protecting Yourself from Consumer Fraud|8.5 Identity Theft Prevention and Recovery|8.6 Understanding Home Buying|8.7 Understanding the Risks of Gambling (combines L-36 and L-37)|8.8 Charitable Giving and Financial Planning (combines L-39 and L-40)
```

### Complete L_CHAPTER_MAPPINGS Line

```
L_CHAPTER_MAPPINGS: L-48→1.1|L-49→1.2|L-50→1.3|L-51→1.4|L-52→1.5|L-6→2.1|L-7→2.2|L-53→2.3|L-54→2.4|L-55→2.5|L-1→3.1|L-2→3.2|L-3→3.3|L-41→3.4|L-42→3.5|L-44→3.6|L-45→3.7|L-8→4.1|L-25→4.2|L-4→5.1|L-5→5.2|L-13→5.3|L-26→5.4|L-30→5.5|L-46→5.6|L-21→6.1|L-22→6.2|L-23→6.3|L-24→6.4|L-38→6.5|L-14→7.1|L-15→7.2|L-16→7.3|L-17→7.4|L-18→7.5|L-19→7.6|L-47→7.7|L-33→8.1|L-34→8.2|L-35→8.3|L-28→8.4|L-29→8.5|L-32→8.6|L-36+L-37→8.7|L-39+L-40→8.8
```

### Verification
- **Total mapping entries:** 45 (43 individual + 2 combined) ✓
- **Core chapters covered:** 37 individual + 4 via combined = 41 core topics ✓
- **Extended chapters:** L-46, L-47, L-48, L-49, L-50, L-51, L-52, L-53, L-54, L-55 ✓
- **Combined chapters:** LC-36 (8.7), LC-39 (8.8) ✓
- **Duplicates:** NONE ✓

### Omitted Chapters (8) — With TEKS §113.76 Rationale

| Omitted | Title | Rationale |
|---------|-------|-----------|
| L-9 | Tax Deductions and Credits | Advanced detail; tax fundamentals covered by L-6, L-7, L-8 |
| L-10 | Tax Planning and Compliance | Fiscal policy covered by L-53; not explicit in TEKS |
| L-11 | Understanding Financial Service Providers | Banking covered by L-13 (Banking Tools) |
| L-12 | Choosing and Evaluating Financial Service Providers | Overlaps with L-13; not explicit in TEKS |
| L-20 | Longevity and Retirement Planning | Retirement fundamentals covered by L-19 |
| L-27 | Online Shopping — Convenience at a Cost | Consumer protection covered by L-28; not required by TEKS |
| L-31 | Understanding Costs and Responsibilities of Renting | Housing decisions covered by L-30 per K&S 6(G) |
| L-43 | Job Application Process | Career coverage strong with L-41, L-42, L-44, L-45 |

```
OMITTED_CHAPTERS: L-9, L-10, L-11, L-12, L-20, L-27, L-31, L-43 (8 core chapters omitted to accommodate 10 economics/extended chapters per TEKS §113.76 scope)
```


---

## PART 5: Rhode Island Complete Build

### Overview
- **Standards:** Council for Economic Education National Standards (RIGL 16-22-13)
- **Standards Count:** 6
- **Total Chapters:** 45
- **Uses Combined Chapters:** NO — Rhode Island uses SEPARATE chapters (L-36, L-37, L-39, L-40 all individual)
- **Extended Chapters:** NONE (no freed slots from combinations)
- **This is a straight L-1 through L-45 build**

### Complete Chapter Listings

```
STANDARD_1_CHAPTERS: 1.1 Jobs vs. Careers|1.2 Paying for Post-Secondary Education|1.3 Income and Taxes|1.4 Career Exploration and Goal Setting|1.5 Resume Building and Personal Branding|1.6 Job Application Process|1.7 Interview Skills and Workplace Readiness|1.8 Entrepreneurship and Side Hustles

STANDARD_2_CHAPTERS: 2.1 Financial Goal Setting|2.2 Managing Your Income Effectively|2.3 Understanding Financial Service Providers|2.4 Choosing and Evaluating Financial Service Providers|2.5 Understanding and Using Banking Tools|2.6 Online Shopping — Convenience at a Cost|2.7 Protecting Yourself from Consumer Fraud|2.8 Identity Theft Prevention and Recovery

STANDARD_3_CHAPTERS: 3.1 Understanding Federal and State Taxes|3.2 Understanding Tax Brackets and Tax Rates|3.3 Understanding Tax Filing Requirements|3.4 Understanding Tax Deductions and Credits|3.5 Tax Planning and Compliance|3.6 Getting Started Saving and Investing|3.7 Understanding the Power of Compound Interest and the Rule of 72

STANDARD_4_CHAPTERS: 4.1 Evaluating Saving and Investment Strategies|4.2 Time is Money — Developing a Savings and Investment Strategy|4.3 Understanding Monetary Risks in Saving and Investing|4.4 Planning for Retirement|4.5 Longevity and Retirement Planning

STANDARD_5_CHAPTERS: 5.1 Understanding the Cost of Borrowing|5.2 Choosing the Right Source of Credit|5.3 Understanding Your Credit Score and Its Impact|5.4 Consumer Credit Legislation|5.5 Understanding Student Loans|5.6 Credit Card Use and Management|5.7 Strategies for Managing High Levels of Debt|5.8 Renting vs. Owning — Making Informed Housing Decisions|5.9 Understanding the Costs and Responsibilities of Renting|5.10 Understanding Home Buying

STANDARD_6_CHAPTERS: 6.1 Understanding and Managing Risk|6.2 Insurance as a Risk Management Tool|6.3 Managing Insurance Costs|6.4 Understanding the Risks of Gambling|6.5 The Costs and Benefits of Gambling|6.6 Charitable Giving and Financial Planning|6.7 Checking Out Charitable Groups
```

### Complete L_CHAPTER_MAPPINGS Line

```
L_CHAPTER_MAPPINGS: L-1→1.1|L-2→1.2|L-3→1.3|L-41→1.4|L-42→1.5|L-43→1.6|L-44→1.7|L-45→1.8|L-4→2.1|L-5→2.2|L-11→2.3|L-12→2.4|L-13→2.5|L-27→2.6|L-28→2.7|L-29→2.8|L-6→3.1|L-7→3.2|L-8→3.3|L-9→3.4|L-10→3.5|L-14→3.6|L-15→3.7|L-16→4.1|L-17→4.2|L-18→4.3|L-19→4.4|L-20→4.5|L-21→5.1|L-22→5.2|L-23→5.3|L-24→5.4|L-25→5.5|L-26→5.6|L-38→5.7|L-30→5.8|L-31→5.9|L-32→5.10|L-33→6.1|L-34→6.2|L-35→6.3|L-36→6.4|L-37→6.5|L-39→6.6|L-40→6.7
```

### Verification
- **Total mapping entries:** 45 (all individual, no combined) ✓
- **Core chapters covered:** ALL L-1 through L-45 ✓
- **Extended chapters:** NONE ✓
- **Combined chapters:** NONE (Rhode Island uses separate) ✓
- **Duplicates:** NONE ✓
- **Missing chapters:** NONE ✓

```
OMITTED_CHAPTERS: L-46 through L-55 (extended chapters not included; Rhode Island uses separate L-36/L-37/L-39/L-40 so no freed slots for extended content)
```

## PART 6: Mississippi Complete Rebuild

Mississippi's file has 35 out of 49 title-to-L-chapter mismatches plus 4 duplicate mappings. It needs a full rebuild.

### Overview
- **Standards:** Mississippi Financial Literacy Standards
- **Total Chapters:** 45 (all core content covered)
- **Uses Combined Chapters:** Yes — LC-36 and LC-39
- **Extended Chapters:** L-46, L-47

### Complete Chapter Listings

```
UNIT_1_CHAPTERS: 1.1 Financial Goal Setting

UNIT_2_CHAPTERS: 2.1 Jobs vs. Careers|2.2 Paying for Post-Secondary Education|2.3 Income and Taxes|2.4 Career Exploration and Goal Setting|2.5 Resume Building and Personal Branding|2.6 Job Application Process|2.7 Interview Skills and Workplace Readiness|2.8 Entrepreneurship and Side Hustles

UNIT_3_CHAPTERS: 3.1 Understanding Financial Service Providers|3.2 Choosing and Evaluating Financial Service Providers|3.3 Understanding and Using Banking Tools

STANDARD_4_CHAPTERS: 4.1 Managing Your Income Effectively|4.2 Understanding Federal and State Taxes|4.3 Understanding Tax Brackets and Tax Rates|4.4 Understanding Tax Filing Requirements|4.5 Understanding Tax Deductions and Credits|4.6 Tax Planning and Compliance

STANDARD_5_CHAPTERS: 5.1 Understanding the Cost of Borrowing|5.2 Choosing the Right Source of Credit|5.3 Understanding Your Credit Score and Its Impact|5.4 Consumer Credit Legislation|5.5 Understanding Student Loans|5.6 Credit Card Use and Management|5.7 Online Shopping — Convenience at a Cost|5.8 Strategies for Managing High Levels of Debt

STANDARD_6_CHAPTERS: 6.1 Getting Started Saving and Investing|6.2 Understanding the Power of Compound Interest and the Rule of 72|6.3 Evaluating Saving and Investment Strategies|6.4 Time is Money — Developing a Savings and Investment Strategy|6.5 Understanding Monetary Risks in Saving and Investing|6.6 Introduction to Investment Types

STANDARD_7_CHAPTERS: 7.1 Planning for Retirement|7.2 Longevity and Retirement Planning|7.3 Renting vs. Owning — Making Informed Housing Decisions|7.4 Understanding the Costs and Responsibilities of Renting|7.5 Understanding Home Buying|7.6 Automobile Finance — Buying vs. Leasing

STANDARD_8_CHAPTERS: 8.1 Understanding and Managing Risk|8.2 Insurance as a Risk Management Tool|8.3 Managing Insurance Costs|8.4 Protecting Yourself from Consumer Fraud|8.5 Identity Theft Prevention and Recovery|8.6 Understanding the Risks of Gambling (combines L-36 and L-37)|8.7 Charitable Giving and Financial Planning (combines L-39 and L-40)
```

### Complete L_CHAPTER_MAPPINGS Line

```
L_CHAPTER_MAPPINGS: L-4→1.1|L-1→2.1|L-2→2.2|L-3→2.3|L-41→2.4|L-42→2.5|L-43→2.6|L-44→2.7|L-45→2.8|L-11→3.1|L-12→3.2|L-13→3.3|L-5→4.1|L-6→4.2|L-7→4.3|L-8→4.4|L-9→4.5|L-10→4.6|L-21→5.1|L-22→5.2|L-23→5.3|L-24→5.4|L-25→5.5|L-26→5.6|L-27→5.7|L-38→5.8|L-14→6.1|L-15→6.2|L-16→6.3|L-17→6.4|L-18→6.5|L-47→6.6|L-19→7.1|L-20→7.2|L-30→7.3|L-31→7.4|L-32→7.5|L-46→7.6|L-33→8.1|L-34→8.2|L-35→8.3|L-28→8.4|L-29→8.5|L-36+L-37→8.6|L-39+L-40→8.7
```

### Verification
- **Total mapping entries:** 45 (43 individual + 2 combined)
- **Core chapters covered:** ALL L-1 through L-45 ✓
- **Extended chapters:** L-46, L-47 ✓
- **Combined chapters:** LC-36 (8.6), LC-39 (8.7) ✓
- **Duplicates:** NONE ✓ (was 4 duplicates)
- **Missing chapters:** NONE ✓

### What Changed from Original
- Removed ALL 4 duplicates (L-27, L-31, L-32, L-46)
- Fixed ALL 35 title mismatches
- Reorganized standards to group related content logically
- Reduced from 49 to 45 mapping entries (removed spurious positions)
- Updated all STANDARD_X_CHAPTERS lines, including Standard 7 Sub A/B consolidation

---

## PART 7: Remaining Duplicate Fixes (8 States)

For each state below, the fix is the corrected `L_CHAPTER_MAPPINGS` entry. The old (wrong) entry should be found and replaced.

### Florida
**Problem:** L-46 at positions 1.3 AND 13.3
**Root cause:** L-46 (Auto Finance) was put in L-45's slot

| Fix | Old | New |
|-----|-----|-----|
| Change 1.3 | `L-46→1.3` | `L-45→1.3` |
| Keep 13.3 | `L-46→13.3` | `L-46→13.3` (no change) |

**Also fix title:** Position 1.3 CHAPTERS entry should change from "Entrepreneurship and Side Hustles" to stay "Entrepreneurship and Side Hustles" (now correctly mapped to L-45).
Position 13.3 CHAPTERS entry should change to "Automobile Finance — Buying vs. Leasing".

**Florida is also missing L-31.** Check which position should have it and add it. Florida currently has L-45 nowhere (that was the missing piece creating the L-46 duplicate). After this fix, L-45 goes to 1.3.

### Illinois
**Problem:** L-2 at positions 1.2 AND 3.6
**Root cause:** L-45 (Entrepreneurship) is completely missing from the file

| Fix | Old | New |
|-----|-----|-----|
| Keep 1.2 | `L-2→1.2` | `L-2→1.2` (no change) |
| Change 3.6 | `L-2→3.6` | `L-45→3.6` |

**Also fix title:** Position 3.6 should be "Entrepreneurship and Side Hustles"

### Minnesota (3 duplicates)

**Problem 1:** L-46 at positions 3.7 AND 4.9
| Fix | Old | New |
|-----|-----|-----|
| Keep 3.7 | `L-46→3.7` | `L-46→3.7` (no change) |
| Change 4.9 | `L-46→4.9` | `L-45→4.9` |

**Also fix titles:** 3.7 → "Automobile Finance — Buying vs. Leasing", 4.9 → "Entrepreneurship and Side Hustles"

**Problem 2:** L-6 at positions 1.3 AND 8.1
Minnesota has 55 mapping entries (uses economics chapters). Position 8.1 in a tax benchmark having L-6 duplicated likely means a different tax chapter belongs there.
| Fix | Old | New |
|-----|-----|-----|
| Keep 1.3 | `L-6→1.3` | `L-6→1.3` (no change) |
| Change 8.1 | `L-6→8.1` | Check what chapter title is at 8.1 and assign the matching L-chapter |

**Likely fix:** If 8.1 is titled something about tax systems, it might need L-52 (Government and the Economy) or another economics chapter from L-48-L-55 since Minnesota uses those.

**Problem 3:** L-34 at positions 5.6 AND 8.2
| Fix | Old | New |
|-----|-----|-----|
| Keep 5.6 | `L-34→5.6` | `L-34→5.6` (no change) |
| Change 8.2 | `L-34→8.2` | `L-35→8.2` (Managing Insurance Costs) |

**Fix title at 8.2** to "Managing Insurance Costs"

### New Jersey
**Problem:** L-46 at positions 5.4 AND 9.5

| Fix | Old | New |
|-----|-----|-----|
| Keep 5.4 | `L-46→5.4` | `L-46→5.4` (no change) |
| Change 9.5 | `L-46→9.5` | `L-45→9.5` |

**Fix titles:** 5.4 → "Automobile Finance — Buying vs. Leasing", 9.5 → "Entrepreneurship and Side Hustles"

### Oregon
**Problem:** L-46 at positions 3.10 AND 3.11

| Fix | Old | New |
|-----|-----|-----|
| Keep 3.10 | `L-46→3.10` | `L-46→3.10` (no change) |
| Change 3.11 | `L-46→3.11` | `L-45→3.11` |

**Fix titles:** 3.10 → "Automobile Finance — Buying vs. Leasing", 3.11 → "Entrepreneurship and Side Hustles"

### Virginia
**Problem:** L-46 at positions 7.1 AND 9.2

| Fix | Old | New |
|-----|-----|-----|
| Change 7.1 | `L-46→7.1` | `L-45→7.1` |
| Keep 9.2 | `L-46→9.2` | `L-46→9.2` (no change) |

**Fix titles:** 7.1 → "Entrepreneurship and Side Hustles", 9.2 → "Automobile Finance — Buying vs. Leasing"

---

## PART 8: Combined Chapter System Documentation

### What Are Combined Chapters?

Two pairs of core chapters have "combined" versions that merge two chapters into one:

| Combined ID | Merges | Freed Slot Used For |
|-------------|--------|-------------------|
| LC-36 | L-36 (Gambling Risks) + L-37 (Gambling Costs/Benefits) | L-46 (Auto Finance) |
| LC-39 | L-39 (Charitable Giving) + L-40 (Checking Charitable Groups) | Additional slot |

### How Combined Chapters Work in the App

When the mapping line says `L-36+L-37→5.3`:
- The app serves the **LC-36 combined content file**, NOT L-36 and L-37 separately
- The student sees ONE chapter covering both gambling topics
- The combined file is a single, unified lesson (not two lessons concatenated)

### File Locations

**Slide Decks (Day 1):**
- Repository: `pfl-academy-sync-90`
- Branch: `claude/add-state-variables-slides-017dH4k6D8oq1Qu7NjHgPmmD`
- Path: `/slide-decks/`
- Files:
  - `LC-36-combined-gambling-slides.html`
  - `LC-39-combined-philanthropy-slides.html`
  - `L-46-automobile-finance-slides.html`
  - `CHAPTER_RESOURCES_L46-LC39.md` (external resources and teaching support)

**Day 2 Content:** Combined versions needed for LC-36 and LC-39 Student Workbooks and Teacher Guides.

### State Configuration Rules

**30 states use COMBINED (LC-36 + LC-39):**
Alabama, Colorado, Connecticut, Delaware, Florida, Iowa, Kansas, Kentucky, Louisiana, Maine, Maryland, Michigan, Minnesota, Mississippi, Missouri, Nebraska, New Hampshire, New Jersey, Oklahoma, Oregon, Pennsylvania, South Carolina, Tennessee, **Texas-PFL, Texas-PFLE**, Utah, Virginia, West Virginia, Wisconsin

**5 states use SEPARATE (individual L-36, L-37, L-39, L-40):**
California, Illinois, Indiana, North Carolina, **Rhode Island**

**Georgia: HYBRID** — L-36/L-37 separate, L-39+L-40 combined

### Key Implementation Note

For **separate** states: The app serves L-36, L-37, L-39, L-40 as four individual chapters. These states do NOT get L-46 because no slots were freed.

For **combined** states: The app serves LC-36 and LC-39 as two combined chapters. The freed slots are used for L-46 (and sometimes L-47 or other extended chapters depending on the state).

---

## PART 9: Additional Issues Found

### North Carolina — Missing L-9
North Carolina is missing L-9 (Understanding Tax Deductions and Credits). Needs to be added to the appropriate standard.

### Louisiana — Mapping Structure
Louisiana maps to 45 entries but uses extended chapters (L-46, L-47, L-56-L-62) while omitting some core chapters (L-30, L-31, L-32, L-34, L-35). This appears intentional per Louisiana's unique requirements, but should be verified against actual Louisiana standards.

### Missouri and Oklahoma — Arrow Character
These two states use `í` instead of `→` in their mapping lines. The app parser needs to handle both characters, OR the files should be updated to use `→` consistently.

### Florida — Missing L-31
Florida is missing L-31 (Renting Costs). After fixing the L-46→L-45 duplicate at position 1.3, Florida still needs L-31 added somewhere in its curriculum.

---

## PART 10: Validation Checklist

Before deploying ANY state file, run this checklist:

1. ☐ `L_CHAPTER_MAPPINGS` line exists and is parseable
2. ☐ No duplicate L-chapter numbers (each L-number appears at most once, except in combined entries)
3. ☐ Combined entries use `L-36+L-37` and `L-39+L-40` format (not individual)
4. ☐ ALL core chapters L-1 through L-45 are present (either individually or via combined)
5. ☐ Every position in `L_CHAPTER_MAPPINGS` has a matching entry in the `_CHAPTERS` line
6. ☐ Every chapter title matches the canonical title for its L-chapter (see Part 1)
7. ☐ No hallucinated titles ("Professional Development", "Career Advancement Strategies", "Workplace Skills" when mapped to wrong L-chapter)
8. ☐ Arrow character is `→` (not `í` or `->`)
9. ☐ Chapter counts in line items match actual chapter counts in CHAPTERS lines
10. ☐ OMITTED_CHAPTERS line accurately reflects what's excluded and why
