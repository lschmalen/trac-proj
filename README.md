# Track time spent on different activities
Very simple project tracker that (manually) tracks how much time is spent on a project and outputs overviews.

## Background 
During work, I noticed that I spent more time on unpleasant activities (e.g., reading e-mails, meetings) than I would have liked to and too little time on projects that I enjoyed. In order to get an idea on the time spent n different activities, I decided to write this little tool. Most tools that I found were either not free and/or too complex for simply monitoring activities (e.g., including billing support for projects). I simply wanted to track the time I spent on e-mail, meetings, and a handful of projects. Periodically, I wanted to look at some statistics and see if I can improve my time management.

This program can also be handy for checking if the time you spend on a project is within the boundaries you defined or have been imposed. It can be use as a helper for improving your own time management.

## Configuration
The program is written in python. I recommend to use a virtual environment or a Python distribution like [Anaconda](https://www.anaconda.com/). Anaconda is also the preferred method to install a complete Python environment on a Windows machine. If you are using Anaconda, I advise you to create an environment within which you run the code. You can directly create the environment for running the notebooks using the provided environment.yml file using `conda env create -f environment.yml`. You can then activate the envinronment using `conda activate track_project`.

To configure the program, you can press the _Settings_ button in the program, which will open a small window where you can type in the name of the buttons inside the field. Each line corresponds to a button. Currently, you need to restart the program for the changes to become effective.

Alternatively, you can also configure the program by editing the `config.ini` file. In the `[Buttons]` section, you can specify the different tasks and projects. Every task is assigned a `ButtonX` variable, where `X` should be replaced by a numeral counting from 1 to the number of buttons. For example
* `Button1 = Research`
* `Button2 = Powerpoint`

will create two buttons correspondings to two projects "Research" and "Powerpoint".

The file `config.ini` contains another parameter in the `[Output]` section, namely `Percentage`. This parameter controls if the weekly statistics are given in terms of percent or in absolute time (minutes).

## Usage
The usage is pretty straightforward. Every project/task is assigned a button that can be toggled. If active, the button turns white with red font and time is counted on that task. If the button is either deactivated or another button activated, time spent on that task is counted and written into a file (in the datafiles directory). For every day a file is created that contains the seconds spent on each task.

Pressing the __convert__ button generates an Excel file with daily statistics (number of minutes spent per day on each task) and, in a different worksheet, weekly statistics (either number of minutes or percentage of time spent on each task in a week. That's about it. The __consolidate__ button cleans the database files but is disabled in the current version.






