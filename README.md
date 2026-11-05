# Potential Customer Relevance Scoring System 
# 潜在客户相关度评分系统

## Project Background

During industrial B2B customer development, researching potential customers can be time-consuming. Sales professionals often need to visit multiple websites, investigate company backgrounds, review product portfolios, and manually assess whether a company is worth approaching. These assessments can also vary depending on individual experience and product knowledge.

However, a company's relevance to a specific industrial product category can often be identified through industry keywords, product keywords, business activities, and application areas.

**Potential Customer Relevance Scoring System** is designed to make this process faster and more consistent.

By simply providing a company's official website URL, the system aims to automatically research its business profile, identify relevant products and industries, and generate a structured relevance score.

The goal is to reduce manual customer research time by up to 90%, standardize prospect evaluation, and help sales professionals quickly identify, prioritize, and organize potential customers.

For fiber optic connectivity suppliers, potential customers are not limited to companies that already purchase MPO/MTP assemblies or fiber optic patch cords.

Relevant prospects may include:

- Fiber optic connectivity brands
- Optical communication product manufacturers
- Telecommunications equipment suppliers
- Data center infrastructure suppliers
- Fiber optic product distributors
- Networking and cabling solution providers
- Companies with existing fiber optic product portfolios and potential external sourcing needs



## 2. Project Objectives

The system is designed to:

1. Collect publicly available information about target companies.
2. Identify their main business activities and product portfolios.
3. Evaluate their relevance to fiber optic connectivity products.
4. Assess company size, business scale, industry relevance, and business potential.
5. Calculate qualification scores using a predefined scoring model.
6. Classify potential customers into different priority levels.
7. Generate structured company research and qualification reports.
8. Provide traceable evidence and source links for important findings.

The system should help answer one central question:

**Is this company a suitable potential customer for a fiber optic connectivity supplier, and how much effort should be invested in developing it?**

## 3. Project Scope

### Included in V3

V3 focuses exclusively on company research and customer qualification.

| Module | Description |
|---|---|
| Company Input | Accept company name, website, and country |
| Public Information Research | Collect publicly available company information |
| Company Profile Extraction | Extract company descriptions, business activities, and company size |
| Product Analysis | Identify fiber optic products and related product categories |
| Industry Analysis | Identify relevant industries and applications |
| Evidence Collection | Record source URLs and supporting information |
| Company Scoring | Calculate scores using predefined Python rules |
| Customer Classification | Assign A/B/C/D or other qualification statuses |
| Report Generation | Generate structured company research reports |

### Explicitly Excluded from V3

The following functions are outside the scope of this version:

- Customer database management
- CRM functionality
- Lead pipeline management
- Automatic follow-up scheduling
- Autonomous prospecting agents
- Automatic email generation and sending
- Multi-agent collaboration
- Vector databases and complex RAG systems
- Automated purchasing-intent prediction

These functions may be considered in V4 or future versions.

**V3 is a company research and qualification tool, not a complete sales automation platform.**

## 4. Target Customer Profile

The project evaluates companies from the perspective of a fiber optic connectivity supplier.

The primary focus is on established industrial B2B companies, particularly medium-sized brands, manufacturers, distributors, and solution providers.

Relevant product categories include:

- Fiber optic patch cords
- MPO/MTP assemblies
- LC/SC fiber optic connectors and adapters
- Fiber optic distribution frames and panels
- Fiber optic enclosures and accessories
- PLC splitters
- FTTH products
- Optical cables
- Data center fiber connectivity solutions
- Other passive fiber optic components

Relevant industries and applications include:

- Data centers
- Telecommunications
- FTTH
- Enterprise networking
- Structured cabling
- Optical communication
- Network infrastructure

### Important Qualification Principle

A company does not need to sell MPO/MTP products to qualify as a potential customer.

Companies with other relevant fiber optic products may also be valuable prospects.

MPO/MTP product availability is a positive relevance signal, not a mandatory qualification requirement.

The system should evaluate the company's overall product and business relevance rather than relying on a single product keyword.

## 5. Company Scoring Model

The qualification model uses five dimensions with a total weight of 100 points.

| Dimension | Weight | Evaluation Focus |
|---|---:|---|
| Product Relevance | 50 | Relevance of the company's product portfolio to fiber optic connectivity |
| Company Size | 15 | Employee count, locations, and organizational scale |
| Business Scale | 10 | Public revenue and other reliable business-scale indicators |
| Industry Relevance | 15 | Relevance to data centers, telecom, FTTH, and networking |
| Business Potential | 10 | Brand positioning, product range, sales channels, and potential external sourcing opportunities |
| **Total** | **100** | |

### 5.1 Product Relevance

Product relevance has the highest weight because the project prioritizes companies with existing or potential demand for fiber optic connectivity products.

Initial scoring guidance:

| Product Profile | Score Range |
|---|---:|
| Core business includes MPO/MTP, fiber optic assemblies, or connectivity solutions | 45–50 |
| Offers LC/SC patch cords, distribution panels, adapters, and other fiber connectivity products | 35–44 |
| Offers PLC splitters, FTTH products, optical cables, or related fiber products | 25–34 |
| Offers a limited range of fiber-related products, but fiber is not a core business | 10–24 |
| No relevant products identified from available evidence | 0 |

These ranges are initial evaluation guidelines. Detailed scoring rules may be refined through testing with real companies.

The absence of MPO/MTP products must not automatically disqualify a company.

### 5.2 Company Size

Evaluate publicly available information such as:

- Employee count
- Number of offices or business locations
- Geographic business coverage
- Sales and technical team scale, where available

Company size should be evaluated in the context of industrial B2B business rather than using employee count alone.

### 5.3 Business Scale

Use reliable publicly available information, such as:

