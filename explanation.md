# RPA
### Project folders
- ##### Requests
Accomodates spreadsheet containing the data to be processed is saved in a file called `Requests.xlsx`. 
- ##### Processed 
Accommodate the processed spreadsheets in the name formart `Request_Date_Timestamp.xlsx`

The project is divided into three workflows.

### Main

- It initiates the automation process and also invokes the other workflows.
- New variables are defined here to store the data that we would get from the `ReadRequests` workflow. 
- The variables are used in the `SaaSAutomatio`n workflow, where they are used to populate the ticktet fields on Zoho Desk.
- It is also moves the processed request to the processed folder and rename the files using the variable `Now.ToString("MM-dd-yyyy_hh_mm_ss")`.
- It is implemented in parallel process to run a trigger scope that defines a hotkey to trigger the termination of a workflow using the hotkey `esc`.

### ReadRequests

This workflow picks up the Request Excel file from the folder we created, reads the ticket data, and incorporates it into variables for the next workflow to process.

### SaaSAutomation
It uses the data obtained from the Requests file to create the support ticket within Zoho Desk.
