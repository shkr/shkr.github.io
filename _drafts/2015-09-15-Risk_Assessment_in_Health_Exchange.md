---
layout: post
title:  A simple model of the CMS HCC Reimbursement for Medicare & Medicaid organizations
---

The HHS risk adjustment model, as given in the final HHS Notice of Benefit and
Payment Parameters, Final Rule (http://www.gpo.gov/fdsys/pkg/FR-2014-03-11/pdf/2014-05052.pdf)
is used to make assessment.

Description of the risk score calculated using  HHS risk adjustment model
========================================================

The HHS risk adjustment models calculates a risk score by summing an enrollee’s factors

1. age
2. sex
3. HCCs
4. HCC-interaction terms
5. Plan metal level
6. Cost-Sharing Reductions (if enrollee qualifies)

First, the algorithm crosswalks from acceptable diagnoses (listed with their ICD9s in claims data) to HHS Condition Categories (HHS-CCs).

Second, it creates HHS Hierarchical Condition Categories (HHS-HCCs) by grouping the HHS-CCs into one or more HHS-HCCs. For enrollee without claims no HHS-HCCs variables are created.

Third, after HHS-HCCs are created, the algorithm computes predicted scores by creating
	1. Demographic variables (age/sex)
	2. HHS-HCC interaction variables - created when one or more combination of HHS-HCCs
	are present to represent severity of illness.

Fourth, the metal level of the plan and cost-sharing reductions for enrollees who qualify for it. The metal level and cost sharing reductions provide Coefficients for the variables created from Step 1 to Step 3

Final,

The risk_score is reported as the financial risk bearing of an enrollee given their individual diagnoses for the current year

risk_score = ( coefficient_1 x variable_1 ) + ( coefficient_2 x variable_2 ) +( coefficient_3 x variable_3 ) ....

where,

variable_x from set of ( HHS-HCCs variables + Demographic Variables + HHS-HCC interaction variables )

coefficient_x from Fourth Step

Coefficients_x is calculated from metal level of the plan and cost-sharing reductions
Variable_x is calculated from HHS-HCCs variables, Demographic variables, HHS-HCC interaction variables
HHS-HCC variables and HHS-HCC interaction variables are derived from acceptable diagnoses (listed with their ICD9s in claims data)
Demographic variables are collected from claims data

The HHS risk adjustment model, as given in the final HHS Notice of Benefit and Payment Parameters, Final Rule (http://www.gpo.gov/fdsys/pkg/FR-2014-03-11/pdf/2014-05052.pdf) is used to make assessment.


Bibliography
==================

1. http://www.oliverwyman.com/insights/publications/2014/apr/risk-adjustment-arrives-for-commercial-health-insurance.html#.VFkTIVPF91Y


2. https://www.cms.gov/CCIIO/Resources/Regulations-and-Guidance/Downloads/ra-instructions-4-16-13.pdf
