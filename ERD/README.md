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
| Description        | VARCHAR(20)  |             |

## 3. Locations

The Locations table contains details of the locations where campaigns may be held.

| Field               | Type         | Constraints |
|---------------------|--------------|-------------|
| LocationId          | VARCHAR(20)  | PK, NN      |
| Location            | VARCHAR(20)  | NN          |
| Description         | VARCHAR(20)  |             |

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

## 5. Campaigns

The Campaigns table tracks marketing campaigns, including the campaign details and performance metrics.

| Field          | Type        | Constraints                         |
|----------------|-------------|-------------------------------------|
| CampaignId     | VARCHAR(20) | PK, NN                              |
| StartDate      | DATETIME    | NN                                  |
| EndDate        | DATETIME    | NN                                  |
| ChannelId      | VARCHAR(20) | FK (ref: Channels.ChannelId)        |
| ClientId       | VARCHAR(20) | FK (ref: Client.ClientId)           |
| Audience       | VARCHAR(20) | NN                                  |
| Views          | INT         | NN                                  |
| Clicks         | INT         | NN                                  |
| Conversions    | INT         | NN                                  |
| Expenses       | FLOAT       | NN                                  |
| LocationId     | VARCHAR(20) | FK (ref: Locations.LocationId)      |
| Sales          | FLOAT       |                                     |
| CampaignTypeId | VARCHAR(20) | FK (ref: CampaignTypes.TypeId)      |
| EmpId          | VARCHAR(20) | FK (ref: Employees.EmpId)           |

## 6. CampaignTypes

| Field          | Type        | Constraints  |
|----------------|-------------|--------------|
| CampaignTypeId | VARCHAR(20) | PK, NN       |
| CampaignType   | VARCHAR(20) | NN           |
| Descritpion    | VARCHAR(20) |              |

## 7. Departments

| Field        | Type        | Constraints  |
|--------------|-------------|--------------|
| DeptId       | VARCHAR(20) | PK, NN       |
| Department   | VARCHAR(20) | NN           |
| Description  | VARCHAR(20) |              |

### Relationships

The relationships between the tables are as follows:

- Client has many Campaigns (1-to-many relationship)
- Campaign belongs to Client and Channel (many-to-1 relationship)
- Campaign has a Location (many-to-1 relationship)
- Employee works on many Campaigns (1-to-many relationship)
- Campaign has a CampaignType (many-to-1 relationship)
- Employee may have a Supervisor (self-referencing relationship in Employees table)
- Employee works in a Department (many-to-1 relationship)

#### ERD Diagram

![ERD](ERD)

