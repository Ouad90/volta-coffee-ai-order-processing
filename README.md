# Volta Coffee AI Order Processing

An AI-assisted workflow for processing wholesale coffee orders using n8n, Google Gemini, JavaScript, Airtable, and Gmail.

![Workflow overview](images/workflow_overview.png)

## Project Overview

This project was created as part of the AI Automations & Agent Foundations module.

The goal was to automate the first stage of wholesale order processing. Customer orders often arrive as free-text messages containing products, quantities, delivery details, and special requests. Reading and processing every order manually is repetitive and can lead to delays or inconsistent handling.

The workflow extracts the relevant information, validates the AI response, stores the order, classifies it, and sends the appropriate customer email.

## Workflow

The workflow follows five main stages:

1. **Customer Intake**  
   A wholesale order is submitted through an n8n form.

2. **AI Processing**  
   Google Gemini extracts structured information from the free-text order.

3. **Validation**  
   A JavaScript node parses and normalizes the AI output.

4. **Order Storage**  
   The validated order is stored in Airtable.

5. **Classification and Communication**  
   A Switch node routes the order and Gmail sends the appropriate response.

## Order Classifications

### Standard

The order is complete and does not contain special conditions.

**Outcome:** Confirmation email.

### Needs Review

The order contains a substitution, large quantity, or special request requiring human attention.

**Outcome:** Review email.

### Needs Clarification

Important information, such as quantity or delivery details, is missing or unclear.

**Outcome:** Clarification email.

## Technologies Used

- n8n
- Google Gemini
- JavaScript
- JSON
- Airtable
- Gmail

## Testing

The workflow was tested using three representative scenarios:

| Scenario | Expected Classification | Result |
|---|---|---|
| Complete order | Standard | Passed |
| Substitution request | Needs Review | Passed |
| Missing information | Needs Clarification | Passed |

Testing confirmed that the workflow correctly:

- extracted the order information,
- stored the order in Airtable,
- selected the correct route,
- and sent the expected email.

## Challenges Addressed

During development, several issues were identified and corrected:

- inconsistent JSON output,
- Airtable date-format errors,
- classification value inconsistencies,
- Gmail authentication issues.

The Gemini prompt was refined, JavaScript validation was added, dates were standardized, and classification values were normalized.

## Human Oversight

The workflow automates repetitive processing steps but keeps humans involved when an order contains uncertainty, substitutions, or special conditions.

## Repository Structure

```text
.
├── README.md
├── LICENSE
├── workflow/
│   └── volta_coffee_ai_order_processing.json
├── documentation/
│   ├── 01_Project_Design.pdf
│   ├── 03_Project_Testing.pdf
│   ├── 04_Project_Summary.pdf
│   └── 05_Presentation.pdf
└── images/
    ├── workflow_overview.png
    ├── customer_order_form.png
    ├── airtable_results.png
    └── email_response.png
```

## How to Use the Workflow

1. Download the workflow JSON file.
2. Import it into n8n.
3. Configure your own Gemini, Airtable, and Gmail credentials.
4. Create the required Airtable fields.
5. Update the field mappings and email settings.
6. Test the workflow before activating it.

Credentials are not included in this repository.

## Limitations

The current workflow does not include:

- live inventory checking,
- price calculation,
- invoice generation,
- advanced email validation,
- multilingual order processing.

## Future Improvements

Possible extensions include:

- inventory integration,
- automatic invoice generation,
- CRM integration,
- manager approval workflows,
- multilingual order support.

## Author

**Dr. Ouad Soltani**

Data Analytics and AI Automation
