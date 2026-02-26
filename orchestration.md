[home](README.md)

<p align="center">
<img width="800" src="https://github.com/user-attachments/assets/9c94e953-ab53-4ff6-b4f2-c6e5ea244489" />
</p>

In this chapter of the lab, we are going to explore Campaign Orchestration new capability within AJO designed to build, schedule, and deliver one‑to‑many marketing campaigns—primarily email, SMS, and push—using a marketer‑friendly, visual interface. It complements AJO’s event‑driven journeys by supporting traditional outbound campaigns that run on a defined schedule and target audience segments.

As Luma marketers, we'd like to build a Campaign to promote the Luma's sport's wear clothing. This campaign will send special promotions email to all profiles that made orders above 500 euros. To build this orchestrated campaign, we'd need first to build the target audience, then the email content to be delivered. We'd like to create personalize the email text, the banner image, and promotion using conditional content and AI content generation of image variations.

# Create Campaign Segmentation - Targeting Activities

First go to the new available tab "Orchestration" in the "Campaigns" AJO menu options and click on "Create Campaign" <img width="100" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Create Campaign Button.png" />. Let's start creating the visual campaign orchestration through a workflow: 

- Select Orchestration - Marketing, and name your campaign, please prefix it with the email address you used when creating your account on Luma website
  
  <img width="400" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Campaign creation options.png" />


BUILD AUDIENCE

- In the workflow, after the start activity add the 1st activity "Build Audience" click on the "+" sign <img width="60" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/+Sign image.png" /> and select "Build Audience"
  <img width="155" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Build Audience start.png" />
- then select the relational schema "Luma_Orders_record" as your targeting dimension

  <img width="155" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Select Targeting Dimension.png" />

- Now that the targeting dimension is selected, let's click on "Create Audience" <img width="90" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Create Audience Button.png" />
- Let's define the elligibility criteria of our audience by adding conditions:
  - Select the attribute "Order_Amount", it should be equal or higher than 500 euros
 <img width="400" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Condition 500.png" />
  - Select the attribute "Order_date" and select all order dates in the last year
 <img width="400" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Condition Date.png" /> 

- You should have the below Audience eligibility criteria definition:
 <img width="400" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Final Audience Target NB.png" />




DATA ENRICHMENT
  
  - Now let's enrich our data with the enrichment activity that exists to bring additional data into the workflow at run‑time, so that your audience selection and personalization logic can operate with richer context than what is available in the entry dataset alone. Click on the "+" after the "build audience" activity created, and select "Enrichment"

     <img width="250" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Add_Enrichment.png" />
- In the enrichment activity you need to select some fields/attributes that you would like to pass to personalize the email content like:
  - "Order Amount" - Click Add data enrichment from the current Order Table "Luma_Orders_Record", as per the screenshot below

     <img width="400" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Order_Amount_Attribute.png" />

  - "Average Order value" and "email" of the recipient - Add data enrichment from the Recipients table "Recipient_Orders" (relationship), as per the screenshot below

    <img width="400" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Order_Amount_Attribute.png" />
  
  - "Product Name" and "Product Price" attributes - Add data enrichment from table "Order_Items" which is related to "Products_Item" table

    <img width="400" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Order Items_attributes.png" />

  - The final "Order_items" related product attributes can be in a data collection mode if you would like to collect 3 related product items of your order (you can change the number of items to be collected). The screenshot below shows the final enrichment data for these attributes

    <img width="400" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/OrderItems_Final.png" />
 
- The final view of your Enrichment data activity should look like:

  <img width="500" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Enrichment_FinalView.png" />


CHANGE DIMENSION

In AJO Campaign Orchestration, we can start building on-demande audiences targeting different dimensions (multi-entity segmention), in this exercice, we started targeting "Orders" and now we need to deliver the promotions email to our final Recipients/Profiles. AJO Campaign Orchestration offers the "Change Dimension" activity, so we can change the targeting dimension from Orders to "Recipients" (for deliverability purposes).

- In the campaign workflow, click again in the "+" sign after the Enrichment activity just created. When you click, select "Change Dimension" activity:

  <img width="250" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Change Dimension.png" />

- Click on Targeting Dimension and select the table "Recipient_Orders"
  
  <img width="600" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Change_Dimension_Recipients.png" />

- With this step, we complete our Campaign Segmentation, your workflow should look like the below screenshot:

  <img width="600" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Final_Segmentation_View.png" />

- You can play the Campaign segmentation workflow in test mode (**do not publish**). Click in "Start" on the above right menu of your campaign orchestration workflow <img width="50" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Start_Workflow.png" />  You can also STOP, ReStart the workflow, always in a safe test mode (before publishing).

  <img width="600" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Final_Segmentation_Play.png" />

- Clicking in "Preview Results" a list of orders per recipient and respective 3 column Order items (as per the data collection defined in the enrichment) is displayed and you'll get the below view:

  <img width="600" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Segmentation_Preview_Results.png" />
  
 

