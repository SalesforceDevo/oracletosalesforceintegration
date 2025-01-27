# Salesforce and Oracle Database Integration Using MuleSoft

## Overview
This project demonstrates the integration of **Salesforce** with an **Oracle database** using MuleSoft. The purpose of this integration is to seamlessly fetch customer data from the Oracle database and synchronize it with Salesforce. 

Key features include:
- Fetching customer data based on specific criteria from an Oracle database.
- Transforming the data before sending it to Salesforce.
- Creating records in Salesforce via batch processing.

---

## Architecture
### MuleSoft Flow Overview
The MuleSoft flow consists of the following components:
1. **Listener**:
   - Triggers the integration when a request is received.
2. **Database Connector**:
   - Executes an SQL query to fetch customer data from the Oracle database.
3. **Logger**:
   - Logs the process at various stages for monitoring and debugging.
4. **Transform Message**:
   - Maps and transforms the Oracle database response into a Salesforce-compatible format.
5. **Salesforce Connector**:
   - Creates records in Salesforce using the transformed data.
6. **Batch Processing**:
   - Ensures efficient processing of large data sets by dividing them into chunks.

---

## Project Workflow
1. **Request Trigger**:
   - A request is sent to the MuleSoft application via an HTTP listener.
2. **Fetch Data from Oracle**:
   - The application uses the **Database Connector** to execute the SQL query:
     ```sql
     SELECT * FROM customers WHERE customer_id <= 500;
     ```
   - The query retrieves customer records with IDs less than or equal to 500.
3. **Transform Data**:
   - The data is transformed into a structure compatible with Salesforce.
4. **Send Data to Salesforce**:
   - The **Salesforce Connector** creates new records in Salesforce.
5. **Batch Processing**:
   - Records are processed in batches for scalability and reliability.
6. **Error Handling**:
   - An **Error Handling** flow logs errors and ensures the process continues for the remaining data.

---

## Features
- **Oracle Database Query**:
  Retrieves customer records from Oracle with flexible filtering options.
- **Salesforce Integration**:
  Synchronizes Oracle data with Salesforce to maintain up-to-date customer records.
- **Batch Processing**:
  Handles large volumes of data efficiently.
- **Error Handling**:
  Logs errors and ensures smooth recovery during processing.

---

## Configuration
### Prerequisites
- MuleSoft Anypoint Studio
- Salesforce account with appropriate permissions
- Oracle database with connection credentials
- MuleSoft Database and Salesforce connectors

### Setup
1. Configure the **Database Connection**:
   - Set up a connection to the Oracle database using the `Database_Config` global element.
2. Configure the **Salesforce Connection**:
   - Use your Salesforce credentials to authenticate the Salesforce connector.
3. Deploy the application in MuleSoft Anypoint Studio or a Mule runtime.

---

## Screenshots
### MuleSoft Flow
![MuleSoft Flow](Screenshot%202025-01-20%20111243.png)


---

## How to Use
1. Clone this repository:
   ```bash
   git clone https://github.com/your-repo/salesforce-oracle-integration.git
