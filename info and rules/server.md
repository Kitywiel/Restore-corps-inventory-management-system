# This is the server ***info/workings/processes/rules***.

## in this file are the processes and the workings around the `./server` file.

***code/futher edits under the line, starts at line <u>37</u>.***

---

### RULES

###### these rules need to be followed no matter what

- all server files need to be in the `./server` folder. *except if there is no other way if it impacts the fundamental of runing the server*
- all files need to be optimized to run on a ***low-end server*** with a 50 Mb/s ethernet port.
- all **javascript** files that the server runs on need to go in `./server/javascript`. *like google api link and* ***not*** *login or other scripts that are linked to mostly css or html*

### processes/working

###### the next lines are what and how it will work

- the database will be a **google spreadsheet** where all the login and other data will be stored
- no processes will be stored locally or in the server so ***no data*** will be stored in the RAM
- all user specific data will be retrieved from sheets when logging in
- passcode will be stored in hash
- cros tab info will be retreved using a central user id. *will look like `USER:xxxxxxxxxxxxxxxxxxxx` random 20 long number string*
- for info over the speadsheet layout look at `./info and rules/spreadsheet layout.md
`

### info

###### this is what it is used for and why

- the site will be hosted on a server that only has RAM and SSD


###### \ / code/info under here \ /
