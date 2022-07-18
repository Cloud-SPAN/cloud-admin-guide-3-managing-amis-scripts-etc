---
title: "Configure Your AWS Account"
teaching: 20
exercises: 10
questions:
- Why to configure an AWS account?
- What is involved in configuring an AWS account?
objectives:
- Secure your AWS account. 
- Configure your AWS account for daily work.   
keypoints:
- "The Root account should only be used for high-level admin tasks."
- "IAM accounts should be created and configured for daily use."
---
> ## Prerequisites
> To complete this episode you will need:
> - to have opened your AWS account as described in the first episode of this lesson: [Create Your AWS Account](../01-create-your-account). 
> - to be logged in to your AWS account as the **Root User** (described also in that episode, at the end). 
> - ideally, your mobile phone to add multi-factor authentication (**MFA**) to your AWS account. However, **if you don't have a mobile phone, you can skip this step** and still use your AWS account.
{: .prereq}

# Introduction
> ## Steps
> These are the main steps you will follow to configure your AWS account:
>
> 1. **Change the default region of your account to Ireland.**\
> AWS services are provided through many regions around the world and a region is allocated by default. You will need to change the region of your account to Ireland because the Amazon Machine Image from which you will create your AWS instance is stored in the Ireland region. But you can later change your account region if you wish.  
>
> 2. **Secure your AWS Root User account.**\
> The account your created in the last episode is your Root user account and can perform any operation including closing the account. It is best practice to use the Root user account only for high-level administration and to create and an **IAM** (Identity Access Managment) user account for day-to-day work. It is also best practice to secure the Root user account with multi-factor authentication (MFA).
>
> 3. **Create an IAM user account to create and manage your instance.**\
> IAM user accounts are attached to a **User Group** that has a set of specific permissions (such as reading, writing and deleting) on specified resources. We will create a User Group with predefined permissions and a IAM user account in that group. 
>
> 4. **Create an alias for your account id**.\
> Your Root user account id is a 12-digit number that is difficult to remember. We are going to create an alias that is easier to remember. This is especially useful because the alias will replace the 12-digit number in the web address for logging in to your account as IAM user. 
{: .callout}

## 1. Change the default region of your account to Ireland

Once you have logged to your AWS Root user account, your browser will display a page showing the default region in the top right. This may be **N. Virginia** or another default.
You need to change the region to **Europe (Ireland)  eu-west-1** using the drop-down menu. Your browser will redirect to the AWS servers in the selected region.

![Caption.](../fig/config-acc/ca01-signedin-options-services-and-cookies.jpg "Browser showing N. Virginia as the region for the account in the top right.")


> ## Note
> You can change the region any time you need. 
{: .callout}

## 2. Secure your AWS **Root user** account

We now are going to add multi-factor authentication (MFA) to your Root user account as an extra security mechanism. This requires you to download an app to your mobile phone, as described below. 

> ## No mobile phone?
> If you don't have a mobile phone, don't worry, you can skip this step and go straight to **3. Create an IAM user account to create and manage your instance**.  
> If you are not using MFA it is best to use your AWS Root user account only from your personal computer or a trusted computer.
{: .callout}

Type **iam** in the AWS search box and press Enter. You will be presented with the "IAM Dashboard". Click on **Add MFA** (on the right).

![Caption.](../fig/config-acc/ca02-root-user-requires-mfa1.jpg "The 'IAM Dashboard' showing the Add MFA button.")

On the page that appears, "Your Security Credentials", click **Activate MFA**.

![Caption.](../fig/config-acc/ca03-root-user-activate-mfa.jpg "The 'Your Security Credentials' page showing the Activate MFA button")

A pop-up window called "Manage MFA device" will appear. Select **Virtual MFA device** and **Continue**.

![Caption.](../fig/config-acc/ca04-root-user-choose-mfa-device.jpg "The 'Manage MFA device' pop-up window showing Virtual MFA device selected.")

You will now be presented with a pop-up called "Set up a virtual MFA device". Don't select anything at the moment.

![Caption.](../fig/config-acc/ca05-root-user-setup-mfa-device.jpg "The 'Set up a virtual MFA device' pop-up")

