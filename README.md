# Serverless Event Announcement Platform

A serverless event notification system that allows users to subscribe to event updates and receive automated email notifications when new events are created.

This project demonstrates how to design an event-driven application using managed AWS services while avoiding server management.

---

## Architecture Overview

The application uses a fully serverless architecture to handle user subscriptions and event announcements.

Frontend assets are hosted on Amazon S3 as a static website. Users interact with the backend through REST endpoints provided by Amazon API Gateway. These endpoints invoke AWS Lambda functions that manage subscriptions and publish events.

When a new event is created, the system updates the events storage file in S3 and publishes a notification through Amazon SNS, which sends email alerts to subscribed users.

---

## Architecture Diagram

<p align="center">
  <img src="https://i.gyazo.com/071f93db4eb0e3e1c36c3b710ee76692.png" alt="Diagram" width="700">
  <br>
  <sub>Figure 1: Architecture Diagram</sub>
</p>

---

### Key Services

- Amazon S3 – Static website hosting and event data storage
- Amazon SNS – Email notification delivery
- AWS Lambda – Backend processing for subscriptions and event creation
- Amazon API Gateway – REST API interface
- IAM – Access control between AWS services

---

## Workflow

```text
User opens event website
        ↓
Frontend hosted on S3
        ↓
User submits subscription or new event
        ↓
API Gateway receives request
        ↓
Lambda processes request
        ↓
SNS updates subscribers or sends notifications
        ↓
Event data stored in S3 JSON file
```

---

## Key AWS Configuration

Example configuration screenshots from the infrastructure.

<p align="center">
  <img src="https://i.gyazo.com/96adfca2f4dc09add01d1c67ae457815.png" alt="SNS Topic Configuration" width="700">
  <br>
  <sub>Figure 2: SNS Topic Configuration</sub>
</p>

<p align="center">
  <img src="https://i.gyazo.com/aeb6668b4c236b9fa48304077a461e4a.png" alt="API Gateway Endpoint" width="700">
  <br>
  <sub>Figure 3: API Gateway Endpoint</sub>
</p>

---

## Application Interface

Example of the event listing interface and subscription functionality.

<p align="center">
  <img src="https://i.gyazo.com/a5335804c11b0381c1b3dc9e2f32cebc.png" alt="Event Website Interface" width="700">
  <br>
  <sub>Figure 4: Event Website Interface</sub>
</p>

<p align="center">
  <img src="https://i.gyazo.com/407db8ca96936fa0e7d092996b1b755f.png" alt="Successful Event Creation" width="700">
  <br>
  <sub>Figure 5: Successful Event Creation</sub>
</p>

<p align="center">
  <img src="https://i.gyazo.com/af81acb96ca383e5eef9959c0cfd153f.png" alt="Email Delivery" width="700">
  <br>
  <sub>Figure 6: Email Delivery</sub>
</p>

---

## Key Features

- Fully serverless architecture
- Email-based event notifications
- Simple event management interface
- API-driven backend services
- Scalable and cost-efficient design

---

## Design Considerations

**Serverless Design** <br>
The application avoids traditional infrastructure by relying entirely on managed services.

**Scalability**<br>
Using SNS and Lambda ensures the system scales automatically as event subscriptions increase.

**Cost Efficiency**<br>
Serverless services reduce operational costs because resources only run when needed.

---

## Future Improvements

- Replace JSON storage with a DynamoDB database
- Add authentication for event creation
- Implement event categories and filtering
- Add subscription management for users

---
