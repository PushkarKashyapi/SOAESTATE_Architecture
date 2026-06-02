SOAESTATE Desktop Application

Production-grade desktop application built by DaNg in collaboration with Signmozo

Focused on Security • Scalability • Performance • Cost Optimization

Overview

This project was developed as a private desktop application exclusively for Signmozo's internal operations.

The primary goal was to create a secure and efficient platform capable of handling large volumes of design files while maintaining high performance and minimizing storage costs.

Client Requirements
Complete privacy and security
Access restricted to authorized personnel only
Efficient management of design assets and files
Cost-effective storage architecture
Scalable and high-performance system

To achieve these objectives, we built a custom desktop application using ElectronJS and a full-stack architecture.

Problem Statement

The application was heavily data-centric and involved storing a large number of design files, images, and documents.

A straightforward solution would have been storing all files directly in MongoDB. However, this approach would have significantly increased storage costs and impacted overall system efficiency.

The challenge was to design a solution that remained:

Secure
Fast
Scalable
Cost-efficient

while delivering a seamless user experience.

Solution

Instead of storing files directly in MongoDB, we designed a hybrid storage architecture.

Approach
Files are uploaded to Google Drive.
Google Drive stores the actual file.
Drive returns metadata such as:
File ID
Preview Link
Accessible Link
Additional File Information
Only the metadata is stored inside MongoDB.
Files are accessed through Google Drive whenever needed.

This architecture significantly reduced storage costs while maintaining performance and reliability.

System Architecture
┌─────────────────────────────┐
│ Electron Desktop App        │
└─────────────┬───────────────┘
              │
              ▼
┌─────────────────────────────┐
│ Backend API                 │
└─────────────┬───────────────┘
              │
      ┌───────┴────────┐
      │                │
      ▼                ▼

┌─────────────┐   ┌─────────────────┐
│ MongoDB     │   │ Google Drive    │
├─────────────┤   ├─────────────────┤
│ Metadata    │   │ Actual Files    │
│ Links       │   │ Images          │
│ Preview URL │   │ Documents       │
│ Records     │   │ Design Assets   │
└─────────────┘   └─────────────────┘
Technology Stack
Frontend
ElectronJS
HTML
CSS
JavaScript
Backend
Node.js
Express.js
Database
MongoDB
Cloud Storage
Google Drive API
Key Features
Secure Company Access

The application was developed exclusively for Signmozo and is not publicly accessible.

Features include:

Restricted user access
Secure authentication
Private internal data management
Smart File Management

Designed to handle large volumes of design-related assets efficiently.

Capabilities include:

File uploads
File organization
Metadata tracking
File previews
Fast retrieval
Cost-Optimized Storage

Instead of storing large files inside MongoDB:

Files are stored in Google Drive
Only metadata is stored in MongoDB

Benefits:

Reduced storage costs
Faster database operations
Improved scalability
Better performance
Metadata-Based Retrieval

For every uploaded file, the system stores:

File Name
File ID
Preview Link
Accessible Link
Upload Information
Related Records

This allows quick access without storing heavy binary data inside the database.

Workflow
User Uploads File
        │
        ▼
Google Drive Stores File
        │
        ▼
Metadata Generated
        │
        ▼
Metadata Saved in MongoDB
        │
        ▼
Application Fetches Metadata
        │
        ▼
User Accesses File via Drive Link
Project Impact

This project demonstrated how thoughtful architecture decisions can create real business value.

Results
Successfully delivered a production-ready desktop application.
Built a secure platform for internal company operations.
Designed a scalable file management system.
Reduced storage expenses through optimized architecture.
Created a solution capable of serving hundreds of real-world users.
Key Learnings

One of the most valuable lessons from this project was understanding that great software is not just about writing code.

Building production systems requires:

Understanding trade-offs
Choosing the right architecture
Optimizing operational costs
Solving practical business problems

This project reinforced the importance of engineering decisions that balance performance, scalability, security, and cost.

Team

Developed by DaNg in collaboration with Signmozo.

A production-grade desktop application built to deliver secure file management, scalable architecture, and cost-efficient storage solutions.


<img width="992" height="474" alt="Screenshot 2026-06-02 180449" src="https://github.com/user-attachments/assets/27671120-300a-4d31-ab33-80ab8db7d4ed" />
