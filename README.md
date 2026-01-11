# GitHub

GitHub is a cloud-based platform where you can store, share, and work together with others to write code.

Storing your code in a "repository" on GitHub allows you to:

- Showcase or share your work.
- Track and manage changes to your code over time.
- Let others review your code, and make suggestions to improve it.

### Git

Git is a powerful tool for tracking changes in your code, coordinating work among multiple developers, and allowing you to revert to previous versions of your project if needed.

- Repository (Repo): A folder where Git tracks your project and its history. It contains all your project files and a hidden .git directory with metadata.

- Commit: A "snapshot" of your project's staged changes at a specific point in time. Each commit has a unique identifier (hash code) and a descriptive message.

- Branch: A lightweight, movable pointer to a commit. Branches allow you to isolate development work for a new feature or bug fix without affecting the main codebase (usually the main or master branch).

- Staging Area (Index): A middle ground between your working directory (where you edit files) and your repository. You use this area to prepare a set of changes to be included in the next commit. 

### Git Commands 

- `git status`: Shows the status of changes as untracked, modified, or staged.
- `git add <filename>`: Stages a specific file for the next commit. Use git add . to stage all modified files.
- `git commit -m "message"`: Records the staged snapshot permanently in the repository with a descriptive message.
- `git branch <branchname>`: Creates a new branch.

### Github Concepts

- Clone: To download a copy of a remote repository to your local machine.
- Push: To send your local commits to the remote repository on GitHub.
- Pull: To fetch the latest changes from the remote repository and merge them into your local branch.
- Pull Request (PR): A mechanism to propose changes from your branch to the main branch of a repository. It allows collaborators to review the code before merging


# Mulesoft

## Integration Patterns

### Migration

This pattern involves moving a large volume of data from a source system to a destination system at a specific point in time.

### Bi-directional Synchronization

This pattern combines two datasets in different systems so they behave as a single, consistent logical dataset, allowing changes in either system to be reflected in the other.

### Broadcast
Data flows from a single source system to one or many destination systems.This ensures that data across multiple systems stays up-to-date.

### Correlation

 It only synchronizes data for items that already exist in both systems (the intersection of the datasets). 

### Aggregation

This pattern involves querying data from multiple systems on demand, merging or processing that data, and presenting it as a single, consolidated response or report. The data is not replicated to a separate database.


## Fire-and-Forget (Asynchronous Communication)

The Fire-and-Forget pattern (also known as one-way messaging) is an asynchronous communication model where the sender sends a message or invokes a service without waiting for any confirmation or response.


## Request-Response (Synchronous Communication)

The Request-Response pattern is a synchronous communication model where the sender of a message waits for a reply from the receiver before proceeding with its own subsequent actions.

### HTTP/HTTPS

The client (browser, application, API gateway) opens a connection, sends a request line, headers, and an optional body, and then waits for the server to send back a status code, headers, and a response body.

### WebSockets

WebSockets upgrade the connection to a persistent, bi-directional channel, often used when continuous, low-latency communication is needed after the initial request.


## Monolith Architecture

A monolith or monolithic architecture is a traditional, unified approach to software design where an application is developed as a single, cohesive, and indivisible unit. 

In a monolithic application, all components—including the user interface, business logic, and data access layers—are part of a single, large codebase and are deployed together as a single package

## Microservices

Microservices is an architectural style that structures an application as a collection of small, independent, and loosely coupled services. 

Each service is self-contained, focusing on a single business capability, and can be developed, deployed, scaled, and maintained independently of the others. These services communicate with each other over a network, typically using lightweight protocols like HTTP/HTTPS with JSON or gRPC.

## API (Application Programming Interface)

An API (Application Programming Interface) is a set of rules, definitions, and protocols that allows different software applications to communicate with each other.

APIs are the building blocks of modern software and integration, enabling modularity and connectivity between services.

## Three Layered Architecture in Mulesoft 

The Three Layer Architecture is a specific implementation strategy used to organize APIs and integrations based on their function and proximity to source systems or user interfaces.

### System API Layer

This is the foundational layer. System APIs sit closest to the underlying systems of record (SoRs), such as databases (SAP, Oracle, Salesforce), legacy systems, and mainframes.

Example: A "Salesforce System API" that provides basic CRUD (Create, Read, Update, Delete) operations for Contact objects in Salesforce.

### Process API Layer

Process APIs consume data from multiple System APIs, orchestrate their interactions, apply business rules, and enrich the data as needed.

Example: A "Customer Onboarding Process API" that orchestrates calls to the "Salesforce System API," an "ERP System API" (for finance setup), and a "Notification System API" to ensure a new customer is provisioned correctly across all relevant systems.

### Experience API Layer

Experience APIs remix and format data specifically for the intended consumer (web portal, mobile app, partner application, etc.).

Example: A "Mobile App Experience API" that calls the "Customer Onboarding Process API" but formats the response specifically for the mobile UI, displaying a subset of data relevant to a phone screen.


