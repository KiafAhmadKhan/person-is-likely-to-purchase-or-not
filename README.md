###'''you have been tasked to creating a decision tree modelto predict wether a person is likely to purchase,
### A new smartphone based on there Age,Income and Education level.
### you are provide a data set containing these attribute amd the target variable indicating weather a person made a purchase or not.'''
import numpy as np
from sklearn.tree import DecisionTreeClassifier
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score
x= np.array([[25,50000,3],[45,90000,4],[30,65000,5],[20,30000,2],[55,120000,5],[20,28000,1],[50,36000,2],[45,56000,4],[36,43000,2]])
y=np.array([1,0,1,0,1,0,1,0,1])
x_train,x_test,y_train,y_test= train_test_split(x,y,test_size=0.2,random_state=42)
model= DecisionTreeClassifier()
model.fit(x_train,y_train)
y_pred=model.predict(x_test)
accuracy= accuracy_score(y_test,y_pred)
print(accuracy)
age= float(input('enter your age: '))a
income= float(input('enter your encome: '))
education= float(input('enter your education age(1,2,3,4,5): '))
user_input = np.array([[age,income,education]])
prediction= model.predict(user_input)
if prediction[0]==1:
    print('user is likely to buy a smart phone')
else:
    print('''user didn't want to buy a smartphone''')
