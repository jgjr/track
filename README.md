# Track
This is a very simple, lightweight time tracker for the command line written in Python.
It keeps all of the times tracked in a file called '.tracking.json' in the directory in which it was initialised, all further commands must then be issued in the same directory. A tracking file can be initialised in any directory.
## Installation
I have written and tested this on Linux, but I am assuming it could be fairly easily adapted to work on OS X or Windows. 
The application consists of one file: 'track', so this file just needs to be placed somewhere in your path, and made executable (chmod +x track). It requires Python (2 or 3) and the datetime and json modules. 
## Usage
* track init - initialize time tracking file
* track start &lt;label&gt; (optional) - start tracking time
* track stop - stop tracking time
* track clear - clear all tracked times
* track show - show the daily totals for tracked times
* track export &lt;filename&gt; - export the totals to a specified file
## Output
The tracking file ('.tracking.json') contains a list of all the times tracked in JSON format and may look something like this in the terminal window:
```json
{
    "times": [
        {
            "start": "2017-07-21 09:11:04",
            "end": "2017-07-21 12:58:17",
            "label": "Task 1"
        },
        {
            "start": "2017-07-21 14:03:02",
            "end": "2017-07-21 17:52:48",
            "label": "Task 2"
        },
        {
            "start": "2017-07-22 20:29:33",
            "end": "2017-07-22 21:08:21",
            "label": ""
        }
    ]
}
```
The command 'track show' will output something like this:
```
Labels:
Task 1 - 3:47:13
Task 2 - 3:49:46
No label - 0:38:48

Days:
2017-07-21 - 7:36:59
2017-07-22 - 0:38:48

Total:
8:15:47
```
and 'track export file.txt' will generate a file containing the totals with the same format as the 'track show' command
## "Why?" You ask
I don't have the willpower to use any other time tracking software, but I often need to keep track of how many hours I have spent on a project. I can just about summon the energy to type 'track start' and 'track stop' into my current terminal window, and I organise all my projects into separate directories, the top level of which is where I keep my time tracking file. 
