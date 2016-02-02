---
layout: null
title: Zuora/Netsuite FAQ
permalink: /finance-faq/
---

# Netsuite & Zuora Frequently Asked Questions

* [Zuora](#zuora)
  * [Credit Card `Transaction declined` errors](#zuoracc)
  * [How do I change my password?](#zuorapw)
* [Netsuite](#netsuite)
  * [How do I change my password?](#netsuitepw)
  * [How do I update my security questions?](#netsuitequestions)
* [Netsuite and Zuora](#netsuitezuora)
  * [How do I make changes to a payment in NetSuite and resync to Zuora](#nszuresyncpmt)

## <a id="zuora">Zuora FAQ</a>

### Why did Zuora produce this error for a Credit Card transaction: `Error: Transaction declined.12 - Declined: 15005-This transaction cannot be processed`<a id="zuoracc"></a>

This is caused by the Credit Card’s issuing bank. It is generally due to a limit on the card. **The partner will need to contact their credit card provider** and ask the limit to be increased or for eFolder Inc. to be added to their whitelist for purchases.

### How do I change my password?<a id="zuorapw"></a>

Hover over the settings menu in the top right and click personal settings:

![personal settings](http://i.imgur.com/Gy9sexq.png)

Click the `Change my Password` Link:

![change my password](http://i.imgur.com/AzDPJ0Z.png)

Enter your current password and new password. Please make note of the Password enforcement rules at the bottom of the page.

![password enforcement rules](http://i.imgur.com/227VgKS.png)

## NetSuite <a id="netsuite"></a>

### How do I change my password?<a id="netsuitepw"></a>
First go to your home dashboard by clicking the `home` icon in the top left of NetSuite:

![home icon](http://i.imgur.com/ZQOSmPc.png)

Look for the `settings` pane, generally located at the bottom of the page. Click the `Change Password` link.

![settings](http://i.imgur.com/l9QLJxy.png)

You will need to enter your current and new passwords. Please note the password enforcement rules on the page.

![password enforcement rules](http://i.imgur.com/Wh6jcll.png)

### How do I update my security questions?<a id="netsuitequestions"></a>
First go to your home dashboard by clicking the home icon in the top left of NetSuite.

![home icon](http://i.imgur.com/ZQOSmPc.png)

Look for the settings pane, generally located at the bottom of the page. Click the `Update Security Questions` link.

![update security questions](http://i.imgur.com/7vR5LxT.png)

Enter your current password and choose and answer each of the three question prompts.

## NetSuite and Zuora<a id="netsuitezuora"></a>

### How do I make changes to a payment in NetSuite and resync to Zuora?<a id="nszuresyncpmt"></a>
1. Request a Transaction unlock on the payment by hitting the "Request Unlock" button in NetSuite. Wait for a response from the NetSuite Admin before proceding to step 2 below.
2.	Find the equivalent payment in Zuora for this payment. Should be pretty easy to find, but you can find additional information in the “Zuora Sync Details” tab, specifically the Zuora ID, which can be used in Zuora’s URL to go straight to the payment.
 * a.	https://www.zuora.com/apps/NewPayment.do?method=view&id=<em>zuoraidhere</em> 
 * EG: https://www.zuora.com/apps/NewPayment.do?method=view&id=2c92a0ff528dec7f01529e8952f95044
3.	Edit the payment in Zuora, set the “Transferred to Accounting” field to “Ignore”. Save
4.	Cancel the payment in Zuora.
5.	Let the NetSuite Admin know once the Zuora Payment is cancelled, They will then unlock the payment in NetSuite for editing.
6.	When it is unlocked in NetSuite, you will need to first clear out two fields of data in the “Zuora Sync Details” tab, clear out the “ZUORA ID” field and the “ZUORA INTEGRATION STATUS” field, make them both blank. This will let Zuora know this payment needs to be resynced. <strong>Do not save yet.</strong> Now go ahead and make the appropriate edits needed, then save. After you save, the transaction will automatically relock and Zuora will know to attempt resyncing the payment from NetSuite to Zuora.

