# 📸 AWS Serverless Image Processing Pipeline

A fully serverless, event-driven image processing pipeline built using AWS services.

The project automatically processes uploaded images, resizes them, applies a watermark, stores image metadata, and sends a completion notification.

---

# Architecture

<img width="1536" height="1024" alt="Architecture Diagram" src="https://github.com/user-attachments/assets/a4a03936-3ee8-4829-b140-e029d6128c25" />

---

# Project Overview

This project demonstrates how to build a fully serverless image processing system using AWS managed services.

Whenever an image is uploaded to the source S3 bucket:

1. Amazon S3 publishes an event.
2. The event is delivered to Amazon SQS.
3. SQS triggers a Lambda function.
4. The Lambda function starts an AWS Step Functions workflow.
5. Images are resized.
6. A watermark is added.
7. Image metadata is stored in DynamoDB.
8. Amazon SNS sends a completion notification.

The project follows an event-driven architecture that is scalable, loosely coupled, and highly available.

---

# AWS Services Used

| Service | Purpose |
|----------|----------|
| Amazon S3 | Store original and processed images |
| Amazon SQS | Queue image processing requests |
| Dead Letter Queue | Store failed processing events |
| AWS Lambda | Execute image processing logic |
| AWS Step Functions | Orchestrate the workflow |
| Amazon DynamoDB | Store image metadata |
| Amazon SNS | Send completion notifications |
| CloudWatch | Logging and monitoring |
| Lambda Layers | Package the Pillow image library |

---

# Workflow

```
Upload Image
      │
      ▼
Amazon S3
      │
      ▼
Amazon SQS
      │
      ▼
StartImageWorkflow
      │
      ▼
AWS Step Functions
      │
      ▼
ResizeImage
      │
      ▼
WatermarkImage
      │
      ▼
SaveImageMetadata
      │
      ▼
Amazon DynamoDB
      │
      ▼
Amazon SNS
```



# Features

- Event-driven architecture
- Serverless processing
- Automatic image resizing
- Automatic watermarking
- Metadata storage
- Email notifications
- Dead Letter Queue support
- Step Functions orchestration
- CloudWatch monitoring

---

# DynamoDB Metadata

Each processed image stores:

- Image ID
- File Name
- Upload Time
- Original Dimensions
- Processed Dimensions
- Image Format
- Processing Status
- Source Bucket
- Destination Bucket
- Object Keys

---

# Notifications

When processing finishes successfully, Amazon SNS sends an email notification containing:

- File name
- Processing status
- Processed object key

---

# Scalability

The architecture is designed using AWS managed services, allowing automatic scaling without provisioning servers.

Benefits include:

- High availability
- Loose coupling
- Fault tolerance
- Event-driven processing
- Pay-per-use pricing

---


# 📸 Screenshots

- AWS Step Functions
  <img width="1919" height="859" alt="Step Function Workflow + Code" src="https://github.com/user-attachments/assets/102b2ebd-91db-41d9-a395-1946dd3d8a80" />

- Lambda Functions
  <img width="1919" height="865" alt="Lambda Functions" src="https://github.com/user-attachments/assets/0dc15935-077d-4a3d-a407-60e33925c97a" />

- DynamoDB Table
  <img width="1919" height="826" alt="DynamoDB Table" src="https://github.com/user-attachments/assets/07cce073-1abe-4080-896d-b434ed2a0b51" />

- S3 Buckets
  <img width="1919" height="820" alt="S3 Source Bucket" src="https://github.com/user-attachments/assets/0b0c370c-f874-4a24-b87a-86bbbed5cf32" />
  <img width="1913" height="858" alt="Destination Bucket" src="https://github.com/user-attachments/assets/0c27aa11-feaf-499c-a08c-e51ad5a58d83" />


- SNS Email
  <img width="1915" height="908" alt="Email Notification" src="https://github.com/user-attachments/assets/541b1afe-6385-460c-a93d-e2ea865ce583" />

- CloudWatch Logs
  <img width="1919" height="863" alt="CloudWatch Logs" src="https://github.com/user-attachments/assets/891fa7b1-e9a5-4dc2-bc3b-1b6c2e9ff14c" />


---

# Author

**Ahmed Ehab**

Computer Science Graduate | Junior Data Engineer | AWS Cloud Practitioner

---

# Connect with Me

🔗 **LinkedIn:**  
[https://www.linkedin.com/in/YOUR-LINKEDIN-USERNAME/](https://www.linkedin.com/in/ahmed-ehab-73635624a/)
