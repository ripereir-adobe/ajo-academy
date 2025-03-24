[home](README.md)

<p align="center">
<img width="1280" alt="image" src="https://github.com/user-attachments/assets/1bf8639a-755b-4aa3-88e0-5126a064b41b" />
</p>

In this chapter of the lab, we are going to explore single action campaigns. Journey Optimizer campaigns delivers one-time content to a specific audience as opposed to journeys where actions are executed in sequence. The delivery of the campaign can be performed immediately, based on a specified schedule or triggered through an API call. 

As a Luma marketers, we'd like to build a Campaign to promote the new Luma Fall Collection. This campaign will display a banner on the website to invite visitors to look at the Fall Collection Landing Page. To build a campaign, we'd need first to determine the tatget audience, then the web content to display. We'd like to create 2 variants of our content and test out which one works best to then communicate the most effective variant to our audience.


## Create the Audience
First let's target our high value customers who are most likely to buy from this collection: 

- Under _Customer_ menu entry, select _Audiences_, then click the <img width="155" alt="image" src="https://github.com/user-attachments/assets/7c065322-7e52-437b-983b-66207e98b85f" /> button on the top right hand corner.
- Select the _Build Rule_ option, then _Create_
- Name your audience _High Propensity Equipment Buyers_
- Let's define the elligibility criteria of our audience:
  - Under Fields section > _Attributes_, 
    - Look for _propensity_, drag and drop the _propensityScore_ attribute and add condition _is greather_ than  0.7
    - Look for _category_, and click the <img width="34" alt="image" src="https://github.com/user-attachments/assets/73072fda-3b1f-465f-a5ed-b7ad3b6469fa" /> icon to display the value breakdown
      
      <img width="354" alt="image" src="https://github.com/user-attachments/assets/ac92c5b8-7b0f-425f-9a98-24f22d64dd83" />
     -  drag and drop the _category_ attribute and add select the _equipment_ value
   - Look for _Direct_ and select _General Marketing Direct Preferences_, drag and drop the  _Choice Value_ attribute and add condition _equals to_ Y (opt-in)
   - You should have the following conditions in your segmentation builder
     
  <img width="800" alt="image" src="https://github.com/user-attachments/assets/f2561b93-0fda-4464-b393-d06f49f6b14a" />
  - If you click on _Refresh Estimate_, you should see the number of profiles that currently qualify to your audience
  - You can also see sample profiles that qualified by clicking the _Show Profile_ button
  - Publish the Audience by clicking the _Publish_ button
 

Then, let's build a campaign that will display a personalized banner on the website to this specific audience
## Create the Campaign
Adobe Content Cards help Luma effectively showcase the Fall'25 Collection in a way that is personalized, visually appealing, and user-friendly, leading to higher engagement and increased sales. Unlike traditional push notifications, Content cards integrate seamlessly into the user interface, offering persistent, non-intrusive updates that enhance user interaction and experience.

This feature enables marketers to present relevant, rich media content to users, driving higher engagement and ensuring important messages are seen without disrupting the user journey.

<img width="452" alt="image" src="https://github.com/user-attachments/assets/820b7bd0-f57e-4bbe-81c9-99ea0a7c0106" />

### Create a Content Card


### Create an Experimentation


### Simulate the content


### Activate the Campaign


--

Congratulations! You've completed the lab 👍 ✨ 🎉 🚀 🤘 Together, we were able to:
- Improve our customer knowledge by collecting visitor data on our website
- Build a customer profile with behavioral and personal data
- Improve revenue by retargeting abandoners through personalized customer journeys
- Target our high value customers to incent them to visit the new Luma Fall Collection
  
All this in 2 hours 👏 👏 👏 It deserves a gift for all this effort 😛

[Home](README.md)
