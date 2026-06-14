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

<img width="1920" height="947" alt="01_UI_Policy_Condition" src="https://github.com/user-attachments/assets/d5eee0ce-3dc7-4d73-a2c1-d00945c260a8" />


### 02. UI Policy Action Rule
Explicit configuration mapping target state attributes to the dependent field. When triggered, the rule dynamically changes the `business_justification` form properties to `Visible = True` and `Mandatory = True`.

<img width="1920" height="944" alt="02_UI_Policy_Action" src="https://github.com/user-attachments/assets/e548c970-b68a-4967-aaf0-3f9ee6c6f52d" />

### 03. Dynamic Form Frontend Verification
Live end-to-end user experience testing on the ServiceNow Service Portal interface. Selecting **Administrator Access** instantly forces the mandatory business justification field to render, preventing submission until data validation criteria are satisfied.

<img width="983" height="943" alt="03_Dynamic_Form_Testing" src="https://github.com/user-attachments/assets/deb902fb-f6a9-4ebc-9c67-0d3655498849" />


## Project Summary & Key Takeaways

* **Form Efficiency:** Hiding the justification box keeps the form clean and simple for standard users, only showing it when advanced access is requested.
* **No Code Needed:** Learned how to create dynamic forms using ServiceNow's built-in UI Policies instead of writing complex custom code.
* **Automatic Clean Up:** Kept the "Reverse if false" setting on so that if a user changes their mind and switches back to Standard Access, the justification box automatically disappears again.
