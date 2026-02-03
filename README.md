# gradCPT-suite
Code and app releases related to the gradCPT task and their variants.

gradCPT (Gradual Onset Continuous Performance Task) – BALLAB

This repository hosts documentation and release downloads for the gradCPT task developed by BALLAB.
The gradCPT is distributed as a compiled MATLAB application for Windows and is commonly used in behavioral and fMRI research.

System Requirements
	•	Operating system: Windows 10 or Windows 11 (64-bit)
	•	Administrator privileges: required for installation
	•	Screen resolution: 1024 × 768 (recommended)
	•	MATLAB Runtime: Installed automatically during setup (if not already present)

Installation

1. Download the installer

Download the compiled installer (e.g., MyAppInstaller_mcr.exe) from the Releases page of this repository.

⚠️ Windows SmartScreen may warn about an unknown publisher.
Click More info → Run anyway.

⸻

2. Run the installer
	1.	Double-click MyAppInstaller_mcr.exe
	2.	Accept all default installation options (strongly recommended)

By default, the application installs to:
C:\Program Files\gradCPTv01\application\

3. Install additional required components

Navigate to:
C:\Program Files\gradCPTv01\application\
Install the following if prompted:

a. Microsoft Visual C++ Runtime
Run:
vcredist_x64_2015-2019.exe

If Windows reports it is already installed, skip this step.
b. GStreamer
Run:
gstreamer-1.0-msvc-x86_64-1.18.5.msi
Choose Complete Setup Type during installation.

c. USB library
Copy: libusb-1.0.dll
to: C:\Windows\System32\
(Administrator privileges required.)

4. Install stimulus files

Unzip the following archives:
	•	scene5.zip
	•	faces.zip

Extract them without changing folder structure into:
C:\Program Files\gradCPTv01\application\
You may delete the .zip files after extraction.

5. Create a data output directory
Create a folder outside Program Files for configuration files and participant data.
Example: C:\Users\USERNAME\Documents\gradCPT\DataOutput\

Initial Setup (Before MRI Scanner)
	1.	Set screen resolution to 1024 × 768
	2.	Run: gradCPTv01.exe
  3.	Configure:
	  •	Save directory
	  •	Response key
	  •	Quit key
(Spacebar cannot be used)

⚠️ Do not manually close dialog boxes — they will close automatically.
	4.	Click Save Config
	5.	Close the application

Verify Installation
	1.	Relaunch gradCPTv01.exe
	2.	Click Load Config
	3.	Select: ExpParams.mat
from your Save Dir
	4.	Modify Task Parameters for a short test
	5.	Click Start
	6.	Complete a test run:
	•	Press the response button for city images
	•	Withhold responses for mountain images

Verify data output

Open the QC file in your Save Dir.
If Omissions_Tot ≈ 1, there may be response-detection issues.

MRI Scanner Setup
	1.	Set screen resolution to 1024 × 768
	•	If stimuli appear warped, try 800 × 600
	2.	Connect:
	•	Projector
	•	MRI trigger
	•	Button box
	3.	Launch gradCPTv01.exe

Identify trigger and response keys

MRI trigger
	•	Open a text editor
	•	Initiate a scan
	•	Record the key/number sent by the scanner
(Confirm with MRI technician if needed)

Button box
	•	Press the response button
	•	Note the key/number generated

Enter both into the GUI.

Run timing test
	1.	Click Run Time Test
	2.	Wait several minutes until completion
	3.	Confirm that an error value is populated
	4.	Click Save Config

Final Scanner Check
	•	(Optional) Set task duration to 30 seconds for testing
	•	Press Start
	•	Verify:
	•	Trigger starts task correctly
	•	Button box responses are detected
	•	Stimulus size is correct
	•	Data files are saved correctly

⸻

Participant Practice (Before Scan)

Have participants complete the online practice task:

https://gradcpt.org/one-time-task/WXkOQm49GVreClFvNiTv

Read instructions aloud and answer questions.
Participants may repeat the practice if desired.

⸻

Running the Task During fMRI
	1.	Load saved configuration (ExpParams.mat)
	2.	Confirm 8-minute task parameters
	3.	Remind participant:

“You will see pictures of cities and mountains.
Press the button as quickly as you can when you see a city.
Do not press the button when you see a mountain.
The task lasts about 8 minutes and is meant to be challenging.”

⸻

Data Output

All data files are automatically saved to the configured Save Dir, including:
	•	Trial-level output
	•	QC summary files

⸻

Support & Citation

If you use this task in published work, please cite appropriately and acknowledge BALLAB.

For questions or issues, please use the GitHub Issues page for this repository.
