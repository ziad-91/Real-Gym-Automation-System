# Real-Gym-Automation-System
A real system I built for my client that increased revenue by 30% every month &amp; saved 10hrs/week

Designed and deployed a real-world automation system to improve revenue collection and operational efficiency for a gym.

This project combines workflow automation, data modeling, and system design to solve real business problems under practical constraints.

---

## Key Results

- Reduced late payments from **40% → <5%**
- Increased collected revenue by **~30%**
- Saved **~10 hours/week** of manual admin work
- Improved payment timing (more payments received on time)
- Reduced staff workload and operational stress
- Client confirmed they would **not revert** to the previous system

---

## What I Built

A multi-component system consisting of three integrated subsystems:

1. **Revenue Recovery Automation**
2. **Reactivation Campaign System**
3. **ID-Based Check-in Optimization**

The system connects **Airtable (data layer)**, **n8n (automation engine)**, and **Twilio WhatsApp (communication layer)**.

---

## System Architecture

flowchart TD
A[Airtable - Data & Logic Layer] --> B[n8n - Automation Layer]
B --> C[Twilio WhatsApp API]
C --> D[Members]
B --> E[Gym Owner]

---

## System 1 — Revenue Recovery Automation

### Problem
Manual follow-up on expiring memberships led to:
- delayed payments  
- missed revenue  
- inconsistent communication  

### Solution
- Automatically detect:
  - members with 3 days remaining  
  - expired members  
- Send personalized WhatsApp reminders  
- Send summary reports to the owner  

### Flow

flowchart TD
A[Airtable logic] --> B[Expiring members]
A --> C[Expired members]
B --> D[n8n workflow]
C --> D
D --> E[Send WhatsApp reminders]
D --> F[Send owner summary]


### Outcome
- Eliminated manual chasing  
- Significantly improved payment consistency  (30% revenue increase every month)

---

## System 2 — Reactivation Campaign System

### Problem
No structured way to re-engage inactive or expired members.

### Solution
- Built a **webhook-triggered campaign system**
- Each class has a trigger button in Airtable
- Automatically:
  - fetch expired members of that class  
  - send targeted WhatsApp campaigns  

### Flow


### Outcome
- Eliminated manual chasing  
- Significantly improved payment consistency  

---

## System 2 — Reactivation Campaign System

### Problem
No structured way to re-engage inactive or expired members.

### Solution
- Built a **webhook-triggered campaign system**
- Each class has a trigger button in Airtable
- Automatically:
  - fetch expired members of that class  
  - send targeted WhatsApp campaigns  

### Flow


### Outcome
- Enabled fast, segmented marketing campaigns  
- Increased ability to re-engage inactive members  

---

## System 3 — ID-Based Check-in Optimization

### Problem
Check-in process was slow and error-prone:
- coaches asked for full names  
- manual typing during sessions  
- high friction during busy classes  

### Solution
- Designed and implemented a **unique member ID system**
- Built a daily workflow to:
  - detect active members without IDs sent  
  - send IDs automatically via WhatsApp  
  - update records to prevent duplication  

### Flow

flowchart TD
A[Daily trigger] --> B[Fetch active members where idSent = false]
B --> C[Send ID via WhatsApp]
C --> D[Update Airtable]
D --> E[Mark idSent = true]


### Outcome
- Reduced check-in friction significantly  
- Improved session efficiency  
- Saved staff time during peak hours  

---

## Data & System Design

Airtable was used as a **lightweight relational database + logic engine**:

- Membership status tracking  
- Subscription date calculations  
- Formula-driven expiry detection  
- Segmentation by class  
- State tracking (`idSent`) for rollout automation  

n8n orchestrated:
- scheduled workflows  
- filtering and branching logic  
- webhook triggers  
- communication workflows  
- state updates  

---

## Engineering Decisions

This system was designed around real-world constraints:

- Members do not carry phones during sessions → QR solutions not viable  
- Needed fast check-in → implemented numeric ID system  
- High message open rate required → used WhatsApp over SMS  

Focus was placed on:
- adoption  
- simplicity  
- reliability  

---

## What This Demonstrates

- End-to-end system design  
- Workflow automation in production environments  
- Data modeling and state management  
- Event-driven architecture (webhooks + triggers)  
- Business-driven problem solving  
- Ability to deliver measurable impact  

---

## Tech Stack

- n8n  
- Airtable  
- Twilio WhatsApp API  

---

## Notes

Sensitive data (API keys, phone numbers, webhook URLs) has been removed and replaced with placeholders.

---

## Author

Ziad El Marsafawy  
Data Science Student — Cairo University  
Focused on building real-world AI and automation systems

