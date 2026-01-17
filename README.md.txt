#  AI LinkedIn Outreach Agent

**Scrape Leads → AI Personalization → Automated LinkedIn Invitations**

This project is an end-to-end LinkedIn outreach automation built with **n8n**, **Apify**, **OpenAI**, and **PhantomBuster**.

It automatically:
- Scrapes targeted LinkedIn leads
- Writes **unique, context-aware** connection messages using AI
- Sends personalized LinkedIn invitations at human-like speeds

No templates. No copy-paste. No manual work.

---

##  Video Walkthrough

![Video Demo](https://somup.com/cOVbDrSxHW)

A short walkthrough showing:
- The n8n workflow execution  
- AI-generated messages  
- Automated LinkedIn invitations being sent  

---

##  Workflow Overview

### 1️Data Sourcing (Apify)
Targeted LinkedIn profiles are scraped using an Apify actor with filters such as:
- Industry
- Country
- Role / Job title

![Apify Runs](screenshots/apify_runs.png)

---

### 2️ Automation Logic (n8n)
n8n orchestrates the entire pipeline:
- API calls to Apify and OpenAI
- Prompt logic and validation
- Data transformation and routing

This is the “brain” of the system.

![n8n Workflow](screenshots/n8n_workflow.png)

---

### 3️ AI-Generated Dataset (Google Sheets)
All processed leads are logged into Google Sheets, which acts as a live database between systems.

Each row contains:
- Lead details
- A **fully personalized LinkedIn message**
- Message length capped at **280 characters**

No two messages are the same.

![Google Sheets](screenshots/Google_sheets.png)

---

### 4️ Automated Execution (PhantomBuster)
PhantomBuster consumes the Google Sheet and runs the **LinkedIn Network Booster** to send connection requests.

Human-like behavior is enforced using:
- Randomized delays
- Typing simulation
- Daily safety limits

![PhantomBuster UI](screenshots/phantombuster_ui.png)

---

### 5️ Final Result (LinkedIn)
A real, personalized connection request delivered directly to a lead’s LinkedIn inbox.

![LinkedIn Proof](screenshots/linkedin_proof.png)

---

##  Key Features

- **Dynamic Scraping**  
  Filter leads by industry, location, and role using Apify.

- **Context-Aware AI Personalization**  
  OpenAI analyzes each profile’s bio, role, and company to generate a message that feels written by a human — not a bot.

- **Platform-Safe Automation**  
  PhantomBuster mimics natural user behavior to reduce the risk of LinkedIn restrictions.

- **Zero Manual Data Entry**  
  Google Sheets acts as the live bridge between scraping, AI generation, and outreach.

- **Fully Modular**  
  Swap PhantomBuster for email, WhatsApp, or CRM integrations without changing the core logic.

---

##  How the AI Writes the Messages

The OpenAI node is configured with a **System Prompt** acting as a *Professional Networking Expert*.

The AI is instructed to:
- Be friendly, natural, and concise
- Mention the lead’s **specific role or company**
- Stay under **280 characters**
- Avoid salesy or spam-like language

Fallback logic ensures usable output even when profile data is minimal.

---

##  Setup Instructions

### Prerequisites
- n8n (v1.0+)
- Apify API Token (LinkedIn Lead Scraper actor)
- OpenAI API Key
- Google Sheets (shared access)
- PhantomBuster API Key (LinkedIn Network Booster Phantom)

---

### Configuration Steps

1. **Import Workflow**  
   Import `LinkedIn_agent.json` into your n8n canvas.

2. **Update Credentials**  
   Configure credentials for:
   - OpenAI  
   - Google Sheets  
   - PhantomBuster  

3. **Apify Node**  
   Edit the JSON input to change:
   - Target industry  
   - Country  
   - Role  
   *(Default: Computer Software — Kenya / India)*

4. **PhantomBuster Node**  
   Insert your Phantom ID from the PhantomBuster dashboard.

---

##  Results (Example Test Run)

- 200 connection requests sent  
- ~30% acceptance rate  
- Multiple replies within 48 hours  

*(Results vary based on targeting, profile quality, and daily limits.)*

---

##  Roadmap / Ideas

- Reply classification (Interested / Neutral / Ignore)
- Automated follow-ups after X days
- CRM integrations (Notion, HubSpot)
- Prompt A/B testing
- Lead scoring & prioritization
- Multi-channel outreach (Email, WhatsApp)

---

##  Contributing

Ideas, improvements, and pull requests are welcome.  
Open an issue or fork the repo and build on it.

---

##  License

MIT License
