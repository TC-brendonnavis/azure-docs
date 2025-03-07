---
title: 'Tutorial: Azure AD SSO integration with ThirdLight'
description: In this tutorial, you'll learn how to configure single sign-on between Azure Active Directory and ThirdLight.
services: active-directory
author: jeevansd
manager: CelesteDG
ms.reviewer: celested
ms.service: active-directory
ms.subservice: saas-app-tutorial
ms.workload: identity
ms.topic: tutorial
ms.date: 11/21/2022
ms.author: jeedes
---
# Tutorial: Azure AD SSO integration with ThirdLight

In this tutorial, you'll learn how to integrate ThirdLight with Azure Active Directory (Azure AD). When you integrate ThirdLight with Azure AD, you can:

* Control in Azure AD who has access to ThirdLight.
* Enable your users to be automatically signed-in to ThirdLight with their Azure AD accounts.
* Manage your accounts in one central location - the Azure portal.

## Prerequisites

To configure Azure AD integration with ThirdLight, you need to have:

* An Azure AD subscription. If you don't have an Azure AD environment, you can get a [free account](https://azure.microsoft.com/free/).
* A ThirdLight subscription that has single sign-on enabled.
* Along with Cloud Application Administrator, Application Administrator can also add or manage applications in Azure AD.
For more information, see [Azure built-in roles](../roles/permissions-reference.md).

## Scenario description

In this tutorial, you'll configure and test Azure AD single sign-on in a test environment.

* ThirdLight supports SP-initiated SSO.

## Add ThirdLight from the gallery

To configure the integration of ThirdLight into Azure AD, you need to add ThirdLight from the gallery to your list of managed SaaS apps.

