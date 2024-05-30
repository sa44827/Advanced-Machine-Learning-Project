# Advanced-Machine-Learning-Project

Project by Nishant Kushwaha, Spandan Pal, David Gong, Sharan Arora and Mansi Sharma​​

## Introduction
The focal point of our project is the meticulous identification of hotels where victims of human trafficking are photographed, an intricate task compounded by the challenge posed by subpar image quality and atypical camera angles. Our team is dedicated to employing advanced image analysis methodologies to discern recurrent patterns within images of hotel rooms. This analytical pursuit is designed to offer invaluable assistance to investigators grappling with human trafficking cases.

To achieve this goal, we utilize a multifaceted approach integrating a variety of tools and techniques. Our data foundation is drawn from Kaggle, specifically sourced from TraffickCam, providing a substantial repository for our analysis. In the technical implementation, Python plays a pivotal role, facilitating image resizing and masking procedures essential for enhancing image clarity and isolating relevant features. Furthermore, our methodology employs sophisticated classification algorithms, notably stacked Convolutional Neural Networks (CNNs), known for their efficacy in pattern recognition tasks, to decipher and categorize image content accurately.

By amalgamating these tools and methodologies, we aim to create a comprehensive framework that enhances the capacity of law enforcement and anti-trafficking entities to identify potential locations associated with human trafficking activities, thereby contributing significantly to the fight against this heinous crime.

## Background
Identifying the hotels depicted in photographs plays a pivotal role in human trafficking investigations, as it enables the tracking and intervention necessary to combat these illicit activities effectively. However, a significant challenge arises from the submission of numerous images to law enforcement agencies, many of which suffer from poor quality and unfavorable angles. This limitation severely hampers investigators’ ability to pinpoint the hotels associated with trafficking, thereby endangering more lives.

Our project introduces a groundbreaking approach by leveraging image processing and machine learning methodologies in a crucial realm of law enforcement. By addressing this challenge, we aim to significantly enhance the prospects for advancements in human trafficking investigations.

## Data Description
Containing 100,000 images sourced from more than 3,100 hotels situated in prominent metropolitan regions across the United States, this dataset presents a wide-ranging and diverse collection of visual data. Acquired via a mobile application crafted by the Exchange Initiative in 2015, this dataset underscores the significance of community involvement in combating human trafficking.

Accessing this expansive dataset was made possible through Kaggle, where it was made available for a competition. The dataset, originating from the TraffickCam mobile app, exemplifies a crowdsourced initiative. It serves as an input to a phone application designed to aid law enforcement in locating victims and prosecuting individuals involved in trafficking activities.

## Our Approach

## Image Processing 

Image Resizing & Masking : The team undertook the standardization of image resolution to 256x256 pixels, a strategic move aimed at overcoming the obstacle posed by disparate image sizes. This standardization holds pivotal importance in ensuring uniformity during image processing and the subsequent training phases of the machine learning model. To augment the dataset, an additional approach involved the generation of supplementary data through image masking. This involved the application of a “mask” to images extracted from the dataset, selectively covering specific areas of the image to create variations and expand the dataset.

![Image](https://github.com/sa44827/Advanced-Machine-Learning-Project/blob/b881a430ab719bb3ff053fbf4195014e6cd44a66/images/image1.webp)

Filling the Masks : Upon creating the masks, there arose a necessity to address the void left within the masked portions of the images due to information loss. It’s crucial to highlight that simply using content generated from stable diffusion to fill these masks would not serve our purpose, as our focus lies in capturing the unique features specific to each hotel for classification. Hence, utilizing the remaining parts of the image became imperative to fill the masks adequately.
Subsequently, we implemented horizontal and vertical flips on the images, resulting in the generation of numerous filled images. Our dataset comprised 3,116 hotels, each with approximately 20 classes, and an additional 4,950 mask images available for masking. When multiplied together, this equated to a staggering potential of approximately 308.5 million new images that could be utilized for our training algorithm. However, the generation time for a single image amounted to approximately 8 seconds, rendering the creation of all 308.5 million images an unfeasible endeavor within a reasonable timeframe.