# Create the Campaign Email content

Let's build a personalized email content for the Recipients/Profiles targeted in the above on-demand audience. For this exercice, please use the existing "_Luma New Offers_" email content template.

- In the campaign workflow, after the "Change Dimension" activity, click "+" and add an email activity from the menu options
- Edit the email and in the tab "Actions", select the email configuration for this exercice: "**EmailMarketing_CO**"

 <img width="500" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Email_configselection.png" />

- Click on "Edit Content" and then click on "Edit Email". At this point you will select an existing Email content called "_Luma New Offers_" in the "saved templates" tab

 <img width="500" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Email_Templateselection.png" />

 - On the top right of your screen, click on "Use this template" and **Save** your email before doing any changes

 <img width="500" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Email_UseTemplate.png" />

 - Let's personalize the content of this email, some dynamic content is already available in the image banner, let's create some more personalization:

     - Personalize the text box containing "It All starts with you..." with recipient's/profile "_first name_" field just after the word "you", click edit personalization <img width="30" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Personalization_Icon.png" /> and select "target Attributes" on the left menu. This is a new personalization option for fields we are passing with the enrichment activity of this campaign
       orchestration workflow. Refer to the screenshot below. After this please **Save** your email
  
       <img width="500" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Personalization_RecipientFirstName.png" />
       

     - We added in our enrichment activity, a group of Order_Items related attributes, Product Name and Price, and we configured a collection of 3 lines of data, let's personalize the email with the last 3 products that
       Customer ordered. Before the personalization let's add the text "_Thanks to your below product items ordered recently, we would like to propose you our new sports gear collection in exclusivity!_" in the text block
       as per the screenshot below. Don't forget to **Save** your email

       <img width="600" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Personalization_AddText.png" />

     - Below the text, let's add a fragment block already available called "Luma Last Orders Items". Go to fragments in here <img width="50" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Personalization_FragmentIcon.png" /> and drag and drop the fragment to the position as per the screenshots below. **Save** your changes
  
       <img width="500" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Personalization_FragmentDragDrop.png" />  <img width="500" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Personalization_Final_Fragment.png" />

     - This fragment helps us saving some time creating a grid of products and respective prices but now we need to personalize the content with the data enrichment from the workflow. Before we personalize the text in the
       fragment block, we need to "break the inheritance so we can edit the fragment content, click in here <img width="50" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Fragment_BreakInheritanceIcon.png" />

     - Now, double click over each text block inside the grid and add a "**{**" at the beginning of the text, and a "**}**" at the end of the text, this will activate the attribute validation from the personalization menu
       "Target Attributes". When the fragment was created, we couldn't call the "Target Attributes" yet, as these are only available and passing in the campaign workflow, through the enrichment activity. Please check the
       screenshot below. **Save** your changes
       
       <img width="500" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Personalization_FragmentAttributes.png" />

       
     - After the above action to personalize with product attributes, you want to test your content personalization so hard...we understand, but first don't forget to **asave your email**, then, go back to the workflow
       and be sure you re-start it in test mode, this way we are sure the email activity inherited the enrichment data. Otherwise, let's keep personalizing our email with some dynamic content.

     - Select the "_New Radiant Tee - Shop Now_" image and click on <img width="50" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Personalization_DynamicContent.png" /> to start creating variants of
       the content you want to show

     - We'll keep the default variant with the above image "_New Radiant Tee - Shop Now_", and let's configure the 2nd variant of the content:
  
       - Let's rename the 2nd variant to "_Men Gear_"

        <img width="500" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Personalization_DynCont_VariantName.png" />
  
       - Then we need to select or create a condition for the content variant we want to display for men (simple condition for this exercice, more complex conditions can be created based on profiles or existing audiences).
         Let's select the men's condition already defined as per the screenshots below
         
        <img width="500" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Personalization_DynCont_VariantCondition.png" />
        
        <img width="500" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Personalization_DC_Variant_SelectCondition.png" />

       - Now we need to add a new content for the condition "Men" we just defined. Let's use Adobe Ai content Assistant to help us create relevant content:
         
        - Be sure you are selecting the 2nd variant "Men", you'll see that by default the content is the same as the default variant. Let's add a cool image generated by Adobe's Ai content Assistant. Selecting the "Men"
          variant, click on the Content Gen Ai icon <img width="50" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Ai Assistant_icon.png" /> and let's start defining what do we want to
          generate

        - In the Ai Assistant panel, let's write the following text to the prompt _Generate an image of a sportive man with text "New Running T-Shirts" and a button with text "Shop Now"_
      
           <img width="350" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Ai Assistant_Menu_General.png" />  <img width="350" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Ai Assistant_TextPrompt.png" />

        - After the text prompt, in the **Image settings**, change **content type** to "_Photo_" as per the screenshot below
      
           <img width="300" alt="image" src="https://ripereir-adobe.github.io/ajo-academy/assets/Ai Assistant_ImageSettings.png" />

          




        
  


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
