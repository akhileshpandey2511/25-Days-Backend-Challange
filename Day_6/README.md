## Day_6: Ecommerce and Hospital management Data modelling

### Overview
This repository contains the data modeling for both E-commerce and Hospital Management systems.

### Features
- E-commerce Data Modeling: Includes entities such as Product, Order, User, and Category.
- Hospital Management Data Modeling: Includes entities such as Patient, Doctor, Hospital, and Medical Records.
- Relationships: Defines relationships between entities to capture complex interactions within each domain.

## Usage
### E-commerce Data Model
1. Entities:
  - Product: Represents a product available for sale.
  - Order: Represents a purchase made by a customer.
  - User: Represents a registered user who makes purchases.
  - Category: Represents a physical or virtual store where products are sold.
2. Attributes:
  - Product: ID, Name, Description, Price, Category, productImage, Stock, Owner.
  - Order: ID, orderprice, customer, orderItems, adress, status.
  = User: ID, Name, Email, Address.
  = Category: ID, Name.
3. Relationships:
  - Product and Order: One-to-Many relationship.
  - User and Order: One-to-Many relationship.
  - Category and Product: One-to-Many relationship.

### Hospital Management Data Model
1. Entities:
  - Patient: Represents a patient receiving medical care.
  - Doctor: Represents a healthcare professional providing medical services.
  - Hospital: Represents an appointment scheduled between a patient and a doctor.
  - Medical Records: Represents a medical department within the hospital.
2. Attributes:
  - Patient: ID, admittedIn, gender, bloodGroup, age, adress, diagnosedWith, name.
  - Doctor: ID, Name, worksInHospital, experienceinnumber, salary, qualification.
  - Hospital: ID, name, adressLine1, adressLine2, city, pincode, specilizationIn.
  - Medical Records: ID, patientname, diagnosedWith, status, tharapy.
3. Relationships:
  - Patient and Doctor: One-to-Many relationship.
  - Doctor and Hospital: One-to-Many relationship.
  - Medical records and Patient: One-to-Many relationship.

🔗 https://github.com/akhileshpandey2511/mongoose-model
