# Problem Statement  
Mitron Bank is a legacy financial institution headquartered in Hyderabad. They want to introduce a new line of credit cards, aiming to broaden its product offerings and reach in the financial market.  

AtliQ Data Services came to know about this through an internal link and approached Mitron Bank with a proposal to implement this project. However, strategy director of Mitron Bank, Mr.Bashnir Rover is skeptical and asked them to do a pilot project with the sample data before handing them the full project. They provided a sample dataset of 4000 customers across five cities on their online spend and other details.  

## 1. ASK  
Stakeholder: Mr. Bashnir Rover 

### Questions:  
- Demographic classification: Classify the customers based on available demography such as age group, gender, occupation etc. and provide insights based on them.
- Spending Insights: Where do people spend money the most? Does it have any impact due to occupation, gender, city, age etc.? This can help you to add relevant credit card features for specific target groups.
- Key Customer Segments: By doing above, you should be able to identify and profile key customer segments that are likely to be the highest-value users of the new credit cards. This includes understanding their demographics, spending behaviours, and financial preferences.
- Credit Card Feature Recommendations: Provide recommendations on what key features should be included in the credit card which will improve the likelihood of credit card usage. This should be backed by the insights from data provided and also some secondary research on the internet for this.


## 2. PREPARE  
### Data Storage:
The public dataset is completely available on the Code basis website platform where it stores and consolidates all available datasets for analysis. The specific individual datasets at hand can be obtained at this link below: https://codebasics.io/challenge/codebasics-resume-project-challenge  

### Data Organized:
The dataset is taken from the AtliQ. Thanks to the AtliQ for providing datasets for public access which is a great learning asset - feel free to explore them. This dataset contains only 2 csv file and 1 text file (meta_data)


## 3. PROCESS  
### Tools Used:
- Microsoft Excel
- Power BI

### Data Used:
dim_customers, fact_spends  

### About Data:  
Column Description for dim_customers:
- customer_id: This column represents the Unique ID assigned to each customer.
- gender: This column represents the gender of the customer. (Male, Female)
- age_group: This column categorizes the customer into different age groups. (21-24, 25-34, 35-45, 45+)
- marital_status: This column indicates the marital status of the customer (single, married).
- city: This column represents the city of residence for the customer. (Mumbai, Delhi-NCR, Chennai, Hyderabad, Bengaluru)
- occupation: This column denotes the occupation or profession of the customer. (Salaried IT Employees, Salaried Other Employees, Business Owners, Freelancers, Government Employees)
- average_income: This column indicates the monthly average income of the customer, in INR currency.

Column Description for fact_spends:
- customer_id: This column represents the Unique ID of each customer, linking to the dim_customer table.
- month: This column indicates the month in which the spending was recorded. (May, June, July, August, September, October)
- category: This column describes the category of spending (Entertainment, Apparel, Electronics, etc).
- payment_type: This column specifies the type of payment used by the customer (Debit Card, Credit Card, UPI, Net Banking).
- spends: This column shows the total amount spent by the customer in the specified month, category and payment_type.

### Data Cleaning & Transformation:
- Microsoft Excel was used to clean and transform raw data.
- Duplicates were checked and removed.
- Gaps were checked with the TRIM function.
- Delhi NCR change into New Delhi


## 4. ANALYZE  
Data Analyzing  
Power BI was used to analyze data.  

### Key Metrics:
Avg income utilisation%: Find the average income utilisation % of customers (avg_spends/avg_income). The higher the average income utilisation%, the more is their likelihood to use credit cards.

### KPIs:  
- Annual Expenditure = [Expenditure]*2
- Annual Income = [Income]*2
- Average Monthly Spend = AVERAGE(fact_spends[spend])
- Credit Card = CALCULATE([Utilisation %], fact_spends[payment_type]="Credit Card")
- Customers = COUNT(dim_customers[customer_id])
- Expenditure = SUM(fact_spends[spend])
- Expenditure* = SUM(fact_spends[spend])/6
- Female = CALCULATE([Customers], dim_customers[gender]="Female")
- Female Utilization = CALCULATE([Utilisation %], dim_customers[gender]="Female")
- Income = SUM(dim_customers[income])
- Income* = SUM(dim_customers[avg_income])
- Male = CALCULATE([Customers], dim_customers[gender]="Male")
- Male Utilization = CALCULATE([Utilisation %], dim_customers[gender]="Male")
- Male% = [Male]/[Customers]
- Net Banking = CALCULATE([Utilisation %], fact_spends[payment_type]="Net Banking")
- Saving = [Income]-[Expenditure]
- Saving* = [Income*]-[Expenditure*]
- Transaction = COUNT(fact_spends[customer_id])
- UPI = CALCULATE([Utilisation %], fact_spends[payment_type]="UPI")
- Utilisation % = [Expenditure*]/[Income*]


## 5. SHARE   
![1717956853299](https://github.com/iankitnegi/PowerBI_Banking_Project/assets/132642567/218e6b53-d9ad-49cf-ae18-27431a29f7c0)  
![1717956853293](https://github.com/iankitnegi/PowerBI_Banking_Project/assets/132642567/c53c50ca-df87-4452-be49-68ee02d0649e)


## 6. ACT  
### Insights:
- Key Metrics: Customer: 4000, Male: 2597, Female: 1403, Total Transactions: 864K, Total Income: 1240M, Total Expenditure: 531M, Average Income Utilization: 42.82%
- Age group distribution shows a peak in the 25-35 category, with a total of 1498 individuals.
- Mumbai city boasts the highest count with 1078 customers.
- Credit cards lead in spending, totaling $216 million, with a utilization rate of 17.45%.
- September emerges as the peak spending month, totaling $116 million, constituting 21.84% of the total spend.
- Males exhibit a higher income utilization rate at 44.39%, compared to females at 39.92%.


### Recommendations:  
- Offering cashback or No Cost EMI options during September and August can drive credit card sales, especially during festive seasons when customer spending peaks.
- Target audience comprises married males aged 25-34 working in the IT sector & residing in Mumbai. Their higher income levels make it easier for them to manage credit card repayments.
- Spending patterns, Bills (105M) and Groceries (85M) are the top categories. Offering reward points specifically in these categories could significantly boost credit card usage, leading to increased credit charges.
- Credit cards and UPI are the most preferred modes of payment. By integrating credit card options within UPI apps, we can significantly boost the indirect use of credit cards.


Thank you for reading and evaluating my repo :)  
Live Dashboard [Link](https://app.powerbi.com/view?r=eyJrIjoiYmI1ZDVkMzYtOTNjMi00NDA5LWFlYjQtZDg0OTBlYzNmOThmIiwidCI6ImM2ZTU0OWIzLTVmNDUtNDAzMi1hYWU5LWQ0MjQ0ZGM1YjJjNCJ9)
