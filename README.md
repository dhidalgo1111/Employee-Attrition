# Employee-Attrition


A video was created to present the dashboard. Feel free to watch at https://youtu.be/swqraaFX_wA

Problem
A pharmaceutical company is concerned about retaining good employees.

The cost to replace an employee can range from 1/3 to 2 times the employee’s annual wages or more. These costs include recruiter fees, time spent interviewing candidates, background checks, and preparing training materials.

The company wants to predict whether a current employee is likely to resign in the near future and why. With this knowledge management can collaborate with the employee to forestall the resignation.

Solution
My associate and I developed a machine learning model that predicts whether an employee is likely to resign. In addition to generating a prediction, the model can rank the importance of the input variables in making a prediction.

The deliverable is a Tableau dashboard that a manager can use to understand which employees are likely to resign, and why.


Process
Our hypothetical client provided us with extensive data about its past employees. The data provided includes data about the employee, data about the employee’s relationship with the company, and whether the employee resigned.

The data provided is listed below.

employee personal information

age
gender
education level
education field
marital status
total working years
Did the employee resign?

yes / no
employee’s relationship with the company

compensation:
monthly pay
percent of last raise
stock options level
distance from home
business travel yes / no
satisfaction, from a survey
job satisfaction
relationship satisfaction
work / life balance
history with company
years at company
years since last promotion
years with current manager
We chose recall as the primary metric by which we would compare model performance. In plain language, this means that we endeavored to minimize false negatives at the expense of generating more false positives. In the context of this project, we would prefer to err on the side of misidentifying some non-resigners as possible resigners and to avoid overlooking a potential resigner by misidentifying him / her as a non-resigner.

Ideally we would have strong recall and F1 scores, but we are satisfied with these scores considering the vagaries of human decision making.

We tested 25 hyperparameter tuned and non-tuned models. We excluded 441 records from the machine learning training process as test data.


![image](https://github.com/dhidalgo1111/Employee-Attrition/assets/126840488/24bd032c-4d43-4ecd-a3cc-385bd6b9f786)

The most suitable model, by a wide margin, was the stacking classifier. The stacking classifier combined hyperparameter tuned random forest, gradient boosting, decision tree, and xgBoost models.

The confusion matrix below reports the models performance on test data.


![image](https://github.com/dhidalgo1111/Employee-Attrition/assets/126840488/c809faf2-645d-474b-b117-da05167632b5)

Our model correctly identified the intentions of 296+51 = 347 employees. We view the 74 false positives as being acceptable: it doesn’t hurt to reach out to these employees even though they are not planning to resign. The most problematic quadrant is the 20 false negatives. These employees were flagged as non-resigners, but in actuality this group left the company.

The machine learning model ranked the input variables for relative importance. We chose to focus on the 10 most important variables.

![image](https://github.com/dhidalgo1111/Employee-Attrition/assets/126840488/c7734667-9955-4369-80ea-cd048d1ced6c)

Our deliverable is a Tableau dashboard that managers can use to identify which employees are likely to resign, and why. Click on each image below for a large view.



![image](https://github.com/dhidalgo1111/Employee-Attrition/assets/126840488/cf2c4507-7e71-4444-8f8b-24a65d47df13)

Our model predicts that this employee is likely to resign.

This person appears to be an early-career employee: she’s relatively young, has a lower income, has been with the company only one year, has been working for only one year and has had only one previous employer.

Her job and environment satisfaction are good as well, plus, she’s been granted stock option level 1.

But her relatively long commute of 22 miles may be a source of discontent.







