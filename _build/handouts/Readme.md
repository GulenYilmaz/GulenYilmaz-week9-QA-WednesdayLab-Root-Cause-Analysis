Week_9
Increasing Confidence and the Purpose of QA
Initial results from inspecting the site:

“Forgot password” function appears to be broken
Map covers Utah only and has a marker at Lat 0 Long 0
Test items in order:

Create account for renter and user
Login / log out / log back in
Create item to rent
Rent item out
Rent an item from owner
Check owner profile and renter profile
Review item
Yoodlize Search Test

Search for Rubik’s Cube from home page search produces no results
Searching Toys and Games catalog for Rubik’s Cube also no results; from page 5 of Advanced Search results in Toys and Games category, no results
Metrics:

Selecting “See All” on the front page for any category only displays about half the pages of items. The rest of the pages show “No Results” when clicked.
Forgot Password does nothing
Map covers Utah
Item cannot be shown for rent outside Utah
Create an account hard to find
Categories are not curated; Ford Excursion Limo is not clothing
Facebook reviews indicate Yoodlize may not be as careful with customer data as they could be
Resizing page can take user to a page requesting user download mobile app
Listings appear in catalog but do not persist on user page
Posted items cannot be edited
What are some good things about Yoodlize?

Tells a story clearly
Handles pictures logically and consistently
Good categorization
Easy to sign up
Test Report:

Yoodlize is a site with great potential, that only needs some attention to a few important details before it can marry a great concept with great execution. When the user first encounters Yoodlize, they are drawn in immediately by bright colors and friendly, sans-serif fonts. After the user finds the sign-up function, signing up for a new account is easy and intuitive.

After a strong start, however, some issues show:

While signing up is easy, if a user forgets their password, the “forgot password” function does not work.
Once a user posts an item for rent, that item doesn’t stay on their profile page, and it cannot be edited.
When searching for items through the “See All” links shown on the front page for each category, not all the items will be displayed.
Login does not work on different browsers.
Items only display when the user who posted them is logged in. Those are some of the major issues. I’m sure with a little more time we can give the site a thorough check and help develop an action plan for fixing any problems.
Pilot Support and the Process of QA

Was the customer justified with their complaints?
A: Absolutely. Apparently, nobody told the customer this wasn’t the final product.

Did the QA do a good job responding to the customer’s complaints?
A: The QA did an okay job responding to the customer’s complaints. Too much justification and not enough listening and attempting to try to figure out how they ended up here in the first place. It’s good to address customer dissatisfaction, but better to avoid it in the first place.

Would you address them in a different way?
A: I would definitely address the customer in a different way. If the customer is just now hearing that what they’re seeing is a prototype, it makes the customer think we’re a bunch of amateurs. The progression of product releases should have been communicated clearly to all stakeholders well in advance. The testing could have been preceded by a showcase session to set expectations. Better still would have been to limit releases to more fully functional versions.

What information would you need to adequately respond to their concerns?
The original specifications and any further changes arising from other communications with the customer. Customer’s Feature Checklist:

Enter all required data, including email
Save entered data
Search for data
Log in and log out
Attractive styling
Testing Document Outline:

What are we testing? We are testing the data entry, save, and cancel functions
How long will we test? Until all tests are complete or allotted time ends
Are there pieces we won’t test? Connectivity to database will not be tested
How do we plan to test? We will test by changing each of the employee fields and entering, then doing the same and cancelling.
How will we know we’re done testing?
We will know we are done when all functions have been tested.

Testing: Basic functionality is good. Data is not saved after refreshing browser.

Test Document:

Purpose: To test the XYZ Company Employee Manager app for functionality Application Overview: The Employee Manager app allows the user to enter employee data in the form of an employee card containing field for name, phone number, and employee title. Employees are given an employee ID number that cannot be changed.

Testing Scope:

In-Scope:

Entering data, saving data, basic functionality, security check