1. Sign in to the Azure portal using either a work or school account, or a personal Microsoft account.
1. On the left navigation pane, select the **Azure Active Directory** service.
1. Navigate to **Enterprise Applications** and then select **All Applications**.
1. To add new application, select **New application**.
1. In the **Add from the gallery** section, type **ThirdLight** in the search box.
1. Select **ThirdLight** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 Alternatively, you can also use the [Enterprise App Configuration Wizard](https://portal.office.com/AdminPortal/home?Q=Docs#/azureadappintegration). In this wizard, you can add an application to your tenant, add users/groups to the app, assign roles, as well as walk through the SSO configuration as well. [Learn more about Microsoft 365 wizards.](/microsoft-365/admin/misc/azure-ad-setup-guides)

## Configure and test Azure AD SSO for ThirdLight

Configure and test Azure AD SSO with ThirdLight using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between an Azure AD user and the related user in ThirdLight.

To configure and test Azure AD SSO with ThirdLight, perform the following steps:

1. **[Configure Azure AD SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **[Create an Azure AD test user](#create-an-azure-ad-test-user)** - to test Azure AD single sign-on with B.Simon.
    1. **[Assign the Azure AD test user](#assign-the-azure-ad-test-user)** - to enable B.Simon to use Azure AD single sign-on.
1. **[Configure ThirdLight SSO](#configure-thirdlight-sso)** - to configure the single sign-on settings on application side.
    1. **[Create ThirdLight test user](#create-thirdlight-test-user)** - to have a counterpart of B.Simon in ThirdLight that is linked to the Azure AD representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

## Configure Azure AD SSO

Follow these steps to enable Azure AD SSO in the Azure portal.

1. In the Azure portal, on the **ThirdLight** application integration page, find the **Manage** section and select **single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, click the pencil icon for **Basic SAML Configuration** to edit the settings.

    ![Screenshot shows to edit Basic S A M L Configuration.](common/edit-urls.png "Basic Configuration")

1. In the **Basic SAML Configuration** dialog box, perform the following steps:

    1. In the **Identifier (Entity ID)** box, type a URL using the following pattern:
    `https://<subdomain>.thirdlight.com/saml/sp`

    1. In the **Sign on URL** box, type a URL using the following pattern:
    `https://<subdomain>.thirdlight.com/`

	   > [!NOTE]
	   > These values are placeholders. You need to use the actual Identifier and Sign on URL. Contact the [ThirdLight support team](https://www.thirdlight.com/support) to get the values. You can also refer to the patterns shown in the **Basic SAML Configuration** dialog box in the Azure portal.

1. On the **Set up Single Sign-On with SAML** page, in the **SAML Signing Certificate** section, select the **Download** link next to **Federation Metadata XML**, per your requirements, and save the file on your computer:

	![Screenshot shows the Certificate download link.](common/metadataxml.png "Certificate")

1. In the **Set up ThirdLight** section, copy the appropriate URLs, based on your requirements:

	![Screenshot shows to copy configuration appropriate U R L.](common/copy-configuration-urls.png "Metadata")

### Create an Azure AD test user

In this section, you'll create a test user in the Azure portal called B.Simon.

1. From the left pane in the Azure portal, select **Azure Active Directory**, select **Users**, and then select **All users**.
1. Select **New user** at the top of the screen.
1. In the **User** properties, follow these steps:
   1. In the **Name** field, enter `B.Simon`.  
   1. In the **User name** field, enter the username@companydomain.extension. For example, `B.Simon@contoso.com`.
   1. Select the **Show password** check box, and then write down the value that's displayed in the **Password** box.
   1. Click **Create**.

### Assign the Azure AD test user

In this section, you'll enable B.Simon to use Azure single sign-on by granting access to ThirdLight.

1. In the Azure portal, select **Enterprise Applications**, and then select **All applications**.
1. In the applications list, select **ThirdLight**.
1. In the app's overview page, find the **Manage** section and select **Users and groups**.
1. Select **Add user**, then select **Users and groups** in the **Add Assignment** dialog.
1. In the **Users and groups** dialog, select **B.Simon** from the Users list, then click the **Select** button at the bottom of the screen.
1. If you are expecting a role to be assigned to the users, you can select it from the **Select a role** dropdown. If no role has been set up for this app, you see "Default Access" role selected.
1. In the **Add Assignment** dialog, click the **Assign** button.

## Configure ThirdLight SSO

1. In a new web browser window, sign in to your ThirdLight company site as an admin.

1. Go to **Configuration** > **System Administration** > **SAML2**:

    ![Screenshot shows the System Administration.](./media/thirdlight-tutorial/admin.png "System Administration")

1. In the SAML2 configuration section, take the following steps.
  
    ![Screenshot shows the S A M L configuration section.](./media/thirdlight-tutorial/source.png "Folder")

	1. Select **Enable SAML2 Single Sign-On**.

	1. Under **Source for IdP Metadata**, select **Load IdP Metadata from XML**.

	1. Open the  metadata file that you downloaded from the Azure portal in the previous section. Copy the file's content and paste it into the **IdP Metadata XML** box.

    1. Select **Save SAML2 settings**.

### Create ThirdLight test user

To enable Azure AD users to sign in to ThirdLight, you need to add them to ThirdLight. You need to add them manually.

To create a user account, take these steps:

1. Sign in to your ThirdLight company site as an admin.

1. Go to the **Users** tab.

1. Select **Users and Groups**.

1. Select **Add new User**.

1. Enter the user name, a name or description, and the email address of a valid Azure AD account that you want to provision. Choose a Preset or Group of New Members.

1. Select **Create**.

> [!NOTE]
> You can use any user account creation tool or API provided by ThirdLight to provision Azure AD user accounts.

## Test SSO

In this section, you test your Azure AD single sign-on configuration with following options. 

* Click on **Test this application** in Azure portal. This will redirect to ThirdLight Sign-on URL where you can initiate the login flow. 

* Go to ThirdLight Sign-on URL directly and initiate the login flow from there.

* You can use Microsoft My Apps. When you click the ThirdLight tile in the My Apps, this will redirect to ThirdLight Sign-on URL. For more information about the My Apps, see [Introduction to the My Apps](../user-help/my-apps-portal-end-user-access.md).

## Next steps

Once you configure ThirdLight you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Cloud App Security](/cloud-app-security/proxy-deployment-aad).