# Azure DevOps Test Case Format Instructions

## Test Cases Steps Format

Each feature must have a **high-level user story** and corresponding **test cases** written in Gherkin format:

```gherkin
   Given <initial state or precondition>
   And <another precondition>
   When <action performed>
   Then <expected outcome>
```

### Test Case Row Format
- For each test case, use the following row structure:
  1. The first row contains only the test case metadata (Title, Priority, State, Area Path, etc.), with Step Action and Step Expected left empty and Test Step left empty.
  2. The second row must have the GIVEN statement in the `Step Action` column (Step Expected is empty), and the `Test Step` column set to `1`. All other columns must be empty.
  3. The third row must have the WHEN statement in the `Step Action` column and the **first** expected result in the `Step Expected` column, with the `Test Step` column set to `2`. The Step Expected value in this row must begin with `THEN ` (all caps).
  4. For each **additional expected result**, add a new row with:
     - The `Step Action` column left empty,
     - The next expected result (as a full sentence) in the `Step Expected` column, beginning with `AND ` (all caps),
     - The `Test Step` column incremented (3, 4, ...),
     - All other columns empty.
- Do not use `\n-` or bullet points in the Step Expected column. Each expected result must be in its own row, starting with `THEN` for the first, and `AND` for subsequent rows.
- Do not combine Given/When/Then in a single row.
- Do not repeat metadata (Title, Priority, etc.) in the GIVEN, WHEN, or expected result rows; only the first row contains these values.
- In the GIVEN, WHEN, and expected result rows, the Priority, Automation Status, Area Path, Assigned To, and State columns must always be empty. Do not place any value in these columns except in the metadata row.
- If any value in Step Action or Step Expected contains a comma, the entire value must be enclosed in double quotes to ensure correct CSV formatting.

### Test Case Template

Use the following format for **ALL test cases**:

```csv
ID,Work Item Type,Title,Test Step,Step Action,Step Expected,Priority,Automation Status,Area Path,Assigned To,State
,Test Case,GET /edge/api/v1/graph - Successful authentication returns access token,,,,2,Not Automated,PSS\DeltaV,,Design
,,,1,"Given the API server is running and the user has valid credentials",,
,,,2,"When a GET request is sent to /edge/api/v1/graph with valid username and password","THEN the API should return HTTP status code 200.",,,,,
,,,3,,"AND the response should contain an 'access_token' field.",,,,,
,,,4,,"AND the response should match the expected schema.",,,,,
```

**Important:**
- The `Area Path` column must always be set to `PSS\DeltaV` (metadata row only).
- The `Priority` column must always be set to `2` (metadata row only).
- The `Automation Status` column must always be set to `Not Automated` (metadata row only).
- The `State` column must always be set to `Design` (metadata row only).
- The column order must be strictly followed as shown in the header.
- Only the first (metadata) row contains values for Title, Priority, Automation Status, Area Path, and State. The GIVEN, WHEN, and expected result rows must leave these columns empty except for Step Action (GIVEN/WHEN) and Step Expected (WHEN and expected result rows only).
- Never place expected results or any other value in the Priority, Area Path, or any column other than Step Expected in the WHEN or expected result rows.
- Always enclose Step Action or Step Expected in double quotes if the value contains a comma.
- In the GIVEN row, the `Test Step` column must be set to `1`.
- In the WHEN row, the `Test Step` column must be set to `2`.
- In each expected result row, increment the `Test Step` column (3, 4, ...).
- Only the metadata row should have an empty `Test Step` column.

#### Column Mapping Table

| Column Name        | Value (for all test cases)         |
|--------------------|------------------------------------|
| ID                 | (empty)                            |
| Work Item Type     | Test Case (metadata row only)      |
| Title              | <test case title> (metadata row only) |
| Test Step          | (empty for metadata row, `1` for Given row, `2` for When row) |
| Step Action        | (empty for metadata row, then <Gherkin Given step>, then <Gherkin When step>) |
| Step Expected      | (empty for metadata and Given row, then <b>Then</b> + <user-friendly, full-sentence expectations> for When row) |
| Priority           | 2 (metadata row only)              |
| Automation Status  | Not Automated (metadata row only)  |
| Area Path          | PSS\DeltaV (metadata row only)     |
| Assigned To        | (empty)                            |
| State              | Design (metadata row only)         |
| Tags               | AI Generated (metadata row only)   |

Keep Work Item Type as "Test Case" and only occur in the first row of every test case.
Keep ID to be empty for now, as it will be filled in later.
Keep "Assigned To" empty for now, as it will be filled in later.
Add "State" as "Design" for now, as it will be updated later for every first row of every test case.
Always include "AI Generated" to the "Tags" field to indicate that the test case was generated by AI.
Enclose every field in double quotes, even if it is empty.

### Clarification on Expected Results

- Each expected result must be written in plain language as a full sentence, describing what the tester should observe or verify.
- The first Step Expected for each WHEN step must begin with `THEN ` (all caps). Each additional expected result for the same WHEN step must begin with `AND ` (all caps).
- Do not add assertion rows as separate lines in the CSV except as described above (one expected result per row, Step Action empty except for the first WHEN row).
- Never place expected results or any other value in the Priority column or any column other than Step Expected in the WHEN or expected result rows.
- Always enclose Step Action or Step Expected in double quotes if the value contains a comma.
- Example for multiple user-friendly expectations:

```csv
,Test Case,GET /edge/api/v1/graph - Missing username returns 400,,,,2,Not Automated,PSS\DeltaV,,Design
,,,1,"Given the API server is running",,
,,,2,"When a GET request is sent to /edge/api/v1/graph with missing username","THEN the API should return HTTP status code 400.",,,,,
,,,3,,"AND the response should include an error message that clearly indicates the username is missing.",,,,,
```

This ensures the output is valid for Azure DevOps import and makes the Title, Given, and When steps explicit and sequential in the test case steps, while also being clear and user-friendly for manual testers.


### **File Naming and Output Location**

The generated csv file **must** be saved in the `Output` folder using the format `<feature_name>_test_cases_yyyyMMdd.N.csv`, where `N` is the next available integer (starting from 1).

**Before saving, check for existing files with the same base name and increment `N` until an unused filename is found.**

**Example:**
If `Output/GET_edge_api_v1_graph_api_test_cases_20250529.1.csv` exists, and `Output/GET_edge_api_v1_graph_api_test_cases_20250529.2.csv` exists, then the next file should be `Output/GET_edge_api_v1_graph_api_test_cases_20250529.3.csv`.