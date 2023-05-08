Download Link: https://assignmentchef.com/product/solved-solvedhockey-player-statistics-program-solution
<br>
A. Lab # CIS CIS170A-A1

B. Lab 7 of 7: Files, Menus, and Other Controls

C. Lab Overview – Scenario / Summary:

TCOs:

9. Given a set of program specifications for a simple menu-driven application, code and test the program that meets the specifications and employs best programming practices.

13. Given a set of program specifications for a simple business problem requiring file input/output, code and test the program, and ensure that it meets the specifications and employs best programming practices.

This lab will familiarize the student with the processes required to manipulate data with text files.

D. Deliverables:

StepDeliverablePoints5Program Listing, Output, and Project Files45

The Dropbox deliverables include the following:

1. Include a zipped file with all the files from your Visual Basic project (see directions in Doc Sharing on how to collect and zip files).

2. Create a single MS Word document and include the following:

· For each lab, copy and paste your code directly into the MS Word file.

· Include screenshot(s) of your test data with test results. Enter enough data to demonstrate that all your code has been tested.

· Include another screenshot of the Visual Basic build output messages. Check your build output to make sure you have a successful build with (0) errors and (0) warnings. NOTE: The build output messages appear at the bottom of your window after you click the Build menu and before you click the Start Without Debugging option. Your build output messages provide a list of compiler warnings or errors and let you know if your program compiled successfully.

· Include the Word document as part of the zipped project file.

3. Upload each part of the lab into its corresponding weekly Dropbox.

E. Lab Steps:

Preparation:

If you are using the Citrix remote lab, follow the login instructions located in the iLab tab in Course Home.

Locate the Visual Studio 2010 icon on the desktop. Click to open.

Lab:

Step 1: Create a New Project

Create a new project in VB.NET. Name your project CIS170A_Lab07

In the Week 5 Hockey Player Statistics program, we modularized the design and, along with the techniques demonstrated in the Week 6 Room Rental program, we began to realize the benefits of creating modular programs. We noticed that while the communication between modules adds some complexity to the program design, being able to compartmentalize the program’s operations into self-contained modules reduces the logical complexity of the program. We also are able to reuse modules not only within a single program, but some modules can be reused with little or no modification between programs. As a result, the efficiency and productivity improvements we gain from creating modular programs outweigh the perceived communication complexity.

Note, we say “perceived communication complexity” because once you gain more experience, you will begin to recognize that creating well-defined communication interfaces will become easier, but a well-designed interface will make your programs more reliable and improve your ability to reuse modules, and actually reduce complexity. However, this is always difficult to see when you are first exposed to modular programming and creating interfaces.

This week, we are going to further investigate the benefits of modular programming by taking the Week 5 Hockey Player Statistics program and adding some additional operations and features. The important point to realize here is that since we have modularized the baseline version of the Hockey Player Statistics program, adding the additional operations into the program will have little effect on what we have already accomplished. That is, we can add additional modules to the program that implement the new requirements with only minimal effect to the other modules. This is another major benefit of creating modular programs and is a design objective of every real world, professional development team.

One final note as you review the analysis and design information: most of the design given below was implemented in Week 5 and in this lab we are just adding to what we have already done. However, the full set of flowcharts, objects, and event tables are given below for completeness. You will notice that the changes to the design have been highlighted with notes and comments.

Step 2: Program Description

As a reminder, here are the requirements of the Week 5 program.

Create a program that will calculate and display the career statistics for a hockey player. The program will input the name of the hockey player and the name must be a non-empty string. The number of seasons played, which must be at least one season and no more than 20 seasons, must be provided. Processing the goals and assists cannot start until a valid season value is provided. Once the valid season value is provided, the program will prompt the user to provide the number of goals and assists for each season. The valid number of goals is between 0 and 60 and the valid number of assists is between 0 and 60. The program will keep a running total of the number of goals, the number of assists, and the total points. Also, a list of the each season’s data will be displayed after the season data is provided. Once all the season data is collected, the program shall list the summary information for the player and all the seasons.

1. The customer for your program has decided that they want to change the upper limits for the goals, assists, and seasons. They want the upper limit of the seasons to be 25, the upper limit for the goals to be 70, and the upper limit for assists to be 75.

2. As with most programs that collect names of individuals, the full name shall be broken into two parts: the first name and the last name. Both the first and last name must contain non-empty string values.

3. The customer wants to keep track of how old the player was when he or she started playing hockey, so the program shall provide a field to collect and validate the age of the player when he or she was a rookie. The starting age shall be at least 18 years old and no more than 30 years old, and the age shall be displayed as part of the summary output.

4. The user cannot begin to collect season data until after the first name, last name, seasons, and age are all provided and validated.

New Requirements:

The following are the new requirements that need to be added to the Week 5 Hockey Player Statistics Program:

1. The user shall be able to input information for multiple players. After each player and the number of seasons information is input, the program shall write the summary information for the player to a file called “PlayerStats.txt”. Any previous information that is saved in the file shall be preserved and not lost.

2. Once a player’s summary information has been written to the file, the program shall automatically clear all the input fields and output information for the player and be ready to accept data about another player.

3. Create a second form titled “Player Summary” that shall have operations to open the “PlayerStats.txt” file and display all the summary records for all the saved players.

4. The Player Summary form shall have an operation to clear the contents of the “PlayerStats.txt” file.

5. Exception handling for file operations shall be included to prevent the program from crashing when the files are opened or read.

6. The main form (frmHockeyStats) shall contain a menu that will have two menu items: “File” and “Tools”.

7. Under the “File” menu, there shall be menu items to “Clear” the fields and “Exit” the application.