Test 1: Enter null data

Result: Entering blank name deletes employee but leaves blank where 
employee name was. Entering blank data in other forms has no effect. 
Test 2: Entering incorrect phone number

Result: Entering overly long string of numbers or entering letters is not prevented, 
although console appears to detect “Uncaught RangeError: Maximum call stack size exceeded”
Test 3: Entering long string length in title

Result: No limits on string length in title
Test 4: Entering special characters

Result: Special characters can be entered for name, phone number and title without restriction
Test 5: Using cancel button

Cancel button works
Test 6: Security

Certificate is valid and trusted, connection is secure, resources are served securely
Test 7: Speed

Chrome Lighthouse test returns 100%. Suggests removing non-functional JavaScript for 0.15s saving
Test 8: General visual

Result: Employee ID 4 is actually -4
Out of Scope:

System Integration testing
Regression testing
Items not tested:

None
Metrics:

5 out of 5 
Test Environment and Tools: Windows 11, Chrome 96.0.4664.45

Lessons Learned:

Chrome has some testing tools built in
Testing may uncover unexpected side effects that force you to go back and redo the tests
Recommendations:

Add email field
Change Employee ID 4
Restrict entry length and use of special characters
Best Practices:

Restricting entry of special characters prevents use of unwanted scripting commands 
and reduces the likelihood of bad data being entered into the system either intentionally or unintentionally.
Exit Criteria:

When all functions have been tested or allotted time is complete
Conclusion:

Employee Manager is a solid performer that needs a few changes to achieve perfection. 
Add an email field, make all the entry fields sensitive to string length and content, disallow entering null data.
Definitions, Acronyms, Abbreviations: N/A

Root Cause Analysis

New Features
Text entries have upper and lower limits
Phone number entry must be ten digits
New employees can be added
Bug fixes
Text entries have upper and lower limits
Phone entries must be ten digits
Items I’d like to see added:

A second field for both email and phone
Notes on design/user flow:

Design is simple, intuitive
Adding new employees as “New Employee” means erasing the text, raising the potential for mistakes
New employees can’t be added below the bottom of the browser screen
What features are listed to be added in the docs?

Phone numbers will be formatted in US format
Employee list will be on database and accessed through API
A search function will be added to filter employee list based on Job Title, Name, and/or ID
An email address field will be added
How do you want to see these features implemented?

I’d like to see these features implemented for the next release
Some of the reasons why issues brought up by the customer have not yet been addressed might be that the app is still in the prototype stage, and that the functionality to support the features mentioned by the customer aren’t ready yet.
Customer Update Letter:

Hi, I just wanted to tell you about the latest features we’ve added to your app, Employee Manager.

Since the last time you saw it, we’ve added the ability to add new employees to the list, and upper and lower limits to the number of characters that can be entered.

This should greatly reduce the possibility of faulty entries. No blank entries can be made.

The app now saves data until the browser refreshes. The save and cancel buttons are now only available after changes have been made, and the cancel button will revert the entry back to the most recently saved version.

We’ve also fixed our error message functions and enabled the save function to work after error messages are sent.

We remember how you felt about the style and looks, and hope to have your input incorporated into an upcoming release. We also remember you requested a log-in/log-out function and search function as well, and will be adding those to upcoming releases.

Rather than set specific dates in this letter for those functions, I’d like to put them on the roadmap at the earliest opportunity. How about our upcoming Planning meeting?

QA Manager Report:

During this sprint:

Added the “Add New Employee” function
Save and cancel buttons only work after changes are made
No blank entries are allowed
Cancel button reverts to previous save
Fixed the bug in the employee ID that caused one to be a negative number
Fixed error messages
Enabled saving after error message
Set upper and lower limits on text entry lengths
Set telephone number entries to ten digits only
Planning and Reporting Results https://trello.com/b/JffVtRqK/planning-reporting-results-employee-manager-app