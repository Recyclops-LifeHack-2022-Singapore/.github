## Recyclops Organisation ReadMe

# Recyclops
**Chosen Theme:** Environment  
**Problem Statement:** What can we do to encourage more people to recycle, or make recycling more convenient and accessible?

## Problem

At this point of time, almost all of us know what recycling is and the importance of recycling. There is a recycle bin below every single block in Singapore and recycling has never been easier. But why do we still see recycling rates going down? [Contamination of recyclables and incorrect recycling](https://www.channelnewsasia.com/singapore/contamination-recyclables-incorrect-recycling-among-possible-factors-singapores-low-domestic-recycling-rate-experts-764641) are possible factors and we have to learn how to do it properly.


## Solution
Recyclops is a mobile web app that aims to simplify recycling for Singaporeans. Empowered by machine learning, the user can scan any household object. Recyclops will inform them if it is safe to recycle, how to recycle it and whether any special instructions are needed. It also serves as an information dashboard of articles so users can access them easily to learn more. 

We envision Recyclops to be driven by the community, pictures taken can be used further to improve the quality of the machine learning algorithm. Community efforts can also update government advisories on recyclable and non-recyclable items. This will ensure Recyclops stay relevant throughout the test of time.

## How does it answer the problem statement?
We believe Recyclops will remove users' doubt and uncertainty on whether an object is recyclable with direct information from the government. Furthermore, the instant image classification helps save the user’s time.

Recyclops is a progressive web app (PWA), allowing users to easily install the app on their mobile device's home screen and receive updates seamlessly. This removes the need for users to remember website links or constantly update the app through their device’s app store.

The recyclable data and machine learning algorithm are consistently updated and improved to ensure our application stays relevant so users will not have to look elsewhere for updated information.


## How we built our hack
### Backend
`Pytorch` is used to train & test models while `Flask` is used to serve the model for our frontend to send image inference requests.

Our dataset is gathered from multiple data sources (listed below). We first filtered specific classes on each dataset that we believe are relevant, which was followed by a data cleaning step to remove images that are wrongly labeled. This has left us with 5,989 training and 1,480 test images.

Finally, we re-trained the last few layers of pre-trained models on our custom dataset. We experimented with hyperparameter tuning during training to optimise our models. After testing the trained models, we deployed our best trained model.

### Frontend
Our frontend was designed to help users easily identify which items are recyclable and which are non-recyclable and provide them with clear instructions on how to recycle them properly.

We started planning out the functionalities of our app and we came up with the initial Figma design with several considerations in mind. Firstly, we wanted the app to be user–friendly and suitable for people of all ages, especially for the elderly who have a hard time searching for information online. We made sure that all of our functionalities were clear and straightforward and you should be able to find what you came for within 3 to 4 clicks.

Next, we had to take into account the time constraint because it is hard to find proper datasets for all common household items and train our model within 24 hours. Also, we realized that our model might not always be able to identify the object given and we decided to include a list view for users to search for their items manually which will definitely be reliable.

We have a history page for users to keep track of their recently recycled items for easier access to items that they frequently recycle. One of our other goals is also to educate our users more about good recycling practices and environment-friendly habits/activities and therefore our homepage also includes interesting information about recycling and links to read more about it.

## Difficulties
As a team, we are relatively new to pytorch and especially serving a model on the backend. It took a while to understand the pytorch library and refactor the template code to start training our models. Without proper training pipelines, training many models manually and simultaneously required care to ensure we did not confuse between the trained models. We started off training on smaller number of classes before scaling up

Next, we had to take into account the time constraint because it is hard to find proper datasets for all common household items and train our model within 24 hours. Also, we realized that our model might not always be able to identify the object given and we decided to include a list view for users to search for their items manually which will definitely be reliable. We strived to follow exactly what we designed but we faced many obstacles due to unfamiliarity with designing components and had to spend time to solve it or find workarounds. 

## Biggest Learning Point

The willingness to dive into something new. Despite this being a hackathon, learning a new library, using new frameworks is always worth the experience as that is when we gain the most from this hackathon. 


## Dataset Sources
We looked for open source datasets that are relevant for our machine learning task. For certain categories such as aluminum cans, online data sources did not fit our requirement and hence we had to manually source for more aluminum cans on google images and other sites.


[Kaggle Garbage Collection](https://www.kaggle.com/datasets/asdasdasasdas/garbage-classification)<br>
[Waste Image from Sushi Restaurant](https://www.kaggle.com/datasets/arthurcen/waste-images-from-sushi-restaurant) <br>
[Kaggle Waste Images](https://www.kaggle.com/datasets/wangziang/waste-pictures) <br>
[Thrash Box](https://github.com/nikhilvenkatkumsetty/TrashBox)
