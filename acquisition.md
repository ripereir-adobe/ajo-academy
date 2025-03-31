[home](README.md)

<p align="center">
<img width="800" src="https://github.com/user-attachments/assets/9c94e953-ab53-4ff6-b4f2-c6e5ea244489" />
</p>

---
# Acquiring New Customer Data

First, let's open a new tab in an **incognito mode (sometimes called private browsing)** browser session, copy the Luma demo website address:
<a href="https://dsn.adobe.com/web/ajo-academy/" target="_blank">https://dsn.adobe.com/web/ajo-academy/</a>. 

You may have to verify your identity if this is your first time login. If so, check your mailbox to enter the one time code you received and complete your profile (don't worry, these information won't be used outside of this lab). 

This the Luma website powered by Adobe web SDK to collect in real time customer behaviors. Before that, you need to give your consent by clicking the **Allow All** button displayed in the cookie notice banner. 
<img width="630" alt="image" src="https://github.com/user-attachments/assets/1f529fa1-9146-44d4-89c8-0c12b2c12094" />


---
# Browsing as a Guest

![image](https://user-images.githubusercontent.com/40355195/216579845-3ff93b0d-9913-43f2-897b-db5770c2fdaf.png)

Browse the site, click on product pages (men, women, and equipment).

View the events collected in the Real Time Customer Profile panel by clicking on the Adobe logo in the top left corner of the screen and on the Events tab. Click the refresh icon to update the list.

![image](https://user-images.githubusercontent.com/40355195/216580677-491b28d3-fb54-4f91-8ad4-73d760f462dc.png)

If you have visited three product pages in the same category (men or women), you are automatically qualified for the corresponding segment. Notice also the status of the audience evaluation, either _Realized_ or _Exited_ based on how long your in the audience. 

<img width="366" alt="image" src="https://github.com/user-attachments/assets/51d589c0-d4f3-4fd5-ba44-b3fa8e77775c" />


---
# Create an account

Click the  ![image](https://github.com/user-attachments/assets/d85996df-dad1-43f0-a048-3e051a7f4cb1) button in the top right corner, then click the ![image](https://github.com/user-attachments/assets/804ea637-32ab-4835-a0dc-6ea132afa126)
 link.

Enter your information to create your account. Remember the email address , you'll need it to access your mailbox and lookup your profile details in AEP.

> [!NOTE]
> Use a valid email address linked to a mailbox where you can check your emails.  
> It can be the one you use to first login to the environment


- Toggle on _I want to join loyalty program_ and 
- Set Communication Preferences to _Email_
- Add your preferences (shoe size / shirt size and favorite color)
- Click the _Submit_ button.
- Once your account is created you can login (no need to type a password, it is a demo website)

A couple of minutes later, if you refresh the Real Time Customer Profile panel, the profile information are updated.

There you see the information collected by AEP, such as the profile details from the form as well as the identities collected, either cross device ids such as email address, phone number and also device id (Experience Cloud Id) set by the web sdk. Derived values, either calculated by AJO or coming from an external datasource enrich your profile (eg: Churn Prediction Score)

Scrolling down, you can also see the audience memberships AEP automatically calculated for you:
- based on from behavioral data collected in real time, such as product category interest
- based on user inputs (eg: _I want to join the Loyaly Program_  input onboards you to _Luma - Blue+ Memberbers audience_)

<img width="366" alt="image" src="https://github.com/user-attachments/assets/d9ea4589-4f59-4174-8aa0-b25939742e11" />


---
# Viewing the profile in Adobe Experience Platform

Still in the Real Time Customer Profile panel, click Utilities and _View Profile in AJO_

<img width="366" alt="image" src="https://github.com/user-attachments/assets/a13cad8d-02b9-4533-b6a5-ecf3afddd81b" />


The profile view opens in a new tab. Observe:
- the events captured in the _Events_ tab
- the profile attributes collected in the _Attributes_ tab
- the segments associated with our contact in the _Segment Membership_ tab

![image](https://github.com/user-attachments/assets/c5c81d2f-f876-4661-87df-21e75a16f045)


Click on Show Identity Graph to view Identities collected and assigned to the real-time profile over time

<img width="1165" alt="image" src="https://github.com/user-attachments/assets/7b4c8508-8664-4fae-a34c-d60d16898564" />


---
# Receiving the email in the webmail

Log in to your mailbox using the same email address you used to create the your account on Luma website. 
If you do not see the email in your inbox folder, please check  the spam / junk folder (yes it is a demo instance where deliverability setup isn't 100% complete)

<img width="1394" alt="image" src="https://github.com/user-attachments/assets/ba06e671-9ad3-4174-99a2-db9b5ccba628" />



<br /><br />
Congratulations! You have completed the first chapter of the 👍 ✨, go to the [next step](conversion.md) or return to the [home](README.md)
