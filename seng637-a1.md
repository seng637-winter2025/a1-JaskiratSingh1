**SENG 637 - Dependability and Reliability of Software Systems**

> **Assignment \#1** > **Introduction to Testing and Defect (Bug) Tracking**  
>  Instructor: Dr. Behrouz Far (far@ucalgary.ca)
> Department of Electrical and Software Engineering
> University of Calgary

Due Date: Check D2L for the submission deadline.

# 1 Introduction

This lab is designed to provide students with a comprehensive understanding of software testing. The lab is divided into four main sections:

- Familiarization with the system under test (SUT) and the defect tracking system
- Exploratory (manual non-scripted) testing
- Manual scripted testing
- Regression testing (re-testing a system after it has been changed)

In the familiarization stage, students will explore the software system to be tested (System Under Test, or SUT), as well as a typical defect tracking
system. During the exploratory testing phase, students will be free to test the system in any manner that they choose (and are able). Once students reach
the manual scripted testing phase, they will be required to use a predefined test suite to test the SUT. Finally, students will perform some simple regression testing on an updated version of the system (corrected by imaginary developers in response to a list of defect reports), and record differing system behavior in the defect tracking system appropriately.

# Objectives

This lab is designed to provide students with a basic understanding of software testing concepts. By participating in this lab, students will gain:

- Practical experience in testing a software system
- Knowledge of the differences between exploratory, manual scripted, and regression testing
- Familiarity with industrial defect tracking systems, processes, and practices.

This lab aims to provide students with a foundational understanding of software testing so that they can apply these concepts in real-world scenarios.

# Pair Testing

In this lab, two/three students in each group will work together in "pair testing." This technique is a software development method in which two team members work at one keyboard to test the software application. One person will conduct the testing while the other reviews and analyzes the results. This technique can be used between a tester and developer, business analyst, or between two testers who take turns at the keyboard. This approach allows for more efficient and effective testing, as well as an opportunity for team members to learn from each other.

# Group Work

In this lab, each group will consist of 2 or 4 members. Two/Three members will work together in a pair testing method to complete the lab report. After the pair testing, both pairs will combine their reports and submit one final lab report.

# Submission Guidelines

All lab reports in this course should be submitted on GitHub. It is important to follow the suggested format when submitting your lab report on D2L and on GitHub.

## D2L Submission

- Please make sure to include your group number
- Provide the link to your GitHub repository
- Include the full name and student ID of all group members

## GitHub Submission

- Include your group number
- Include the first name of all group members
- It is important to note that personal information such as student ID should not be included in the GitHub submission.

- The main lab report must be submitted in the .md (Markdown File Format) only. Submitting in any other format will result in a loss of marks.
- You are not allowed to submit Microsoft Word of PDF or any other file format for your main reports.
- The attachments for example bug list and screen shots can be in any other file format

- One member of the group should be responsible for submitting the link to the GitHub repository on D2L. The due date for this assignment can be found on D2L. Make sure to submit your lab report and all necessary files before the deadline.

It is important to follow these guidelines to ensure a smooth submission process and to avoid any issues or delays.

# Issue Tracking Systems

