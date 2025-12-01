# this is the spreadsheet info file.

## in this file the layout of the sheet will be explaned.

### tabs
| [USERS](#WORKING%20USERS) | INVENTORY | ACOUNT_SETTINGS | GUEST_ACOUNTS | USER_WARNINGS |
|-------|-----------| --------------- | ------------- | ------------- |

### TAB 1 ***USERS***

| USER_NAME | PASSCODE | EMAIL |          USER_ID          | INV_USED | USER_UNLIMITED |   CREATED  | LAST_LOGGED_IN | STATUS | ROLE | ITEM_LIMIT |
| --------- | -------- | ----- | ------------------------- | -------- | -------------- | ---------- | -------------- | ------ | ---- | ---------- |
|  user123  | $2b$10$  | T@T.A | USER:12345678901234567890 |    0     |  TRUE / FALSE  | 10/10/2025 |   10/10/2025   | ACTIVE | USER |     20     |


#### WORKING USERS

* `USER_NAME` > the user name of the user.
* `PASSCODE` > the pascode fo the user hash(Argon2 + salt).
* `EMAIL` > the email of the user.
* `USER_ID` > the id of the user. used around the spreadsheet to keep data to the user.
* `INV_USED` > displays the total items in there invetory.
* `USER_UNLIMITED` > if the user has unlimited invetory.
* `CREATED` > only changes the first time the user creats that acount.
* `LAST_LOGGED_IN` > resets every time the user logges in to there acount displays the last time the user loged in.
* `STATUS` > displays if the acount is active or not can only be changed by a admin.
* `ROLE` >  if the user is a user or admin (user defalt).
* `ITEM_LIMIT` > this is how many items the user can have gets over ruled if `USER_UNLIMITED`= TRUE

### TAB 2 ***INVENTORY***
