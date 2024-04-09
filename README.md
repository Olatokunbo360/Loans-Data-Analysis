# Loans Data Analysis
 Data analysis of Loans obtained from a Bank

 # ( Exploratory Analysis of Prosper Loan Dataset )
## by (Yusuf Sanni)


## Dataset

>

This data set contains 113,937 loans with 81 variables on each loan, including loan amount, interest rate, current loan status, borrower income, and many others. The analysis in this part would be structured to provide simple univariate relationships to multivariate relationships, this research would provide answers to questions like whether the monthly loan payment has a correlation or any relationship between loan original amount, what is the spread of term of loan in loan status, identifying the frequency of the categorical variables; Term of loan, borrower's employment status, year of loan, and loan status, are there differences between loans depending on how the loan term large the original loan amount was.

The dataset used for this was sourced from Kaggle and it includes the following attributes:

* **ListingKey**:Unique key for each listing, same value as the 'key' used in the listing object in the API.
* **ListingNumber**:	The number that uniquely identifies the listing to the public as displayed on the website.
* **ListingCreationDate**:	The date the listing was created.
* **CreditGrade**:	The Credit rating that was assigned at the time the listing went live. Applicable for listings pre-2009 period and will only be populated for those listings.
* **Term**:	The length of the loan expressed in months.
* **LoanStatus**:	The current status of the loan: Cancelled,  Chargedoff, Completed, Current, Defaulted, FinalPaymentInProgress, PastDue. The PastDue status will be accompanied by a delinquency bucket.
* **ClosedDate**:	Closed date is applicable for Cancelled, Completed, Chargedoff and Defaulted loan statuses.
* **BorrowerAPR**:	The Borrower's Annual Percentage Rate (APR) for the loan.
* **BorrowerRate**:	The Borrower's interest rate for this loan.
* **LenderYield**:	The Lender yield on the loan. Lender yield is equal to the interest rate on the loan less the servicing fee.
* **EstimatedEffectiveYield**:	Effective yield is equal to the borrower interest rate (i) minus the servicing fee rate, (ii) minus estimated uncollected interest on charge-offs, (iii) plus estimated collected late fees.  Applicable for loans originated after July 2009.
* **EstimatedLoss**:	Estimated loss is the estimated principal loss on charge-offs. Applicable for loans originated after July 2009.
* **EstimatedReturn**:	The estimated return assigned to the listing at the time it was created. Estimated return is the difference between the Estimated Effective Yield and the Estimated Loss Rate. Applicable for loans originated after July 2009.
* **ProsperRating (numeric)**:	The  Prosper Rating assigned at the time the listing was created: 0 - N/A, 1 - HR, 2 - E, 3 - D, 4 - C, 5 - B, 6 - A, 7 - AA.  Applicable for loans originated after July 2009.
* **ProsperRating (Alpha)**:	The Prosper Rating assigned at the time the listing was created between AA - HR.  Applicable for loans originated after July 2009.
* **ProsperScore**:	A custom risk score built using historical Prosper data. The score ranges from 1-11, with 11 being the best, or lowest risk score.  Applicable for loans originated after July 2009.
* **ListingCategory**:	The category of the listing that the borrower selected when posting their listing: 0 - Not Available, 1 - Debt Consolidation, 2 - Home Improvement, 3 - Business, 4 - Personal Loan, 5 - Student Use, 6 - Auto, 7- Other, 8 - Baby&Adoption, 9 - Boat, 10 - Cosmetic Procedure, 11 - Engagement Ring, 12 - Green Loans, 13 - Household Expenses, 14 - Large Purchases, 15 - Medical/Dental, 16 - Motorcycle, 17 - RV, 18 - Taxes, 19 - Vacation, 20 - Wedding Loans
* **BorrowerState**:	The two letter abbreviation of the state of the address of the borrower at the time the Listing was created.
* **Occupation**:	The Occupation selected by the Borrower at the time they created the listing.
* **EmploymentStatus**:	The employment status of the borrower at the time they posted the listing.
* **EmploymentStatusDuration**:	The length in months of the employment status at the time the listing was created.
* **IsBorrowerHomeowner**:	A Borrower will be classified as a homowner if they have a mortgage on their credit profile or provide documentation confirming they are a homeowner.
* **CurrentlyInGroup**:	Specifies whether or not the Borrower was in a group at the time the listing was created.
* **GroupKey**:	The Key of the group in which the Borrower is a member of. Value will be null if the borrower does not have a group affiliation.
* **DateCreditPulled**:	The date the credit profile was pulled.
* **CreditScoreRangeLower**:	The lower value representing the range of the borrower's credit score as provided by a consumer credit rating agency.
* **CreditScoreRangeUpper**:	The upper value representing the range of the borrower's credit score as provided by a consumer credit rating agency.
* **FirstRecordedCreditLine**:	The date the first credit line was opened.
* **CurrentCreditLines**:	Number of current credit lines at the time the credit profile was pulled.
* **OpenCreditLines**:	Number of open credit lines at the time the credit profile was pulled.
* **TotalCreditLinespast7years**:	Number of credit lines in the past seven years at the time the credit profile was pulled.
* **OpenRevolvingAccounts**:	Number of open revolving accounts at the time the credit profile was pulled.
* **OpenRevolvingMonthlyPayment**:	Monthly payment on revolving accounts at the time the credit profile was pulled.
* **InquiriesLast6Months**:	Number of inquiries in the past six months at the time the credit profile was pulled.
* **TotalInquiries**:	Total number of inquiries at the time the credit profile was pulled.
* **CurrentDelinquencies**:	Number of accounts delinquent at the time the credit profile was pulled.
* **AmountDelinquent**:	Dollars delinquent at the time the credit profile was pulled.
* **DelinquenciesLast7Years**:	Number of delinquencies in the past 7 years at the time the credit profile was pulled.
* **PublicRecordsLast10Years**:	Number of public records in the past 10 years at the time the credit profile was pulled.
* **PublicRecordsLast12Months**:	Number of public records in the past 12 months at the time the credit profile was pulled.
* **RevolvingCreditBalance**:	Dollars of revolving credit at the time the credit profile was pulled.
* **BankcardUtilization**:	The percentage of available revolving credit that is utilized at the time the credit profile was pulled.
* **AvailableBankcardCredit**:	The total available credit via bank card at the time the credit profile was pulled.
* **TotalTrades**:	Number of trade lines ever opened at the time the credit profile was pulled.
* **TradesNeverDelinquent**:	Number of trades that have never been delinquent at the time the credit profile was pulled.
* **TradesOpenedLast6Months**:	Number of trades opened in the last 6 months at the time the credit profile was pulled.
* **DebtToIncomeRatio**:	The debt to income ratio of the borrower at the time the credit profile was pulled. This value is Null if the debt to income ratio is not available. This value is capped at 10.01 (any debt to income ratio larger than 1000% will be returned as 1001%).
* **IncomeRange**:	The income range of the borrower at the time the listing was created.
* **IncomeVerifiable**:	The borrower indicated they have the required documentation to support their income.
* **StatedMonthlyIncome**:	The monthly income the borrower stated at the time the listing was created.
* **LoanKey**:	Unique key for each loan. This is the same key that is used in the API.
* **TotalProsperLoans**:	Number of Prosper loans the borrower at the time they created this listing. This value will be null if the borrower had no prior loans.
* **TotalProsperPaymentsBilled**:	Number of on time payments the borrower made on Prosper loans at the time they created this listing. This value will be null if the borrower had no prior loans.
* **OnTimeProsperPayments**:	Number of on time payments the borrower had made on Prosper loans at the time they created this listing. This value will be null if the borrower has no prior loans.
* **ProsperPaymentsLessThanOneMonthLate**:	Number of payments the borrower made on Prosper loans that were less than one month late at the time they created this listing. This value will be null if the borrower had no prior loans.
* **ProsperPaymentsOneMonthPlusLate**:	Number of payments the borrower made on Prosper loans that were greater than one month late at the time they created this listing. This value will be null if the borrower had no prior loans.
* **ProsperPrincipalBorrowed**:	Total principal borrowed on Prosper loans at the time the listing was created. This value will be null if the borrower had no prior loans.
* **ProsperPrincipalOutstanding**:	Principal outstanding on Prosper loans at the time the listing was created. This value will be null if the borrower had no prior loans.
* **ScorexChangeAtTimeOfListing**:	Borrower's credit score change at the time the credit profile was pulled. This will be the change relative to the borrower's last Prosper loan. This value will be null if the borrower had no prior loans.
* **LoanCurrentDaysDelinquent**:	The number of days delinquent.
* **LoanFirstDefaultedCycleNumber**:	The cycle the loan was charged off. If the loan has not charged off the value will be null.
* **LoanMonthsSinceOrigination**:	Number of months since the loan originated.
* **LoanNumber**:	Unique numeric value associated with the loan.
* **LoanOriginalAmount**:	The origination amount of the loan.
* **LoanOriginationDate**:	The date the loan was originated.
* **LoanOriginationQuarter**:	The quarter in which the loan was originated.
* **MemberKey**:	The unique key that is associated with the borrower. This is the same identifier that is used in the API member object.
* **MonthlyLoanPayment**:	The scheduled monthly loan payment.
* **LP_CustomerPayments**:	Pre charge-off cumulative gross payments made by the borrower on the loan. If the loan has charged off, this value will exclude any recoveries.
* **LP_CustomerPrincipalPayments**:	Pre charge-off cumulative principal payments made by the borrower on the loan. If the loan has charged off, this value will exclude any recoveries.
* **LP_InterestandFees**:	Pre charge-off cumulative interest and fees paid by the borrower. If the loan has charged off, this value will exclude any recoveries.
* **LP_ServiceFees**:	Cumulative service fees paid by the investors who have invested in the loan.
* **LP_CollectionFees**:	Cumulative collection fees paid by the investors who have invested in the loan.
* **LP_GrossPrincipalLoss**:	The gross charged off amount of the loan.
* **LP_NetPrincipalLoss**:	The principal that remains uncollected after any recoveries.
* **LP_NonPrincipalRecoverypayments**:	The interest and fee component of any recovery payments. The current payment policy applies payments in the following order: Fees, interest, principal.
* **PercentFunded**:	Percent the listing was funded.
* **Recommendations**:	Number of recommendations the borrower had at the time the listing was created.
* **InvestmentFromFriendsCount**:	Number of friends that made an investment in the loan.
* **InvestmentFromFriendsAmount**:	Dollar amount of investments that were made by friends.
* **Investors**:	The number of investors that funded the loan.



