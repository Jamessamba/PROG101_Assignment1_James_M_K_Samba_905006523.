# PROG101_Assignment1_James_M_K_Samba_905006523.
 
1. EXECUTIVE SUMMARY
This assignment presents the logical design of a Community Waste Management System (CWMS) for a selected community in Freetown, Sierra Leone. The proposed system is intended to improve how households report waste collection needs, how collection teams receive and complete assignments, and how community administrators monitor service delivery. It is a logical design exercise: it explains the system through algorithms, pseudocode, flowcharts, variables, decisions, repetition, modules and sample outputs. It does not claim that a working software application has already been built.
The system focuses on a manageable service process. A resident submits a collection request or reports uncollected waste, the system checks the details and service area, assigns the request for action, records the collection outcome and updates the resident. If a collection is not completed, the request remains open for rescheduling or escalation. The design supports clearer records, accountability and better communication between residents, collectors and administrators.
2. RATIONALE
2.1 Problem Description
Poorly coordinated waste collection can leave household and community waste unattended for long periods. When collection schedules are unclear, collection points are missed, or residents do not know where to report a problem, waste may accumulate around homes, roadsides, markets and drainage areas. Uncollected waste can create unpleasant surroundings, attract pests and contribute to blocked drains, especially during heavy rainfall. The extent and causes of the problem differ between communities, so the proposed system is designed as a practical model that a local community could adapt.
The problem addressed by this project is not simply the existence of waste. It is the difficulty of coordinating information about where waste needs to be collected, when a collection is expected, whether the collection has taken place and what should happen when it has not. In an informal or paper-based process, reports may be lost, repeated or passed verbally without a reliable reference number. Residents may not receive feedback, while supervisors may find it difficult to identify overdue requests or assess the performance of collection teams.
2.2 Background
Freetown and other urban communities in Sierra Leone need dependable arrangements for handling household and public-space waste. Waste management involves several connected activities: residents separating or storing waste responsibly, service providers collecting it, transport and disposal arrangements, and local authorities or community groups monitoring public cleanliness. A digital information system cannot replace collection vehicles, workers, disposal facilities or sound environmental policies. It can, however, support the communication and record-keeping that help those services operate in a more organised way.
The proposed CWMS is deliberately limited to the service coordination stage. It records residents and collection locations, accepts requests and complaints, schedules assignments, tracks the status of each request and prepares simple reports. It assumes that a community administrator or authorised service provider maintains the service-area list and that collection teams provide truthful completion updates. The system should be usable on a basic smartphone or through an assisted reporting point for residents who do not have reliable internet access.
2.3 Who Is Affected and Why the Problem Exists
The people most directly affected are households, pedestrians, market users, school communities and people who work or trade near collection points. Waste collectors and supervisors are also affected because incomplete information, duplicate reports and poorly planned routes can waste time and resources. The project does not assume that every community has the same collection arrangements; local leaders and service providers would need to confirm operating days, collection zones and reporting contacts before deployment.
Possible contributing factors include irregular or insufficient collection capacity, unclear collection schedules, limited communication channels, incomplete location details, weak follow-up on complaints and a lack of shared records. Some causes, such as insufficient trucks or disposal capacity, cannot be solved by software alone. The CWMS addresses the information and coordination aspects by giving each request a reference number, recording its location and status, assigning responsibility and keeping a history of actions.
2.4 Proposed Solution and Community Impact
The proposed solution is a simple Community Waste Management System with three main user groups: residents, collection teams and community administrators. Residents can register a household, submit a collection request or lodge a complaint. Administrators validate the information, check whether the location is within the service area, assign a request to a collection team and monitor deadlines. Collection teams view their assigned work and submit a completion or non-completion update. The system stores the status and provides a reference number so that residents can follow up.
If used consistently, the system could reduce lost or duplicated reports, make overdue collections easier to identify and improve communication about service progress. It could also provide summary information to help community leaders identify locations with repeated problems. These are expected benefits, not measured results: actual improvement would depend on staff training, reliable collection services, accurate data, maintenance and community participation. The system should collect only necessary personal information and restrict administrative records to authorised users.
The proposed system is appropriate for a programming logic assignment because its processes can be described using input, processing and output; sequence; selection; repetition; variables; constants; data types; Boolean conditions; functions; and modular design. It also provides a realistic opportunity to explain how an open-source approach, Digital Public Goods principles and relevant Sustainable Development Goals may support a community-focused solution.
3. PROPOSED SOLUTION AND SYSTEM SCOPE
3.1 Main Objectives
•	Provide a consistent way for residents to submit waste collection requests and complaints.
•	Assign a unique reference number to each valid request for tracking and follow-up.
•	Allow administrators to check service-area coverage and schedule collection work.
•	Allow collection teams to update whether an assigned collection was completed.
•	Keep a basic record of requests, statuses, dates and actions for reporting.
•	Support accessible, accountable and community-oriented waste service coordination.
3.2 Users and Responsibilities
User	Main responsibilities
Resident	Register household details; submit request or complaint; keep reference number; check status.
Community administrator / supervisor	Maintain service areas and schedules; validate reports; assign teams; review overdue requests; prepare reports.
Collection team	View assigned tasks; visit assigned location; report completed, partly completed or missed collection.
System	Validate required fields; generate references; store records; apply status rules; produce notifications and summaries.

