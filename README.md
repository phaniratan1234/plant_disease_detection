# Plant Disease Detection
--------------------------
An application that Predicts the disease of a plant by Taking a snap of the leaf of the plant as every leaf has it's own properties, The application predicts the plant and it's disease and whether it is spoiled or not and if spoled how much percentage it is being spoilt and an advice on how to overcome such problems using the right set of fertilizers and manures in the right composition

Data
------
We are using the PlantDoc dataset here which in total consists of 38 categories of plants , in out future scope we can append various varities of plant images tagged along with their disease names if present else healthy

Block 1
---------
In the first block we are going to develop a model of our own wihtout going for transfer learning, on my observation while using transfer learning we are more likely to overfit, we have tried on VGG16 , VGG19, Dense and Google Net but it tends to overfit so how about we design our own architecture
* we have taken zero padding in order to preserve the information
* we have taken repeated convolutions to important features
* to reduce overfit we have constantly added batch normalization and dropout 
* At the Dense layers we have used a random set of decaresing numbers approximated

* once we get the predicted disease name the name itself contains information whether it is diseased or not so that way the condition parameter gets defined

Block 2
--------
Afer we Identified the disease, we need to predict the percent it has been spoilt, for this we tried a lot of approaches but our centric idea was to choose the region of interest and then considers the non green shades of pixels count and find the green pixel count including all green shades and then find the ratio but inorder to extract the ROI we have used mask RCNN, a pre-defined pixellib implementation is used and is trained on a custom dataset manually annotated by using Label me and finally we got it to work the model used the data to mask the leaf and after extracting the segmented object we have taken HSV range for green pixels to extract only the green pixels leaving the deseased portions aside, Finally the ratio is produced converted to a percentage

* We have manually given the Advice for the crops but that can be customized by the target users

The future scope of this project is to append a lot of new data of varities of plants and train on the model and build or extend a new one and make better facilities for the application and construct a working usable app on the stores available

what you see depends on how you view the world, To most people it's just dirt but to a farmer it's Potential
-----------------------------------------------------------------------------------------------------------