8. Under the “Tools” menu, there shall be menu items to “Get Player Statistics” and “Summary Data” that opens the summary information forms.

9. Each control (except labels) will have a Tooltip with a short, user-friendly description of what the control provides.

The updated hierarchy chart, which shows the structure and flowchart of the program, is given below. The flowchart for the overall program and each of the modules listed in the hierarchy chart are also provided below. Notice the changes in the modules are given in bold and that the button events and the menu item events use the same modules to perform the operations.

Before you begin constructing your program, ensure that you review these diagrams carefully and pay attention to the comments in the call out boxes. Also, it is highly recommended that you refer to these diagrams often while you are building your program. Finally, all the diagrams are provided, even those that have not changed have been included.

Step 3: Build the FormThe following is the Object, Property, Setting, Event chart for the form controls, and each input field will have a label/input field pair. Also, group the related information in the associated group box.

The form and form controls will be logically placed on the form, the controls aligned and sized, and a logical tab order will be assigned to each of the form controls.

Hint: Button and Menu controls can use the same Click event handler, such as:

Private Sub btnGetStats_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles _

btnGetStats.Click, _

mnuGetStats.Click

Hint: When creating files, use the default path “bindebug”. This will allow you to move your project between machines and for submittal since the file will be included in the set of project files. For example, the following will create or open a file called “PlayerStats.txt” in the bindebug folder:

statsFile = System.IO.File.AppendText(“PlayerStats.txt”)

Hint: Use the examples in section 8.1, page 350-351 to read the file and display the summary data in a datagridview control.

Hockey Player Statistics Main Form

ObjectPropertySettingfrmHockeyStatsTextHockey Player StatisticslblHeadingTextName, Course Title, Week Number, Lab TitlegrpPlayerTextPlayer InformationlblFirstNameTextFirst Name:txtFirstNameText(empty)txtFirstNameTootip on Tooltip1Player’s first namelblLastNameTextLast Name:txtFirstNameText(empty)txtFirstNameTootip on Tooltip1Player’s last namelblSeasonsTextNumber of Seasons:txtSeasonsText(empty)txtSeasonsTootip on Tooltip1Number of seasons playedlblAgeTextRookie AgetxtAgeText(empty)txtAgeTootip on Tooltip1Rookie age of the playergrpStatisticsTextStatistic OperationsbtnGetStatsTextGet Player StatisticsbtnGetStatsTootip on Tooltip1Click to enter player statisticsgrpResultsTextSeason ResultslstSeasonsItems(empty)lstSeasonsTootip on Tooltip1Season by season goals, assists, and total pointslblTotalText(empty)grpOperationsTextOperationsbtnSummaryTextDisplay SummarybtnSummaryTootip on Tooltip1Click to open player summary formbtnClearTextClearbtnClearTootip on Tooltip1Click to clear all input and output databtnExitTextExitbtnExitTootip on Tooltip1Click to exit the Hockey Player statistics programmnuFileTextFilemnuClearTextClear FormmnuExitTextFilemnuToolsTextToolsmnuGetStatsTextGet Player StatisticsmnuSummaryTextSummary Data

Player Summary Form

ObjectPropertySettingfrmPlayerSummaryTextPlayer SummarylblHeadingTextPlayer’s Season SummarygrpOperationsTextOperationsbtnGetStatsTextSeason SummarybtnGetStatsTootip on Tooltip1Click to retrieve and display summary databtnClearTextClear SummarybtnClearTootip on Tooltip1Click to clear summary data filebtnCloseTextClose SummarybtnCloseTootip on Tooltip1Click to close the summary formdgvStatisticsText(empty)dgvStatisticsTootip on Tooltip1All players career goals, assists, and points

You are free to experiment with colors and form design as you see fit. However, your application must meet the listed requirements.

Step 4: Implement the Event HandlersUse the following as the design for your event handlers, referring to the flowchart for rules on input validation and processing. The final calculation SHOULD NOT be completed until all the input fields are validated.

Note that some of the event handlers use the same modules to perform the operations.

Hockey Player Statistics Main Form

Control NameEventTasktxtFirstNameValidatingGet player first name

Validate player nametxtLastNameValidatingGet player first name

Validate player nametxtSeasonsValidatingGet number of seasons

Validate number of seasonstxtAgeValidatingGet age

Validate age

Enable/disable get statistics command buttonbtnGetStats/mnuGetStatsClickCollect Statistics

Display Summary DatabtnClear/mnuClearClickClear all textboxes and output label

btnExit/mnuExitClickClose program (Hint: use “Application.Exit”)

btnSummary/mnuSummaryClickOpen Summary Form

frmHockeyStatsLoadClear all textboxes and output label (Hint: call the ClearFields module)

Player Summary Form

Control Name (frmPlayerSummary)EventTaskbtnGetStatsClickRead Summary File

Display Summary Data

btnClearClickOpen file for writing in CreateText mode

Close file

Display confirmation message

btnCloseClickClose form (Hint: use “Me.Close”)

Step 5: Executing the Program

To execute your code, click Start and then start debugging. Check your output to ensure that you have space(s) where appropriate. If you need to fix anything, close your execution window and modify your code as necessary and rebuild.

Step 6: Deliverables

1. Capture a screen print of your output [Do a PRINT SCREEN and paste into an MS Word document].

2. Copy your code and paste it into the same MS Word document that contains the screen print of your output.

3. Save the Word document as CIS170A_Lab07_LastName_FirstInitial

4. Zip up the Word document along with complete set of project files into a single document.

5. Place deliverables in the Dropbox.