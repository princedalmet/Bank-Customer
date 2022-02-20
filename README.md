# Bank-Customer
Predict customer exit or not using ANN model

![1](https://user-images.githubusercontent.com/99526815/154836855-6e89bb77-6c85-4e6e-a2d7-29bad0f906de.jpg)


Predict customer exit or not using the below unknow data --

Use our ANN model to predict if the customer with the following informations will leave the bank:

Geography : France

Credit Score : 600

Gender : Male

Age : 40 years old

Tenure : 3 years

Balance : $ 60000

Number of products : 2

Does this customer having credit card? Yes

Is this customer an active member? Yes

Estimated Salary : $ 50000

So, should we say good bye to customer



![2](https://user-images.githubusercontent.com/99526815/154836964-0d6040c8-aac0-436b-91c7-563e263d1fe8.PNG)


Cleaning data 


# Feature selection
from sklearn.preprocessing import StandardScaler
sc = StandardScaler()
X_train = sc.fit_transform(X_train)
X_test = sc.fit_transform(X_test)


Building the ANN

**Initializing the ANN

**Adding the input layer and first hidden layer

**Adding the second hidden layer


# Adding first input layer and the first hidden layer
ann.add(tensorflow.keras.layers.Dense(units = 6, activation = 'relu'))


# Adding second hidden layer
ann.add(tensorflow.keras.layers.Dense(units = 6, activation = 'relu'))



# Adding the output layer
ann.add(tensorflow.keras.layers.Dense(units = 1, activation = 'sigmoid'))



# Training the ANN
ann.compile(optimizer='adam', loss='binary_crossentropy', metrics=['accuracy'])



Unknown_data = [600, 'France', 'Male', 40, 3, 60000, 2, 1, 1, 50000 ]


Unknown_data = ct.transform([Unknown_data])


ann.predict(sc.transform(Unknown_data)) > 0.5


array([[False]])


There is less chance of this customer will move out from bank.
