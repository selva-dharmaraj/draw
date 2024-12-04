

# Chase Pay Over Time - Bundling Transactions Feature: Architecture Assessment

## 1. Executive Summary

This document provides an architecture assessment for a new feature proposed for the Chase Pay Over Time (CPOT) - After Purchase product. The feature aims to introduce transaction bundling capabilities to enhance customer experience and increase installment loan origination. This assessment outlines the scope, feature details, research findings, and solution options to aid leadership in decision-making and resource allocation.

## 2. Scope

The scope of this assessment covers:
- Evaluation of the current CPOT - After Purchase product
- Analysis of the proposed bundling feature
- Comparison of three potential solution options
- Impact assessment on various systems and capabilities
- High-level development effort estimation

## 3. Current Product Overview

Chase Pay Over Time (CPOT) - After Purchase is an existing offering for Chase credit card customers. Key features include:
- Conversion of single transactions over $100 into payment plans
- Installment options of 3, 6, or 12 months
- Accessible through online and customer-assisted channels
- Small fee associated with each plan

Limitation: Currently allows creation of payment plans for only one transaction at a time.

## 4. Proposed Feature: Transaction Bundling

### 4.1 Feature Objective
To allow customers to combine multiple transactions into a single installment plan, aiming to:
- Attract more customers
- Increase installment loan origination
- Enhance customer flexibility in managing expenses

### 4.2 Research Findings
The Digital Customer Experience (DCE) team conducted market research and customer interviews, initially exploring nine variations of bundling transactions. The research narrowed down to three top bundling concepts that showed high customer interest and potential for increased product revenue.

## 5. Solution Options Comparison

| Aspect | Option 1: Bundling Transactions Over $100 | Option 2: Bundling Related Transactions (Any Amount) | Option 3: Balance-Based Plans |
|--------|-------------------------------------------|------------------------------------------------------|-------------------------------|
| Description | Allow bundling of multiple transactions, each over $100 | Allow bundling of multiple related transactions of any amount | Create plans based on available balance without attaching to specific transactions |
| Pros | - Quick win solution<br>- Minimal system-level changes<br>- Builds on existing $100 threshold logic | - Ideal for mixing various transactions<br>- Increased customer flexibility<br>- Potential for higher customer attraction | - Novel approach to plan creation<br>- Utilizes available balance flexibly |
| Cons | - Excludes smaller transactions<br>- Limited attraction for new customers | - Significant impact on backend architecture<br>- Major updates required for eligibility rules and systems | - Potentially lower customer uptake<br>- Significant architectural changes required |
| Key Assumptions | - No changes to existing plans<br>- All transactions must be over $100<br>- No changes to entry points, pricing, or promo offers | - New eligibility rule changes required<br>- No pricing or promotion changes | - New eligibility rule changes<br>- No pricing or promotion changes |
| Impacted Systems | - GUI<br>- Marketing<br>- Plan creation<br>- Return/refund handling | - Eligibility rules and systems<br>- GUI<br>- Marketing<br>- Plan creation<br>- Transaction filtering and sorting | - Eligibility rules and systems<br>- Marketing<br>- Plan creation<br>- GUI<br>- Balance and transaction management |
| Complexity | Low | Medium | High |
| Customer Appeal | Moderate | High | Moderate |
| System Impact | Low | High | High |
| Development Effort | Low | High | Very High |
| Time to Market | Short | Medium | Long |
| Revenue Potential | Moderate | High | Moderate |

## 6. Impacted Capabilities and Systems

### 6.1 Capabilities

1. CPOT Dashboard (Owner: Lending Innovation)
2. Entry points / Nudges (Owner: Digital Channels)
3. Retrieve Transaction Data (Owner: Transaction Utility)
4. Retrieve Account Data (Owner: Account Utility)
5. Loan Origination Orchestration (Owner: Lending Innovation Service)
6. Installment Plan Price calculation (Owners: Lending Innovation Service, Pricing)
7. Installment Plan Creation (Owner: Pricing)
8. Account Eligibility (Owners: Lending Innovation Service, P&I, Risk)
9. Transaction Eligibility (Owners: Lending Innovation Service, P&I, Transaction Utility, Card Financial Transaction, Operations CDFO)
10. Installment Loan Management (Owner: Card Account Management)
11. Credit Card Account Management (Owner: Card Account Management)
12. Credit Card Transactions (Owner: Card Financial Transaction)
13. Customer Assistance (Owner: Servicing OCS)
14. Transaction Fraud / Disputes (Owner: Operations CDFO)
15. Transaction Return / Refund (Owners: Lending Innovation Service, Pricing)
16. Customer Eligibility (Owner: Risk)

### 6.2 Impacted Systems

1. Lending Innovation (Service)
2. Lending Innovation (UI)
3. P&I
4. GCP
5. Utilities
6. Servicing (OCS)
7. Operations (CDFO)
8. Pricing
9. Card Financial Transaction
10. Card Account Management
11. Risk
12. Digital Channels

## 7. Comparison and Estimation

| Aspect | Option 1 | Option 2 | Option 3 |
|--------|----------|----------|----------|
| Complexity | Low | Medium | High |
| Customer Appeal | Moderate | High | Moderate |
| System Impact | Low | High | High |
| Development Effort | Low | High | Very High |
| Time to Market | Short | Medium | Long |
| Revenue Potential | Moderate | High | Moderate |

### Estimated Development Hours (High-Level)

| System | Option 1 | Option 2 | Option 3 |
|--------|----------|----------|----------|
| Lending Innovation (Service) | 200 | 500 | 600 |
| Lending Innovation (UI) | 150 | 300 | 350 |
| P&I | 100 | 250 | 300 |
| GCP | 50 | 150 | 200 |
| Utilities | 100 | 200 | 250 |
| Servicing (OCS) | 150 | 300 | 350 |
| Operations (CDFO) | 100 | 200 | 250 |
| Pricing | 150 | 300 | 350 |
| Card Financial Transaction | 200 | 400 | 450 |
| Card Account Management | 150 | 300 | 350 |
| Risk | 100 | 250 | 300 |
| Digital Channels | 150 | 300 | 350 |
| **Total Estimated Hours** | **1,600** | **3,450** | **4,100** |

Note: These are rough estimates and should be refined with input from each team.

## 8. Recommendation

Based on the analysis, Option 2 (Bundling Related Transactions) appears to offer the best balance between customer appeal and business value. While it requires significant development effort, it provides the most flexibility for customers and has the highest potential for increasing product revenue.

However, a phased approach could be considered:
1. Implement Option 1 as a quick win to introduce the bundling concept.
2. Plan for Option 2 as a major update in the next phase, leveraging learnings from Option 1.
3. Consider Option 3 for long-term product evolution based on customer feedback and market trends.

## 9. Next Steps

1. Review this assessment with stakeholders from each impacted system.
2. Conduct a detailed technical feasibility study for the recommended option.
3. Develop a more precise estimation of development efforts and timeline.
4. Create a phased implementation plan.
5. Prepare a budget proposal based on the refined estimates.
6. Schedule a leadership review for final decision-making.

