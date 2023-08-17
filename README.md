# **Important**
Files uploaded in the repository were dataset used and model building code. The final results such as model built and xlsx files were not included due to the size of the models.

It is highly recommended to split each models into individual folders, unless you plan to use only one type of model. The duration of running the code varies on the power of device used. To avoid error due to overload, it is recommended to **not build models all at once** (for example, build only the first until tenth model, then the eleventh until twentieth model).

# **Screenshots**

# **A. Introduction**
As time went by, vending machines that initially only accepted coins can now accept paper money. On the other hand, despite being able to accept paper money, vending machines in Indonesia do not accept money in poor conditions such as being dirty and torn. In fact, these kinds of paper money should still be valid for trade. This suggests the need for a model that can recognize banknotes in these conditions.

# **B. Objective**
This study aimed to produce a model that can recognize the rupiah paper currency using the Convolutional Neural Network (CNN) method with the VGG-16 and VGG-19 models and analyze the comparison of model results with image processing and without image processing.

# **C. Dataset**
The dataset collected is 2016 and 2022 emission years rupiah paper money with denominations of Rp1000,00, Rp2000,00, Rp5000,00, Rp10.000,00, Rp20.000,00, Rp50.000,00, and Rp100.000,00, of which each emission year amounts to 175 pieces. The images used are the front and back of the banknotes so that the number of images in the 2016 and 2022 emission years is 350 images each. Because the images of the 2016 and 2022 emission years are combined, the dataset is **700 images** in total.

For each denomination, there are images of **normal, scuffed, dirty, torn, and blurred banknotes**. The dirty and torn images are normal banknote images that were edited using an application. The data is collected using a scanner.

# **D. Method**
## Image Processing
Before classification, image processing is applied first. The research is divided into two parts; the first, after the initial stage of the research, the classification stage is carried out while the second is after the initial stage of the research, the image processing stage is carried out first. Both researches with image processing and research without image processing perform grayscaling to speed up computation. Image processing consists of grayscaling, image enhancement, and image segmentation.

The method used is histogram equalization. To determine the type of histogram equalization used, a Peak Signal-to-Noise Ratio (PSNR) calculation is performed where the histogram equalization method with the highest PSNR value will be used. After image enhancement, image segmentation using Otsu is applied to help obtain and highlight important parts of the image.

## Classification
The classification stage is carried out to classify the image of rupiah banknotes. The dataset is first divided into training data, testing data, and validation data with a ratio of 70:10:20. Classification is performed using the VGG-16 and VGG-19 models. Model building is done 192 times for each method, resulting in 768 model building times in total.

The model is built using the pretrained structure of VGG-16 and VGG-19. Three layers are added to the model architecture, namely two batch normalization layers and one dropout layer. The batch normalization layer is applied after the dense layer and flatten while the dropout layer is applied after the second batch normalization layer. In total, VGG-16 has 26 layers (23 pretrained models plus three additional layers) while VGG-19 has 29 layers (26 pretrained models plus three additional layers).

## Evaluation
The evaluation stage is carried out to assess the model created Evaluation is done with confusion matrix followed by calculation of precision, recall, f-measure, and accuracy values

# **E. Result**
The model produced can recognize rupiah paper currency well. VGG-16 with image processing gives the best average accuracy of 57.28%. VGG-19 with image processing followed with an average accuracy of 55.55%, followed by VGG-16 without image processing at 53.90%, and VGG-19 without image processing at 45.23%. The highest accuracy obtained was 91.43%.

# **F. Conclusion**
This study showed that VGG-16 with image processing gave the best results with the highest accuracy of 91.43%. In addition, the study proved that image processing can improve the accuracy of the model, as shown in the average accuracy of the image processing study which is higher than the study without image processing. The average accuracy obtained by VGG-16 and VGG-19 in research without image processing is 53.90% and 45.23% while the average accuracy obtained in research with image processing is 57.28% and 55.55%.