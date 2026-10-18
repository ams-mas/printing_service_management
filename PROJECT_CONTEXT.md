# Printing Service Management System

## 1. Project Overview

The Printing Service Management System is a web-based application designed for printing shops, printing presses, and printing service companies.

Its purpose is to help printing businesses manage customer orders, organize production activities, track order progress, and ensure customers receive their finished products.

The system will be developed in stages. The initial stage focuses on customer orders and order tracking. Additional features and services can be introduced as the project grows.

## 2. Main Objectives

The system should:

- Allow customers to submit printing orders online.
- Allow authorized staff to enter orders manually for walk-in customers or customers who contact the shop directly.
- Track every order from submission to final delivery.
- Show the current status of each order.
- Help staff organize and manage printing work.
- Keep customer, order, and production information organized.
- Reduce mistakes, delays, and lost orders.
- Provide a foundation for adding more printing services and business features.

## 3. Initial Printing Services

The initial product categories are:

1. Printing papers and documents.
2. Booklets and brochures.
3. Stamps.
4. Photos and photo printing.
5. Banners and large-format printing.

The system should allow administrators to introduce new product categories in the future without rebuilding the entire application.

Different products may require different order details, such as dimensions, paper type, quantity, color, finishing options, uploaded designs, and special instructions. Make these details configurable or extendable where practical.

## 4. Proposed Order Workflow

Each order should move through a clear workflow:

1. **Order Received** — A customer submits an order online or staff enters it manually.
2. **Order Review** — Staff reviews requirements, files, quantities, and specifications.
3. **Quotation and Approval** — Price is calculated or quoted, and customer approval is recorded when required.
4. **Confirmed** — The order is approved for production.
5. **In Production** — The printing shop works on the order.
6. **Quality Check** — Finished products are checked for quality and accuracy.
7. **Ready for Pickup or Delivery** — The order is ready to be handed over or dispatched.
8. **Out for Delivery** — The order is on its way to the customer, when applicable.
9. **Completed** — Receipt by the customer or pickup is confirmed.

Support exception statuses where appropriate, such as Cancelled, On Hold, or Awaiting Customer Approval. The workflow may vary by product or service.

## 5. Customer Management

Maintain customer records with relevant information, such as:

- Customer name or business name.
- Contact information.
- Order history.
- Special instructions or preferences.
- Billing and delivery information when needed.

Staff should be able to search for customers and view their current and previous orders.

## 6. Order Tracking

Each order should have a unique order number. Authorized users should be able to:

- View orders and their current statuses.
- Search by order number, customer, product, or status.
- View order details and specifications.
- Record progress updates.
- Record important dates and responsible staff members.
- Track expected completion dates and actual delivery.
- Identify delayed orders.
- Maintain a history of status changes.

Customers should eventually be able to check their own order status through a secure tracking page without accessing internal business information.

## 7. Proposed User Roles

Use role-based access control. Potential roles include:

- **Administrator:** Manages system settings, users, services, and permissions.
- **Order Management Staff:** Creates orders, manages customer information, and updates order details.
- **Production Staff:** Views assigned work and updates production progress.
- **Delivery or Dispatch Staff:** Manages dispatch and delivery information.
- **Customer:** Submits orders, views their own orders, and tracks progress.

The first release may start with fewer roles, but the architecture should allow additional roles later.

## 8. Future Expansion

Potential future features include:

- Online quotations and pricing calculators.
- Customer file uploads and artwork approval.
- Online payments, invoices, and deposits.
- Payment balance tracking.
- Email, SMS, or messaging notifications.
- Delivery management.
- Production scheduling and workload management.
- Inventory and material tracking.
- Reports and business analytics.
- Repeat orders and saved customer preferences.
- Additional printing products and specialized workflows.

These are future possibilities, not mandatory requirements for the first release.

## 9. Development Principles

ChatGPT and any developer working on this project should:

