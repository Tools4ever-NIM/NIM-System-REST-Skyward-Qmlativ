# NIM-Conn-System-REST-Skyward-Qmlativ
NIM Connector for Skyward Qmlativ Custom API

## Table of Contents
- [Available Data](#available-data)
- [Setting up the API Access](#setting-up-the-api-access)
  - [General Notes](#general-notes)
  - [API User](#api-user)
  - [API User Access](#api-user-access)
  - [Integration Access Secrets](#integration-access-secrets)
- [Configure NIM](#configure-nim)
- [NIM docs](#nim-docs)


## Available Data
- Curriculum_Subject
- Demographics_Address
- Demographics_Country
- Demographics_County
- Demographics_Directional
- Demographics_EmailType
- Demographics_GenderIdentity
- Demographics_Language
- Demographics_NameAddress
- Demographics_NameAlias
- Demographics_NameEmail
- Demographics_NamePhone
- Demographics_NameSuffix
- Demographics_NameTitle
- Demographics_Name
- Demographics_Occupation
- Demographics_PhoneType
- Demographics_Relationship
- Demographics_Street
- Demographics_Zip
- District_Building
- District_BuildingSchoolYear
- District_CalendarYear
- District_ConfigEntityYear
- District_District
- District_DistrictSchoolYear
- District_Entity
- District_FiscalYear
- District_Floor
- District_Room
- District_RoomType
- District_SchoolYear
- Employee_Calendar
- Employee_CheckLocation
- Employee_DegreeType
- Employee_Degree
- Employee_EmployeeDistrict
- Employee_EmployeeFiscalYear
- Employee_Employee
- Employee_EmployeeYearExperience
- Employee_Employment
- Employee_EmploymentStatus
- Employee_Termination
- Enrollment_EntitySchool
- Enrollment_EntryCode
- Enrollment_EntryWithdrawal
- Enrollment_GradeLevel
- Enrollment_Homeroom
- Enrollment_School
- Enrollment_StudentEntityYear
- Enrollment_StudentType
- Enrollment_WithdrawalCode
- Family_Family
- Family_FamilyGuardian
- Family_StudentFamily
- Family_StudentGuardian
- FoodService_Customer
- Position_Assignment
- Position_AssignmentDetail
- Position_AssignmentType
- Position_Department
- Position_EmployeePlacement
- Position_EmployeePlacementDetail
- Position_EmployeePositionType
- Position_FTEGroup
- Position_JobType
- Position_Lane
- Position_Matrix
- Position_MatrixLane
- Position_Placement
- Position_Position
- Position_PositionDistribution
- Position_PositionDistributionSet
- Position_PositionGroup
- Position_PositionNumber
- Position_PositionType
- Position_Step
- Scheduling_CourseType
- Scheduling_Course
- Scheduling_Meet
- Scheduling_MeetSummary
- Scheduling_SchedulingTeam
- Scheduling_Section
- Scheduling_StaffMeet
- Scheduling_StudentSection
- Security_AuthenticationRole
- Security_User
- SkySys_State
- Staff_ConfigEntityGroupYear
- Staff_Department
- Staff_Staff
- Staff_StaffDepartment
- Staff_StaffEntityYear
- Staff_StaffStaffType
- Staff_StaffType
- StateReporting_StateInternetAccess
- StateReporting_StateInternetAccessType
- Student_InternetAccess
- Student_InternetAccessType
- Student_StudentCustomCode
- Student_Student

## Setting up the API Access
### General Notes
Each API Vendor should have an Integration record available in Qmlativ.

 ![image](https://github.com/Tools4ever-NIM/NIM-System-REST-Skyward-Qmlativ/assets/24281600/64e32e13-72a4-466e-a453-cb0ac99aa9ad)

The APIs used by an Integration can also be viewed from the Integration List screen by looking at the lower browse.  The APIs may also be viewed from the Integration APIs tab on the Integration Details screen.

 ![image](https://github.com/Tools4ever-NIM/NIM-System-REST-Skyward-Qmlativ/assets/24281600/e629fce7-210e-4eac-8cf8-7c1e84ec4d37)

If the vendor has indicated that they are using the Custom API, select it to see which Objects and Fields are being used, and what types of access they have to them.

 ![image](https://github.com/Tools4ever-NIM/NIM-System-REST-Skyward-Qmlativ/assets/24281600/2a5f2eff-4c45-4ba1-a5c8-b6dfb29cc781)

An Integration Access record is required to grant Qmlativ API access, similar to the API User record.
If the vendor has requested to set up new Integration Access credentials and their Integration is not visible in the Integration List, please reach out to Skyward to ensure that the Integration Sync process is working properly.

### API User
A new Integration Access record should exist for each active API User record.
API User records may be found under the API area by selecting the User feature:

 ![image](https://github.com/Tools4ever-NIM/NIM-System-REST-Skyward-Qmlativ/assets/24281600/13404ad4-8452-4efa-92a1-505245b443a8)

You may find/create Integration Access records by going to the API area and select the Integration Access feature:

 ![image](https://github.com/Tools4ever-NIM/NIM-System-REST-Skyward-Qmlativ/assets/24281600/2441eb2e-3bb1-40f2-a823-f6a65cfffe88)

Integration Access records can also be found/created from the Integration Details screen.

 ![image](https://github.com/Tools4ever-NIM/NIM-System-REST-Skyward-Qmlativ/assets/24281600/19180006-f55e-40c3-864d-16a5bdc821b4)

It is recommended to copy most of the API User’s settings into the Integration Access.

![image](https://github.com/Tools4ever-NIM/NIM-System-REST-Skyward-Qmlativ/assets/24281600/5764c1ec-85ad-4138-b6b5-273af858544e)

![image](https://github.com/Tools4ever-NIM/NIM-System-REST-Skyward-Qmlativ/assets/24281600/153329dc-a7d7-4f4f-87bc-b543391212ab)

The areas highlighted in red (1-4) can be taken from the API User record. The area highlighted in blue (5) can be taken from the API User Access records associated with the API User record. These values can also be changed to something new but keeping them the same reduces the possibility of errors during the initial conversion.

**NOTE**: _OAuth1 as an Authentication Type has been removed for the Integration Access system. Each vendor that used OAuth1 should migrate to OAuth2 for the new Integration Access system._

### API User Access

One of the main benefits of the Integration Access system is that each Integration is already pre-packaged with which APIs it uses, and therefore with which configuration records it is associated. When configuring an Integration Access, selecting the vendor’s Integration will automatically display the expected API Configuration sections.
Here is an example of the Integration Access screen when the selected Integration uses all APIs. As you can see, the Configuration section displays all configuration options for the APIs:

 ![image](https://github.com/Tools4ever-NIM/NIM-System-REST-Skyward-Qmlativ/assets/24281600/1318e043-58d0-48c3-89d5-4dab27c9ff71)

**NOTE:** _OneRoster, Time Tracking, Identification, Attendance, and Enrollment Configuration records can be shared between the API User Access and Integration Access records._

Custom API Entities is a new entity selector that controls which entities the vendor has access to.  For Integrations that use the Custom API, the modules, objects, and fields that are used by the Integration are now visible on the “Integration Objects” tab, so the old “Allow Security Module Write Operations” checkbox that was on the API User Access is now obsolete.

### Integration Access Secrets
Secrets work differently in the Integration Access system than they did in the API User system. In all situations, it is not possible for districts to generate their own complete set of API credentials. 

* For vendors who do not enable the district to create their own Secret, only a Key and Secret is required to authenticate themselves in the Qmlativ API. 
* For vendors who enable the district to create their own Secret, there is a hidden third value stored by the vendor that enables the Integration Access connection.

Secrets generated for Integration Access can only be viewed once; they cannot be retrieved after closing the confirmation dialog.

# Configure NIM
1.	Open the NIM Admin Interface and go to Systems > Overview
2.	Click “+ Add” to add a new system
 
 ![image](https://github.com/Tools4ever-NIM/NIM-System-REST-Skyward-Qmlativ/assets/24281600/1af7fafb-85b9-429f-abbc-5e1021951462)

3.	Select “Skyward Qmlativ” and name it accordingly. (e.g. Skyward_Qmlativ)
 
 ![image](https://github.com/Tools4ever-NIM/NIM-System-REST-Skyward-Qmlativ/assets/24281600/4357a387-befc-4a33-93f4-0b13a41c6cd9)

4.	Edit the System to configure the connection information
 
 ![image](https://github.com/Tools4ever-NIM/NIM-System-REST-Skyward-Qmlativ/assets/24281600/c2ba793b-f463-4b1d-8145-e6ac8be38128)

5.	Enter the necessary information for the system
    - Customer/tenant ID
        - This is the URL to the instance, typically in this format
            -<Customer>.skyward.com/<customer>API
    -	Client ID
        - Enter the Client Key from the Skyward integration Access Screen
    - Client Key
        -	Enter the Client Secret from the Skyward Integration Access Screen
    -	Integration Key
        - Please reach out to Tools4ever support (support@tools4ever.com) to obtain this key. This key is generated on a per customer basis for access to use the integration
    - Entity ID
        - Typically, this is going to be “1”. It is the ID of the District we’ll be connecting to for this instance. In cases where there are multiple districts under one instance, then a system per district is required.
    - School Year ID
        - This can remain blank and it will refer to the default active school year. Otherwise, you can specify a specific school year to target
    - Fiscal Year ID
        - This can remain blank and it will refer to the default active fiscal year. Otherwise, you can specify a specific fiscal year to target
          
6.	Check the connection by click on “Test Connection”
 
 ![image](https://github.com/Tools4ever-NIM/NIM-System-REST-Skyward-Qmlativ/assets/24281600/2309d2e0-9e38-43fc-aab2-76cef043a4db)

7.	Once the test is successful you can click on the “Configuration” tab and select the tables of table you would like to import into NIM
 
 ![image](https://github.com/Tools4ever-NIM/NIM-System-REST-Skyward-Qmlativ/assets/24281600/65987b14-324a-439c-aec3-180320a849ad)


 
# NIM Docs
The official NIM documentation can be found at: https://docs.nimsuite.com