3.3 In-Scope and Out-of-Scope Features
In scope	Out of scope for this logical design
Household registration and request capture	Live GPS tracking of vehicles
Request validation and reference number generation	Online payment processing
Service-area check and team assignment	Operating waste trucks or machinery
Collection status and complaint follow-up	Controlling landfill or recycling plant operations
Basic reports and notifications	A fully deployed production application

4. COMPUTATIONAL THINKING AND PROBLEM DECOMPOSITION
4.1 Decomposition
The larger waste collection coordination problem is divided into smaller tasks: resident registration, request submission, validation, service-area checking, scheduling, team assignment, collection update, complaint handling and reporting. Each task can be designed and tested separately before being combined into the complete system.
4.2 Pattern Recognition
Similar information is needed for most service requests: resident or contact reference, location, request date, waste description and status. Repeated patterns also occur in the workflow: validate a request, assign it, wait for an update and either close or reschedule it. Recognising these patterns allows the system to use a common request record and reusable validation and status-update functions.
4.3 Abstraction
The design stores only information needed to coordinate the service. For example, the system needs a household reference and collection location; it does not need unrelated personal details. It represents a collection task using a small set of fields such as request ID, zone, date, assigned team and status. Complex operational details such as vehicle maintenance are outside this model.
4.4 Algorithmic Thinking
The workflow follows a defined sequence: receive information, validate it, check eligibility, record the request, assign responsibility, receive a collection result and update the record. Decisions are made at clear points, such as whether details are complete, whether the location is served and whether the collection was completed. Repetition is used when an administrator processes several requests or a team works through a list of assigned tasks.
4.5 Problem Decomposition Diagram
 
Figure 1: Functional modules and shared data/access layer of the proposed CWMS.
5. ALGORITHM DESIGN
5.1 Main Request and Collection Algorithm
1.	Start the system and receive a resident's collection request or report.
2.	Read the resident reference, location, description and preferred collection date.
3.	Check that all mandatory fields are present. If any are missing, ask the resident to correct them and validate again.
4.	Check whether the location belongs to a service area. If it does not, explain that the request cannot be scheduled by this service and refer the resident to the appropriate contact.
5.	If the request is valid and the location is served, generate a unique request reference and save the request with status PENDING.
6.	The administrator reviews pending requests, selects an available collection team and assigns a suitable collection date.
7.	The collection team views its assigned tasks and attempts the collection.
8.	If collection is completed, update the status to COMPLETED, record the completion date and notify the resident.
9.	If collection is not completed, keep the request OPEN, record the reason and reschedule or escalate it.
10.	Repeat the process for the next request until there are no more requests to process.
11.	Generate a summary report and end the process.
6. PSEUDOCODE
The pseudocode below describes the main workflow without using a particular programming language. It uses clear English-like instructions, selection (IF/ELSE), repetition (WHILE/FOR) and modular procedure calls.
CONSTANT MAX_ATTEMPTS = 3

PROCEDURE SubmitWasteRequest
    INPUT residentID, location, wasteDescription, preferredDate

    IF residentID = EMPTY OR location = EMPTY OR
       wasteDescription = EMPTY THEN
        DISPLAY "Please complete all required fields"
        RETURN
    ENDIF

    IF IsServiceArea(location) = FALSE THEN
        DISPLAY "Location is outside the service area"
        RETURN
    ENDIF

    requestID = GenerateReferenceNumber()
    status = "PENDING"

    SaveRequest(requestID, residentID, location,
                wasteDescription, preferredDate, status)

    DISPLAY "Request received. Reference: ", requestID
    AssignCollectionTeam(requestID)
