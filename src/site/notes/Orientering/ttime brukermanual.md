---
{"dg-publish":true,"permalink":"/Orientering/ttime brukermanual/","title":"ttime brukermanual","tags":["orientering"]}
---


# ttime brukermanual

## tTiMe for Dummies

- Press 'MTR' and 'Spool all' to download your MTR logfile(s).
- Press 'Edit Database' to edit your runner database.
- Press 'Wizard'.

		or

- Select 'MTR'->'Download from MTR' to download your MTR logfile(s).
- Select 'Database'->'Open …' to read your runner database.
- Check 'Database'->'Extended view' for startlist, invoice and online
	registration
- Press 'Edit Database' to edit your runner database.
- Select 'MTR'->'Open …' to read additional MTR logfile(s).
- Select 'Output'->'HTML results' to write HTML results.
- Select 'Output'->'HTML splittimes' to write HTML splittimes.
- Press 'Run' to generate your results:
	 - Select the date of the competition. 
	 - Assign the classes to the corresponding code sequences. 
- Select 'Configuration'->'Save' to save your settings for later.

## How-To-Use
A step-by-step tutorial to generate result lists and split times from MTR logfile and a comma separated verbose database. x.) denote optionals.

The basic idea of tTiMe is based on three components:
- runner database containing ECard, class, club, unique runner number and registration status.
- MTR logfile(s) containing ECards with times and codes.
- configuration file defining how and which output should be generated, i.e., result lists, which ECard to omit, ranking mode, overall ranking with chase start, code sequence for each course, etc. 'Run' generates the output based on the those three components.

Check 'Help'->'Dynamic help' to get dynamic help for buttons.

### Configuration
1. Set a filename to define the file of your settings (configuration) such that you can reload it later, or load your old configuration 'Configuration'->'Open …'. Press 'Configuration file' to load a configuration when no filename is given or to save your actual configuration.
2. Download your MTR logfile(s), 'MTR'->'Download from MTR'. The successful downloaded logfile(s) are added automatically to your input configuration. 'Spool range' chose a range of ECards from the MTR memory to be spooled, useful to spool all sessions, when the logfile seems to be incomplete.
3. Set filename of the MTR logfile, 'MTR'->'Open ..'. tTiMe supports multiple logfiles. tTiMe will ask you if you want to add a new logfile or override the logfile(s) with a new one. 
4. Set filename tTiMe database file, which is a CSV or SDV (comma separated verbose) file, 'Database'->'Open …'. Note that tTiMe will chose the right format. There is not support of pure Excel format, but 'Database'->'Open with free format …' enables to customize your own comma or semicolon verbose format. If you launch the database editor you can convert a palisoft/eTiming csv runner and team databases to tTiMe format. The team database is optional, which implies that the team code will be use as club name 
 

#### Options
5. Set the date of your competition if the MTR logfile(s) contains more than one race in the fields 'From date' and 'To date'; retrieve the date with 'MTR'->'Probe logfile' or use 'Tools'->'Grab dates', which retrieves all possible dates from your MTR logfile(s) and sets the date according your selections. 'Past' accepts all dates for 'From date', where 'Future' accepts all dates for 'To date'. If you like to use only entries of a previous race you needed to set 'To date' accordingly. 'From date' defines acceptance of all dates later or equal and 'To date' earlier or equal.
6. 'Omit' enables you to omit ECard(s) when reading the MTR logfile. The to be omitted ECards are separated by comma, e.g., '23456,45632'. You can also omit entries from the logfiles by the line number entry (line number in front of /).
7. In order to set 'Codes' and 'Courses' by hand do a 'Tools'->'Grab codes & classes', which allows you to assign classes to code sequences found in the MTR file. The codes are separated by comma (',') and the different code sequences representing a valid course by colon or semicolon (':' or ';'). Controls with different codes are separated by period ('.'), e.g., '99,100.110.150', means that after code 99, 100 or 110 or 150 is accepted. If you have a forked competition check the according box - enables to assign more than one sequence to a class. If 'Normalize multiple controls' is enabled the smallest number of the group will be assigned. If needed you can assign multiple courses to one class by checking 'Support multiple courses/forking', but should be only used when the competition has forking. 'Match courses with database classes' tries to match the classes based to a valid course together based on your database and logfile(s) 'Tools'->'Grab codes & classes' is automatically called if no 'Codes' and 'Courses' are set under 'Run'. The courses can also be imported from a OCAD course setting text file, 'Tools'->'Import OCAD course setting'. The database editor enables more than to import the names, but also clubs and courses with the corresponding classes.
8. 'Options'->'Accept' allows you to accept different runner status, which are mainly the same as a disqualification, see runner status under conventions. Note that you may also change the runner status or time with 'Manually', see point 9. 
9. 'Manually' enables you to override different times or runner status. You can also set a mass start time such that all runners get the same start time regardless when they activated their ECard. The manual times are pair wise defined staring with either the ECard number or the runner number and the runner status or time, separated by comma, e.g., '13,34:11,76025,DNF,37265,DNF'. To enable mass start use 's' and start time for all runners, e.g. 's,19:40:00', or for a group of classes, e.g. 's;H21;D21,19:40:00'. In order to check the chase start the same yields as for mass start, use 'c', 'c;H21;D21,19:40:00'. Remember that all MTR should have the same time. 
10. 'Options'->'Clear input' clears the runners status, times and splittimes of the input database after reading. This should be checked when computing ranking and the input database should not count for the ranking. If you do not give an input database the output database will be a unique merge of all ranking databases.           
11. 'Options'->'Remove double ECards' removes all double entries when reading the MTR file. Should be checked. Unchecked may only of interest if you like to write the raw splittimes. 'Keep last unique ECards' and 'Remove first DSQ ECards' can be used to supress entries from online registration.
12. 'Format' enables to define your own format, which is set when opening a database with free format. 

