
# Alarm clock

An alarm clock usually requires you to set the specific time you want the alarm to ring. Once you have set your preferred time, the alarm will continuously match the time you provided with the current time. As soon as both the time matches, the alarm rings.



## Setup
We have to install playsound & datetime

pip install playsound 

pip install datetime

Now download any tone from internet but all you have to do is make sure that the file extension of the audio file is .wav.


## Code
Import both modules 

from datetime import datetime

from playsound import playsound

✴️ In first if statement, at len(alarm_time) != 11 we are checking the length of user input to be exactly 11 characters. 

✴️ If not then it will return a statement, asking the user to re-enter the value. 

✴️ If the user input is exactly 11 characters long, then else block will execute, this is where the more in-depth validation of our user input happens.


✴️ In the first if statement within else block, we are validating the first two characters of our input which are HH. There could be a slight chance that user may enter invalid hour values like something more than 12 hours. Here at alarm_time[0:2], we are using a slicing operator to access the first two characters of user input. The input is not more than 12 hours then the execution will move forward to the next conditional statement. But if the input is more than 12 hours, then it will return a statement asking the user to re-enter the time.


✴️ Next two conditional statements do the same job as the first, comparing minutes & seconds respectively.


✴️ If the input is all good then, else block of our function will return an OK. Now, this is where the job of our function is over.


alarm_hour = alarm_time[0:2]

alarm_min = alarm_time[3:5]

alarm_sec = alarm_time[6:8]

alarm_period = alarm_time[9:].upper()

Here we are using slicing operator to store the specific unit of time into specific variables. HH will be stored in alarm_hour, MM in alarm_min and so on.

now = datetime.now()

    current_hour = now.strftime("%I")

    current_min = now.strftime("%M")

    current_sec = now.strftime("%S")

    current_period = now.strftime("%p")

datetime.now() to obtain the current time and we are storing this data in now variable.

% notation to extract specific time data from now variable. 

now.strftime() is used to the data in string format for comparison.

if alarm_period == current_period:

        if alarm_hour == current_hour:
            if alarm_min == current_min:
                if alarm_sec == current_sec:
                    print("Wake Up!")
                    playsound("/Users/macbookair/Desktop/projects/Python Bsc.-adv./python projects/sound.wav")



We are simply using if statements to compare current time & user time.

if statement is executed and if it matches, the Wake Up! will be printed on console & the alarm tone will be played.

To play alarm tone we are making use of our playsound module.

break statement at the end so that the execution of our alarm will stop once the alarm has rung.
⭐⭐⭐