END PROCEDURE


PROCEDURE AssignCollectionTeam(requestID)
    team = FindAvailableTeam(requestID)

    IF team EXISTS THEN
        SaveAssignment(requestID, team, SelectCollectionDate())
        DISPLAY "Request assigned to collection team"
    ELSE
        SetStatus(requestID, "AWAITING_ASSIGNMENT")
        DISPLAY "No team currently available; request remains open"
    ENDIF
END PROCEDURE


PROCEDURE UpdateCollectionResult(requestID)
    INPUT collectionCompleted, reason

    IF collectionCompleted = TRUE THEN
        SetStatus(requestID, "COMPLETED")
        SaveCompletionDate(requestID)
        NotifyResident(requestID, "Collection completed")
    ELSE
        SetStatus(requestID, "OPEN")
        SaveReason(requestID, reason)
        RescheduleOrEscalate(requestID)
        NotifyResident(requestID, "Collection not completed; follow-up pending")
    ENDIF
END PROCEDURE


MAIN
    WHILE NewRequestsAvailable() = TRUE
        SubmitWasteRequest()
    ENDWHILE

    FOR EACH assignedRequest IN Today'sAssignments
        UpdateCollectionResult(assignedRequest)
    ENDFOR

    GenerateDailySummaryReport()
END MAIN

6.1 Pseudocode Notes
•	INPUT receives information supplied by the resident or collection team.
•	IF / ELSE selects an action based on a condition.
•	WHILE repeats request intake while new requests are available.
•	FOR EACH repeats the collection update process for every assigned request.
•	PROCEDURES divide the solution into reusable modules.
•	RETURN ends the current procedure when validation fails.
7. FLOWCHARTS
The flowcharts use standard conventions: rounded rectangles for start/end or process steps, diamonds for decisions and arrows to show the direction of control. YES and NO labels identify the decision paths. The diagrams are original, high-resolution figures prepared for this report in a clean flowchart style.
7.1 Main Request and Collection Flowchart
 <img width="456" height="480" alt="image" src="https://github.com/user-attachments/assets/2ffabbc5-216b-4445-be6d-22a0fc4d0697" />
<img width="372" height="453" alt="image" src="https://github.com/user-attachments/assets/659acbe4-8228-4c1f-9ae7-bb4427ab5a97" />

Figure 2: Main workflow from resident request to collection outcome and reporting.
7.2 Complaint Handling Flowchart
 
Figure 3: Complaint validation, duplicate check, escalation and resident feedback.
8. LOGICAL DESIGN
8.1 Input, Processing and Output
Stage	Description	Example
Input	Information entered by residents, administrators and collection teams.	Resident ID, location, waste description, collection date, completion result.
Processing	Validation, service-area check, reference generation, assignment, status update and report calculation.	Check required fields; assign team; set status to COMPLETED or OPEN.
Output	Information returned or displayed by the system.	Reference number, assignment notice, status update, overdue list and daily report.

8.2 Variables and Constants
Name	Data type	Purpose / example
residentID	String	Unique household or resident reference.
requestID	String	Unique request reference, e.g. CW-2026-0001.
location	String	Community, zone, street or recognised collection point.
wasteDescription	String	Short description of the waste or issue.
preferredDate	Date	Requested or proposed collection date.
status	String / enumerated value	PENDING, ASSIGNED, COMPLETED, OPEN, or AWAITING_ASSIGNMENT.
collectionCompleted	Boolean	TRUE if the assigned collection was completed; otherwise FALSE.
MAX_ATTEMPTS	Integer constant	Maximum permitted validation retry count if retry control is implemented.

