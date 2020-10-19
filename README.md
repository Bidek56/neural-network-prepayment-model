# neural-network-prepayment-model

Here we build a neural-network based prepayment model to predict the likelihood of prepayments on pools of residential mortgage loans.

Mortgage pools are tradable fixed income securities composed of collections of residential mortgage loans. Here we only consider the so calls "agency" mortgage pools, i.e. those whose credit risk is guaranteed by the GSEs (Government Sponsored Enterprises) such as Fannie Mae, Freddie Mac, and Ginnie Mae. In the end it's fair to say that the credit risk inherent in these securities is guaranteed by the US Government. 

Here we only work with mortgage pools guaranteed specifically by Fannie Mae, but it's a very similar dataset to that of Freddie Mac. Ginnie Mae loans are somewhat different and adhare to a different set of rules and regulations, so they would require a model built just for them. We're not considering them here. 

What is a mortgage prepayment? It comes in several forms. The most basic form is when a loan is fully repaid by the borrower before the loan's scheduled maturity. This can happen either due to borrower rifancing his/her mortgage loan into a lower mortgage rate, refinancing due to a mortgage cash-out (partially cashing out the equity that a borrower has in a home), or a home sale. Another form of prepayment is when a borrower defaults on his/her mortgage. In this case the guaranting entity (Fannie Mae) repays the mortgage investor in full for the remaining balance of the loan. And last, but not least, there are partial loan prepayments, which we typically call curtailments. A curtailment occurs is when a borrower pays down more principal than shceduled. Most mortgage borrowers in the US pay down a little more on their mortgages than they have to in hopes of paying off a mortgage early. In all these cases the security containing the loan sees more principal being repaid in a given month than what was scheduled. It shouldn't be a suprise that we measure mortgage prepayments in % of remaining balance after the scheduled principal is paid. Let's look at an example. Suppose a borrower owes 105k on his/her mortgage and is scheduled to repay 5k of the mortgage this month. Instead of making a regular mortgage payment, a borrower pays down 2k more. As a result of that the remaining principal balance of the loan is 98k instead of 100k. So we can that prepayments that month were at 2% SMM (SMM=single month mortality). The model that we are going to build here takes in the attribues of a mortgage pool and outputs an SMM prepayment prediction for next month. 

Besides SMM, another common measure of mortgage prepayments is annualized SMM which is called CPR (Constant Prepayment Rate). SMM and CPR are connected by the following simple formula. CPR is also measured in % of outstanding principal. 

                            CPR = 1-(1-SMM)**12
                            
Mortgage pools have many relevant attributes such as average morgage rate that borrowers in a pool pay, average FICO score of borrowers, LTV (loan to value ratio), and many more. 
