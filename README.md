# CIS_5800_Cube55
This is a simple application created using Microsoft Access for Cube 55, a food cart near Baruch College. It allows the food cart to store information about customers, orders, menu, and allows customers to place orders and track order status.

Cube 55 does not have an order management system. Customers need to place an order in person, by waiting in long lines. Since almost all of its customers are Baruch College students, the long lines are inconvenient for students who have to rush to classes with a short lunch break. This application is aimed to decrease the long waiting lines by allowing customers to place an order beforehand and only come in person to the food cart to pick up their orders after getting the notification that their orders are ready for pick up. This saves a lot of time. It also makes the job easier for the food crat staff because now they can only focus on preparing high quality food for their customers and worry less about preparing food at the same time taking in-person orders from customers.

Tables 

The tables are for internal use by Cube 55. It stores data about the customers who create an account with Cube 55, Cube 55's updated menu, and business operational data including the costs, revenue and profits for each month. 

Forms

Forms can be used by customes to create an account with Cube 55, log into their accounts, place orders conveniently, track orders, and make payment. The form for order placement has navigation buttons like "go to the next record, go to the previous record, go to the first record, go to the last record" and buttons to save and delete a record. There is a drop down list created using Access combo box and VBA that allows customers to choose an order easily by viewing the menu items without having to go back to the meny table to view the meny items. There is also a section for notes which is optional but it is a great way for customers placing online orders to communicate with the food cart staff regarding special food accommodations, enabling Cube 55 to provide high quality customer service.
Account Creation

Next, all the application features are described in detail below including sample code using VBA and SQL.

The form named Customer_Account_info has been designed to enable a customer to create an account with Cube 55. When a customer opens this form and clicks the “Create new account” button, a unique Customer ID is generated automatically by the system for each customer. The form then allows the customer to type in a username and a password that can contain letters, numbers, spaces, and any special characters. This is because in MS Access, the data type for the username and password is short text. The Customer ID is set to be the primary key for this table to ensure that there are no two customers with the same Customer ID. 
The customer can then press the “Save” or the “Create new account” button to create an account. Either one of these buttons need to be pressed after the customer fills in the username and the password to create an account. Once that is done, the customer account information is automatically stored in the table named “Customer_Account_info”. One of the reasons why tables have been designed for just internal use for Cube 55 is because these tables contain sensitive personal information about each customer and so should not be made available to the public. It is Cube 55’s responsibility to ensure that customer information is protected, and data privacy regulations are strictly enforced.

User Login and Authentication

Customers can use the form “Login_Form” to log in to their accounts. The LoginID on this form is a unique ID given to each login session. After a customer enters the username and the password, the button “Login” on the “Login_Form” should be clicked to log in. Once this is done, the data used for log in is immediately updated in the table named “Login”. The query named “Check_Login_Query” checks if the username and password entered by the user in the “Login_Form” matches with the username and password in the table “Customer_Account_info” from when the customer first created an account. The query results show only the matches found after which customers can be allowed to successfully login.

Database
Microsoft Access is a database management tool that can be used by Cube 55 to store data about customer information, customer orders, and internal business operations data such as sales revenue, profit, costs, etc. The forms or the system interface used by customers are efficiently linked with the tables in MS Access so that data is conveniently updated in real time. 

Home Page and Dashboard

Customers can use the “Cube 55 Navigation Form” under forms, to view and navigate the different sections of the home page and dashboard. Using this navigation form, customers can clearly see the various functions of the website which allow creating customer accounts, viewing the menu of Cube 55, and placing and managing orders. Alternatively, the customers can also use the individual forms named “Customer_Account_info_form” and “Customer_Orders_Form” to create an account and place orders respectively. The customer can also view the menu separately using the report named “Menu”. To view a complete list of orders placed by the customer (order history), the customer can use the report named “Customer_Ordered_Report”. 

Menu
As mentioned above, customers can view the menu directly from the “Cube 55 Navigation Form” under forms that serve as the Home Page and Dashboard for Cube 55 customers. The customers can also view the menu from the report named “Menu”. The menu has the MenuID which is a unique ID assigned to each menu item that Cube 55 offers. Each MenuID is paired with an item name, item description, and item price.

Place Orders
The system provides the functionality for customers to place, delete, and manage orders. The form, “Customer_Orders_Form”, can be used by a customer to manage orders. Each order placed by a customer is given a unique ID which is the primary key for this table. A customer can choose an item on Cube 55’s menu from the drop-down list to place an order. For each order, a customer can write a note for the chef. If there are dietary restrictions that Cube 55 needs to be made aware of for each order, a customer can write in the notes section, for example, “Less salt and oil”. Therefore, notes are an excellent way for customers placing contact-less orders to communicate with Cube 55 and to allow Cube 55 to consider their customer’s preferences for how their food needs to be prepared, enabling Cube 55 to provide personalized attention to each customer and order. It should be highlighted that notes are optional.

Once the customer selects a menu item to order, the button “Place Order” should be pressed to place an order. The order is not placed without clicking this button. Once the button is clicked, the order can be seen under the table named, “Customer_Orders”, by Cube 55. However, since the MS Access tables and the form for customer orders are updated in real time, Cube 55 should not rely on the “Customer_Orders” table to start preparing an item immediately because a customer may remove an order that is placed using the form and when that happens, the order will be removed automatically from the table as well. To solve this issue, customers can be informed through the form that if they need to edit or cancel an order, it needs to be done within 10 minutes after initially placing an order and after the 10 minutes, they will not be able to edit an order. If the customer chooses to cancel an order after the 10 minutes, the customer will bear the full cost of the menu item. 

