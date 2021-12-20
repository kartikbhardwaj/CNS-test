# CNS-test

## The Approach, steps, and problems faced for classification Task:

1. The initial step was to load the data. But the given data was very large and thus I chose to work with google colab cloud with data being saved on google drive. Using this approach I was able to build a pipeline that loaded the data from google drive using the Custom batched data loader. This approach was taking a lot of time as the data loader was making calls to drive every time it needed the batch of data. At the same time, the data was not saved so That increased the I/O time. As a result, I implemented a data loader that took all the data at once and stored it in a script variable. This helped in completing the initial step but after a limited time I ran out of the google colab GPU limit usage and GDrive calls usage. Therefore In the end I had to load the data onto the local system and then proceed further. <br>

2. After that, It was time to Do some EDA and Visualization. We find that data was completely balanced but the size of a single image was very large. Therefore I changed it to the format that is accepted by the VGG 16. At the same time, I implemented data Augmentation to counter overfitting. <br>

3. As part of modeling the custom model, I was able to achieve moderate accuracy but the loss function was still decreasing after all the epochs were done. Having been limited by computational power I decided to tune the hyperparameters and not increase the model complexity or train more on the same model. <br>

4. The next part was to make a VGG16 model. This was finally simple to code. But here the computational power required was very large. Therefore I decided to freeze some layers of the VGG 16 model to gain speed up. This lead to the drop inaccuracy to the point where VGG was not giving as good results as were given by the custom model. The VGG model (even though with the frozen layers) was taking a lot of time to run thus I save the best model up till 3rd epoch run and evaluated the results on that. <br>
5. The next step was to get the TSNE 2D formulation of the images. This was implemented without any problems faced. <br>

6. At last, the Confusion matrix is displayed which indicates the modest results. This can be improved given more computational power. 
