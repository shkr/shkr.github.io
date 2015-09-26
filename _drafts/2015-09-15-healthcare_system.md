---
layout: post
title:  A simple model of the Health-care system from an engineer's perspective
---

The U.S. Health care system is an attractor for a quick passionate round of questions and opinions
in discussions these days. There is little warm-up time required for the partakers
even if they just switched from an invigorating discussion on the efficiency of the randomized min-cut algorithm
or ways to maximize a carbohydrate in a chipotle burrito.
Motivation for caching such thoughts and opinions, may not be ill-placed.
Just to put some numbers (hustling in some stats reasoning), United States spends
more on health care per capita ($8,608) or percentage of its GDP (17.2%),than any other nation in 2011.
A good chunk of the financial provisions and spending (60–65%) is from the goverment through programs such as Medicare, Medicaid,
the Children's Health Insurance Program, and the Veterans Health Administration. Add to this a rapidly evolving medicine
and biotechnology industry, it adds a lot of velocity, and the ramification of turbulence in a system yearning to
stabilize. [Add private players in this scenario right now and how they will cope up]
On March 23, 2010, the Patient Protection and Affordable Care Act (PPACA) transformed into a law. It brought major changes
one of the notable ones is that [Insert significant information].
The medical and healthcare system will be forced to change normal procedures and they will be required to prepare for upcoming programs
to meet federal regulations. [refer riskscore and other changes]
Trying to comfort this great zest both for myself and in my crisp to discover (or solve) a painful problem in medicine, I decided
to draw a model system of healthcare services.
The end game of the model must be to lead to simple answers to these questions.

- What are real pain points in medical practice that you wish AI would solve ?
- What would you do with AI in medicine if you could get it to work (pie in the sky best case scenario, and more realistic ones)
- Are there any good public data sources for these problems?

I will attempt to use the Feynman algorithm, to write the problem first and see if the solution.

This is my abstraction of the practice of medicine. The identification of essential objects and the exchanges the objects
partake in, will be the goal. First let us list down the four objects.

1. Payers : The firm which works with providers and sells insurance products to patients (via direct/indirect transaction).
All of the exchanges it has with other entities can be categorized into Billing and pricing.

2. Providers : The firm which manages practitioners and additionally may sell insurance products to patients (via indirect transaction).
Most of the exchanges it has with other entities can be categorized into management of care and billing.

3. Practitioners : The individual who dispense medical consultation or procedural services.
Most of the exchanges it has with other entities can be categorized into diagnostics and management of care.

4. Patients : The individual who consumes medical service.
Most of the exchanges it has with other entities can be categorized into diagnostics and pricing.

Exchanges

Payers <-> Providers
 ===================================================================
1. Patients consume medical services at providers premises.
2. Provider aggregates bills from these interactions and sends it to the respective payer.
3. Provider aggregates diagnostics data from these interactions for record keeping purposes.
?. Provider aggregates diagnostics data to help improve future interactions

Providers <-> Practitioners
===================================================================
1. Practitioners code their interactions with patients using coding systems like ICD9, CPT, SNOMED & HCC.
2. Providers use these codes to bill the payers.
3. Practitioners make referrals to other providers when interacting with the patients, if they perceive that it will benefit the patient to interact with a different practitioner. Provider institutions have a large influence on a
    practitioners referral network.
4. Providers also manage diagnostics labs or availability of therapeutic services to a population of patients.
   They are (most provider systems) )incentivized (as long they don’t have to refer the patients out of their network) for reducing usage of such services.

Major concerns / Possible places to research for precise pain points :

1. The major concern of Provider is to provide the practitioner the right set of tools to code interactions properly.
2. The major concern of Provider is to bill services to the payers correctly.
3. The major concern of Provider is to help practitioners take better care of their patients.
4. The major concern of Provider is to maximize efficacy of diagnostic and therapeutic tests to diagnose/treat the patients.
5. The major concern of Practitioner is to have a strong referral network.

Practitioners <-> Patients
===================================================================
Practitioner patient interactions can be categorized into six types :

1. Differential diagnosis - the process of finding out the disease condition of the patient. At the end of this process the practitioner will have 1 or more probable choices to make a decision about the disease condition.
2. Physical examination - the usage of eyeballing & physical touch to reduce the list of probable choices to
3. Diagnostic tests - the usage of laboratory tests to reduce the list of probable choices to 1.
4. Management of Care - lifestyle recommendations provided to patients in order to bring them to an agreeable health condition; Example - no smoking, running, reduce alcohol consumption, dietary restrictions, dietary supplements
5. Prescription - medication recommendations provided to patients in order to bring them to an agreeable health condition with its usage; Adverse reactions, interactions w/ other medications, dosage, strength information must be clearly provided to the patients along with the medication.
Considering the point of sale perspective for the patient, care must also be taken to prescribe medicines which are easily available at minimal price.
6. Therapeutic - treatment recommendations provided to patients in order to bring them to an agreeable health condition with its usage;
Considering the point of sale perspective for the patient, care must be taken to recommend treatments only if necessary but also at an early/preventive stage.

Major concerns / Possible places to research for precise pain points :

1. The major concern of practitioner is to improve the precision & accuracy of ddx, since false negatives & false positives are very harmful.
2. The major concern of practitioner is to ensure full utilization & correct understanding of the information of a diagnostic test result.
3. The major concern of practitioner is to recommend the right management of care to patients which reduces their hospital visits and helps them recover back to good health condition by usage of a good lifestyle.
4. The major concern of practitioner is to recommend the medication which has minimal side-effects and results in definite improvement in the disease condition of the patient with its consumption.

Patients <-> Payers/Providers
========================================================
Patients buy medical insurance products which decide the price for the medical services the patient will consume at the providers premises.

Major concerns / Possible places to research for precise pain points :
1. The major concern of patient is to easily buy healthcare plans.
2. The major concern of patient is to buy affordable healthcare which has minimal co-pay (fee per medical service consumption) and  preferably includes services for his/her defendants.

Now the additional questions :

- are there companies out there that you know of that are providing diagnosis assistance tools? How much do they charge? Do people care?

There are different types of products which help practitioners. Popular ones include :
1. Epocrates
2. Uptodate
3. EPIC - for coding

- what would you do with AI in medicine if you could get it to work (pie in the sky best case scenario, and more realistic ones)

I will skip this question, hoping the above text is helpful for that.

- what are real pain points in medical practice that you wish AI would solve?

I will skip this question, hoping the above text is helpful for that.

- do you know of any good public data sources for these problems?

1. UMLS : http://www.nlm.nih.gov/research/umls/knowledge_sources/metathesaurus/

2. ConceptNet5 : http://conceptnet5.media.mit.edu/