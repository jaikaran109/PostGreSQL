1. Dataset Overview
1.1 customers
Contains demographic and KYC-related information of bank customers.
This table is mainly used for grouping customers by city/state, filtering by KYC status, and joining with accounts and loans.

Key columns: customer_id, full_name, city, state, kyc_status, created_date


1.2 accounts
Stores account-level information such as account type, branch, balance, and status. 
Useful for partitioning, aggregations, and ranking customers by balances.

Key columns: account_id, customer_id, branch_id, account_type, current_balance, account_status


1.3 transactions
Transaction-level data used for time-based analysis, running totals, previous/next transaction comparison, and advanced window functions.

Key columns: transaction_id, account_id, transaction_date, transaction_type, amount, running_balance


1.4 loans
Contains loan-related information such as loan amount, interest rate, loan type, and status. 
Useful for ranking, cumulative distribution, and credit analysis.

Key columns: loan_id, customer_id, loan_type, loan_amount, interest_rate, loan_status


2. Common Table Expressions (CTEs)
Concept-
A Common Table Expression (CTE) is a temporary result set defined using the WITH clause. It improves query readability and allows complex logic to be broken into simple steps. CTEs are especially useful for intermediate aggregations and reusable subqueries.
Syntax:
WITH cte_name AS (
    SELECT ...
)
SELECT * FROM cte_name;


3. Window Functions
Concept-
Window functions perform calculations across a set of rows related to the current row without collapsing the result set. They are commonly used for ranking, running totals, comparisons, and analytical queries.
Syntax:
function_name() OVER (PARTITION BY column ORDER BY column)
