# Loan_Default_Prediction
<p><b>Objective:</b>
 Lending Club is the world’s largest online marketplace connecting borrowers and investors. An inevitable outcome of lending is default by borrowers. The idea of this project is to create a predictive model that identifies applicants who are relatively risky for a loan.</p> 
 
<p><b>Understanding Problem Statement and Data</b>:</br>Loan default occurs when a borrower fails to pay back a debt according to the initial arrangement. In the case of most consumer loans, this means that successive payments have been missed over the course of weeks or months. Fortunately, lenders and loan servicers usually allow a grace period before penalizing the borrower after missing one payment. The period between missing a loan payment and having the loan default is known as delinquency. The delinquency period gives the debtor time to avoid default by contacting their loan servicer or making up missed payments. Defaulting on a loan will cause a substantial and lasting drop in the debtor's credit score, as well as extremely high interest rates on any future loan. For loans secured with collateral, defaulting will likely result in the pledged asset being seized by the bank. The most popular types of consumer loans that are backed by collateral are mortgages, auto loans and secured personal loans. For unsecured debts like credit cards and student loans, the consequences of default vary in severity according to the type of loan. In the most extreme cases, debt collection agencies can garnish wages to pay back the outstanding debt. The loan is one of the most important products of the banking. All the banks are trying to figure out effective business strategies to persuade customers to apply their loans. However, there are some customers behave negatively after their application are approved.</p>

<p>Data has the following features:</p>
<li>loan_amnt: The amount the borrower promises to repay, as set forth in the loan contract.The loan amount may exceed the original amount requested by the borrower if he or she elects to include points and other upfront costs in the loan.
<li>Purpose:The purpose of the loan is used by the lender to make decisions on the risk and may even impact the interest rate that is offered. For example, if an applicant is refinancing a mortgage after having taken some cash out, the lender might consider that an increase in risk and increase the interest rate that is offered or add additional conditions. Loan purpose is important to the process of obtaining mortgages or business loans that are connected with specific types of business activities.
<li>Dti: Your debt-to-income ratio is all your monthly debt payments divided by your gross monthly income. This number is one way lenders measure your ability to manage the monthly payments to repay the money you plan to borrow.
<li>Fico_range: A FICO score is a credit score created by the Fair Isaac Corporation (FICO).1﻿ Lenders use borrowers’ FICO scores along with other details on borrowers’ credit reports to assess credit risk and determine whether to extend credit. FICO scores take into account data in five areas to determine creditworthiness: payment history, current level of indebtedness, types of credit used, length of credit history, and new credit accounts.
<li>Delinq_amnt : A loan is considered "delinquent" when a borrower doesn't make a loan payment on time. Most lenders allow consumers a grace period to make up a missed payment and get their loan out of delinquency. However, once a loan is delinquent for a certain period of time, it becomes at risk of going into default.
<li>inq_last_6mths: The fundamental problem with multiple hard inquiries is that they influence lenders to form a negative impression about you credit behaviour. Too many hard inquiries over a short time-period showcase you as a credit-hungry customer with a consequently high risk-quotient.
  
  <p><b>Defining independent variable:</b><p>
<li>Fully Paid->Loan has been fully paid off.
<li>Charged off->Loan for which there is no longer a reasonable expectation of further payments.
<li>Does not meet the credit policy. Status:Fully Paid--> While the loan was paid off, the loan application today would no longer meet the credit policy and wouldn't be approved on to the marketplace.
<li>Does not meet the credit policy. Status:charged off->While the loan was charged off, the loan application today would no longer meet the credit policy and wouldn't be approved on to the marketplace.
<li>Current->Loan is up to date on current payments.,
<li>In Grace period->The loan is past due but still in the grace period of 15 days.
<li>Late(30-120)->Loan hasn't been paid in 31 to 120 days (late on the current payment).
<li>Late(16-30)->Loan hasn't been paid in 16 to 30 days (late on the current payment).
<li>Default->Loan is defaulted on and no payment has been made for more than 121 days.
  
<p><b>Handling Missing Values and Feature Engineering:</b></p>
 Missing values are filled using KNN Imputer.
 <li>Imputation for completing missing values using 
k-Nearest Neighbors.Each sample’s missing values 
are imputed using the mean value from n_neighbors
nearest neighbors found in the training set. Two 
samples are close if the features that 
neither is missing are close.
<li>The KNN Imputer class provides imputation 
for filling in missing values using the k-Nearest 
Neighbors approach. By default, a euclidean distance
 metric that supports missing values,
 nan_euclidean_distances, is used to find the 
nearest neighbors. Each missing feature is imputed 
using values from n_neighbors nearest neighbors t
hat have a value for the feature. The feature 
of the neighbors are averaged uniformly or weighted
 by distance to each neighbor.  
<li>Imbalance in target vraiable is handled using SMOTE technique.

<p>Following features are engineered.<p>
<li>total_pymnt:- Payments received to date for total amount funded.
<li>total_pymnt_inv:-Payments received on date for portion of total amount funded by investors.
<li>total_rec_prncp:-Principal received to date.
<li>total_rec_int:-Interest received to date.
<li>total_rec_late_fee:-Late fees received to date.
<li>recoveries:-post charge off gross recovery.
<li>collection_recovery_fee:-post charge off collection fee.
<li>last_pymnt_d:-Last month payment was received.
<li>last_pymnt_amnt:-Last total payment amount received.
<li>funded_amnt:-The total amount committed to that loan at that point in time.
<li>funded_amnt_inv:-The total amount committed by investors for that loan at that time.
</p>
 
  
  <p><b>Building Classifier Model:</b>
    Built different classifier models such as

<li>Logistic Regression
<li>DecisionTree
<li>Random Forest
<li>Gradient Boosting
<li>XG Boost
<li>SVC
 
 Logistic Regression is not giving great results,Decision Trees are had bit better than Logistic Regression,but having lesser recall value on test data.GB Classifier & XBG Classifier  have performed equally good in terms of recall  Score and Test accuracy. XGB Classifier gives the best model giving 84% recall.
  </p>
  
  <p><b>Conclusion</b>:
 <li>The last_fico_range, grade, inq_last_6month features were found to be the most relevant for predicting loan default in. The current model tries to predict default biased data from credit analysts grade and assigned interest rate. . The XGB and Rf models provide substantial improvements on traditional credit screening. A recall score significantly and robustly above 90%, with AUC-ROC scores ≃74%. The features provided to the model in our study generalize to any lending activity and institution, beyond P2P lending. The present work could, therefore, be augmented in order to predict loan default risk without the need for human credit screening.
<li>Only the Random Forest., XGBoost, model is used, but there are many good ones out there even neural networks. The models can also be improved further by finer tunings on hyperparameter.
<li>In the bank loan behaviour prediction, for example, banks want to control the loss to a acceptable level, so they may use a relatively low threshold. This means more customers will be grouped as “potential bad customers” and their profiles will be checked carefully later by the credit risk management team. In this way, banks can detect the default behaviours in the earlier stage and conduct the corresponding actions to reduce the possible loss.
  </p>
  
 