To set up your mobile as MFA device you will need a Virtual MFA app on your mobile phone. We have tested both "Duo Mobile" and "Google Authenticator" and give instructions for both but you may already be using another app. AWS lists some options here: [AWS MFAs](https://aws.amazon.com/iam/features/mfa/).

**If you do not have a Virtual MFA app on your mobile phone:**
Go to the app store on your phone, search for Duo Mobile *or* Google Authenticator, and install it.

Once you have installed an MFA app in your mobile:
- Return to the above pop-up "Set up a virtual MFA device" on your computer and choose **Show QR code**.
- Open the MFA app on your phone
  - Press **+ Add** in Duo Mobile or **+** in Google Authenticator 
  - Press **Use QR code** in Duo Mobile or **Scan a QR code** in Google Authenticator. Your camera will open to scan a QR code.
  - Point your camera at your computer screen showing the QR code to scan. You may need to adjust the zoom for the scan to occur.
- Once the scan is successful, the MFA will display a number for about 30 seconds, and then another number for the same time, and so on until you close it. 
- Of those numbers shown in your mobile MFA, you need to enter two consecutive numbers into the fields **MFA Code 1** and **MFA Code 2** on the pop-up "Set up a virtual MFA device" on your computer. You may need to scroll down to see MFA Code 2. **NB: enter the numbers with no space between them** even if they are shown with a space in your mobile.
- Click on **Assign MFA**. 

You will see a success message which you can close.

Every time you login to your Root user account, you will be asked to enter your password and an MFA code number which you must read from your mobile by simply opening the MFA app.

## 3. Create an IAM user account to create and manage your instance

We are going to create an IAM user account with which you will create and manage your AWS instance in the next lesson. This means first creating an IAM User Group with one or more security policies, and then your IAM user account within that User Group.

We will create a user group called **Administrators**, then a user account called **YourName** (your actual name), and finally attach the account to the group. As this is the first IAM group and IAM account to be created, we need to do this with the Root user account, but then it will be possible to do it with the IAM account we will create because it will have Administrator privileges.

#### **Create the user group**

Go to the IAM Dashboard page by typing **iam** in the AWS search box and pressing Enter. On the IAM Dashboard, click on "User groups" under "Access Management" on the left, and then on **Create group** on the right.

![Caption.](../fig/config-acc/ca11-iam-user-create-group-btton.jpg "The IAM Dashboard showing the User groups option under Access Management on the left and the Create group button on the left.")

In the page that appears, "Create user group", type "Administrators" in the box "User group name" but **don't press** Enter. Scroll down until you see the section "Attach permissions policy - *Optional*". This section has a search box and a list of different policies.

Type "administratoraccess" in the search box and press Enter.

![Caption.](../fig/config-acc/ca13-iam-user-attach-policy1.jpg "The Attach permissions policies - Optional panel with 'administratoraccess' typed into the search box")

This will bring the "AdministratorAccess" policy to the top of the list. Check the box next to that policy and then click on **Create group**. The screen displayed after creating the group may indicate it is loading users --- it's OK, ignore it.

You now have a user group called **Administrators**

![Caption.](../fig/config-acc/ca15-iam-user-group-created.jpg "A list of the User groups in the account showing that there is only one user group called Administrators.")

#### **Create the user and add it to the group**

The next step is to create your IAM user account. Under "Access Management" on the left, click on "Users".

The page titled "Users" will be displayed. Click on **Add users**. 

You can now set your IAM user details as shown in the figure below, by:
- typing your user name (a single word) 
- checking the box "Password - AWS Management Console access"
- checking the box "Autogenerated password" and 
- checking the box "User must create a new password at next sign-in"

Then click on **Next: Permissions**

![Caption.](../fig/config-acc/ca16-iam-user-add-name.jpg "The Add User section showing a user name ('me') typed into the User name box and the 'Password - AWS Management Console access' box checked")
![Caption.](../fig/config-acc/ca16-iam-user-add-name2.jpg "and the 'Autogenerated password' and 'User must create a new password at next sign-in' options as checked. The Next: Permissions button is also shown")

You will be presented with a page that says "Add user - Set permissions". The **Add user to group** option should be set. Leave it set. 

Check the box next to the group Administrators (in blue) and then click on **Next: Tags**

![Caption.](../fig/config-acc/ca17-iam-user-add-to-group.jpg "The 'Add user - Set permissions' page showing 'Add user to group' selected.")

Adding tags --- or keywords --- for a user is optional. You don't need to tag your user account for the time being. It is useful when you are managing multiple user accounts.

Click on **Next: Review**. This will display the options chosen for your user account for review. If these are correct click on **Create user**.

![Caption.](../fig/config-acc/ca18-iam-user-review.jpg "The review user account page")

You will see a message indicating you have successfully added a user. This message includes information you will need.

- Write down the web address: https://xxxxxxxxxxxx.signin.aws.amazon.com/console  --- where xxxxxxxxxxxx is the 12-digit number of your account id.
- Download the  .csv file which contains your account login details: your username, your randomly generated password, and the web address where you will login to as IAM user 
- Close the success message.
 
![Caption.](../fig/config-acc/ca19-iam-user-created.jpg "The message indicating you have successfully aded a user showing the web address you need to note down and the button to download the .csv file")


> ## What's in the file?
> The file you downloaded is a *comma separated value* (CSV) file that you can open in any text editor. The content is something like this:
> 
> `me,0ji)8[bN3{F-X!h,,,https://xxxxxxxxxxxx.signin.aws.amazon.com/console`
> 
> In this line, the first field, `me`, is the user name, the second field (after the first coma), `0ji)8[bN3{F-X!h`, is the password (yours will be different of course), and the last field, `https://xxxxxxxxxxxx.signin.aws.amazon.com/console`, is the web address to login. The third and fourth fields are empty.
> 
> **NB**: the first time you login you will have to change the password. 
{: .callout}

Once you closed the success message above, in the page that appears you should see the User account you have just created, listed along with the Groups (Administrators) of which it is a member and other information. "Never" in "Last activity" means you have not yet logged in.

Open a **new** tab in your browser and go to the login web address of your new account (https://xxxxxxxxxxxx.signin.aws.amazon.com/console) and log in with the username and password from the .csv file you downloaded.

## 4. Create and alias for your IAM user acount

A 12-digit number can be difficult to remember so let's create an alias which is easier to remember. The alias can be used to login to your account.

Type **iam** in the AWS search box and press Enter to go to the "IAM Dashboard".

On the right of the Dashboard, under the heading "AWS Account", is your "Account id" and further below your "Account Alias". Both are the same because you have not set up an alias yet. 

Click on **Create** next to "Account Alias" and then enter the alias you want to use --- which might be some version of your name or date of birth. Note the new sign-in URL. Click on **Save changes**.

![Caption.](../fig/config-acc/ca22-url-alias-create.jpg "Pop-up called 'Create alias for AWS account xxxxxxxxxxxx'. ")

You can now login to your account using either web address: the one with your 12-digit account number or the one with your alias.

You have now configured your AWS account for day-to-day use. 



