# ☕ Volta Coffee – AI Wholesale Order Processing

AI-assisted wholesale order processing workflow built with **n8n**, **Google Gemini**, **JavaScript**, **Airtable**, and **Gmail**.

This project demonstrates how AI can automate repetitive business tasks while keeping humans responsible for important decisions. Free-text wholesale coffee orders are converted into structured data, validated, stored in Airtable, classified according to business rules, and followed by the appropriate automated email response.

---

# ✨ Features

- 🤖 AI-powered information extraction using Google Gemini
- 🧹 JavaScript validation and JSON parsing
- 🗂 Structured order storage in Airtable
- 🔀 Automatic order classification
- 📧 Automated Gmail responses
- 👤 Human-in-the-loop decision making
- ✅ End-to-end workflow automation with n8n

---

# 📌 Business Problem

Wholesale coffee orders often arrive as free-text messages by email or online forms. Employees must manually read every order, extract important information, copy it into internal systems, decide what to do next, and respond to the customer.

This process is repetitive, time-consuming, and prone to errors.

<p align="center">
<img src="images/business_problem.png" width="1000">
</p>

The objective of this project is to automate repetitive administrative work while ensuring that important business decisions remain under human control.

---

# 💡 Proposed Solution

The workflow combines AI with business rules to automate the complete order processing pipeline.

The workflow:

- extracts structured information using Google Gemini
- validates the extracted data
- stores the order in Airtable
- classifies the order
- sends the appropriate customer response

Orders requiring human attention are automatically routed for review instead of being processed automatically.

---

# 🔄 Workflow Architecture

The solution is implemented in **n8n** using modular workflow phases.

<p align="center">
<img src="images/workflow_architecture.png" width="1000">
</p>

The workflow consists of five main stages:

1. Customer Intake
2. AI Processing
3. Order Storage
4. Decision Logic
5. Customer Communication

---

# 🤖 AI Decision Logic

After extracting and validating the order, the workflow classifies it into one of three categories.

<p align="center">
<img src="images/ai_decision_making.png" width="1000">
</p>

| Classification | Workflow Action |
|----------------|----------------|
| ✅ Standard | Confirmation email |
| 🟡 Needs Review | Routed for human review |
| 🔴 Needs Clarification | Customer asked for missing information |

The AI performs the first assessment while humans remain responsible for exceptional cases.

---

# 🗂 Airtable Integration

Validated orders are automatically stored in Airtable to create a centralized and searchable order database.

<p align="center">
<img src="images/airtable_results.png" width="1000">
</p>

Each record contains:

- Customer information
- Ordered products
- Delivery details
- AI classification
- Notes for human review

---

# 📧 Automated Customer Communication

Based on the classification result, the workflow automatically sends one of three email templates.

- ✅ Confirmation Email
- 🟡 Review Email
- 🔴 Clarification Email

This ensures fast and consistent communication while keeping humans involved whenever necessary.

---

# ✅ Testing & Validation

Three representative scenarios were tested.

<p align="center">
<img src="images/testing_validation.png" width="1000">
</p>

| Scenario | Expected Result | Status |
|-----------|----------------|--------|
| Standard Order | Confirmation Email | ✅ Passed |
| Needs Review | Review Email | ✅ Passed |
| Needs Clarification | Clarification Email | ✅ Passed |

The workflow successfully:

- extracted structured information
- validated AI output
- stored records in Airtable
- classified orders correctly
- sent the correct customer email

---

# ⚠ Challenges & Improvements

During development several real-world issues were encountered.

| Challenge | Solution |
|------------|----------|
| Inconsistent AI JSON | Improved Gemini prompt |
| Airtable date formatting | Converted dates to ISO format |
| Classification inconsistencies | JavaScript normalization |
| Gmail authentication | Reconnected OAuth credentials |

These improvements increased the reliability and maintainability of the workflow.

---

# 📈 Project Outcomes

The completed workflow can:

- ✅ Extract structured order information
- ✅ Validate AI responses
- ✅ Store validated records
- ✅ Automatically classify orders
- ✅ Send appropriate customer emails
- ✅ Keep humans involved when required

The project demonstrates how AI can automate repetitive operational tasks while preserving human oversight for business-critical decisions.

---

# 🛠 Technologies Used

- n8n
- Google Gemini
- JavaScript
- Airtable
- Gmail API
- Markdown
- GitHub

---

# 📂 Repository Structure

```text
volta-coffee-ai-order-processing/
│
├── images/
│   ├── business_problem.png
│   ├── workflow_architecture.png
│   ├── ai_decision_making.png
│   ├── airtable_results.png
│   ├── testing_validation.png
│   └── email_response.png
│
├── workflow/
│   └── volta_coffee_ai_order_processing.json
│
├── documentation/
│   ├── Project_Summary.pdf
│   ├── Testing_Report.pdf
│   └── Appendix.pdf
│
├── presentation/
│   ├── Presentation.pdf
│   └── Presentation.pptx
│
├── README.md
└── LICENSE
```

---

# 🚀 Future Improvements

Possible future extensions include:

- Slack notifications
- Inventory availability checks
- ERP integration
- Automatic invoice generation
- Customer CRM integration
- AI confidence scoring
- Dashboard and analytics

---

# ▶️ How to Use

1. Import the workflow JSON into n8n.
2. Configure your Google Gemini credentials.
3. Connect Airtable.
4. Configure Gmail credentials.
5. Execute the workflow using the included order form.

---

# 👤 Author

**Dr. Ouad Soltani**

PhD in Plant Biology

Data Analytics & Artificial Intelligence Program

Masterschool Institute of Technology

---

⭐ *This project was developed as part of the AI Automations & Agent Foundations course and demonstrates the practical application of AI-assisted workflow automation using n8n and Google Gemini.*
