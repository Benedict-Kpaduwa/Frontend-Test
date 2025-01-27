# BankIt Web Application

This is a simple React-based web application that allows users to log in and view their transaction history. The transaction data is fetched from a dummy JSON file located in the `public` folder.

## Features

- **Login Form**: Users can log in using a predefined email and password.
- **Transaction History**: After logging in, users can view a list of transactions.

## Prerequisites

Before running the project, ensure you have the following installed:

- [Node.js](https://nodejs.org/) (v16 or higher)
- [npm](https://www.npmjs.com/) or [Yarn](https://yarnpkg.com/) or [pnpm](https://pnpm.io/)

## Getting Started

### Clone the Repository

```bash
git clone https://github.com/Benedict-Kpaduwa/Frontend-Test.git
cd bankit-app
```

# Questions and Answers


## Section A: General Security and Compliance

### 1. What are the key security considerations when developing financial applications?

Security is a primary concern for financial applications since they handle sensitive data. Important factors include:

- **Data Encryption**: Make sure that any sensitive data, such as transaction details and passwords, is encrypted both at rest (using AES-256 or a comparable protocol) and in transit (using HTTPS/TLS).
- **Authentication and Authorization**:To limit access to sensitive functionality, use role-based/permission-based access control (RBAC/PBAC) and robust authentication techniques (such as multi-factor authentication).
- **Input Validation**: Verify and clean every user input to stop injection attacks (such as XSS and SQL injection).
- **Secure APIs**: To stop abuse, secure APIs and implement rate limits using JWT tokens, OAuth, or API keys.
- **Audit Logging**: Keep thorough records of all user transactions and activity for auditing and troubleshooting purposes.
- **Regular Security Audits**: To find and address security flaws, do vulnerability assessments and penetration tests.

---

### 2. Describe the importance of compliance standards such as PCI-DSS and GDPR in financial applications.

- **PCI-DSS (Payment Card Industry Data Security Standard)**:
  - Ensures secure handling of credit card information.
  - Requires encryption of cardholder data, regular security testing, and access control measures.
  - Non-compliance can result in hefty fines and loss of customer trust.

- **GDPR (General Data Protection Regulation)**:
  - Protects the personal data of EU citizens.
  - demands clear user consent before collecting data, notifying users of data breaches, and granting them the right to have their data deleted.
  - Non-compliance can lead to fines of up to 4% of global annual turnover.

Maintaining legal operations, gaining the trust of clients, and avoiding fines all depend on adherence to these norms.

---

### 3. Explain the concept of "idempotency" in financial transactions and why it's crucial.

- **Idempotency** indicates that carrying out the same action repeatedly yields the same outcome free of unexpected consequences.
- In financial applications, idempotency ensures that:
  - Duplicate transactions (e.g., due to network retries) do not result in multiple charges.
  - APIs can safely retry failed requests without causing duplicate payments or transfers.
- Example: If a user initiates a N100 transfer, retrying the request should not result in multiple N100 transfers.

---

### 4. What are the potential risks of handling sensitive customer data, and how can they be mitigated?

- **Risks**:
  - Data breaches leading to financial loss and reputational damage.
  - Unauthorized access to customer accounts.
  - Non-compliance with regulations like GDPR and PCI-DSS.
- **Mitigation Strategies**:
  - Encrypt sensitive data when at rest and in transit.
  - Implement strong authentication and authorization mechanisms.
  - Regularly update and patch software to fix vulnerabilities.
  - Conduct employee training on data security best practices.
  - Use secure third-party services and libraries.

---

## Section B: Frontend Development

### 1. How would you ensure the UI/UX of a banking web application is both user-friendly and secure?

- **User-Friendly Design**:
  - Use a clean, intuitive layout with clear navigation.
  - Provide helpful tooltips, error messages, and instructions.
  - Ensure the application is mobile-responsive and accessible.
- **Security Measures**:
  - Implement form validation to prevent invalid inputs.
  - Use data masking for sensitive fields (e.g., credit card numbers).
  - Display security badges and SSL certificates to build trust.
  - Log users out after a period of inactivity.

---

### 2. Explain the role of form validation and data masking in financial applications.

- **Form Validation**:
  - Ensures that user inputs are correct and complete before submission.
  - Prevents invalid or malicious data from being processed (e.g., SQL injection, XSS).
  - Example: Validate email format, password strength, and numeric fields.
- **Data Masking**:
  - Protects sensitive information by displaying only partial data (e.g., `**** **** **** 1234`).
  - Reduces the risk of data exposure if the screen is viewed by unauthorized individuals.

---

### 3. Discuss strategies for handling real-time data updates (e.g., account balance changes) in a React application.

- **WebSockets**: Use WebSockets for real-time, bidirectional communication between the client and server.
- **Server-Sent Events (SSE)**: Use SSE for one-way real-time updates from the server to the client.
- **Polling**: Periodically fetch updates from the server (tho it is less efficient than WebSockets or SSE).
- **State Management**: Use React state management libraries like Redux or Context API to manage and update the UI in real time.
- Example: The user interface re-renders to reflect the updated account balance after the server notifies the client of the change.

---

### 4. What are Progressive Web Apps (PWAs), and how can they benefit a financial institution?

- **Progressive Web Apps (PWAs)**:
  - Web applications that provide a native app-like experience.
  - Features include offline functionality, push notifications, and fast loading times.
- **Benefits for Financial Institutions**:
  - Improved user engagement through push notifications (e.g., transaction alerts).
  - Offline access to key features (e.g., viewing account balances).
  - lower development expenses as opposed to keeping up individual native apps.
  - Enhanced performance and reliability, leading to better customer satisfaction.
