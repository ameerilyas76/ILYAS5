---
name: Bug Report-FTS
about: Case Self Service Request....
title: ''
labels: documentation
assignees: ameerilyas76

---

Case Self Service Request

Common Points
•	Requester Email from User Account-(Low priority)
•	Add Case Identity Field to avoid duplicate request
Returning Labor Request
•	Need API for Get working Employee (in Productivity)
•	Other requests use Get Active Employee API

On Validation
•	following request add Validation API and configure
o	Returning Labor Request(confirm employee working with customer in PRL)
o	Iqama Renewal Request
o	ATM Renewal Request
o	Iqama Re-issuance Request
o	ATM Re-issuance Request
o	Escaped Request
o	Retirement Request

Integration
Creation
•	Iqama Renewal Request-Request will available in Customer Approval
•	ATM Renewal Request
•	Iqama Re-issuance Request
•	ATM Re-issuance Request
•	Escaped Request
•	Retirement Request

Status movement

Source Event	Stage	Action
Iqama Renewal
Manpower	Agree	Case Moved to Agree stage
Manpower	Payment	Case Moved to Payment stage
Manpower	Iqama Renewal	Case Moved to Renewal stage
Manpower	Not Agree	Case Moved to Not Agree stage
Manpower	Completed	Case Moved to Completed stage
 	 	 
ATM Renewal
Manpower	Payment Requested	Case Moved to Payment stage
Manpower	Receive In Lodging 	Case Moved to Waiting for Card stage
Manpower	Completed	Case Moved to Completed stage
 	 	 
Iqama Re-issuance Request
Manpower	Payment Requested	Case Moved to Payment stage
Manpower	Waiting For Issue	Case Moved to Reissue stage
Manpower	Receive In Lodging 	Case Moved to Waiting For Card stage
Manpower	Completed	Case Moved to Completed stage
 	 	 
ATM Re-issuance Request
Manpower	Payment Requested	Case Moved to Payment stage
Manpower	Receive In Lodging 	Case Moved to Waiting For Card stage
Manpower	Completed	Case Moved to Completed stage
 	 	 
Returning Labor Request
Case	New Request	Call Business API

Method: PUT
URL:
/api/Contract/Terminate Employees
Body:
{
"contract ID": 0,
"contract Code": "string",
"employee IDs": [
"string"
],
"remarks": "string",
"employees Target": 0
}

public enum Employee Target Enum
{
Lodging = 0,
Customer = 1,
FinalExit = 2,
Escape = 3,
}

Manpower	when Employee check in Completed	move to Completed stage
Escape Request
Manpower	Registered In MOL 	Case Moved to MOL Registration stage
Manpower	Completed	Case Moved to Completed stage
 	 	 
Retirement Request
Case	New Request	Create Retirement Request
Manpower	Under Processing	move to Under Processing stage
Manpower-Final Settlement	Customer Confirmation	move to Customer Confirmation stage
Manpower-Final Settlement	Payment	move to Approved Payment stage
Manpower-Visa	Requested	move to Visa Issuance stage
Manpower-Travel Request	Requested	move to Ticket Issuance stage
Manpower-Retirement	Rejected Request	move to Rejected stage
Manpower-Retirement	Completed	move to Completed stage
