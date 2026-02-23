[home](README.md)

<p align="center">
<img width="800" src="https://github.com/user-attachments/assets/9c94e953-ab53-4ff6-b4f2-c6e5ea244489" />
</p>

In this chapter of the lab, we are going to explore Campaign Orchestration new capability within AJO designed to build, schedule, and deliver one‑to‑many marketing campaigns—primarily email, SMS, and push—using a marketer‑friendly, visual interface. It complements AJO’s event‑driven journeys by supporting traditional outbound campaigns that run on a defined schedule and target audience segments.

As Luma marketers, we'd like to build a Campaign to promote the Luma's sport's wear clothing. This campaign will send special promotions email to all profiles that made orders above 500 euros. To build this orchestrated campaign, we'd need first to build the target audience, then the email content to be delivered. We'd like to create personalize the email text, the banner image, and promotion using conditional content and AI content generation of image variations.

# Create Campaign

First go to the new available tab "Orchestration" in the "Campaigns" AJO menu options and click on "Create Campaign" <img width="100" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Create Campaign Button.png" />. Let's start creating the visual campaign orchestration through a workflow: 

- Select Orchestration - Marketing, and name your campaign, please prefix it with the email address you used when creating your account on Luma website
  
  <img width="300" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Campaign creation options.png" />
  
- In the workflow, after the start activity add the 1st activity "Build Audience" click on the "+" sign <img width="60" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/+Sign image.png" /> and select "Build Audience"
  <img width="155" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Build Audience start.png" />

- then select the relational schema "Luma_Orders_record" as your targeting dimension
  <img width="155" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Select Targeting Dimension.png" />

- Now that the targeting dimension is selected, let's click on "Create Audience" <img width="90" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Create Audience Button.png" />
- Let's define the elligibility criteria of our audience by adding conditions:
  - Select the attribute "Order_Amount", it should be equal or higher than 500 euros
 <img width="155" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Condition 500.png" />
  - Select the attribute "Order_date" and select all order dates in the last year
 <img width="155" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Condition Date.png" /> 

- You should have the below Audience eligibility criteria definition:
 <img width="155" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Final Audience Target NB.png" />





  
  - Under Fields section > _Attributes_, 
    - Look for _propensity_, drag and drop the _propensityScore_ attribute and add condition _is greater_ than  0.7
    - Look for _category_, and click the <img width="34" alt="image" src="https://github.com/user-attachments/assets/73072fda-3b1f-465f-a5ed-b7ad3b6469fa" /> icon to display the value breakdown
      
      <img width="354" alt="image" src="https://github.com/user-attachments/assets/ac92c5b8-7b0f-425f-9a98-24f22d64dd83" />
     -  drag and drop the _category_ attribute and add select the _equipment_ value
   - Look for _Direct_ and select _General Marketing Direct Preferences_, drag and drop the  _Choice Value_ attribute and add condition _equals to_ Y (opt-in)
   - You should have the following conditions in your segmentation builder
     
  <img width="800" alt="image" src="https://github.com/user-attachments/assets/f2561b93-0fda-4464-b393-d06f49f6b14a" />
  
  - If you click on _Refresh Estimate_, you should see the number of profiles that currently qualify to your audience.
  - You can also see sample profiles that qualified by clicking the _View Profile_ button.
  - Publish the Audience by clicking the _Publish_ button.
 


