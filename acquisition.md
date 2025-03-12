[home](README.md)

<p align="center">
<img width="1280" alt="image" src="https://github.com/user-attachments/assets/1bf8639a-755b-4aa3-88e0-5126a064b41b" />
</p>


Acquiring New Customer Data
==========================================

First, let's open a new tab in an **incognito mode (sometimes called private browsing)** browser session, copy the Luma demo website address:
<a href="https://dsn.adobe.com/web/ajo-academy/" target="_blank">https://dsn.adobe.com/web/ajo-academy/</a>

This the Luma website powered by Adobe web SDK to collect in real time customer behaviors. Before that, you need to give your consent by clicking the **Allow All** button displayed in the cookie notice banner 
<img width="630" alt="image" src="https://github.com/user-attachments/assets/1f529fa1-9146-44d4-89c8-0c12b2c12094" />



## Browsing as a Guest

![image](https://user-images.githubusercontent.com/40355195/216579845-3ff93b0d-9913-43f2-897b-db5770c2fdaf.png)

Browse the site, click on product pages (men, women, and equipment).

View the events collected in the Real Time Customer Profile panel by clicking on the Adobe logo in the top left corner of the screen and on the Events tab. Click the refresh icon to update the list.

![image](https://user-images.githubusercontent.com/40355195/216580677-491b28d3-fb54-4f91-8ad4-73d760f462dc.png)

If you have visited three product pages in the same category (men or women), you are automatically qualified for the corresponding segment.

![image](https://user-images.githubusercontent.com/40355195/216581233-eb81a4d6-c50d-4fc1-898c-f3eed9f00537.png)

This segment, calculated in real time from the collected data, is used to personalize the website banner. 

![image](https://user-images.githubusercontent.com/40355195/217661580-2993dad5-4107-45dd-aa40-304b62096f2e.png)

---

## Create an account

Click the _Sign-in_ button in the top right corner, then click the _Create an account_ link.

![image](https://user-images.githubusercontent.com/40355195/216589661-4cd1745d-64fa-4932-94b8-3c83ed15d7b6.png)

<img width="804" alt="image" src="https://github.com/user-attachments/assets/e5e916cb-8a38-4186-8f1f-4695703d64a7" />


Enter your information to create your account. Please use an email address where you have access to the mailbox (remeber the email address, you'll need it to check your emails and lookup your profile details in AEP)
- Toggle on _I want to join loyalty program_ and 
- Set Communication Preferences to _Email_
- Add your preferences (shoe size / shirt size and favorite color)
- Click the _Submit_ button.

A few seconds later, if you refresh the Real Time Customer Profile panel, the profile information are updated.

There you see the information collected by AEP, such as the profile details from the form as well as the identities collected, either cross device ids such as email address, phone number and also device id (Experience Cloud Id) set by the web sdk. Derived values, either calculated by AJO or coming from an external datasource enrich your profile (eg: Churn Prediction Score)

Scrolling down, you can also see the audience memberships AEP automatically calculated for you:
- based on from behavioral data collected in real time, such as product category interest
- based on user inputs (eg: _I want to join the Loyaly Program_  input onboards you to _Luma - Blue+ Memberbers audience_)

<img width="366" alt="image" src="https://github.com/user-attachments/assets/d9ea4589-4f59-4174-8aa0-b25939742e11" />


---

## Viewing the profile in Adobe Experience Platform

Still in the Real Time Customer Profile panel, click Utilities and _View Profile in AJO_

![image](https://github.com/user-attachments/assets/a13cad8d-02b9-4533-b6a5-ecf3afddd81b)


The profile view opens in a new tab. Observe:
- the events captured in the _Events_ tab
- the profile attributes collected in the _Attributes_ tab
- the segments associated with our contact in the _Segment Membership_ tab

![image](https://github.com/user-attachments/assets/c5c81d2f-f876-4661-87df-21e75a16f045)


Click on Show Identity Graph to view Identities collected and assigned to the real-time profile over time

<img width="1165" alt="image" src="https://github.com/user-attachments/assets/7b4c8508-8664-4fae-a34c-d60d16898564" />


---

## Receiving the email in the webmail

Log in to your mailbox using the same email address you used to create the your account on Luma website. 
If you do not see the email in your inbox folder, please check  the spam / junk folder (yes it is a demo instance where deliverability setup isn't 100% complete)

<img width="1394" alt="image" src="https://github.com/user-attachments/assets/ba06e671-9ad3-4174-99a2-db9b5ccba628" />


Congratulations! You have completed the first chapter of the 👍 ✨, go to the [next step](conversion.md) or return to the [home](README.md)
