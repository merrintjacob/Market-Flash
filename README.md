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


## 2. Channels

The Channels table contains information about different marketing channels.

| Field              | Type         | Constraints |
|--------------------|--------------|-------------|
| ChannelId          | VARCHAR(20)  | PK, NN      |
| ChannelName        | VARCHAR(20)  |             |
| ChannelDescription | VARCHAR(20)  |             |

## 3. Locations

The Locations table contains details of the locations where campaigns may be held.

| Field               | Type         | Constraints |
|---------------------|--------------|-------------|
| LocationId          | VARCHAR(20)  | PK, NN      |
| LocationName        | VARCHAR(20)  | NN          |
| LocationDescription | VARCHAR(20)  |             |

## 4. Employees

The Employees table stores employee information, including supervisors and departments.

| Field         | Type         | Constraints                  |
|---------------|--------------|------------------------------|
| EmpId         | VARCHAR(20)  | PK, NN                       |
| FName         | VARCHAR(20)  | NN                           |
| LName         | VARCHAR(20)  | NN                           |
| Address       | VARCHAR(20)  | NN                           |
| Email         | DATETIME     | NN                           |
| Phone         | DATETIME     | NN                           |
| SupervisorId  | VARCHAR(20)  | FK (ref: EmpId)              |
| DeptId        | VARCHAR(20)  | FK (ref: Departments.DeptId) |





### Relationships
#### ERD Diagram
