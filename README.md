# Servicenow-skillwallet-project
### Auto Ticket Classification Using FLOW DESIGNER

#### 📌 Project Overview
This project is a part of the ServiceNow SkillWallet Program. It automates the classification of incoming IT tickets (Incidents) using **ServiceNow Flow Designer**. The flow automatically analyzes the short description and category to assign Priority, Category, and Assignment Group, reducing manual effort and response time.

#### 🎯 Objectives
- To automatically classify incoming tickets
- To reduce manual triage time for IT support team
- To implement no-code automation using Flow Designer
- To improve SLA compliance and ticket routing accuracy

#### ✨ Features
- **Automated Trigger:** Flow triggers when a new Incident is created.
- **Keyword-based Classification:** Classifies tickets as Hardware, Software, Network, or Access Issue based on Short Description.
- **Auto Prioritization:** Sets Priority based on keywords like "down", "urgent", "not working".
- **Auto Assignment:** Assigns ticket to respective Assignment Group (Hardware Team, Software Team, Network Team).
- **No-Code Solution:** Built entirely with Flow Designer, no scripting required.

#### 🛠️ Tech Stack / ServiceNow Components Used
- ServiceNow PDI (Personal Developer Instance)
- **Flow Designer**
- Incident Table [incident]
- Actions: Update Record, Look Up Records, If Condition

#### ⚙️ Flow Logic
**Flow Name:** `Auto Ticket Classification`

**Trigger:** Record Created -> Table: Incident [incident]

**Actions:**
1. **If Condition 1:** If Short Description contains `laptop, mouse, keyboard, hardware` ->
    - Update Category = `Hardware`
    - Assignment Group = `Hardware Support`

2. **If Condition 2:** If Short Description contains `email, outlook, software, install` ->
    - Update Category = `Software`
    - Assignment Group = `Software Support`

3. **If Condition 3:** If Short Description contains `wifi, network, internet, down` ->
    - Update Category = `Network`
    - Priority = `1 - Critical`

4. **Default Action:** Else -> Assign to `Service Desk`

#### 🚀 How to Implement in ServiceNow
1. Login to your ServiceNow PDI.
2. Go to `All -> Process Automation -> Flow Designer`.
3. Click `New -> Flow` and create a new flow for `Incident` table.
4. Set Trigger as `Record Created`.
5. Add `If` logic with `Flow Logic` and configure conditions as above.
6. Add `Update Record` action to set Category, Priority, and Assignment Group.
7. Save, Activate, and Test by creating a new Incident.

#### 🧪 Testing
Create a new Incident with Short Description = "My laptop is not working"
Result: Flow will auto-classify it as Hardware and assign to Hardware Support Group.

#### 📸 Screenshots
(Add your Flow Designer Screenshots here)

#### 👨‍💻 Developed By
**Ebsiba293** as part of ServiceNow SkillWallet Project 2026.

#### 📄 License
This project is for educational purposes.
