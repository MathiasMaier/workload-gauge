# workload-gauge
An easy to deploy secondary task for workload assessment and cognitive load measurement in research and development.

##TLDR;
Do you need to measure cognitive load, mental load or workload? This software allows you to do this with a simple yet effective secondary task for your subjects. And the evaluation will be easy since it creates enough metadata. Since it is contained in a simple webpage you can use it on almost any device that is capable to display an HTML website (with CSS and javascript).

## About this project
I created this project after the software was used successfully in a research project (STARFiSH) that I executed for the company I am currently working for (ATRiCS Advanced Traffic Solutions GmbH) together with our project partners DLR, Fraport and Idiap. The project researches the use of assistant based speech recognition for aiding air traffic controllers. In the project we needed a way to assess the workload and cognitive load for the users (air traffic controllers) of the assistance system (A-SMGCS). I wrote this software in order to have an objective measure (using a simple secondary task) and it was easy to measure and evaluate the resulting data. Since we did several evaluations the software has already somewhat matured a bit so the worst bugs are already fixed. Some of the partners are planning to re-use the software and we all think that it could be helpful in other research and development projects. Nevertheless there are also some things that could be improved and so I decided to open source this and make it available in a github project SO YOU CAN BENEFIT AND CONTRIBUTE. Please check it out and contribute by writing requirements, committing changes or simply give feedback and discuss.

## TODO
Since I am writing this on the first day of a longer off-the-grid holiday this is still missing a lot of information. If you're interested, please be patient and drop me a line what it is that you are missing most.

## About the software
A website displays a button that says "start". When you press it, you will see a word displayed at the top that spells out a color, e.g. "BLUE" but is printed in a different color, e.g. orange. You will also see a stack of buttons that are labelled with names of colors. Both the color the text is displayed in and the color that is spelt out at the top are in the set. The user has to select the color that the color word is displayed in (in the above example: "ORANGE", not what the text says ("BLUE"). The user has to repeat this as often and as quickly as possible.
In the background, the data we collect is
* the colors that were used (randomly),
* the time the user needed to complete one selection,
* if the answer was correct,
* if the answer was never given, i.e. timed out,
* the date and time the "start" button was pressed,
* the date and time one of the answer buttons was pressed.
The website also offers a button to download the data as a JSON file and offers a simple protection against navigating away and losing the data. It also offers an opportunity to recover data in case the user accidentally did navigate away.

## How to use
Simply copy the website to the device you want to use. I hardcoded the size for the devices we used in our project (for a galaxy tab A8). So you need to experiment which size is best for you. Just change the properties in the html file. This is one of the first things that need to be improved soon.

## Snags and requests list
Since I don't have much time today (see TODO) and as a github newbie I will simply write down what needs to be done soon or anytime in a list here:
1) Offer an easy way to adapt the UI to the size of the screen. Semi-automatic would be good: Find something that fits, then allow the user to tweak the sizes of the buttons and the display to their needs in the project.
1) There is a bug that causes the software to sometimes log a different color than displayed (it is always light grey, the background color). This is probably due to the stupid and clumsy way how I do the comparison of the colors for determining if the user's selection was correct. I knew it when I wrote it that it was wrong but this part of what was meant as a quick prototype survived right into production and the bug is so seldom that I didn't realize it until a lot of data was produced.
1) Extensive testing should be done. See above.
1) There should be a small "settings" button for the download of the data and for any other administrative features so that the user won't do anything but the task he/she is supposed to do. In our project, we hid the download button by turning the tablet 90 deg into portrait mode, so it was not accessible.
1) It would be great to have additional, custom metadata to be saved with every evaluation run / experiment that we did. So it would be cool to be able to input the experiment id or other custom data (in our case: the subject's working position or anonymous ID)
1) Experimentors should be able to customize the tests: Select the number of colors and the colors themselves, the background colr, etc.
1) The option to upload the data would be nice in some circumstances. I explicitly wanted an offline solution but you need to get the data off the machines somehow and if you are using a portable device that is not configured for your secure network it would be nice to have the option to just enter a server to upload to. But using google drive or whatever works, too.
1) How to actually use the software should be added here, including screenshots and maybe sample data.