In order to prepare the data for analysis, then some wrangling was done. This involved converting a lot of the data types into other data types based on the type of data they had. For example, columns like employee status and income range were converted into the category datatype for easier analysis. Also, the loan terms were converted from numbers to words and then to the category data type for easier analysis. Then for the Borrower's State, the abbreviations had to be changed to full words for more clarity.

**Files:

_prosperLoanData.csv_: Comma Separated Value file that contains the raw data of loans as downloaded from Kaggle. This file is large (~=86MB) and so it is too large to upload. However, the link to download it is https://s3.amazonaws.com/udacity-hosted-downloads/ud651/prosperLoanData.csv.


_Part_I_exploration_template.ipynb_: Jupyter notebook that contains the Python code for the exploratory data analysis. This would involve wrangling and cleaning the accessed data.

_Part_I_exploration_template.html_: HTML file that contains the created slide deck from the Jupyter notebook for Part I.

_Part_II_slide_deck_template.ipynb_: Jupyter notebook that contains the Python code for the explanatory data analysis to tell a story about the data analysis.

_Part_II_slide_deck_template.slides.html_:  HTML file that contains the created slide deck from the Jupyter notebook for Part II.

_README.md_: This file, providing an overview of the project and instructions for use.

_requirements.txt_: This file provides the list of the Python libraries used for this project.

