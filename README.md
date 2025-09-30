

# Travel Tracker Automation

This project is an automation initiative designed to streamline the management and tracking of employee travel records. The primary goal is to **reduce manual work, improve efficiency, enhance data accuracy, and strengthen data security**.

## Introduction & Objectives

### The Current Problem (As-Is Process)
The existing process for managing employee travel is manual, time-consuming, and prone to errors. Key pain points include:
*   Collecting travel details from request forms and various supporting documents.
*   Manually encoding and updating travel data into Excel spreadsheets.
*   Generating reports manually to track travel frequency, destinations, and associated costs.
*   Difficulty in accessing real-time, updated travel data across different departments.
*   Data security risks and challenges in file retrieval due to inconsistent storage practices.

### Project Objectives
This automation project aims to address the above issues with the following business objectives:
*   **Significantly reduce the time** required to manage and track employee travel records.
*   Save time on encoding, validating, and retrieving travel information.
*   **Increase the processing speed** for travel request approvals and updates.
*   **Improve data visibility**, making it easier to track and report on travel-related metrics.
*   Ensure the **accuracy, consistency, and security** of data.

## Technology Stack

The project leverages the following applications to build the automated workflow:
*   **UiPath**: Used to design, build, and test the automated workflows.
*   **Orchestrator App**: Used to securely upload, organize, and manage related files.
*   **Google Mail**: Used for sending and receiving automated email notifications.
*   **Microsoft Excel**: Used for importing, processing, and exporting travel request data.
*   **OneDrive – File Explorer**: Used for securely uploading and managing files locally.

## Automated Process Flow (To-Be Process)

The automated workflow is designed to optimize efficiency and minimize human intervention. The solution design diagram illustrates how the system components interact to achieve the project's goals.

### 1. Approval Process
1.  **Form Upload**: Human Resources (HR) downloads the travel request form from JIRA and uploads it to the Orchestrator transaction queue.
2.  **Robot Processing**:
    *   The robot downloads the form from Orchestrator for automated processing.
    *   It automatically creates or opens an employee-specific folder in the document library.
    *   **Data is extracted** from the form (e.g., employee info, travel dates).
    *   The extracted information is **updated in the Monitoring Sheet** (an Excel file).
    *   The form is renamed according to a standard convention and archived.
3.  **Notifications**: The system automatically sends an email notification to the employee, line manager, and HR with the request details.
4.  **Approval and Updates**:
    *   HR or a designated approver manually reviews and approves the request.
    *   The system updates the approval status in the monitoring sheet.
    *   After approval, HR uploads additional documents (e.g., tickets, visas) to Orchestrator, which the robot then processes and files into the employee's trip folder.

### 2. Update Document Process
1.  **Document Upload**: HR uploads updated documents (e.g., revised itineraries, approval letters) to Orchestrator.
2.  **Robot Processing**:
    *   The robot downloads the updated documents from Orchestrator.
    *   It extracts the employee's name to identify the correct destination folder.
    *   Files are renamed using a standard convention and **moved into the employee’s existing trip folder**.

### 3. Update Extended Return Process
1.  **Upload New Ticket**: HR uploads the rebooking ticket for an extended return request to Orchestrator.
2.  **Robot Processing**:
    *   The robot downloads the rebooking ticket from Orchestrator.
    *   It **automatically updates the new return date** in the monitoring sheet.
    *   The ticket file is moved into the employee’s designated trip folder.

## Out of Scope

The following processes and tasks have been identified as **out of scope** for this automation project:
*   Downloading the travel request form from JIRA, as it requires human judgment.
*   Manual approval of travel requests by senior management.
*   Handling physical documents like passports and visas.
*   Integration with third-party external travel booking platforms.
*   Installing the OneDrive Desktop app or ensuring a stable internet connection.
*   Resolving disputes related to travel bookings.

## Future Enhancements

The following are suggestions for future iterations to further improve the process by enhancing efficiency and data accuracy:
*   **ENH-1**: Generate a consolidated annual travel report by country and per employee.
*   **ENH-2**: Deploy a travel tracker system for public access with secure login and role-based access control (RBAC).
*   **ENH-3**: Implement a **real-time monitoring dashboard** within the UiPath Orchestrator application.
*   **ENH-5**: Automate the sending of reminders and updates for travel-related events and changes.

## Development Team

The project was executed by a team with the following roles and responsibilities:
*   **Cristelle May Sandoval**: Travel Tracker Automation Lead
*   **James S. Barton**: Solutions Architect
*   **Elaine Negrite, Katherine Roldan**: Product Owner (HR Team)
*   **Jared Ferdinand S. Posada**: Developer/Tester/BA Leader
*   **Maria Dianne Alexa R. Allauigan**: BA/Tester/Documentation
*   **Đặng Nguyễn Gia Bảo**: Developer/Tester
*   **Nguyễn Thu Ngân**: Developer/Tester
*   **Vo Hoang Lam**: Developer/Tester

## Acronyms

*   **RPA**: Robotics Process Automation.
*   **BOT**: UiPath attended/unattended robot.
*   **PDD**: Process Definition Document.
*   **HR**: Human Resources.
