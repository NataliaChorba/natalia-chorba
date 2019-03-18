# Monefy iOS application testing

## Environments 
* Clients: devices or simulators with different screen resolutions: iPhone XS Max, XR, X, 8+, 8, SE, iPads: 10-, 11-, 12.9-inches, Air, Mini
* OS versions: the latest one (currently 12.4.1) and 2 major previous versions (11.4.1, 10.3.3)
* Backend: production and staging

## Tools
* Manual testing: Charles proxy, TestRail
* Automated testing: solution tbd within the team, e.g. XCTest, Postman

## Testing levels
* Unit tests
* API tests
* UI tests, manual and automated
* E2E and exploratory tests
* Live monitoring services

## Testing checklist

## Data connectivity
* Wi-fi
* 3G networks
* 2G or low speed networks 
* No connectivity / Airplane mode

## Device functions
* On call
* Background musik
* Lock screen
* Incoming push notifications
* Go to background mode and then restore
* Kill the app and open again
* Different time zone settings
* Different language settings
* Time behavior: let the phone lay
* Running in law resources

## CRUD (create, read, update, delete)
* Install
* Uninstall, what data left?
* Update: user data and settings didn't change, no functional regressions
* Unlock the app, check that payed functions become available

## Performance and load
* Lounch time
* Resources usage
* Response time of the app
* API response time 
* Emulate load on server and check response time

## UI and usability
* Look and feel
* Easy navigation
* Clarity and readability
* Different screen orientations
* Layout and colors
* Error messages
* Change theme

## Security
* Where password is stored and is it kept in readable form
* FaceID/TouchID

## Localization and Internationalization
* No missing translations
* No stringcuts / broken layout in different languages
* User data is kept when switching languages
* User input in different alphabets

## Tracking
* All required event are sent
* Verify requests parameters values

## Accessibility
* Zoom 
* Enlarged text
* Colorblind

## Beta-testing
* Exploratory black box testing from non-stakeholders

##F unctional testing

### Balance
#### Change balance
* By taping on + button
* By taping on - button
* By taping on category name
* By taping on money amount in balance view
* Cancel balance changes
* Add/remove to cash and payment cart
* Add / remove 0, negative numbers, max allowed numbers, values more than max allowed numbers, invalid money format
* Verify calculator operations
* Add note: empty, different alphabets, special symbols, max length
* Choose category, verify list of available categories for + and -, add new category
#### Balance overview
* Total balance value is correct 
* Time period filters: day, week, month, year, all
* Choose specific date: date with records, date with no records, date in future. Validate error message
* Choose accounts: cart, cash, all accounts
* Counters on category names are same as number of records under category
* Total number is sum of numbers in categories
* Number in categories is sum of numbers in records under categories
* Edit existing records: change amount, category, note
* Delete existing records
* Undo changes
### Money transfer
* Transfer from cash to payment card
* Transfer from payment card to cash
* Transfer to same account, verify error message
* Add note: empty, different alphabets, special symbols, max length
* Verify calculator operations
* Transfer more than available amount
* Transfer 0, negative numbers, max allowed numbers, values more than max allowed numbers, invalid money format
* Undo transfer
* Cancel transfer
* Select date of transfer
* Select date in future
### Charts
* Verify numbers by categories
* Verify balance
* Time period filters: day, week, month, year, all
* Choose specific date: date with records, date with no records, date in future. Validate error message
* Choose accounts: cart, cash, all accounts
* Swipe between charts
* Change balance and check chart is updated
### Categories
* Change icon
* Change name: positive and negative checks
* Delete category
* Undo changes
* Disable category, check that it was removed from chart and list of available categories when changing balance
* Enable category, check that category appeared again
* Cancel changes
* Merge categories and add expence to merged category
* Add expence of specific category and the delete this category
* Create new category and add expences to new category
### Accounts
* Change name
* Change currency
* Change icon
* Include/exclude from balance
* Change initial account balance and date 
* Delete account
* Add new account
* Manage multi-currency accounts
### Budget
* Set month budget
* Check what happens when user is running out of budget
* Change budget amount
### Export to file
* Try different separators and delimiters
* Export to different locations and applications
* Check that file is readable and contains all data
### Synchronization
* Google drive
* Dropbox
* Verify error messages when synchronization is not possible (no internet, read-only mode)
* Open app on different devices and check that all data and settings are synchronized
### Data backup
* Create backup
* Create backup, file can't be saved
* Restore from backup
* Restore from backup of old app version
* Restore from corrupted backup file
* Check that backups history is available
* Restore from different backups
* Clear data, check that no data is left in the app and in all other locations (google drive, phone, dropbox)
### About
* Version and release notes
* Links are clickable
* Disable google analytics and run regression tests. Check in proxy that no events are sent out

## Prioritization of test cases

Main priority checks which highest customer impact would be:
* E2E positive user paths with checks of basic functionality: add/remove to/from balance, show charts by categories, view balance history for specific periods and for accounts
* App response time checks
* Crash rate
* Checks that customer data is not wiped/damaged during app updates or manipulations within the app


















