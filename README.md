# 🍽️ AI-Powered WhatsApp Food Ordering System

An end-to-end **AI-driven restaurant automation system** built with **n8n, Google Gemini, WhatsApp Cloud API, and Google Sheets**.
This project enables customers to place food orders, check stock, view FAQs, and track order status directly via WhatsApp in a conversational, food-delivery app style experience.

---

## 🚀 Features

* 🤖 AI-powered WhatsApp chatbot
* 🛒 Step-by-step food ordering flow
* 📦 Real-time inventory validation
* 📊 Automated order logging with status tracking
* ℹ️ FAQ handling (delivery time, payment, timings)
* 🔍 Order & stock checking
* 🧠 Context-aware conversation memory
* 📁 Google Sheets as database (Inventory, Orders, FAQ)

---

## 🏗️ System Architecture

**Workflow Built in n8n**

1. **WhatsApp Trigger**

   * Receives incoming user messages.

2. **AI Agent (LangChain Agent Node)**

   * Uses Google Gemini as LLM.
   * Follows structured system rules.
   * Handles conversation logic.

3. **Memory Buffer**

   * Maintains last 15 conversation messages.
   * Session tracked via WhatsApp number.

4. **Google Sheets Tools**

   * `Inventory Sheet` → Check stock availability
   * `FAQ Sheet` → Answer common questions
   * `Orders Sheet` → Append confirmed/rejected orders

5. **WhatsApp Send Node**

   * Sends AI-generated response back to user.

---

## 🧠 How It Works

### 1️⃣ Greeting

When a user says “Hi” or “Hello”:

```
Welcome to XYZ Restaurant 🍽️
How can I help you today?
- 🛒 Place an order
- ℹ️ FAQ / Information
- 📦 Check order / stock
```

---

### 2️⃣ Order Flow

AI collects:

* Customer Name
* Food Item
* Quantity

Then:

* Checks Inventory Sheet
* If available → Confirms order ✅
* If not available → Suggests available items ❌

Orders are stored in Google Sheets with:

* Customer Name
* Food Item
* Quantity
* Order Date
* Status (Confirmed / Rejected)
* Description

---

### 3️⃣ FAQ Handling

Answers short, structured responses from the FAQ sheet:

* Delivery time
* Payment methods
* Restaurant hours

---

### 4️⃣ Order Tracking

User can:

* Check order status (Confirmed / Rejected / Delivered / Cancelled)
* Check stock quantity
* View available items

---

### 5️⃣ Cancel Order

AI replies:

```
Sorry 🙏 I cannot cancel orders directly.
Please call the restaurant owner first.
Owner Contact: +95 1224567890
```

---

## 🛠️ Tech Stack

* **Automation Platform:** n8n
* **LLM:** Google Gemini (PaLM API)
* **Messaging API:** WhatsApp Cloud API
* **Database:** Google Sheets
* **Memory Handling:** LangChain Memory Buffer

---

## 📂 Google Sheets Structure

### Inventory Sheet

| Food Item | Quantity Available |
| --------- | ------------------ |

### Orders Sheet

| Customer Name | Food Item | Quantity Ordered | Order Date | Status |

### FAQ Sheet

| Question | Answer |

---

## 🔧 Setup Instructions

### 1️⃣ Clone Repository

```bash
git clone https://github.com/your-username/whatsapp-food-ai.git
cd whatsapp-food-ai
```

### 2️⃣ Import Workflow in n8n

* Open n8n
* Import the provided workflow JSON file
* Configure credentials

---

### 3️⃣ Configure Credentials

You must connect:

* WhatsApp Cloud API
* Google Sheets OAuth2
* Google Gemini API Key

---

### 4️⃣ Update Sheet IDs

Replace:

```
documentId: YOUR_GOOGLE_SHEET_ID
```

With your own Google Sheet document ID.

---

### 5️⃣ Activate Workflow

* Turn workflow ON
* Send a test message from WhatsApp

---

## 🔐 Environment Variables (Recommended)

Store API keys securely:

* `GOOGLE_GEMINI_API_KEY`
* `WHATSAPP_ACCESS_TOKEN`
* `GOOGLE_SHEETS_OAUTH`

---

## 📈 Future Improvements

* Razorpay / Stripe integration
* Auto order cancellation feature
* Admin dashboard
* Delivery tracking system
* Multi-restaurant support
* Voice-based ordering

---

## 🧪 Testing

Test scenarios:

* Greeting flow
* Valid order (in stock)
* Invalid order (out of stock)
* FAQ query
* Check stock
* Check order status
* Cancel order attempt

---

## 🎯 Use Case

This system is ideal for:

* Small restaurants
* Cloud kitchens
* Local food businesses
* Demo AI automation projects
* Portfolio projects (AI + Automation + WhatsApp)

---

## 📜 License

MIT License

---

## 👨‍💻 Author

Developed as an AI Automation Project using n8n + Google Gemini + WhatsApp.
----------------------------developed by nikhil soni-----------------------
