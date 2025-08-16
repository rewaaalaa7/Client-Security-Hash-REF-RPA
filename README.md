## Overview
This project is an implementation of the **Calculate Client Security Hash** assignment from **UiPath Academy – Advanced RPA Developer course**.  
It is built using the **Robotic Enterprise Framework (REF)** and demonstrates end-to-end automation of logging into the **ACME Test website**, retrieving client details, and calculating their security hash.

---

## Features
- Built on **Robotic Enterprise Framework (REF)**.
- Automates the **ACME System 1** login and navigation.
- Reads **WI5 (Work Items - Type 5)** from ACME Test.
- Extracts client details (ID, Name, Country).
- Generates the **Security Hash** using SHA1 encryption.
- Updates the result back into the ACME System.
- Provides transaction logging, exception handling, and retry mechanisms via REF.

---

## Workflow Description
1. **Initialization (Init State)**  
   - Reads configuration from `Config.xlsx`.  
   - Opens the ACME Test web application.  
   - Initializes Orchestrator queues and assets.  

2. **Get Transaction Data**  
   - Retrieves **WI5 transactions** from the ACME Test Work Items.  

3. **Process Transaction**  
   - Extracts Client ID, Name, and Country from each WI5.  
   - Concatenates them in the format:  
     ```
     ClientID-ClientName-ClientCountry
     ```
   - Generates the **SHA1 hash** of this string.  
   - Updates the corresponding Work Item with the generated hash.  

4. **End Process**  
   - Closes applications.  
   - Logs final results.  

---
## Requirements
- **UiPath Studio** (tested with the version you used)  
- **UiPath Orchestrator** (optional but recommended)  
- **ACME Test website credentials** (training site: https://acme-test.uipath.com)  
- `Config.xlsx` properly configured with system URLs, queues, and assets  

---

## How to Run
1. Open the project in UiPath Studio.  
2. Update `Config.xlsx` with your Orchestrator settings and ACME Test credentials.  
3. Publish or run the project.  
4. Monitor execution logs in UiPath Orchestrator (if connected).  
5. Verify updated **WI5 items** in ACME Test with their calculated hashes.  