**Dependencies**

The analysis is conducted using Python programming language and several libraries including:

_Pandas_: For data manipulation and analysis.

_Matplotlib_: For data visualization.

_Seaborn_: For statistical data visualization.

_NumPy_: For numerical computing.

_warnings_: For suppressing warning messages


**Usage**

To run the analysis on your local machine, follow these steps:

Clone this repository to your local machine using the following command:

bash

Copy code
git clone https://github.com/Olatokunbo360/Loans-Data-Analysis.git

Navigate to the project directory:

bash

Copy code
cd Loans-Data-Analysis

Install the required dependencies.
You can use the following command to install dependencies using pip:

Copy code
pip install -r requirements.txt

Once the dependencies are installed, you can open the Jupyter Notebook wrangle_act.ipynb to view the analysis and execute the code cells.

Follow the instructions provided in the notebook to explore the dataset, analyze trends, and visualize insights related to the dataset.

**Contributing**

Contributions to this project are welcome. If you have suggestions for improvements or new analyses, please feel free to open an issue or submit a pull request.


## Summary of Findings

>
 From the questions asked and the analysis and visualizations, it can be deduced that income range plays a key role in the granting of loans to prospective borrowers. The higher your income range, the lesser you pos e a risk to the bank, that is, your Prosper Score is higher. Also, employment status is a key determinant in selecting borrowers. Though, it seems in the dataset, there are a lot of borrowers that fall under the others employment status, it could be more defined subsequently to allow for better analysis. Some of these visualizations would be brought into the presentation.

## Key Insights for Presentation

> The key insights were to show how loan terms, Prosper Score or Income Range could affect a borrower requesting for a loan or even repaying the loan.

By [Yusuf Sanni] - [yusufsanni2003@yahoo.co.uk]
