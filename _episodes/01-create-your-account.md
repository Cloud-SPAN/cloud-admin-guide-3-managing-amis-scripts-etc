---
title: "Taxonomic Annotations - episode 1"
teaching: 20
exercises: 10
questions: 
- "What do you need to open an AWS account?"
- "How do you open an AWS account?"
objectives:
- Open your AWS account. 
- Know how to access your AWS account.
keypoints:
- Your new AWS account is automatically entitled to the one-year AWS Free Tier.
- The Free Tier has some limits that you must observe in order not to incur unwanted costs.
- The link to login to your account in the AWS Management Console is [https://aws.amazon.com/console](https://aws.amazon.com/console)
---
> ## Prerequisites
> You will need the following to complete this episode: 
> - an email address
> - a credit card although new accounts get one-year of AWS Free Tier
> - the phone number (associated with the credit card)
> - the address (associated with the the credit card)
{: .prereq}

# Outline
These are the main steps you will follow to open your AWS account:

1. Sign-up to AWS with your email (as username) and password.

2. Select your account type (**Personal**) and enter your contact information.

3. Enter Billing Information: your credit card details.

4. Confirm your identity to AWS through a phone call or SMS message.

5. Select support plan (**Basic**) and complete sign-up.

6. Login to your AWS account.

## 1. Sign-up to AWS with your email and password

Go to the **sign-up** page by clicking on this link [AWS sign-up](https://portal.aws.amazon.com/billing/signup#/start) --- for convenience, right click on the link and, in the menu that pops up, left click on **Open link in new window**; you can switch between this browser window and the sign-up page window to be opened by pressing the keys Alt-Tab simultaneously. 

You will need to enter your email and password and a name for your account --- you can change the name of your account later.

![Caption.](../fig/open-acc04-signup-page-filled.PNG.jpg "The Sign up for AWS page showing the boxes for your email address, password and account name")

> ## New accounts
> 1. new accounts are all granted the one-year Free Tier (message on the left).
> 2. the name of an account helps to identify the account once the user is logged in, as it is not uncommon for AWS users to have more than one AWS account.
{: .callout}

Once you have entered your email, password and account name, click on **Continue (step 1 of 5)** and complete the **Security check** box that will pop up by typing the characters displayed into the box. Click on **Continue (step 1 of 5)** again.

## 2. Select your account type (Personal) and enter your contact information
The next page asks you **How do you plan to use AWS?** Choose **Personal** and enter your name, phone number and address --- your address must be the one associated with your credit card and this will be verified in the next step. 

Then read the *AWS Customer Agreement* and check the box **I have read and agree to the terms of the AWS Customer Agreement**. Finally, click on **Continue (step 2 of 5)** to move to step 3.

![Caption.](../fig/open-acc07-signup-page-contact-details1.PNG.jpg "The Sign up for AWS page the selection between the business and personal accounts and boxes for you name and phone number")

> ## Account types
> 1. There is no functional difference between a business account and a personal account. Both have access to all AWS services and both support managing sub-accounts which, as we will see in the next episode, are more convenient for every day work. 
> 2. A personal account should not be opened with a work email address as you may change jobs after opening the account. A business account should be opened with a company or institution address linked to a roll or position and not to a person who may change jobs at some point. 
{: .callout}

## 3. Enter Billing Information: your credit card details

Now you are asked for your credit card details. Note that your credit card will be **verified** once you click on the orange button **Verify and Continue (step 3 of 5)** and that you must select/provide the address associated with your credit card.

Please note the Secure verification message on the left: AWS will make a small charge (equivalent to $1 USD) on your card to verify it, but the charge will be returned to you in 3-5 days.

![Caption.](../fig/open-acc10-signup-page-filling-card-details.PNG.jpg "The Sign up for AWS page showing the boxes billing information")

As part of the **verification process** a pop-up window from your bank or financial institution may appear and ask you to verify the AWS transaction.  Choose the phone you want to receive the passcode, click on **Confirm**, and once you receive the passcode enter it as required. 

![Caption.](../fig/open-acc11-signup-page-validating-card.jpg "the pop up window asking you to verify the transaction")

## 4. Confirm your identity to AWS through a phone call or SMS message

You now need to confirm your identity to AWS through an SMS message or a phone call to the phone number that will be associated with your account (we used the same phone number we entered in step 2). 

Please select SMS message or phone call, enter your phone number and the characters in the security check box, and finally click **Send SMS (step 4 of 5)**. After you enter the code, another page will be displayed for your to select a support plan and you will receive the SMS or a phone call within a few seconds.

![Caption.](../fig/open-acc13signup-page-verify-with-SMSmessage.jpg "The identity confirmation page showing options to receive verification code - Text message being selected")

## 5. Select support plan (**Basic**) and complete sign-up

You must now select a support plan. Select the **Basic support** plan and click **Complete sign-up**.  The Basic support plan is free and you don't need more if this is your first AWS account.

![Caption.](../fig/open-acc16signup-page-select-support-plan3.png "The support pan selection page showing the Basic Support - Free option being selected")

The congratulations page will then be displayed.

You will also receive three emails from AWS with the Subjects: 

- "Welcome to Amazon Web Services"
- "AWS Support (Basic) Sign-Up Confirmation"
- "Your AWS Account is Ready - Get Started Now"

These emails have links to useful information and resources.

![Caption.](../fig/open-acc17signup-page-finished-congratulations.jpg "The congratulations page. It includes a button to Go to the AWS Management Console")

## 6. Login to your AWS account

From the congratulations page click **Go to the AWS Management Console** where you will be asked to sign in.

![Caption.](../fig/using-acc01-signingin-as-root-page.PNG.jpg "The sign in page showing the options to choose Root user or IAM user")

> ## Types of user
> 1. The login page will give you the option to login either as the **Root user** or as an **IAM user** --- IAM stands for Identity Access Managment. 
> 2. The Root user account is for the owner of the account who "performs tasks requiring unrestricted access", such as updating billing information or deleting the account, while an IAM user account is for a user who "performs daily tasks" such as using AWS services. 
> 3. At this stage you can only login to the Root user account. In the next episode you will create an IAM account which you will use to create and manage your instance.
{: .callout}

Login to your **Root user** account by entering the email address that you used to open your account in step 1. 

Press **Next** button. You will be prompted to (1) enter some characters by a "Security check" box and then your password, (2) select either the previous or the new version of the **Console Home** (please choose the new version), and (3) select your cookie preferences (select as you prefer). 

![Caption.](../fig/using-acc04-signedin-options-services-and-cookies.PNG.jpg "The AWS Management console after you have logged in")

Finally you will be logged in as Root user, able to use your account. We will first configure your account in the next episode.

> ## Exercise
> As you eventually will logout from your account, please make a note of the address to log back in to the AWS Managment Console: 
> **aws.amazon.com/console**  or  **https://aws.amazon.com/console**
{: .challenge}




