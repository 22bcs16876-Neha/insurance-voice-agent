# Insurance Conversational AI Voice Agent

An enterprise-oriented **Conversational AI Voice Agent** designed to automate insurance customer service workflows such as authentication, policy management, claims, onboarding, customer updates, and human escalation.

Built using **Google Cloud CX Agent Studio**, Python-based backend services, webhooks, and BigQuery with a modular multi-agent architecture.

---

## 🚀 Overview

Insurance contact centers handle a high volume of repetitive customer requests such as:

- Policy and coverage inquiries
- Claim status tracking
- New claim initiation
- Policy renewals
- Customer information updates
- New customer onboarding
- New policy purchases
- Human support escalation

This project demonstrates how **Conversational AI and agent-based workflows** can automate these interactions while maintaining authentication, contextual conversation handling, backend integration, security guardrails, and human handoff.

---

## 💡 Solution

The Insurance Voice Agent follows a structured conversational workflow:

1. Authenticate the customer
2. Understand the customer's intent
3. Route the request to the appropriate business workflow
4. Retrieve or update information through backend APIs
5. Maintain conversation context
6. Provide a contextual response
7. Escalate to a human agent when required

The architecture supports both **existing customers and new customers** through dedicated workflows.

---

## ✨ Key Capabilities

### 🔐 Customer Authentication

- Mobile number and date of birth verification
- Security question validation
- Authentication retry handling
- Session and context management

### 📋 Policy Management

- Multi-policy support
- Policy details lookup
- Benefits and coverage information
- Policy renewal
- Proactive renewal notifications

### 🏥 Claims Management

- Claim status tracking
- New claim initiation

### 👤 Customer Onboarding

- Insurance product discovery
- Product coverage information
- New customer registration
- New policy purchase

### 📝 Customer Updates

- Customer information update requests
- Request status tracking
- Human approval workflow for sensitive changes

### 🤝 Human Escalation

- Support case creation
- Complete conversation context transfer
- Live agent handoff

---

## 🏗️ Architecture

```text
                         Customer
                            │
                            ▼
               ┌─────────────────────────┐
               │  Insurance Voice Agent  │
               │                         │
               │ Authentication          │
               │ Intent Detection        │
               │ Context Management      │
               │ Intent Routing          │
               └────────────┬────────────┘
                            │
          ┌─────────────────┼─────────────────┐
          │                 │                 │
          ▼                 ▼                 ▼
    Policy Services     Claims           Onboarding
          │                 │                 │
          └─────────────────┼─────────────────┘
                            │
                            ▼
                   Update Requests
                            │
                            ▼
                 Backend Webhook APIs
                            │
                            ▼
                      BigQuery
                            │
                            ▼
                  Human Escalation