- Annual revenue
- Published financial reports
- Other verifiable business-scale indicators

If revenue information is unavailable, the dimension must be marked as unknown and excluded from the scoring denominator.

The system must not invent or present estimated revenue as verified information.

### 5.4 Industry Relevance

Evaluate whether the company operates in or supplies products to relevant industries, including:

- Data centers
- Telecommunications
- FTTH
- Enterprise networking
- Structured cabling
- Optical communication

### 5.5 Business Potential

Evaluate potential commercial opportunities based on public business information, including:

- Established brand or market presence
- Breadth of product portfolio
- Distribution and sales channels
- Geographic market coverage
- Potential need for external manufacturing or sourcing
- Opportunities for product portfolio expansion

Business potential is an assessment of commercial fit, not proof of current purchasing demand or supplier-switching intention.

## 6. Qualification Grades

The initial grading thresholds are:

| Grade | Standardized Score | Priority |
|---|---:|---|
| A | 80–100 | High priority |
| B | 65–79.9 | Medium-high priority |
| C | 45–64.9 | Lower priority |
| D | 0–44.9 | Low priority |

Additional statuses:

- **Insufficient Data:** Research coverage is below the minimum required threshold.
- **Not Relevant:** Both product relevance and industry relevance have been explicitly assessed as zero based on available evidence.

### Unknown Information and Coverage

Unknown information must not automatically be treated as zero.

The system calculates the standardized score based on assessed dimensions only:

`Score = Earned Points / Assessed Maximum Points × 100`

Research coverage is calculated separately:

`Coverage = Assessed Maximum Points / 100 × 100`

The initial minimum coverage threshold is 70%.

If coverage is below 70%, the system returns `Insufficient Data` rather than assigning an A/B/C/D grade.

A high score with low information coverage must not be presented as a fully qualified result.

## 7. Research and Evidence Principles

The system relies on publicly available information.

Potential sources include:

- Official company websites
- Product catalogues and datasheets
- Company About Us pages
- Public company profiles
- Published annual reports
- Public business directories
- Other accessible and relevant sources

Important research principles:

1. Important company facts should include source URLs.
2. Official company sources should be prioritized where appropriate.
3. Research findings should distinguish verified facts from estimates and unknown information.
4. Conflicting information should be flagged rather than silently resolved.
5. The system must not invent company information, revenue, employee counts, or purchasing intentions.
6. Research dates and source information should be retained.
7. Product listings should be distinguished from the company's actual core business where possible.

Suggested evidence statuses:

- `verified`: Supported by reliable public evidence.
- `estimated`: An explicitly identified estimate based on available evidence.
- `unknown`: Insufficient information to make a reliable assessment.

The scoring engine should use only information that satisfies the relevant scoring and evidence requirements.

## 8. Technical Architecture

The project uses a simple modular Python architecture.

| Component | Responsibility |
|---|---|
| Research Layer | Search and collect publicly available company information |
| AI Extraction Layer | Extract structured company and product information |
| Evidence Validation | Validate data structure and evidence references |
| Scoring Engine | Calculate qualification scores and grades |
| Report Generator | Generate Markdown or HTML reports |

### Key Design Principle

**AI is responsible for researching, extracting, and organizing information. Python is responsible for validating scoring inputs and calculating qualification results.**

The scoring model should remain independent of the AI model.

This separation improves consistency, transparency, and maintainability.

## 9. Planned Project Structure

```text
Company-Research-Qualification/
│
├── config/
│   └── scoring_rules.py
│
├── core/
│   ├── research.py
│   ├── extraction.py
│   ├── validation.py
│   └── scoring.py
│
├── prompts/
│   └── company_research.txt
│
├── data/
│   └── test_companies/
│
├── reports/
│
├── tools/
│   └── run_research.py
│
├── tests/
│   └── test_scoring.py
│
├── main.py
├── requirements.txt
├── .gitignore
└── README.md
```

The project structure may evolve as development progresses. New modules should only be introduced when they serve a clear functional purpose.

## 10. Development Roadmap

### Phase 1 — Scoring Engine

- Define scoring rules and thresholds.
- Implement the Python scoring module.
- Handle unknown information and coverage.
- Test scoring calculations and qualification grades.

### Phase 2 — Research Data Structure

- Define standardized company profile fields.
- Define product and industry data fields.
- Define evidence records and source formats.
- Establish data validation rules.

### Phase 3 — Public Information Research

- Implement company search.
- Collect public company and product information.
- Retrieve relevant webpages.
- Record sources and retrieval dates.

### Phase 4 — AI Extraction and Validation

- Integrate an AI model.
- Extract structured company information.
- Validate extracted fields.
- Identify missing or conflicting information.

### Phase 5 — Integrated Qualification Reports

- Connect research and extraction modules.
- Integrate the scoring engine.
- Generate company qualification reports.
- Test the system using real target companies.

## 11. Project Development Principles

- Keep the system modular and easy to understand.
- Develop and test one module at a time.
- Avoid unnecessary dependencies and complex infrastructure.
- Do not introduce a database or autonomous agent in V3.
- Keep scoring rules configurable and independent of AI.
- Preserve evidence and source traceability.
- Prioritize practical sales value over technical complexity.

## 12. Future Development

V4 may extend the system into a broader prospecting and sales management platform, potentially including:

- Customer database
- Lead management
- Prospecting workflow automation
- AI-assisted customer follow-up
- Email generation and integration
- Customer activity tracking
- Autonomous research and sales agents

These capabilities are future possibilities and are not part of the current V3 implementation.

---

**Current Version:** V3 — Company Research & Qualification

**Project Status:** Planning and initial development

**Primary Business Focus:** Industrial B2B sales — Fiber Optic Connectivity and Fiber Optic Patch Cord Business Development
