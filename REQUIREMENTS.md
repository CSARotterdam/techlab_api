# Requirements

## Common
**General**
* [ ] [M] privacy statement document
* [ ] [M] terms and conditions document
* [ ] [M] contact mail
* [ ] [C] contact form

**Account**
* [ ] [M] account security; encryption/hashing
* [ ] [M] register account
  * [ ] [M] supplied details
    - mail (student/teacher)
    - mobile number
    - password
    - repeat password
  * [ ] [M] accept privacy statement
  * [ ] [M] accept terms and conditions
* [ ] [M] accounts login/logout
  * [ ] [M] acount roles
  * [ ] [M] edit account details
    - mail (student/teacher)
    - mobile number
    - password
  * [ ] [M] delete account => GDPR
  * [ ] [S] account creation confirmation mail
  * [ ] [S] password reset
    * [ ] [M] send password reset mail
  
**Profile page**

_Note: there can be issues with multiple reservations at once, also with modifying reservations, should discuss_
* [ ] [M] see open loans
* [ ] [M] see placed reservations
  * [ ] [M] see reservations that need to be modified
  * [ ] [M] see accepted reservations
  * [ ] [M] see open reservations
  * [ ] [S] see not picked up, declined reservations
* [ ] [M] remove accepted placed reservation
* [ ] [S] see all previous loans
* [ ] [W] see loan suggestions

**Reservations**

_Note: there can be issues with multiple reservations at once, also with modifying reservations, should discuss_
* [ ] [M] select products from inventory
* [ ] [M] set start and end date
* [ ] [M] produce errors for reservation request
* [ ] [M] add reservation request to queue for admins to pick up
* [ ] [M] send mail to user about reservation placed
* [ ] [M] send mail to user about reservation accepted
* [ ] [M] send mail to user about reservation declined
* [ ] [M] send mail to user about reservation modification requested

**Admin**
* [ ] [M] admin accounts
  * [ ] [S] create account on behalf of student/teacher (without password)
    * [ ] [M] send mail to student/teacher to set a password and login
    * [ ] [M] let student/teacher create password and login
  * [ ] [W] password reset on behalf of student/teacher

_Note: there can be issues with multiple reservations at once, also with modifying reservations, should discuss_
* [ ] [M] see all non-accepted reservations
  * [ ] [M] accept or decline reservations
  * [ ] [M] send modify request for reservation
  
  
**Inventory**
* [ ] [M] add product
* [ ] [M] modify product
  * [ ] [M] set details
    - title
    - description
    - amount
    - image
    - etc.
* [ ] [M] remove product
  * [ ] [M] only remove if not loaned and all are in stock

**Notifications**
* [ ] [M] loan is late reminder (mail)
* [ ] [S] loan is late reminder (frontend)
* [ ] [C] broadcast mails; opening times, events, etc.
* [ ] [C] loan is far too late (mail to admin, who calls student/teacher on mobile phone)

**Statistics**

TODO

# Flow

## Frontend

### Placing a reservation

1. Student/teacher has account?
    * if not, let admin create account
1. checkout inventory
1. select products
1. overview of selected products
1. select start and end date
1. place reservation
    * if invalid, get corrections/modification request
1. sign
1. wait for accept, decline or modification response

### Returning products

1. physically present
1. search for student/teacher mail/username
1. see open loans
1. select applicable loan
1. count products and mutate broken ones if present
1. sign
1. archive

## Backend
