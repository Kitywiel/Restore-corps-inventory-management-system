# this is the spreadsheet info file.

## in this file the layout of the sheet will be explaned.

### tabs
| [USERS](#tab-1-users) | [INVENTORY](#tab-2-inventory) | [SETTINGS](#tab-3-settings) | [GUESTS](#tab-4-guests) | [USER_WARNINGS](#tab-5-user_warnings) |
|-------|-----------| --------------- | ------------- | ------------- |

---

### TAB 1 USERS

| USER_NAME | PASSCODE | EMAIL | USER_ID | INV_USED | USER_UNLIMITED | CREATED | LAST_LOGGED_IN | STATUS | ROLE | ITEM_LIMIT |
| --------- | -------- | ----- | ------------------------- | -------- | -------------- | ---------- | -------------- | ------ | ---- | ---------- |
|  user123  | $2b$10$  | T@T.A | USER:12345678901234567890 | 0 | TRUE / FALSE | 10/10/2025 | 10/10/2025 | ACTIVE | USER | 20 |

#### Working Users

* `USER_NAME` → the user name of the user.
* `PASSCODE` → the passcode for the user; hash (Argon2 + salt).
* `EMAIL` → the email of the user.
* `USER_ID` → the id of the user. Used around the spreadsheet to associate data with the user. (USER:20-character random string)
* `INV_USED` → total items in their inventory.
* `USER_UNLIMITED` → if the user has unlimited inventory.
* `CREATED` → set only when the user account is created.
* `LAST_LOGGED_IN` → updated each time the user logs in.
* `STATUS` → whether the account is active (only admins can change).
* `ROLE` → user or admin (`USER` is default).
* `ITEM_LIMIT` → max number of items the user can have, overridden if `USER_UNLIMITED` = TRUE.

---

### TAB 2 INVENTORY

| USER_ID | DESCRIPTION | ITEM_NAME | CATEGORY | SKU | QUANTITY | USED_QUANTITY | UNIT | PRICE | TOTAL_VALUE | LOCATION | MINIMUM_QUANTITY | INV_NUMMER | DATE_ADDED | DATE_UPDATED | ACTIVE | EXPIRY_DATE|
| ------- | ----------- | --------- | -------- | ---- | -------- | ------------- | ---- | ----- | ----------- | -------- | ---------------- | ---------- | -----------| -----------| ------ |--------|
| USER:12345678901234567890 | this is my first project | project 1 | item | pj01 | 10 | 0 | box | 0.99 | 9.9 | none | 5 | ITEM:12345678901234567890 | 2025-11-27T23:38:44.794Z | 2025-11-27T23:43:43.194Z | TRUE | FALSE |

#### Working Inventory

* `USER_ID` → the id of the user.
* `DESCRIPTION` → description of the item.
* `ITEM_NAME` → name of the item.
* `CATEGORY` → category of the item.
* `SKU` → stock keeping unit of the item.
* `QUANTITY` → how much of the item exists.
* `USED_QUANTITY` → how much has been used.
* `UNIT` → the unit (box, product, etc).
* `PRICE` → price of one item.
* `TOTAL_VALUE` → total price (`QUANTITY`*`PRICE`).
* `LOCATION` → storage location.
* `MINIMUM_QUANTITY` → threshold for low inventory alert.
* `INV_NUMMER` → item id (`ITEM:20-char id`).
* `DATE_ADDED` → date item first appeared (never changes).
* `DATE_UPDATED` → last edit date.
* `ACTIVE` → item is active or not.
* `EXPIRY_DATE` → either `FALSE` or a date.

---

### TAB 3 SETTINGS

| USER_ID | STANDARD_UNIT | NEGATIVE_STOCK | EXPIRY | PRICE_ROUNDING | AUTO_SKU | AUTO_GUEST_ROLE |
| ------- | ------------- | -------------- | ------ | -------------- | -------- | --------------- |
| U1764277259593 | UNIT | FALSE | FALSE | FALSE | TRUE | READ_ONLY |

#### Working Settings

* `USER_ID` → the id of the user.
* `STANDARD_UNIT` → unit that is auto-filled.
* `NEGATIVE_STOCK` → if negative stock is allowed.
* `EXPIRY` → if expiry dates are required.
* `PRICE_ROUNDING` → enables price rounding for items.
* `AUTO_SKU` → auto-generate SKU for user.
* `AUTO_GUEST_ROLE` → role granted to guests automatically.

---

### TAB 4 GUESTS

| USER_ID | GUEST_ID | GUEST_NAME | EMAIL | PASSCODE | ADDED_DATE | ACTIVE | RANK | LAST_LOGGED_IN |
| ------- | -------- | ---------- | ----- | -------- | ---------- | ------ | ---- | -------------- |
| U1764277259593 | U1764278089525 | Rc_Stash_User1 | rc@stash.rc | $2b$10$ | 2025-11-27T21:14:49.525Z | TRUE | read-only | |

#### Working Guests

* `USER_ID` → the id of the user.
* `GUEST_ID` → id for guest (`USER_ID`:GUEST:`20-char random string`)
* `GUEST_NAME` → guest name (`USER_NAME`: chosen name)
* `EMAIL` → email for the guest
* `PASSCODE` → hashed passcode (Argon2 + salt).
* `ADDED_DATE` → when guest created (never changes).
* `ACTIVE` → TRUE/FALSE.
* `RANK` → permissions (read-only, edit-inv, full-access).
* `LAST_LOGGED_IN` → last login date.

---

### TAB 5 USER_WARNINGS

| WARN_ID | USER_ID | WARNED_BY | WARN_REASON | WARN_DATE | SEEN_BY_USER |
| ------- | ------- | --------- | ----------- | --------- | -------------- |
|         |         |           |             |           |                |

#### Working User Warnings

* `WARN_ID` → id of the warning (`WARN:20-char random string`)
* `USER_ID` → id of the affected user.
* `WARNED_BY` → id of the person who warned.
* `WARN_REASON` → the reason given.
* `WARN_DATE` → date of warning.
* `SEEN_BY_USER` → displayed/read flag.