1. Inspect the existing repository and understand its architecture before changing code.
2. Build incrementally, one feature at a time.
3. Prioritize a reliable order management and tracking workflow.
4. Keep the interface simple, professional, and easy for printing shop employees to use.
5. Make the application responsive for desktop, tablet, and mobile devices.
6. Use a maintainable architecture that supports future product categories and features.
7. Validate input and enforce appropriate security controls.
8. Protect customer information, uploaded files, and business records.
9. Use role-based permissions and record important order changes.
10. Avoid unnecessary complexity and dependencies.
11. Preserve existing working features when implementing changes.
12. Never delete production data, overwrite important configuration, or run destructive database changes without explicit authorization and appropriate backups.
13. Test new features and check for regressions before considering them complete.
14. Document significant changes, installation requirements, database migrations, and configuration updates.
15. Distinguish between implemented functionality, agreed requirements, proposed features, and future possibilities.
16. Ask questions when an important business rule is unclear; do not silently invent requirements.

## 10. Suggested Development Roadmap

### Stage 1 — Core Order Management
- Basic application structure and authentication.
- Customer records.
- Printing product categories.
- Manual order entry.
- Unique order numbers.
- Order status management.
- Order history and search.
- Basic dashboard.

### Stage 2 — Customer Ordering and Tracking
- Customer accounts or secure guest ordering.
- Online order submission.
- File uploads and printing specifications.
- Customer order tracking.
- Notifications for important status changes.

### Stage 3 — Production and Delivery
- Production work queues.
- Staff assignments.
- Quality control.
- Pickup and delivery tracking.
- Expected completion dates and overdue-order alerts.

### Stage 4 — Business Management
- Quotations and pricing.
- Invoices and payments.
- Reports and analytics.
- Inventory and material management.

This roadmap is flexible and should be updated as requirements become clearer.

## 11. Instructions for ChatGPT

Treat this document as the initial source of truth for the project's business purpose and intended direction.

Before implementing a feature, explain how it supports the printing service business when that is not obvious. Inspect relevant code and database structures before making changes. Do not claim a feature exists until it has been verified in the repository.

When the owner requests a change, explain significant risks, implement the requested change, and test it where possible. Keep the initial release focused while avoiding design decisions that unnecessarily prevent future expansion.

## 12. Long-Term Vision

Build a dependable printing service platform that helps printing businesses receive orders, manage production, communicate progress, and deliver the correct products to customers on time.

The initial release should solve the core order management problem well. Future features will be introduced according to actual business needs and priorities.

## 13. Required Programming Stack and Architecture

Use the following stack as the default for this project unless the owner explicitly approves a change:

- **Backend:** PHP, using a currently supported PHP release compatible with the deployment host.
- **Database:** MySQL or MariaDB with InnoDB tables, foreign keys, indexes, and transactions where appropriate.
- **Frontend:** HTML5, CSS3, JavaScript, and jQuery.
- **UI framework:** Bootstrap 5 for responsive layouts, forms, navigation, tables, and dashboards.
- **Dependency management:** Composer for PHP libraries.
- **Web server:** Apache for local development and compatible production hosting.
- **Version control:** Git and GitHub.

Develop locally with XAMPP if useful, but configure the production environment separately and securely. The application must be deployable to an online PHP host or VPS. Do not expose a development XAMPP server directly to the public internet.

Prefer a clear, modular PHP application structure with separation between presentation, business logic, and database access. Use PDO with prepared statements for database queries. Consider Laravel if the owner approves adopting a framework; otherwise, plain PHP is acceptable when implemented with disciplined structure and security controls. Do not introduce React, Vue, Node.js, microservices, Docker, or Kubernetes unless a concrete requirement justifies the added complexity and the owner approves.

Use Composer-managed, maintained libraries when useful, such as a suitable PHP PDF library for receipts, quotations, invoices, and production job sheets. Review a library's maintenance status, compatibility, license, and security before adding it. Avoid unnecessary dependencies and do not hardcode secrets or credentials in source control.

