# Serverless Event Announcement Platform

A serverless event notification system that allows users to subscribe to event updates and receive automated email notifications when new events are created.

This project demonstrates how to design an event-driven application using managed AWS services while avoiding server management.

---

## Architecture Overview

The application uses a fully serverless architecture to handle user subscriptions and event announcements.

Frontend assets are hosted on Amazon S3 as a static website. Users interact with the backend through REST endpoints provided by Amazon API Gateway. These endpoints invoke AWS Lambda functions that manage subscriptions and publish events.

When a new event is created, the system updates the events storage file in S3 and publishes a notification through Amazon SNS, which sends email alerts to subscribed users.

### Key Services

- Amazon S3 – Static website hosting and event data storage
- Amazon SNS – Email notification delivery
- AWS Lambda – Backend processing for subscriptions and event creation
- Amazon API Gateway – REST API interface
- IAM – Access control between AWS services

---

## System Workflow

1. Users visit the static website hosted on S3.
2. Users submit email subscriptions or event creation requests through web forms.
3. API Gateway routes the request to the appropriate Lambda function.
4. The Lambda function processes the request:
   - Subscribes the user to the SNS topic
   - Stores new event data in the S3 events file
5. SNS distributes email notifications to all subscribers.

---

## Key Features

- Fully serverless architecture
- Email-based event notifications
- Simple event management interface
- API-driven backend services
- Scalable and cost-efficient design

---

## Architecture Diagram

<p align="center">
  <img src="https://i.gyazo.com/071f93db4eb0e3e1c36c3b710ee76692.png" alt="Diagram" width="700">
  <br>
  <sub>Figure 1: Architecture Diagram</sub>
</p>

---

## Repository Structure

```bash
frontend/
index.html
styles.css
events.json

lambda/
subscribe-function/
create-event-function/

api/
api-gateway-config
```

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

## Skills Demonstrated

- Serverless architecture design
- API development with API Gateway
- Event-driven workflows
- AWS service integration
