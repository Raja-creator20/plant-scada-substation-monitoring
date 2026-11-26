# plant-scada-substation-monitoring
11kV / 132kV Substation Monitoring (AVEVA Plant SCADA)

A monitoring and control screen set for a small 132/11 kV substation, built in AVEVA Plant SCADA 2020 R2. There is no PLC in the project. All values come from the internal memory I/O device and a Cicode simulation that starts with the runtime.

What the project contains
Overview page with a single line diagram: 132 kV incoming line, 132 kV bus, two transformers, 11 kV bus and three feeders. Feeder breakers change colour with their status (open, closed, tripped) and the page shows feeder current, bus voltages and transformer temperature and load.
Transformers page with oil temperature, winding temperature, load, tap position and a trip indicator for each transformer.
Alarms page using the Alarm Table library control. It shows active analog alarms (high and high high limits on transformer temperatures, feeder current and bus voltage) and digital alarms (transformer trip, feeder breaker trip).
Trends page with four trend objects: transformer oil temperature, feeder currents, 11 kV bus voltage and 132 kV bus voltage.
Role based access. Two roles, Operator and Engineer. Breaker open and close buttons carry privilege 1, so they work for an Engineer login and stay locked for an Operator.
A breaker faceplate popup for Feeder 1, opened by clicking the breaker on the Overview page.
Cicode simulation that moves temperatures, currents, voltages and frequency, started through the client startup function.
Tags

Tags are organised under System Model equipment (Substation1, Feeder1 to Feeder3, Transformer1 and Transformer2). Analog tags use raw 0 to 1000 scaled to engineering ranges, for example feeder current 0 to 400 A and transformer oil temperature 0 to 150 degC.

Files in this repository
screenshots/ Runtime screenshots of each page
import-files/ CSV and XLSX files used to import tags, alarms and trends in Studio
cicode/ the simulation source
docs/ any notes

The full Plant SCADA project folder is not included because it contains binary project files and user records.

How to run it
Install AVEVA Plant SCADA 2020 R2.
Create a new project in Studio and add Substation1 and its equipment in System Model.
Import the variable, alarm and trend files from import-files/ using Import All in the matching view.
Recreate the pages, or restore a project backup if one is shared separately.
Set SimStart as the client startup function and run the project.

Author
Raja Sana Ullah, Electrical Engineering, UET Lahore
