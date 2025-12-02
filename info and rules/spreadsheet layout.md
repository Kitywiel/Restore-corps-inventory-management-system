# this is the spreadsheet info file.

## in this file the layout of the sheet will be explaned.

### tabs
| [USERS](#WORKING%20USERS) | INVENTORY | SETTINGS | GUESTS | USER_WARNINGS |
|-------|-----------| --------------- | ------------- | ------------- |

### TAB 1 ***USERS***

| USER_NAME | PASSCODE | EMAIL |          USER_ID          | INV_USED | USER_UNLIMITED |   CREATED  | LAST_LOGGED_IN | STATUS | ROLE | ITEM_LIMIT |
| --------- | -------- | ----- | ------------------------- | -------- | -------------- | ---------- | -------------- | ------ | ---- | ---------- |
|  user123  | $2b$10$  | T@T.A | USER:12345678901234567890 |    0     |  TRUE / FALSE  | 10/10/2025 |   10/10/2025   | ACTIVE | USER |     20     |


#### WORKING USERS

* `USER_NAME` > the user name of the user.
* `PASSCODE` > the pascode fo the user hash(Argon2 + salt).
* `EMAIL` > the email of the user.
* `USER_ID` > the id of the user. used around the spreadsheet to keep data to the user. (USER:`20 long random string`)
* `INV_USED` > displays the total items in there invetory.
* `USER_UNLIMITED` > if the user has unlimited invetory.
* `CREATED` > only changes the first time the user creats that acount.
* `LAST_LOGGED_IN` > resets every time the user logges in to there acount displays the last time the user loged in.
* `STATUS` > displays if the acount is active or not can only be changed by a admin.
* `ROLE` >  if the user is a user or admin (user defalt).
* `ITEM_LIMIT` > this is how many items the user can have gets over ruled if `USER_UNLIMITED`= TRUE

### TAB 2 ***INVENTORY***

| USER_ID                   | DESCRIPTION              | ITEM_NAME | CATEGORY | SKU  | QUANTITY | USED_QUANTITY | UNIT | PRICE | TOTAL_VALUE | LOCATION | MINIMUM_QUANTITY | INV_NUMMER                | DATE_ADDED               | DATE_UPDATED             | ACTIVE | EXPIRY_DATE|
| ------------------------- | ------------------------ | --------- | -------- | ---- | -------- | ------------- | ---- | ----- | ----------- | -------- | ---------------- | ------------------------- | ------------------------ | ------------------------ | ------ |--------|
| USER:12345678901234567890 | this is my firts project | project 1 | item     | pj01 | 10       | 0             | box  | 0.99  | 9,9         | none     | 5                | ITEM:12345678901234567890 | 2025-11-27T23:38:44.794Z | 2025-11-27T23:43:43.194Z | TRUE   | FALSE |

#### WORKING INVENTORY

* `USER_ID` > the id of the user. used around the spreadsheet to keep data to the user.
* `DESCRIOTON` > this is where the descriptoin of the item is
* `ITEM_NAME` > the name of the item
* `CATEGORY` > the category of the item
* `SKU` > the sku of the item
* `QUANTITY` > the amount there is of that item
* `USED_QUANTITY` > the amount that is used of the item
* `UNIT` > what the item is like (box, product, ext)
* `PRICE` > the price that the item is
* `TOTAL_VALUE` > the total price (`QUANTITY`*`PRICE`=`TOTAL_VALUE`)
* `PRICE` > the price that the item is
* `PRICE` > the price that the item is
* `LOCATION` > the location of the item
* `MINIMUM_QUANTITY` > the minimum amount of that item
* `INV_NUMMER` > the item  like: (`ITEM:12345678901234567890`)
* `DATE_ADDED` > the date the item was added ***NEVER CHANGES***
* `DATE_UPDATED` > the date the item was changed
* `ACTIVE` > if the item is active
* `EXPIRY_DATE` > if the ite expires (ither `FALSE`OR`DATE`)

### TAB 3 ***SETTINGS***

| USER_ID        | STANDERT_UNIT | NEGATIVE_STOCK | EXPIRY | PRICE_ROUNDING | AUTO_SKU | AUTO_GUEST_ROLE |
| -------------- | ------------- | -------------- | ------ | -------------- | -------- | --------------- |
| U1764277259593 | UNIT          | FALSE          | FALSE  | FALSE          | TRUE     | READ_ONLY       |

#### WORKING SETINGS

* `USER_ID` > the id of the user. used around the spreadsheet to keep data to the user.
* `STANDERT_UNIT` > the unit that will be atoumaticly filed in
* `NEGATIVE_STOCK` > if the stock can go in the negative
* `EXPIRY` > if the user needs to fill in a expiry date
* `PRICE_ROUNDING` > if the user whants to round the price of items
* `AUTO_SKU` > if the user whants to auto generate the SKU
* `AUTO_GUEST_ROLE` > the role that the guest automaticly gets

* `USER_ID` > the id of the user. used around the spreadsheet to keep data to the user.

###  TAB 4 ***GUESTS***

| USER_ID        | GUEST_ID       | GUEST_NAME     | EMAIL       | PASSCODE                                                     | ADDED_DATE               | ACTIVE | RANK      | LAST_LOGGED_IN |
| -------------- | -------------- | -------------- | ----------- | ------------------------------------------------------------ | ------------------------ | ------ | --------- | -------------- |
| U1764277259593 | U1764278089525 | Rc_Stash_User1 | rc@stash.rc | $2b$10$ | 2025-11-27T21:14:49.525Z | TRUE   | read-only |                |

#### WORKING GUESTS

* `USER_ID` > the id of the user. used around the spreadsheet to keep data to the user.
* `GUEST_ID` > the id of the guest looks like (`USER_ID`:GUEST:`20 long random string like:` 12345678901234567890)
* `GUEST_NAME` > name of the guest (`USER_NAME`:`name chosen by the user`)
* `EMAIL` > email for the guest
* `PASSCODE` > the pascode fo the guest hash(Argon2 + salt).
* `ADDED_DATE` > the data the guest was created ***NEVER CHANGES***
* `ACTIVE` > if the user is active or not
* `RANK` > what the user can do (read-only, edit-inv, full-access)
* `LAST_LOGGED_IN` > when the user hase loged in 

### TAB 5 ***USER_WARNINGS***

| WARN_ID | USER_ID | WARNED_BY | WARN_REASON | WARN_DATE | SEEN_BY_USER |
| ------- | ------- | --------- | ----------- | --------- | -------------- |
|         |         |           |             |           |                |

#### WORKING USER_WARNINGS

* `WARN_ID` > the id of the warning (WARN:`20 long random string`)
* `USER_ID` > the id of the user. used around the spreadsheet to keep data to the user.
* `WARNED_BY` > the id of the perdon that warned the user
* `WARN_DATE` > the date the user got warned
* `SEEN_BY_USER` > if the warning was seen by the user