# Create the Campaign
Let's build a campaign that will display a personalized banner on the website to this specific audience
- Under _Journey Management_, click _Campaigns_ menu entry, select click ![image](https://github.com/user-attachments/assets/0c0cccdc-c45f-432e-8b3a-18005da2fc8e)  button on the top right hand corner.
- Campaign can be triggered immediately, scheduled or through an API call, select _Scheduled_ and click _Create_

<img width="452" alt="image" src="https://github.com/user-attachments/assets/820b7bd0-f57e-4bbe-81c9-99ea0a7c0106" />

- Name your campaign _Fall Collection_, please prefix it with the email address you used when creating your account on Luma website, like: `delaland+p1@adobetest.com - Fall Collection`

- Under Audiences, select your _High Propensity Equipment Buyers_ audience, keep _ECID_ as identity type

- Under _Schedule_ > _Campaign Start_, keep the option _When activated manually_
- Under _Schedule_ > _Campaign End_, select _On a specific data and time_ and stop the campaign at the end of next month midnight.




## Create a Content Card
Adobe Content Cards help Luma effectively showcase the Fall'25 Collection in a way that is personalized, visually appealing, and user-friendly, leading to higher engagement and increased sales. Unlike traditional push notifications, Content cards integrate seamlessly into the user interface, offering persistent, non-intrusive updates that enhance user interaction and experience.
This feature enables marketers to present relevant, rich media content to users, driving higher engagement and ensuring important messages are seen without disrupting the user journey.

- Under _Actions_ section, click <img width="126" alt="image" src="https://github.com/user-attachments/assets/52bef494-de1d-4666-bbab-f04172cf57a7" /> button, then select _Content Card_.
- Label the action name _Luma Fall Collection_.
- Under Content Card configuration, select the predefined setting called _ContentCards_.
- Content card are also available for mobile where you can define additional triggering rules. As we configure it for web now, let's disable the _additional delivery rules_
- Let's author the card by clicking the ![image](https://github.com/user-attachments/assets/486ba657-48bc-4be7-8957-5e043c986987) button


## Create an Experimentation
Experiments allow you to optimize content for the action in your Campaigns. They are a set of randomized trials, which in the context of online testing, means that some randomly selected users are exposed to a given variation of a message and another randomly selected set of users to another treatment. After sending the message, you can then measure the outcome metrics like opens of emails or clicks on banner.

- Click ![image](https://github.com/user-attachments/assets/475e2ef5-963c-4c48-af94-1a11dd846115) button.
- Use Unique Clicks as success metrics.
- Use a 10% Holdout group
- Create a second treatment, A and B distributed evently
- Click _Create_ button

![image](https://github.com/user-attachments/assets/47879ee2-6183-4281-9e54-fe782ef5fc15)

Under Treatment A > Content Card, let's apply the following message
  - Title: _Fall Collection: Limited Stock, Buy Now!_
  - Body: _It's cozy and chic_
  - Media Url: click the <img width="47" alt="image" src="https://github.com/user-attachments/assets/52422be5-fe3d-4d92-bf5a-a5bf514638ec" /> button, browse the  _Ajo Academy_ folder > _Fall Collection_ folder, select _fall-collection-banner-hiking_, then click _Select_ button
  - Under _Buttons_ section, click <img width="123" alt="image" src="https://github.com/user-attachments/assets/0f51086a-9c4d-41ef-b205-b19ddc8426e8" /> button and set _Button Title_ to _Shop Now_.
  - In the _Target_ input type the landing page url: `https://dsn.adobe.com/web/ajo-academy/fall-collection`
 
The experiment should look like this: 
![image](https://github.com/user-attachments/assets/e4bff3dd-c34c-457d-ba01-e37756ea4ad9)

Let's create now the second experiment with the help of generative AI to speed up the content creation process
- Under Treatment B > Content Card, let's apply the following message
  - Title: click the ![image](https://github.com/user-attachments/assets/aa503e9b-e8e7-4cdc-b106-4ea933043f21) button, add your prompt (eg: _Luma Outdoor appareil fall collection_), fine tune the communication strategy and tone using the Text settings, then click _Generate_ and select the variation you like the most.
  - Body: Apply the same as above to generate an Exclusive yet Empathetic message based on your prompt (eg: _Discover our new camping gears_)
  - Media Url: In the Digital Assets, browse the  _Ajo Academy_ folder > _Fall Collection_ folder, select _fall-collection-banner-camping_
  - Under _Buttons_ section, click <img width="123" alt="image" src="https://github.com/user-attachments/assets/0f51086a-9c4d-41ef-b205-b19ddc8426e8" /> button and set _Button Title_ to _Shop Now_.
  - In the _Target_ input button, copy the landing page url: `https://dsn.adobe.com/web/ajo-academy/fall-collection`
 
The experiment should look like this: 
![image](https://github.com/user-attachments/assets/e1da8764-b8d5-4a53-82d3-ffe58ba5a6de)

That's it, you can review the campaign now, just click the <img width="151" alt="image" src="https://github.com/user-attachments/assets/ebcdfb82-dc34-432e-9036-0ad67d732b53" /> button! 
if you go back to the Luma website home page, you shoud see an example of a live campaign promoting Luma Fall Collection activated. 



# You made it !

Congratulations! You've completed the lab 👍 ✨ 🎉 🚀 🤘 Together, we were able to:
- Improve our customer knowledge by collecting visitor data on our website.
- Build a customer profile with behavioral and personal data.
- Improve revenue by retargeting abandoners through personalized customer journeys and relevant contextual messages.
- Target our high value customers to incent them to visit the new Luma Fall Collection using A/B testing on inbound channels. 
  
All this in 2 hours 👏 👏 👏 It deserves a gift for all this effort 😛

[Home](README.md)