#### Output
13. 'HTML results' to write the results as HTML, if 'HTML split' is specified the according links are added to the HTML result file.
14. 'HTML splittimes' to write the split times as HTML.
15. 'HTML overall' to write overall results as HTML.
18. 'ttime database' to write back the tTiMe database (comma separated verbose), including the runner status or time, split times, start time, arrival time and arrival order. The output database includes the times, splittimes and other runner related information, e.g., you can look at the time of arrival at the finish by enabling 'Database'->'Extended View' and loading the output database into the database editor.
19. 'XML database' to write output as IOF 3.0 XML.
20. 'RAW splittimes' defines the text file to write the raw splittimes. 
21. 'HTML ranking' to write the ranking as HTML.
22. 'CSV Splitsbrowser' to write CSV Splitsbrowser file.

23. Press 'Run' to generate your results and output files. Done!

	Note that pressing a button corresponds to open 'Output'->… . 

### Polling during race
Press 'MTR' and start the polling with 'Poll MTR' or 'Poll 250', tTiMe will write the in coming ECards to file and if possible based on database and/or courses check for:
- ok
- disqualified runners
- unknown runner/ECard
- rental ECard
If you already have polled or downloaded parts to a file you can append to it, tTiMe will continue where you ended (MTR). The polling runs in the background such that you can update your database in the mean while or produce results. Changes in the database are propagated for polling.

### Online registration
Online registration is supported both for MTR untits and 250 untis. tTiMe will move the selection cursor the runner with the corresponding ECard, and will notify you if there are multiple matches or no match at all. The next ECard will trigger an update, no need to press 'Update', if the registration is ok. Sort your database after 'Status'. There is also a history of the last 5 registered ECards and the last ECard number can be paste from the clip board. There is also toggle button to temporary store incomming runners to a logfile. 

tTiMe does also support an option ('Options'->'Remove frist DSQ ECards') to exlude the first ECard if not valid (DSQ) to handle registration and incomming runners on same MTR.

## Notes
- The databases are plain text files in comma separated verbose format; Excel CSV or SDV.
- For ordinary races none of the accept options should be checked. 
- Norwegian characters are normalized when reading input files.
- Newline for output files are operating system dependent, Windows and Unix/Linux differ.
- Before any competition clear the MTR and set correct date and time on MTR.
- Requester when configuration unsaved or modified.
- You can compute the ranking based on previous output databases and add to your actual race, including the actual race.
- You can compute the ranking only from output databases. If you define an input database you should check 'Clear input' to avoid the input database to be counted for the ranking, or you do not define the input database, tTiMe will do an unique merge of all ranking databases.
- Support of USA date & time format, and setting no valid date & time to 1970-01-01.
- Support of import of palisoft/eTiming csv name, course, class and team databases.
- Option to read eLine control/competition logfiles.
- Packing all required input files to one zip file.
- Server down- & upload of runner database.
- Support of forked courses.
- Import of OCAD course setting text and xml file
- tTiMe supports generation of startlist, online registration, invoicing; check 'Database'->'Extended view'
- online code check
- online registration

## Conventions

### Runner Time Status
DNC : Did Not Clear, ECard was not cleared.
MFS : Multiple Finishes, runner did passed finish more than once.
RWC : Ran Wrong Course, runner ran wrong course.
DSQ : Disqualified.
DNF : Did Not Finish.
DNS : Did Not Start, status A.
RUN : Running, status X or P, but not arrived yet.

### Runner Entry status
' ': not active / entered
X : entered
P : entered, group or pair, when several runners run with same ECard.
A : first entered, but then resigned or no show

### Filenames
MTR logfile: '*.log', '*.txt' or '*.text'.
Database: '*.sdv' or '*.csv'.
HTML: '*.htm' or '*.html'.
XML: '*.xml'

### Database format
The databases are plain text files in comma separated verbose format; Excel CSV or SDV.

tTiMe database:
1;;Alvheim, Atle;HA;Fana IL;;87000;
2;;Alvheim, Martin;HA;Fana IL;;24717;
…

- Unique runner number
- Runner entry status:
- Name
- Class
- Club
- Option for additional internal information:
B : alternative ECard   
C : chase start: class|chase start time
D : date at MTR
E : runner time status / error code
F : real time at finish control 
G : real time at MTR
H : MTR serial number
J : ranking: class|ranking|order & points or time
K : ranking: rank / after time 
L : course
M : incoming order at MTR
N : logfile order
O : incoming order at finish control
P : placement: total, 1. splittime, 1. total split, 2. splittime, …
R : ranking: race|class|time|after time|rank / after time
S : real time at start
T : Micr-O penalties
U : start time
V : seed
W : random number
Z : register state/fee
- ECard
- Time
- Splittimes (optional): 
1. control; 1. split time; 1. total time; 2. control; …

NC database:

Løpernr;Påmeldt;Navn;Klubb;Br.nr.;Nytt Br.nr.;Tid;Klasse;Lykt;Betalt;Strekktider
1;;Alvheim, Atle;Fana IL;87000;;;HA;;;
2;;Alvheim, Martin;Fana IL;24717;;;HA;;;
…

- Unique runner number
- Runner entry status:
- Name
- Club
- ECard
- Alternative ECard
- Time
- Class
- Other
- Other
- Other

Thanks to: Bjørge (www & ttime.no), Terje (MTR download), Sindre (250), Andreas (beta tester), Varegg (license), Scott (books) and Jan (perl).

tTiMe 0.73 © 2004-20 by Thierry Matthey (MSWin32 MSWin32-x86-multi-thread-64int C:\ttime\ttime(3)