8.3 Data Types and Boolean Logic
The design uses strings for identifiers and descriptions, dates for scheduling, integers for counters and Boolean values for yes/no conditions. Example Boolean conditions include IsServiceArea(location) = TRUE and collectionCompleted = FALSE. A request can be assigned only when the required information is valid and the location is covered by the service. A request can be closed as COMPLETED only after a collection team records a successful collection.
8.4 Decision Structures
•	IF required details are missing, request correction; ELSE continue validation.
•	IF the location is outside the service area, do not schedule it; ELSE create a request.
•	IF a collection team is available, assign the task; ELSE retain it for later assignment.
•	IF collection is completed, close the request; ELSE keep it open and reschedule or escalate.
8.5 Repetition Structures
A WHILE loop can continue accepting requests while new submissions are available. A FOR EACH loop can process every task on the day's assignment list. Repetition must have a clear stopping condition, such as no new requests remaining or the end of the assignment list, to prevent an endless loop.
8.6 Data Validation and Basic Controls
•	Reject a request if mandatory fields are blank.
•	Use a unique request reference to reduce confusion between reports.
•	Check service-area eligibility before assigning a collection team.
•	Restrict administrative actions, such as changing service zones or assigning teams, to authorised users.
•	Keep a record of status changes, dates and responsible roles for accountability.
•	Avoid collecting unnecessary personal information and protect contact details from public display.
9. FUNCTIONAL MODULES AND FUNCTIONS
Module / function	Purpose	Example output
RegisterResident()	Creates a household/resident record after checking required fields.	Resident reference created.
ValidateRequest()	Checks required details and acceptable formats.	VALID or INVALID.
IsServiceArea(location)	Checks whether the location is covered by the service.	TRUE or FALSE.
GenerateReferenceNumber()	Creates a unique identifier for a request.	CW-2026-0001.
SaveRequest()	Stores the request details and initial status.	Request saved as PENDING.
FindAvailableTeam()	Finds an eligible collection team for the zone and date.	Team ID or no team available.
AssignCollectionTeam()	Records the team and planned collection date.	Request marked ASSIGNED.
UpdateCollectionResult()	Records completed or missed collection and reason.	COMPLETED or OPEN.
NotifyResident()	Sends or displays an update through the chosen channel.	Status message displayed.
GenerateDailySummaryReport()	Counts requests by status and identifies overdue items.	Daily service summary.

Modular design makes the solution easier to understand, test and maintain. Each function has one clear responsibility. For example, the validation function can be reused when a resident submits a new request and when an administrator edits an existing request.
10. EXPECTED OUTPUTS AND SAMPLE SCENARIOS
The following scenarios are illustrative examples used to demonstrate the expected behaviour of the proposed logic. They are not real service records or claims about actual collection performance.
Scenario	Input / condition	Expected system output
1. Valid request	Resident ID R-014; location is in Zone A; description is provided; service is available.	Request accepted; reference CW-2026-0001 generated; status PENDING; sent for assignment.
2. Missing details	Location is blank.	Request not saved; message asks resident to enter the missing location.
3. Outside service area	Location is not listed in the approved service zones.	Request is not scheduled; resident receives a referral message.
4. Team unavailable	Valid request but no team is available for the proposed date.	Status AWAITING_ASSIGNMENT; request retained for supervisor review.
5. Collection completed	Team records collectionCompleted = TRUE.	Status COMPLETED; completion date saved; resident notified.
6. Collection missed	Team records collectionCompleted = FALSE and gives reason.	Status OPEN; reason saved; request rescheduled or escalated; resident notified.

10.1 Example Daily Summary
Measure	Illustrative count
Requests received today	24
Completed collections	17
Open / missed collections	4
Awaiting team assignment	3
Outside service area / referred	0

