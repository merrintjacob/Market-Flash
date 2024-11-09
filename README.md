#  Market Flash ERD (Entity Relationship Diagram)
<u></u>

The purpose is to outline the ERD for the Market Flash Campaign Performane, which tracks campaigns, clients, channels, locations, employees, and departments.The Scope of the system allows for campaign tracking, client management, employee allocation, and reporting on KPIs such as conversions, clicks, and engagements.

## Tables
<u></u>
## 1. Clients

The Client table stores information about clients participating in campaigns.

| Field          | Type         | Constraints      |
|----------------|--------------|------------------|
| ClientId       | VARCHAR(20)  | PK, NN          |
| ClientName     | VARCHAR(200) | NN              |
| ClientAddress  | VARCHAR(200) | NN              |
| Email          | VARCHAR(20)  | NN, UNIQUE      |
| Phone          | VARCHAR(20)  | NN              |
| ContactPerson  | VARCHAR(20)  | NN              |


## 2. 
### Relationships
#### ERD Diagram