As mentioned, a customer can click the “Remove Order” button to remove an order that was placed. Just to clarify, we are focusing on orders placed by a single customer or user of the system which means that the application does not allow a way for an order to be lined with a specific customer. Orders need to be placed one at a time by clicking the “Place Order” button. The customer will be able to place another order by clicking the “Place Order” button after their first order has been placed. Alternatively, the customer can press the “Go to the next order” button. 
Customers can also navigate through the orders placed easily by clicking the “Go to the next order”, “Go to the first ordered item”, “Go to the previous order”, or “Go to the last order”. These navigation tools will be useful for customers to edit or cancel an order. There is also a button named “Save” so that customers can rest assured that their orders have been placed successfully. Finally, there is also a search icon on the form that customers can use to search for a specific thing that they are looking for on that form. They can simply type in keywords in the search dialog box that appears after clicking the button and they will be able to see results if the keywords have been matched. However, the focus of this project is not on the search tool.

Payment Gateway
The form “Payment_Form” can be used by a customer to fill in the name on the debit/credit card, the card number, and the card pin to make a payment. The form is designed as a simple payment gateway, giving each payment session a unique PaymentID. The customer can view the total, tax, and the total amount to be paid before entering the card details to make the payment. There is a button named “Save Payment Info” for customers who would like to save their payment information. However, this button is just for view purposes because all payment information are automatically transferred to the table “Payment” once the form is submitted using the “Submit” button. 

In this case, the table data is what will go to the financial institution who will take necessary steps to check if the payment can be processed. The form provides a simple understanding of the system interface a user will have for the payment gateway.

Order Tracking Functionality (Customer)
Once the customer submits an order request using the form “Customer_Orders_Form”, all the order information from the form is updated automatically in the table “Customer_Orders”. This table can be used by Cube 55 to update the status of the order using the table field “status”. 

This order status can then be seen by the customer immediately in real time from the form “Order_tracking_Form”. The form has also useful buttons to navigate through the customer orders like going to the previous, next, first or last order to see their status.

Order Tracking Functionality (Staff)

Like mentioned above, the table “Customer_Orders” can be used by Cube 55 to update the status of the order using the table field “status”.

Staff Analytics Reports
Three queries have been designed in Access that are just a few examples of how the application we designed can be used to perform data analysis. There is a query named “2023 Progress Query” to show business operational data from the table “Business_Analytics” for just 2023. There is also a similar query for 2024 named “2024 Progress Query”. The third query “Profit 2024 Query” shows all the months for 2024 where Cube 55’s profit was greater than $20,000. 

Reports can be generated easily using the application. A report named “2024 Profit Over $20K” shows the query results from the query named “Profit 2024 Query”. The “2024 Progress Report” is a sample report that shows Cube 55’s business report. Likewise, other reports can easily be created to provide insights for Cube 55 about how they can improve their business operations and optimize performance by lowering costs and increasing revenue and profits. 

For example, by looking at the “2024 Profit Over $20K Report”, Cube 55 can conclude that profit was below $20K during the month of May 2024 compared to others. Taking a closer look at the May 2024 data, Cube 55 will see that the lower profit was due to the higher cost during that month compared to the other months. Moreover, the revenue in May 2024 was also the lowest $20K which decreased Cube 55’s profit drastically for that month. These reports provide Cube 55 a simple and quick starting point to taking necessary steps to fix potential business issues. For example, now using this report, Cube 55 will realize the need to conduct deeper analysis of why the cost might have increased and the revenue might have decreased for May. Doing that will enable Cube 55 to figure out the bottleneck to work on to fix the issue. 

Source Code Sample

To enable customers to select a menu item from the drop-down list, a combo box in MS Access was created using VBA. The following code used is:

Option Compare Database
 
Private Sub Combo Box_AfterUpdate()
    Dim db As DAO.Database
    Dim rs As DAO.Recordset
    
    Set db = CurrentDb
    Set rs = db.OpenRecordset("Customer_Orders", dbOpenDynaset)
    
    rs.AddNew
    rs![SelectedMenuItem] = Me.ComboBox.Value
    rs.Update
    
    rs.Close
    Set rs = Nothing
    Set db = Nothing
End Sub
 
Overall, this code snippet captures the event when a user selects an item from a combo box. It then adds a new record to the "Customer_Orders" table in the current database, with the value selected in the combo box stored in the "SelectedMenuItem" field of the new record.

Code for creating the query to check if the user name and the password from the table that stores data from when the account was originally created, match with the input data from customers through the login form.

SQL Code
SELECT Customer_Account_info.UserName AS Customer_Account_info_UserName, Customer_Account_info.Password AS Customer_Account_info_Password
FROM Customer_Account_info INNER JOIN Login_Table ON (Customer_Account_info.Password = Login_Table.PassWord) AND (Customer_Account_info.[UserName] = Login_Table.[UserName]);

“2023 Progress Query”
SQL Code:
SELECT Business_Analytics.Year, Business_Analytics.Month, Business_Analytics.Cost, Business_Analytics.Revenue, Business_Analytics.Profit
FROM Business_Analytics
WHERE (((Business_Analytics.Year)="2023"));

“2024 Progress Query”
SQL Code:
SELECT Business_Analytics.Year, Business_Analytics.Month, Business_Analytics.Cost, Business_Analytics.Revenue, Business_Analytics.Profit
FROM Business_Analytics
WHERE (((Business_Analytics.Year)="2024"));

“Profit 2024 Query”
SQL Code:
SELECT Business_Analytics.Year, Business_Analytics.Month, Business_Analytics.Cost, Business_Analytics.Revenue, Business_Analytics.Profit
FROM Business_Analytics
WHERE (((Business_Analytics.Year)="2024") AND ((Business_Analytics.Profit)>20000));




