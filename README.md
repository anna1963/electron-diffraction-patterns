# electron-diffraction-patterns
Development of AI Methods for Finding Hidden Dimensions (Summer 2021)
We first load material details of bismuth, which is a cif file, to the CrystalMaker software. Then CrystalMaker will simulate its diffraction pattern. CrystalMaker also allow us to edit the structure easily, the parameter we choose to edit is called Uiso. As the value of Uiso changes, the structures of the bismuth changes. Then we export the profiles for the simulated diffraction patterns to a text file. The picture on left hand side is part of a text file. Each file has two columns: intensity and angle.. A python code was written to convert the profile to a ring-like diffraction pattern. 

<img width="765" alt="Screen Shot 2023-07-27 at 3 40 04 PM" src="https://github.com/anna1963/electron-diffraction-patterns/assets/68674174/2869af08-7015-431a-9c7b-5c48560f90fa">

We choose the range of Uiso to be 0-1, and step size 0.01. So we now have 11 classes, and each class only have 1 sample. Here is a graph showing the 11 classes. The input is synthetics images, and the labels are values of Uiso. We increase the number of samples by 1.add random noises. 2.create off-centered images. 3. Changing preferred orientations. ImageDataGenerator from tensorflow.keras is also a useful tool to increases the samples volume. We finally got more than 10 thousand synthetics diffraction patterns. 80 percent of them are put in training set and 20 percent are put to test set. 

<img width="735" alt="Screen Shot 2023-07-27 at 3 39 40 PM" src="https://github.com/anna1963/electron-diffraction-patterns/assets/68674174/7f091c4d-5949-4944-8b3b-9da6058fcc4f">

Here is a graph of the prediction of real diffraction patterns, the x-axis is the time when the real diffraction patterns were taken, the pump excite the molecules at time zero. You can see that there is an increase of the values of Uiso before and after time zero, which is exactly what we want. There are some other things we can do to in future. For example, we can use smaller step size to build the training and test sets, and that will give us a more continues prediction. We can also build a CNN to predict the Biso of the real diffraction patterns, and then use our predictions to find the relation between Biso and Uiso. 

<img width="726" alt="Screen Shot 2023-07-27 at 3 39 46 PM" src="https://github.com/anna1963/electron-diffraction-patterns/assets/68674174/40df859d-0d9f-403f-baef-63cedd96e25c">