## 14. Mandatory Security and Data Protection Rules

Security must be considered in every feature from the beginning, not added only before deployment.

1. **SQL injection:** Use PDO prepared statements for all variable database values. Do not build SQL queries by concatenating untrusted input.
2. **Passwords:** Store passwords only using PHP's `password_hash()` and verify them with `password_verify()`. Never store plaintext passwords or reversible password values.
3. **Authentication and sessions:** Use secure session configuration, regenerate session IDs after login or privilege changes, enforce idle/session expiration where appropriate, and protect login forms against brute-force attempts with rate limiting and safe error messages.
4. **Authorization:** Enforce role-based permissions on the server for every protected operation. Hiding a button in the interface is not authorization. Customers must only access their own orders and files.
5. **CSRF:** Protect state-changing browser requests with validated CSRF tokens.
6. **XSS and output encoding:** Escape output according to its context. Do not trust customer names, order notes, uploaded filenames, or other user-controlled content as HTML or JavaScript.
7. **Input validation:** Validate and normalize all data on the server, including order specifications, quantities, prices, IDs, file metadata, and status transitions. Client-side validation is only a convenience.
8. **File uploads:** Allow only necessary file types and reasonable size limits; validate content rather than trusting extensions or browser MIME types; generate safe server-side filenames; prevent executable uploads; store files outside the public web root where practical; enforce access checks on downloads; and consider malware scanning.
9. **Transport security:** Use HTTPS/TLS in production, redirect HTTP to HTTPS, and configure secure cookies and appropriate security headers.
10. **Secrets and configuration:** Keep database passwords, API keys, and other secrets outside tracked source files, using environment variables or protected server configuration. Provide a safe example configuration without real credentials.
11. **Database integrity:** Use foreign keys, constraints, transactions, and appropriate indexes. Apply schema changes through reviewed, documented migrations or update scripts. Back up data before destructive changes.
12. **Backups and recovery:** Establish automated backups, protect backup access, and periodically test restoration.
13. **Audit trail:** Record important actions such as order status changes, price/payment changes, administrative actions, and relevant access events. Include actor, time, and affected record; do not log passwords, session tokens, or unnecessary sensitive data.
14. **Errors and logging:** Show users safe error messages; keep technical details in protected logs. Never display stack traces, SQL errors, secrets, or internal paths to public users.
15. **Production configuration:** Disable debug output and directory listing, remove installation/test utilities after use, restrict database and server access, keep PHP and dependencies patched, and apply least privilege.
16. **Payments:** If online payments are added, use a reputable payment provider and do not store raw card numbers or security codes.
17. **Testing:** Test authentication, permissions, input validation, upload restrictions, CSRF protection, order workflows, and regression behavior before release. Review dependencies for known vulnerabilities.
18. **Privacy:** Collect only information needed for the service, limit access, and define reasonable retention and deletion practices.

Never claim the application is completely secure. Describe security controls that have actually been implemented and tested, and identify remaining risks before deployment.

## 15. Mandatory Development and Deployment Workflow

For each change:

1. Inspect the current repository, relevant files, database schema, and existing behavior before editing.
2. Follow the approved programming stack and preserve working functionality.
3. Make focused changes rather than rewriting unrelated parts of the system.
4. Avoid destructive database or file operations without explicit owner approval and a verified backup.
5. Add or update migrations and documentation when the schema or deployment process changes.
6. Test the change and relevant neighboring workflows where possible; report what was tested and what was not.
7. Never commit credentials, private customer data, production database dumps, or uploaded customer artwork.
8. Before online deployment, verify HTTPS, production configuration, least-privilege database access, backups and restoration, error handling, access control, and removal of development tools.

If a requested change conflicts with these rules, explain the risk and propose a safer implementation before proceeding.