The only tool required for this lab is an issue tracking system. In this lab, we will be using Atlassian Jira (https://www.atlassian.com/software/jira) or Azure DevOps (https://azure.com/devops) as our defect tracking system. These systems are widely used in the software industry for managing and tracking bugs and issues. They provide features such as the ability to prioritize and assign defects to developers, advanced search capabilities, and integration with email notifications. By using these systems, students will gain hands-on experience with industry-standard tools for defect tracking.

To familiarize yourself with these tools, you can use the following source or any other source of your choice:

- [Reporting bugs in Jira Software](https://marker.io/blog/jira-bug-tracking#reporting-bugs-in-jira-software)
- Azure DevOps:
  - [Create Organization](https://aex.dev.azure.com/me?mkt=en-GB)
  - [Change basic project to (agile, scrum or CMMI)](https://learn.microsoft.com/en-us/azure/devops/organizations/settings/work/change-process-basic-to-agile?view=azure-devops)
  - [How to report bug as a work item I](https://www.azuredevopsguide.com/creating-a-bug-in-azure-devops/)
  - [How to report bug as a work item I](https://learn.microsoft.com/en-us/azure/devops/boards/backlogs/manage-bugs?view=azure-devops#bug-work-item-type)

# Lab Materials

In addition to the lab document, which is to be submitted in a markdown file format, each lab in this course will require additional materials. These materials, known as lab artifacts, may include items such as the software system under test (SUT), source code, and other relevant files. It is important to submit all required lab artifacts as specified in each lab's instructions to ensure proper evaluation of your lab work.

# System Under Test

The system under test for this lab is an ATM simulation system [1]. To get started with this system, download the _seng637-a1-artifacts.zip_ file under Assignment 1. There are two versions of the ATM system inside that zip file which represent two consecutive releases of the software with bugs and bug fixes (details in the next sections):

- ATM System - Lab 1 Version 1.0
- ATM System - Lab 1 Version 1.1

1.  **Purpose of the System**

This system was originally developed in an American college (called Gordon College) in order to demonstrate an entire iteration of an object-oriented software development methodology. The entire project is available open-source online, see reference [1] for the URL. The purpose of the system is to allow the user to deposit, withdraw, query and transfer funds to/from his/her hypothetical
bank account(s).

2.  **Usage of the System**

    To use the ATM simulation system, run JAR file _ATM System – Lab 1 Version 1.0.jar_ which is inside _Assignment 1 - artifacts.zip_. The system should begin execution with the GUI as shown in Appendix A.

    There are two valid hard-coded card numbers and PINs:

    - Card Number: 1 PIN: 42 Available Accounts: Checking and Savings

    - Card Number: 2 PIN: 1234 Available Accounts: Checking and Money Market Note:

    Both of these cards access the same checking account.

    The initial balances are: Checking: \$100 Savings: \$1,000 Money Market: \$5,000

# Instructions

This section outlines the steps required to complete the lab.

## Familiarization with the ATM System

1. Run the JAR file ATM System - Lab 1 Version 1.0.jar to display the GUI

2. Turn on the system using the “On” button.

3. Enter the number of \$20 bills that the system is assumed to start with, noting that this is the number of bills, not the total value of the bills. For example, entering a value of 10 indicates that the ATM is starting with \$200 (10 twenty-dollar bills). Any number greater than 0 will suffice for now.

4. Click on the “Click to insert card” button which is now displayed on the main interface below the simulated ATM display.

5. The screen will change to a prompt for the user to input the card number (since there is no actual physical card reader). Enter 1 for the card number and press Enter. Upon returning to the main screen, the display will now request the PIN to be entered.

6. Type 42 using the simulated keypad and press Enter. The display will now prompt the user to perform one of four transactions: withdraw, deposit, transfer, or balance inquiry

7. Press 2 on the simulated keypad to perform a deposit. The display will now prompt the user to indicate which account they would like to deposit to: checking, savings, or the money market account.

8. Press 2 on the simulated keypad to deposit to the savings account. The display will now prompt the user to enter the deposit amount.

9. Enter a positive value and press Enter. A button that simulates inserting the deposit envelope will appear.

10. Click the button to simulate inserting the envelope. The display will prompt the user to perform another transaction or not.

11. Press 2 on the simulated keypad to indicate that you do not wish to perform another transaction. The main window will show a button that simulates the card being ejected.

12. Press the System Power Button again to turn off the ATM system.

## Writing Effective Bug Reports

When creating bug reports, it's important to include certain key elements that product support teams will expect and require. **When submitting your bug reports, make sure to include**:

- The function being tested (e.g. login)
- The initial state of the system (e.g. the system is on and idle)
- Detailed steps to reproduce the defect/bug (e.g. insert a card, enter the correct card number and PIN)
- The expected outcome (e.g. the system should successfully accept the customer and display the banking menu)
- The actual outcome (e.g. the system crashes or displays an error message)
- The priority or severity of the bug (low, medium, high, or critical)
- TThe version of SUT (V 1.0/ V 1.1) in which the bug was found.

## Exploratory (Manual Non-scripted) Testing

1. In order to perform any testing, the requirements must first be known. Read over the requirements for the ATM simulation system as outlined in Appendix B before continuing with the rest of this section.

2. Before beginning testing, try to come up with a high-level exploratory test plan for how you intend to test the system. Record key details of this plan, as it will be required in the lab report. This plan could include but is not limited to, information such as: functions being targeted, the approach to be taken (test most functions a little bit, or test a few functions extensively, etc.), and how you plan to come up with test cases (test most common paths, or exceptional paths, etc.).
   Keep in mind that this does not need to necessarily be the best plan, as long as it is justifiable.

3. Reporting defects: Carry out your devised exploratory test plan for roughly half an hour. Each pair of students needs to perform exploratory testing and record defects. While performing the tests, if any of the actual results differ from the expected results, report that as a defect. Record defects as they are found before forgetting the defect and its detailed conditions. At the end, two pairs of each group will review all defects and report them in the bug tracking tool.

## Manual Scripted Testing

This section is to be performed as a group. One student can ‘drive’ the testing (operate the computer executing the system under test), while the other student keeps track of which tests have been performed, reports any defects found, and determines what order to execute tests in. Keep track of what order the tests are executed in, as it will be useful information later on. Note that it does not matter which student reports the defects, as it is a group effort.

1.  In Appendix C, a basic test suite has been provided for this SUT. Execute each of the test cases at least once, verifying that the actual results match the expected results for each case. Report any defects found. In order to differentiate between defects found during this stage and the previous stage, in the summary field type “MFT:“ (Manual Functional Testing) before the summary of the defect. Do not report defects which have already been found by your group during the exploratory testing phase, however you may wish to take note of which defects are found using both testing methods as it may be relevant in your report.

2.  Upon completion of testing, review all defect reports created. To do this,perform a search (in backlog, you may need to use the your project innavigation bar then “Issues” and then “Search” feature for this) for defectscontaining “MFT:” in the summary field. This will produce a list of thenewly added defect reports. The student who was previously executing thetests should now be the main participant in reviewing the defect reports.

## Regression Testing (Verification of Defect Fixes)

This section is to be performed as a group. The defects reported in the twoprevious stages of testing can be divided among the
group members and can beretested individually.

1.  Download the updated version (version 1.1) of the ATM simulation system from blackboard. This version of the system has been partially fixed by imaginary developers based on the defect reports previously existing.

2.  Add an additional version (1.1) for your product in your bug tracking system, by simply using the same procedure for reporting the issues in version section writhe but version 1.1 (the issues for previous version should be marked as 1.0).

3.  Perform a search in your bug tracking tool for all defects reported by your group for version 1.0 of the ATM system product.

4.  Retest each of these defects to determine which have been fixed and which have not. Since we do not know which defects have been fixed exactly, assume that all defects have had an attempt to fix them. Update the defect status to Resolved (Fixed) by opening that defect for editing, and changing its status appropriately. If the defect has actually been fixed in the ATM system version 1.1, change the status once again to RSOLVED. If the defect has not actually been fixed in the ATM system version 1.1, change the status to IN-PROGRESS and write a comment stating “Defect still exists in version 1.1”.

5.  Execute steps 4 and 5 (Manual Scripted Testing) once again, looking only for new defects that have been created. If a defect is found which had previously been reported, do not report it again. When reporting these defects, ensure that version 1.1 is selected.

# Summary

Within your group, you should now each be familiar with the main features of a bug tracking system, and have a general understanding of how to use it to effectively report and track defects. You have also progressed through a short iteration of exploratory testing, two iterations of manual functional testing and an iteration of regression testing.

# Deliverables and Grading

For this assignment, you need to submit one Excel/PDF/Markdown file and the lab report.

## Defect Reports (60%)

Grading for students will be based on the quality of their defect reports, which must be submitted to their GitHub repository. They should use the designated bug tracking system to create a detailed report of any bugs found, in either PDF, Excel, or Markdown format. If the tool does not produce a report, one must be manually created.

The grading criteria (rubric) for defect reports are as follows.

| **Defect Reports**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --- |
| Correctness: Do the defect reports contain the detailed defect information:<br>- The function being tested is clearly stated?<br>- The initial state of the system is accurately described?<br>- The steps to reproduce the defect are detailed and precise?<br>- The expected outcome is correctly mentioned?<br>- The actual outcome is clearly stated?<br>- The priority or severity of the bug is appropriately classified?<br>- The version of the SUT in which the bug was found is correctly noted?<br>- Has the status of the bug changed after the regression test? | 40% |
| Number of defects found: Note that not all defects need to be found. But if it appears that not enough effort was made in finding defects, marks may be deducted.                                                                                                                                                                                                                                                                                                                                                                                                            | 20% |

## Lab Report (40%)

To be consistent, please use the template markdown file “seng637-1-team_number.md” provided online. Change the team number to your team number. If desired, feel free to rename the sections, as long as the headings are still descriptive and accurate.

| **Lab Report**                                                                                                                                                                                                                                   |     |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --- |
| Test plan including (check [Test_Plan_Sample.pdf](https://d2l.ucalgary.ca/d2l/le/content/570970/viewContent/6290762/View) on D2L for more information):<br>- Test Types<br>- Scope of Testing<br>- Test Logistics (Who tests each functionality) | 15% |
| A comparison of exploratory and manual functional testing (based on the provided test suite) from several perspectives (e.g., benefits, tradeoffs, effectiveness, efficiency, etc.)                                                              | 15% |
| Notes and discussion of the peer reviews of defect reports created by each pair in a group.                                                                                                                                                      | 5%  |

| **Reflection and Learning**                                                                                                                                              |     |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --- |
| Any difficulties encountered, challenges overcome, and lessons learned from performing the lab                                                                           | 2%  |
| Comments/feedback on the lab and lab document itself. (Did you find it a useful practice? Was it easy to follow?) Please try to keep comments and feedback constructive. | 3%  |

# Acknowledgements

This lab is part of a software-testing laboratory course available under a Creative Commons license.

Some part of this document has been developed in the former SoftQual lab of University of Calgary for teaching SENG 637.

# References

- [1] R. C. Bjork, "Example ATM Simulation System," Internet: http://www.math-cs.gordon.edu/courses/cps211/ATMExample/ [Jan, 2017]
- [2] J. B. Cem Kaner, Bret Pettichord, "Chapter 4 - Bug Advocacy," in Lessons Learned in Software Testing, New York: John Wiley & Sons Inc., 2002.
- [3] C. Kaner, "Assignment - Replicate and Edit Bugs," 2008.

# Appendix

## Appendix A: GUI

![](media/sut-gui.jpeg)

## Appendix B: High Level Requirements

The software to be designed will control a simulated Automated Teller Machine
(ATM) having a magnetic stripe reader for reading an ATM card, a customer
console (keyboard and display) for interaction with the customer, a slot for
depositing envelopes, a dispenser for cash (in multiples of \$20), a printer for
printing customer receipts, and a key-operated switch to allow an operator to
start or stop the machine. The ATM will communicate with the bank's computer
over an appropriate communication link. (The software on the latter is not part
of the requirements for this problem.)

The ATM will service one customer at a time. A customer will be required to
insert an ATM card and enter a Personal Identification Number (PIN) - both of
which will be sent to the bank for validation as part of each transaction. The
customer will then be able to perform one or more transactions. The card will be
retained in the machine until the customer indicates that he/she desires no
further transactions, at which point it will be returned - except as noted
below.

> The ATM must be able to provide the following services to the customer:

- A customer must be able to make a cash withdrawal from any suitable account
  linked to the card, in multiples of

  \$20.00. Approval must be obtained from the bank before cash is dispensed.

  - A customer must be able to make a deposit to any account linked to the
    card, consisting of cash and/or checks in an envelope. The customer will
    enter the amount of the deposit into the ATM, subject to manual
    verification when the envelope is removed from the machine by an
    operator. Approval must be obtained from the bank before physically
    accepting the envelope.

    - A customer must be able to make a transfer of money between any two
      accounts linked to the card.

    - A customer must be able to make a balance inquiry of any account
      linked to the card.

    - A customer must be able to abort a transaction in progress by
      pressing the Cancel key instead of responding to a request from the
      machine.

The ATM will communicate each transaction to the bank and obtain verification
that it was allowed by the bank. Ordinarily, a transaction will be considered
complete by the bank once it has been approved. In the case of a deposit, a
second message will be sent to the bank indicating that the customer has
deposited the envelope. (If the customer fails to deposit the envelope within
the timeout period, or presses cancel instead, no second message will be sent to
the bank and the deposit will not be credited to the customer.)

If the bank determines that the customer's PIN is invalid, the customer will be
required to re-enter the PIN before a transaction can proceed. If the customer
is unable to successfully enter the PIN after three tries, the card will be
permanently retained by the machine, and the customer will have to contact the
bank to get it back.

If a transaction fails for any reason other than an invalid PIN, the ATM will
display an explanation of the problem, and will then ask the customer whether
he/she wants to do another transaction.

The ATM will provide the customer with a printed receipt for each successful
transaction, showing the date, time, machine location, type of transaction,
account(s), amount, and ending and available balance(s) of the affected account
("to" account for transfers).

The ATM will have a key-operated switch that will allow an operator to start and
stop the servicing of customers. After turning the switch to the "on" position,
the operator will be required to verify and enter the total cash on hand. The
machine can only be turned off when it is not servicing a customer. When the
switch is moved to the "off" position, the machine will shut down, so that the
operator may remove deposit envelopes and reload the machine with cash, blank
receipts, etc.

The ATM will also maintain an internal log of transactions to facilitate
resolving ambiguities arising from a hardware failure in the middle of a
transaction. Entries will be made in the log when the ATM is started up and shut
down, for each message sent to the Bank (along with the response back, if one is
expected), for the dispensing of cash, and for the receiving of an envelope. Log
entries may contain card numbers and dollar amounts, but for security will
_never_ contain a PIN.

## Appendix C: SUT Use Cases

![](media/sut-usecases.jpeg)

| **Test Case \#** | **Use Case**         | **Function Being Tested**                                        | **Initial System State**                                    | **Input**                                             | **Expected Output**                                                                      | **Ver. 1.0 Actual Output**                                                                                             | **Ver. 1.1 Actual Output**                                                               | **Steps to Reproduce**                                                            | **Priority / Severity** | **Version Found** | **Bug / Defect Status** |
|------------------|----------------------|------------------------------------------------------------------|-------------------------------------------------------------|-------------------------------------------------------|------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------|------------------------|-------------------|-------------------------|
| 1                | **System Startup**   | System is started when switch is turned "on"                     | System is off                                               | Activate the "on" switch                              | System requests initial cash amount                                                      | System requests initial cash amount                                                                                     | System requests initial cash amount                                                      | 1. Power on system<br>2. Flip ON switch                                          | N/A                    | N/A               | N/A                     |
| 2                | **System Startup**   | System accepts initial cash amount                               | System is requesting cash amount                            | Enter a legitimate amount                             | System is on                                                                             | System is on                                                                                                            | System is on                                                                             | 1. Start system<br>2. Enter valid amount (e.g., $2000)                           | N/A                    | N/A               | N/A                     |
| 3                | **System Startup**   | Connection to the bank is established                            | System has just been turned on                              | Perform a legitimate inquiry transaction              | Connection to the Bank is demonstrated                                                  | Connection to the Bank is demonstrated                                                                                  | Connection to the Bank is demonstrated                                                  | 1. Start system<br>2. Immediately request an inquiry                            | N/A                    | N/A               | N/A                     |
| 4                | **System Shutdown**  | System is shut down when switch is turned "off"                  | System is on and not servicing a customer                   | Activate the "off" switch                             | System is off                                                                            | System is off                                                                                                           | System is off                                                                            | 1. System ON<br>2. Flip OFF switch                                              | N/A                    | N/A               | N/A                     |
| 5                | **Session**          | System reads a customer's ATM card                               | System is on & not servicing a customer                     | Insert a readable card                                | Card accepted; System asks for PIN                                                      | Card accepted; System asks for PIN                                  | Same as expected                                                                  | 1. System ON<br>2. Insert readable card<br>3. Observe if card flows normally     | N/A        | N/A               | N/A                    |
| 6                | **Session**          | System rejects an unreadable card                                | System is on & not servicing a customer                     | Insert an unreadable card                             | Card ejected; Error screen displayed; Ready for new session                             | **Card not ejected** but asked for PIN → then card ejected, no error on screen                                                                                                        | Same error as Ver 1.0                                                                       | 1. System ON<br>2. Insert damaged/misaligned card<br>3. Check system response   | High/Critical                    | 1.0               | Open                     |
| 7                | **Session**          | System accepts customer's PIN                                    | System is asking for entry of PIN                           | Enter a PIN                                           | System displays a menu of transaction types                                              | Same as expected                                                                                                        | Same as expected                                                                        | 1. Insert card<br>2. Enter valid PIN                                             | N/A                    | N/A               | N/A                     |
| 8                | **Session**          | System allows customer to perform a transaction                  | Menu of transaction types displayed                          | Perform a transaction                                 | System asks if customer wants another transaction                                        | Same as expected                                                                                                        | Same as expected                                                                        | 1. Insert card<br>2. Enter valid PIN<br>3. Select valid transaction option       | N/A                    | N/A               | N/A                     |
| 9                | **Session**          | System allows multiple transactions in one session               | System is asking whether customer wants another transaction | Answer yes                                            | System displays a menu of transaction types                                              | Same as expected                                                                                                        | Same as expected                                                                        | 1. Insert card<br>2. Enter valid PIN<br>3. Choose transaction<br>4. When asked, choose "yes" | N/A            | N/A               | N/A                     |
| 10               | **Session**          | Session ends when customer chooses not to do another transaction | System is asking whether customer wants another transaction | Answer no                                             | System ejects card; Ready for new session                                               | Same as expected                                                                                                        | Same as expected                                                                        | 1. Insert card<br>2. Complete transaction<br>3. Choose "no" at prompt           | N/A                    | N/A               | N/A                     |

| **Test Case #** | **Use Case**         | **Function Being Tested**                                         | **Initial System State**                                          | **Input**                                             | **Expected Output**                                                                                              | **Ver. 1.0 Actual Output**                                                                                 | **Ver. 1.1 Actual Output**                                                       | **Steps to Reproduce**                                                                             | **Priority / Severity** | **Version Found** | **Bug / Defect Status** |
|-----------------|----------------------|-------------------------------------------------------------------|--------------------------------------------------------------------|-------------------------------------------------------|------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------|------------------------|-------------------|-------------------------|
| 11              | **Transaction**      | System handles an invalid PIN properly                            | A readable card has been entered                                  | Enter an incorrect PIN, then attempt a transaction    | The Invalid PIN exception is performed                                                                          | Same as expected                                                                                       | Same as expected                                                                   | 1. Insert card<br>2. Enter incorrect PIN<br>3. Attempt transaction                               | N/A                    | N/A               | N/A                     |
| 12              | **Withdrawal**       | System asks for account to withdraw from                          | Menu of transaction types displayed                               | Choose Withdrawal transaction                          | System displays a menu of account types                                                                           | Same as expected                                                                                       | Same as expected                                                                   | 1. Insert card<br>2. Enter PIN<br>3. Choose "Withdrawal"                                          | N/A                    | N/A               | N/A                     |
| 13              | **Withdrawal**       | System asks for withdrawal amount                                 | Menu of account types displayed                                   | Choose checking account                               | System displays a menu of possible withdrawal amounts                                                            | Same as expected                                                                                       | Same as expected                                                                   | 1. Choose "Withdrawal" → Checking<br>2. Observe next step                                         | N/A                    | N/A               | N/A                     |
| 14              | **Withdrawal**       | Legitimate withdrawal transaction                                 | Menu of withdrawal amounts displayed                               | Choose amount ≤ system cash & ≤ account balance       | Cash dispensed; Correct receipt (amount + new balance); Tx logged                                                | **Dispenses wrong amount** (the next higher option), but receipt/log show correct withdrawal             | **Fixed** in Ver. 1.1 (dispenses correct amount, receipt/log correct)                               | 1. Insert card<br>2. Enter PIN<br>3. Withdrawal → pick known valid amount                           | High / Major            | 1.0               | Resolved in 1.1         |
| 15              | **Withdrawal**       | Verifies sufficient cash on hand                                  | System < max withdrawal in cash; waiting for amount                | Choose an amount > system’s current on-hand cash      | System shows message; asks for a different amount                                                                | Same as expected                                                                                       | Same as expected                                                                   | 1. Insert card<br>2. Enter PIN<br>3. Choose large withdrawal amount > ATM’s on-hand               | N/A                    | N/A               | N/A                     |
| 16              | **Withdrawal**       | Verifies customer's balance is sufficient                         | System is requesting a withdrawal amount                           | Choose an amount ≤ ATM cash but > customer’s balance  | Message displayed; offers another transaction or exit                                                             | **Does not** offer another transaction                                                                    | Correctly offers another transaction or exit                                                       | 1. Insert card<br>2. Enter PIN<br>3. Withdrawal > user’s balance                                    | Medium        | 1.0               | Resolved in 1.1 |
| 17              | **Withdrawal**       | Can be canceled before choosing a dollar amount (account-type menu) | System is displaying menu of account types                          | Press "Cancel" key                                  | Displays message; offers another transaction or not                                                              | Same as expected                                                                                       | Same as expected                                                                   | 1. Insert card<br>2. Enter PIN<br>3. Choose “Withdrawal” → then press “Cancel”                     | N/A                    | N/A               | N/A                     |
| 18              | **Withdrawal**       | Can be canceled before choosing a dollar amount (amount menu)     | System is displaying menu of dollar amounts                         | Press "Cancel" key                                    | Displays message; offers another transaction or not                                                              | Same as expected                                                                                       | Same as expected                                                                   | 1. Insert card<br>2. Enter PIN<br>3. Withdrawal → choose account → press “Cancel” at amounts list | N/A                    | N/A               | N/A                     |
| 19              | **Deposit**          | Asks customer to choose an account to deposit to                  | Menu of transaction types displayed                               | Choose Deposit transaction                            | System displays a menu of account types                                                                          | Same as expected                                                                                       | Same as expected                                                                   | 1. Insert card<br>2. Enter PIN<br>3. Choose “Deposit”                                              | N/A                    | N/A               | N/A                     |
| 20              | **Deposit**          | Asks customer to enter a dollar amount to deposit                 | Menu of account types displayed                                   | Choose checking account                               | System displays request to type a dollar amount                                                                  | Same as expected                                                                                       | Same as expected                                                                   | 1. Insert card<br>2. Choose “Deposit → Checking” → observe request for amount                      | N/A                    | N/A               | N/A                     |

| **Test Case #** | **Use Case**  | **Function Being Tested**                                                                                 | **Initial System State**                                           | **Input**                                   | **Expected Output**                                                                                                                                     | **Ver. 1.0 Actual Output**                                                                                    | **Ver. 1.1 Actual Output**                                                                           | **Steps to Reproduce**                                                                                                         | **Priority / Severity** | **Version Found** | **Bug / Defect Status** |
|-----------------|---------------|------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------|---------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------|------------------------|-------------------|-------------------------|
| 21              | **Deposit**   | System asks customer to insert an envelope                                                                | System is displaying request to type deposit amount                 | Enter a legitimate dollar amount           | System requests envelope                                                                                                                                | Same as expected                                                                                            | Same as expected                                                                                 | 1. Insert card<br>2. Enter PIN<br>3. Deposit → Checking → Enter $ → Wait for envelope prompt                             | N/A                    | N/A               | N/A                     |
| 22              | **Deposit**   | Legitimate deposit transaction                                                                            | System requesting envelope insertion                                | Insert an envelope                         | Envelope accepted; Correct receipt (amount + updated balance); Tx logged                                                                               | **Updated balance is incorrect** (only half is added), but log is correct                                   | **Still an issue** but slightly different: adds $19.90 on $20 deposit. Log remains correct.                     | 1. Insert card<br>2. PIN<br>3. Deposit → Checking → Enter $20 → Insert envelope → Confirm deposit     | High / Major            | 1.0 + 1.1               | Open                    |
| 23              | **Deposit**   | Deposit can be canceled before inserting envelope (on account-type menu)                                 | Menu of account types displayed                                     | Press "Cancel" key                         | Displays message; offers another transaction or not                                                                                                    | Same as expected                                                                                            | Same as expected                                                                                 | 1. Insert card<br>2. Enter PIN<br>3. Choose “Deposit” → press “Cancel” at account menu                                  | N/A                    | N/A               | N/A                     |
| 24              | **Deposit**   | Deposit can be canceled before inserting envelope (on amount prompt)                                     | System requesting a dollar amount                                   | Press "Cancel" key                         | Displays message; offers another transaction or not                                                                                                    | Same as expected                                                                                            | Same as expected                                                                                 | 1. Insert card<br>2. PIN<br>3. Deposit → Checking → press “Cancel” before typing amount                                | N/A                    | N/A               | N/A                     |
| 25              | **Deposit**   | Deposit can be canceled before inserting envelope (on envelope prompt)                                   | System requesting envelope insertion                                | Press "Cancel" key                         | Displays message; offers another transaction or not                                                                                                    | Same as expected                                                                                            | Same as expected                                                                                 | 1. Insert card<br>2. PIN<br>3. Deposit → Checking → Enter $ → press “Cancel” at envelope prompt                       | N/A                    | N/A               | N/A                     |
| 26              | **Transfer**  | Asks customer to choose an account to transfer **from**                                                   | Menu of transaction types displayed                                | Choose Transfer transaction                | System displays a menu of account types specifying transfer-from                                                                                         | Same as expected                                                                                            | Same as expected                                                                                 | 1. Insert card<br>2. Enter PIN<br>3. Choose “Transfer”                                              | N/A                    | N/A               | N/A                     |
| 27              | **Transfer**  | Asks customer to choose an account to transfer **to**                                                     | Menu of account types for transfer-from displayed                   | Choose checking account                    | System displays menu of account types specifying transfer-to                                                                                            | Same as expected                                                                                            | Same as expected                                                                                 | 1. Choose Transfer → pick “Checking” → see next menu for “Transfer-To”                               | N/A                    | N/A               | N/A                     |
| 28              | **Transfer**  | Asks customer to enter a dollar amount to transfer                                                        | Menu of account types for transfer-to displayed                     | Choose savings account                     | System displays request to type a dollar amount                                                                                                         | Same as expected                                                                                            | Same as expected                                                                                 | 1. Choose Transfer → Checking → then choose “Savings” → see request for amount                       | N/A                    | N/A               | N/A                     |
| 29              | **Transfer**  | Legitimate transfer transaction                                                                           | System displaying request for transfer amount                       | Enter a legitimate dollar amount           | Correct receipt (amount + updated balance); Tx logged (bank message + approval)                                                                          | **Incorrect** amount on receipt (e.g., transferring $20 but receipt shows $19.50). Available cash is the same as Savings Balance.       | Now displays correct transfer and correct balance.                                                            | 1. Insert card<br>2. Enter PIN<br>3. Transfer → Checking → Savings → Enter $20 → Confirm          | Medium / Major          | 1.0               | Resolved in 1.1         |
| 30              | **Transfer**  | Transfer can be canceled before entering amount (on “transfer-from” menu)                                | System is displaying menu of account types specifying transfer-from | Press “Cancel” key                        | Displays an appropriate message; offers another transaction or not                                                                                      | Same as expected                                                                                            | Same as expected                                                                                 | 1. Insert card<br>2. Enter PIN<br>3. Transfer → press “Cancel” at the first account-type prompt                      | N/A                    | N/A               | N/A                     |

| **Test Case #** | **Use Case**               | **Function Being Tested**                                                                                                | **Initial System State**                                          | **Input**                                                 | **Expected Output**                                                                                                                   | **Ver. 1.0 Actual Output**                                                                                  | **Ver. 1.1 Actual Output**                                                                   | **Steps to Reproduce**                                                                                                                  | **Priority / Severity** | **Version Found** | **Bug / Defect Status**    |
|-----------------|----------------------------|---------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------|-----------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------|------------------------|-------------------|----------------------------|
| 31              | **Transfer**              | Transfer can be canceled before entering amount (on “transfer-to” menu)                                                  | Menu of account types specifying transfer-to displayed             | Press “Cancel” key                                        | Displays an appropriate message; offers another transaction or not                                                                                | Same as expected                                                                                           | Same as expected                                                                                 | 1. Insert card<br>2. Enter PIN<br>3. Transfer → choose “Checking” → see “Transfer-To” → press Cancel                                | N/A                    | N/A               | N/A                        |
| 32              | **Transfer**              | Transfer can be canceled before entering amount (on amount prompt)                                                        | System is requesting a dollar amount                               | Press “Cancel” key                                        | Displays an appropriate message; offers another transaction or not                                                                                | Same as expected                                                                                           | Same as expected                                                                                 | 1. Insert card<br>2. Enter PIN<br>3. Transfer → choose from/to accounts → press Cancel when asked for amount                       | N/A                    | N/A               | N/A                        |
| 33              | **Inquiry**               | Asks customer to choose an account to inquire about                                                                       | Menu of transaction types displayed                                | Choose Inquiry transaction                                | System displays a menu of account types                                                                                                            | **Does not** display Savings account in the menu                                                            | Displays all account types (fixed)                                                          | 1. Insert card<br>2. Enter PIN<br>3. Choose “Inquiry” → check menu of accounts                                          | Medium / Major          | 1.0               | Resolved in 1.1            |
| 34              | **Inquiry**               | Legitimate inquiry transaction                                                                                           | Menu of account types displayed                                    | Choose checking account                                   | Receipt with correct balance; Tx logged (bank message + approval)                                                                                 | Same as expected                                                                                           | Same as expected                                                                                 | 1. Insert card<br>2. PIN<br>3. Inquiry → Checking → confirm                                                     | N/A                    | N/A               | N/A                        |
| 35              | **Inquiry**               | Inquiry can be canceled before choosing an account                                                                       | Menu of account types displayed                                    | Press “Cancel” key                                        | Displays an appropriate message; offers another transaction or not                                                                                | Same as expected                                                                                           | Same as expected                                                                                 | 1. Insert card<br>2. PIN<br>3. Inquiry → press “Cancel” before choosing account                                       | N/A                    | N/A               | N/A                        |
| 36              | **Invalid PIN Extension** | Customer is asked to reenter PIN if initial PIN is incorrect                                                              | System is asking for entry of PIN                                  | Enter incorrect PIN, attempt an inquiry on checking acct  | Customer is asked to re-enter PIN                                                                                                                 | Same as expected                                                                                           | Same as expected                                                                                 | 1. Insert card<br>2. Enter wrong PIN<br>3. Attempt Inquiry → see prompt to re-enter PIN                             | N/A                    | N/A               | N/A                        |
| 37              | **Invalid PIN Extension** | Correct re-entry of PIN is accepted                                                                                       | Request to re-enter PIN displayed                                  | Enter correct PIN                                         | Original transaction completes successfully                                                                                                       | **Transaction not completed**; request to re-enter PIN even though latest reattempt at entering PIN is correct                         | Same issue persists                                                                                 | 1. Insert card<br>2. Wrong PIN<br>3. Re-enter correct PIN → watch if transaction proceeds                           | High / Major            | 1.0 + 1.1               | Open                        |
| 38              | **Invalid PIN Extension** | Incorrect re-entry is not accepted                                                                                       | Request to re-enter PIN displayed                                  | Enter incorrect PIN again                                 | Displays an appropriate message, prompts PIN re-entry once more                                                                                   | Same as expected                                                                                           | Same as expected                                                                                 | 1. Insert card<br>2. Wrong PIN<br>3. Wrong PIN again → watch system’s response                                  | N/A                    | N/A               | N/A                        |
| 39              | **Invalid PIN Extension** | Correct PIN on second try is accepted                                                                                    | Request to re-enter PIN displayed                                  | Enter incorrect PIN first, then correct PIN               | Original transaction completes successfully                                                                                                       | **Transaction still not completed** request to re-enter PIN even though latest reattempt at entering PIN is correct                                   | Same issue persists                                                                                 | 1. Insert card<br>2. Wrong PIN<br>3. Another wrong PIN<br>4. Correct PIN → see if transaction goes through          | High / Major            | 1.0 + 1.1              | Open                        |
| 40              | **Invalid PIN Extension** | Correct PIN on third try is accepted                                                                                     | Request to re-enter PIN displayed                                  | Enter incorrect PIN twice, correct on third try           | Original transaction completes successfully                                                                                                       | **Transaction still not completed** request to re-enter PIN even though latest reattempt at entering PIN is correct                             | Same issue persists                                                                                 | 1. Insert card<br>2. Enter wrong PIN x2<br>3. Third attempt correct → see if transaction is allowed                | High / Major            | 1.0 + 1.1              | Open                        |



**Exploratory Testing Defects**
| **Test Case #** | **Use Case**  | **Function Being Tested**                                     | **Initial System State**                        | **Input**                                                  | **Expected Output**                                                                                      | **Ver. 1.0 Actual Output**                                                                            | **Ver. 1.1 Actual Output**                                  | **Steps to Reproduce**                                                                                               | **Priority / Severity** | **Version Found** | **Bug / Defect Status** |
|-----------------|--------------|--------------------------------------------------------------|------------------------------------------------|------------------------------------------------------------|--------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------|------------------------------------------------------------|----------------------------------------------------------------------------------------------------------|------------------------|-------------------|-------------------------|
| 1              | **Session**          | System rejects an invalid card number gracefully         | System is on and idle                                    | Enter an invalid card number (e.g., "3"), then input a PIN | System rejects the card and does not proceed to PIN entry       | **ATM becomes unresponsive after invalid card number is entered** | **Fixed:** ATM rejects invalid card and remains operational | 1. Start ATM<br>2. Insert a card with an invalid number (e.g., "3")<br>3. Enter any PIN<br>4. Observe system response | **Critical**             | **1.0**           | **Resolved in 1.1**    |
| 2              | **Inquiry**          | System displays all linked accounts for balance inquiry | ATM is operational, user has multiple accounts linked  | Insert ATM card<br>Enter PIN<br>Select "Balance Inquiry"<br>Choose "Savings Account" | ATM communicates with the bank, retrieves and displays the balance for savings account | **Savings Account option is missing from the list of accounts for balance inquiry** | **Fixed** as expected now | 1. Insert card<br>2. Enter PIN<br>3. Select "Balance Inquiry"<br>4. Check if Savings Account appears | **Critical**             | **1.0 only**      | **Open**    |
|3               | **Deposit**          | System correctly updates account balance after deposit | ATM is operational, card #1 has $100 in chequing         | Insert ATM card<br>Enter PIN<br>Select "Deposit"<br>Choose "Chequing"<br>Deposit $1000 | New balance should be **$1100** ($100 initial + $1000 deposit) | **Balance takes away $10 upon every deposit** | **Issue persists in Version 1.1; incorrect balance calculation varied but remains** | 1. Insert ATM card<br>2. Enter PIN<br>3. Select "Deposit"<br>4. Choose "Chequing"<br>5. Deposit $1000<br>6. Check displayed balance | **Critical**             | **1.0 + 1.1**      | **Open**    |
| 4              | **Transfer**  | Receipt shows correct "Transfer From" and "Transfer To"     | ATM is operational, user has Checking & Savings | Choose Transfer → Checking to Savings<br>Enter $20.00      | Receipt correctly shows **"TRANSFER FROM: CHKG TO: SVGS"**                                            | **Receipt incorrectly shows "TRANSFER FROM: SVGS TO: CHKG"**, reversing the accounts.                | Same issue persists| 1. Insert ATM card<br>2. Enter PIN<br>3. Select "Transfer"<br>4. Choose "Checking" to transfer from<br>5. Choose "Savings" to transfer to<br>6. Enter $20.00<br>7. Review printed receipt | **Critical**             | 1.0 + 1.1           | Open    |
| 5              | **User Interface**    | On-screen text displays correctly without typos         | User navigating ATM transaction prompts              | Insert ATM card<br>Enter PIN<br>Begin a transaction (e.g., withdrawal, deposit)<br>Select "Cancel"<br>Observe on-screen messages | All on-screen text should be correctly spelled (e.g., "Would you like to do another transaction?") | **"Would" is misspelled as "wood" in multiple transaction messages** | **Fixed** as expected now | 1. Insert ATM card<br>2. Enter PIN<br>3. Start a transaction (withdrawal, deposit, etc.)<br>4. Select "Cancel"<br>5. Observe on-screen text | **Minor**                 | **1.0 only**      | **Resolved in 1.1**    |
| 6              | **Inquiry**          | Savings balance inquiry displays correct information | ATM is operational, user has a savings account      | Insert ATM card<br>Enter PIN<br>Select "Balance Inquiry"<br>Choose "Savings Account" | ATM should ask if user wants another transaction and print a receipt with the correct available balance | **ATM displays "unknown error" and dispenses $500 without user input** | **Issue persists in Version 1.1; incorrect ATM behavior remains** | 1. Insert ATM card<br>2. Enter PIN<br>3. Select "Balance Inquiry"<br>4. Choose "Savings Account"<br>5. Observe ATM display and cash output | **Critical**             | **1.1 only**      | **Open**    |
| 7              | **User Interface**    | Withdrawal screen displays correct formatting for cash amounts | ATM is operational, user has funds in checking/savings account | Insert ATM card<br>Enter PIN<br>Select "Withdrawal" <br> Choose any account | The ATM should display cash withdrawal options with proper formatting (e.g., $60) |  The amount for 60 is displayed as 60 without the $ sign  | **Issue persists in Version 1.1; incorrect formatting remains** | 1. Insert ATM card<br>2. Enter PIN<br>3. Select "Withdrawal"<br>4. Choose any account<br>5. Observe cash withdrawal options | **Minor**                 | **1.1 only**      | **Open**    |
| 8              | **Inquiry**          | Money Market Balance Inquiry functions correctly | ATM is operational | Insert ATM card<br>Enter PIN<br>Select "Balance Inquiry"<br>Choose "Money Market" account | The ATM should display the correct balance for the Money Market account and ask if the user wants another transaction | **Console displays "unknown error" and dispenses free money ($500) instead of showing the balance** | **Fixed in Version 1.1; Money Market balance inquiry functions correctly** | 1. Insert ATM card<br>2. Enter PIN<br>3. Select "Balance Inquiry"<br>4. Choose "Money Market" account<br>5. Observe ATM response | **Critical**             | **1.0 only**      | **Resolved in 1.1**    |
| 9             | **Transaction Selection** | Selecting transaction type "5" functions correctly | ATM is operational, user selecting transaction type | Insert ATM card<br>Enter PIN<br>Select transaction type "5" | ATM should navigate to the correct transaction screen and not dispense money | **Selecting transaction type "5" dispenses free $20 on Windows**<br>**Lags on Macs** | **Issue persists in Version 1.1; incorrect transaction behavior remains** | 1. Insert ATM card<br>2. Enter PIN<br>3. Select transaction type "5"<br>4. Observe ATM behavior | **Critical**             | **1.0 + 1.1**      | **Open**    |
| 10              | **Session**          | ATM correctly identifies inserted card | ATM is operational, user inserts card for transaction | Insert Card 1 → Observe displayed card number<br>Insert Card 2 → Observe displayed card number | The ATM should display the correct card number for the inserted card | **Card numbers are indexed incorrectly**<br>**Insert Card 1 → Displays as Card 2**<br>**Insert Card 2 → Displays as Card 3** | **Issue persists in Version 1.1; incorrect card indexing remains** | 1. Insert Card 1 → Check displayed card number<br>2. Insert Card 2 → Check displayed card number | **Critical**             | **1.0 + 1.1**      | **Open**    |