The illustrative figures above are only sample data for demonstrating report output. In a real deployment, counts would be calculated from stored request records for the selected reporting period.
11. SDG ALIGNMENT
The project directly supports the intention of SDG 11: Sustainable Cities and Communities, particularly the goal of making human settlements inclusive, safe, resilient and sustainable. Better coordination of collection requests and follow-up can support cleaner public spaces and more organised local services. It can also contribute indirectly to SDG 3: Good Health and Well-being, because improved waste handling may reduce environmental conditions that contribute to health risks. The system itself does not guarantee achievement of either goal; it is an information-support tool that depends on effective waste collection and disposal services.
The strongest alignment is SDG 11, with SDG 3 as a related benefit. The project should avoid claiming that software alone solves waste pollution. It supports coordination, reporting and accountability as part of a wider community waste-management effort.
12. OPEN SOURCE SOFTWARE JUSTIFICATION
12.1 Why an Open-Source Approach
An open-source approach would allow a community, educational institution or local service organisation to inspect, use, adapt and improve the system under the terms of an appropriate open-source licence. This is relevant where local organisations may need to customise community zones, collection schedules, language labels or reporting procedures. The project should use a recognised licence and publish clear documentation rather than simply describing the software as open source.
12.2 Benefits for Sierra Leone
•	Transparency: authorised users and contributors can inspect how the system's logic works.
•	Local adaptation: community groups or developers can adjust forms and workflows to fit local service arrangements.
•	Learning: students and local developers can study the design and contribute improvements.
•	Shared maintenance: more than one capable contributor can identify errors and suggest improvements.
•	Reduced dependence: a community is less tied to one vendor, although hosting, support and maintenance still have costs.
12.3 Potential Community Contributions
Residents and community representatives could review whether request forms are understandable. Local developers could improve accessibility, add language support or refine reports. Waste collection organisations could verify service-zone and scheduling rules. Student contributors could test the pseudocode against sample scenarios, improve documentation and report design errors. Contributions should be reviewed before they are merged into the main project.
13. DIGITAL PUBLIC GOODS (DPGs) JUSTIFICATION
A Digital Public Good is a digital solution that can create public benefit and is developed and shared in a way that supports openness, privacy, relevant standards and responsible use. The proposed CWMS could move towards DPG status if it is made openly available under an appropriate licence, documented clearly, designed for reuse and maintained with community needs in mind. A project is not automatically a Digital Public Good merely because it is free to download.
Accessibility should be considered from the beginning. The interface should use plain language, work on low-cost smartphones and avoid unnecessarily large data requirements. Where internet access is unreliable, an assisted reporting channel or offline-first design could be considered in a later implementation. Openness should be balanced with privacy: public users may see general service information, but personal contact details and administrator records must not be exposed.
For wider recognition as a Digital Public Good, the project would need to meet applicable DPG criteria and safeguards, including an open licence, clear documentation, privacy and security practices, and evidence of public benefit. This assignment proposes a design direction; it does not claim that the system has been formally recognised as a DPG.
14. SIERRA LEONE COMMUNITY IMPACT AND SUSTAINABILITY
14.1 Problem Being Addressed
The project addresses weak communication and coordination in reporting, assigning and following up waste collection work. It focuses on the information gap between residents, collection teams and supervisors.
14.2 Expected Impact and Beneficiaries
Residents may gain a clearer reporting channel and a reference number for follow-up. Collection teams may receive more structured assignments. Supervisors may see outstanding requests and recurring problem locations. Community leaders may use summary reports to support discussions about collection schedules and service gaps. These benefits depend on accurate reporting and the availability of actual collection services.
14.3 Long-Term Sustainability
•	Identify a responsible local organisation to own and maintain the service records.
•	Train administrators and collection teams and provide simple user guidance.
•	Review service zones and collection schedules regularly.
•	Provide a low-data mobile-friendly interface and an assisted reporting option.
•	Budget for hosting, device access, support, backups and security updates.
•	Publish the system documentation and licence so future contributors can maintain it.
•	Monitor practical indicators such as requests received, completion rate, overdue requests and repeat complaints.
16. CONCLUSION
The Community Waste Management System provides a logical response to a practical community challenge in Sierra Leone. It focuses on improving the coordination of collection requests, team assignments, status updates and complaints. The design demonstrates computational thinking, algorithms, pseudocode, flowcharts, input-processing-output, variables, data types, Boolean logic, decision structures, repetition, functions and modular design. It also explains how an open-source approach, Digital Public Goods principles and the Sustainable Development Goals can inform a community-focused digital solution.
The proposed system is not a substitute for collection workers, vehicles, disposal facilities or local environmental management. Its value lies in supporting better information flow and accountability. A real implementation would require consultation with residents and service providers, testing, privacy safeguards, reliable maintenance and clear responsibility for acting on submitted reports.
17. REFERENCES
United Nations (2015) Transforming our world: the 2030 Agenda for Sustainable Development. Available at: https://sdgs.un.org/2030agenda (Accessed: 5 November 2026).
United Nations Department of Economic and Social Affairs (n.d.) Goal 11: Make cities and human settlements inclusive, safe, resilient and sustainable. Available at: https://sdgs.un.org/goals/goal11 (Accessed: 5 November 2026).
United Nations Department of Economic and Social Affairs (n.d.) Goal 3: Ensure healthy lives and promote well-being for all at all ages. Available at: https://sdgs.un.org/goals/goal3 (Accessed: 5 November 2026).
Digital Public Goods Alliance (n.d.) Digital Public Goods Standard. Available at: https://digitalpublicgoods.net/standard/ (Accessed: 5 November 2026).
Open Source Initiative (n.d.) The Open Source Definition. Available at: https://opensource.org/osd (Accessed: 5 November 2026).
Limkokwing University of Creative Technology, Sierra Leone (2026) PROG101: Principles of Programming Logic and Design — Individual Assignment Brief, September 2026 to January 2027. Unpublished course document.

