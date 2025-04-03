# User ER Diagram

![user-er-diagram](https://github.com/user-attachments/assets/8f605610-8829-4220-a347-8017df1963a0)


This ER diagram models a user authentication and management system with the following key components:

Users: This table stores user details such as a unique identifier (UUID), email, hashed password, activation status, and the account creation timestamp.
Roles: Defines various roles (with a unique name) that can be assigned to users.
UserRoles: Acts as a junction table establishing a many-to-many relationship between Users and Roles, indicating which roles are assigned to each user.
LoginAttemptLogs: Logs each login attempt made by a user, capturing details like the timestamp, success status, IP address, and user agent. This helps in monitoring and auditing authentication activities.
PasswordChangeLogs: Keeps a record of when a user’s password was changed and the IP address from which the change was initiated, providing a trail for security audits.
JwtSessions: Manages JWT (JSON Web Token) sessions by storing token details, including when they were issued, when they expire, and whether they have been revoked, which supports session management and security.

# Order Diagram
![order-er-diagram](https://github.com/user-attachments/assets/be5eb4eb-4ec5-45bc-b7cc-cfabc3d2da9a)

This ER diagram outlines an e-commerce system that manages products, promotions, shopping carts, orders, transactions, and history logs, providing a comprehensive view of the sales and fulfillment process.

Product: Stores product details such as a unique identifier, name, description, price, stock quantity, and audit information like creation and update dates and the associated user details.
Promotion: Captures details of discount offers with fields for a unique id, promotion code, description, discount values (both fixed and percentage), validity periods, and audit metadata.
Cart and CartItem: A shopping cart is associated with a user and can contain multiple cart items. Each cart item links a specific product to the cart along with the quantity selected.
Order and OrderItem: An order, tied to a user and potentially a promotion, records order details including the order date, status, and total amount. Order items detail individual products purchased, including unit price, quantity, and any discount applied.
Transaction: Represents the financial aspect of an order by recording payment details such as the method, status, amount, and payment timestamp.
HistoryLog: Provides a tracking mechanism for orders by recording various actions performed on an order, who performed them, and when.
Relationships:

A Product can be part of multiple OrderItems (included in orders) and CartItems (added to carts).
A Promotion can be applied to multiple Orders and can discount multiple OrderItems.
A Cart can contain several CartItems.
An Order can have multiple OrderItems, can generate multiple Transactions, and is tracked by multiple HistoryLogs.
