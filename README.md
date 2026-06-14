# ServiceNow Service Catalog: Dynamic Form Control (Catalog UI Policies)

This project details the configuration of a dynamic ServiceNow Catalog UI Policy. To optimize the user experience and enforce data governance, a frontend rule was configured to hide sensitive configuration prompts until explicit administrative privileges are requested.

## Features Configured
* **Conditional Execution Framework:** Built a real-time policy engine monitoring user selections on the access tier dropdown.
* **Dynamic Property Inversion:** Configured backend actions to modify form field properties (`Visible` and `Mandatory`) on the fly.
* **Data Validation Enforcement:** Blocked form submission until administrative business justification criteria are explicitly provided.

---

## Project Architecture & Verification

### 01. UI Policy Trigger Condition
Definition of the baseline conditional execution policy framework evaluating frontend user actions in real time. The engine monitors the `access_level` state, listening for a value change to "admin".

./01_UI_Policy_Condition.png

### 02. UI Policy Action Rule
Explicit configuration mapping target state attributes to the dependent field. When triggered, the rule dynamically changes the `business_justification` form properties to `Visible = True` and `Mandatory = True`.

./02_UI_Policy_Action.png

### 03. Dynamic Form Frontend Verification
Live end-to-end user experience testing on the ServiceNow Service Portal interface. Selecting **Administrator Access** instantly forces the mandatory business justification field to render, preventing submission until data validation criteria are satisfied.

./03_Dynamic_Form_Testing.png
