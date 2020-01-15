---
# required metadata

title: Add an iOS line-of-business app to Microsoft Intune
titleSuffix:
description: Learn about how to add an iOS line-of-business (LOB) app to Microsoft Intune.
keywords:
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology:
ms.assetid: 099101e8-4b22-40ac-ba19-82ba5c71944c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure
ms.collection: M365-identity-device-management
---

# Add an iOS line-of-business app to Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Use the information in this article to help you add an iOS line-of-business (LOB) app to Microsoft Intune. A line-of-business (LOB) app is an app that you add to Intune from an IPA app installation file. This kind of app is typically written in-house. You will first need to join the iOS Developer Enterprise Program. For more information about how to do this see [Apple's website](https://developer.apple.com/programs/ios/enterprise/).

>[!NOTE]
>Users of iOS devices can remove some of the built-in iOS apps, like Stocks and Maps. You cannot use Intune to redeploy these apps. If users delete these apps, they must go to the app store and manually reinstall them.
>
>iOS LOB apps have a maximum size limit of 2 GB per app.

## Step 1: Specify the software setup file

1. Sign in to the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Select **Apps** > **All apps** > **Add**.
3. In the **Add App** pane, select **Line-of-business app** as the **App type**.

## Step 2: Configure the app package file

1. In the **Add app** pane, select **App package file**.
2. In the **App package file** pane, select the browse button. Then select an iOS installation file with the extension **.ipa**.
3. When you're finished, select **OK**.


## Step 3: Configure app information

1. In the **Add app** pane, select **App information**.
2. In the **App information** pane, add the details for your app. Depending on the app that you chose, some of the values in this pane might be automatically filled in.
    - **Name**: Enter the name of the app as it appears in the company portal. Make sure all app names that you use are unique. If the same app name exists twice, only one of the apps appears in the company portal.
    - **Description**: Enter a description for the app. The description appears in the company portal.
    - **Publisher**: Enter the name of the publisher of the app.
    - **Minimum Operating System**: From the list, choose the minimum operating system version on which the app can be installed. If you assign the app to a device with an earlier operating system, it will not be installed.
    - **Category**: Select one or more of the built-in app categories, or select a category that you created. Categories make it easier for users to find the app when they browse through the company portal.
    - **Display this as a featured app in the Company Portal**: Display the app prominently on the main page of the company portal when users browse for apps.
    - **Information URL**: Optionally, enter the URL of a website that contains information about this app. The URL appears in the company portal.
    - **Privacy URL**: Optionally, enter the URL of a website that contains privacy information for this app. The URL appears in the company portal.
    - **Developer**: Optionally, enter the name of the app developer.
    - **Owner**: Optionally, enter a name for the owner of this app. An example is **HR department**.
    - **Notes**: Enter any notes that you want to associate with this app.
    - **Logo**: Upload an icon that is associated with the app. This icon is displayed with the app when users browse through the company portal.
3. When you're finished, select **OK**.

## Step 4: Finish up

1. In the **Add app** pane, verify that the details for your app are correct.
2. Select **Add** to upload the app to Intune.

The app that you created now appears in the list of apps. From the list, you can assign the apps to groups that you choose. For help, see [How to assign apps to groups](apps-deploy.md).

> [!NOTE]
> Provisioning profiles for iOS LOB apps have a 30 day notice before they will expire.

## Step 5: Update a line-of-business app

[!INCLUDE [shared-proc-lob-updateapp](../includes/shared-proc-lob-updateapp.md)]

The update to the line-of-business app will be installed automatically.

> [!NOTE]
> For the Intune service to successfully deploy a new IPA file to the device, you must increment the `CFBundleVersion` string in the Info.plist file in your IPA package.

## Next steps

- The app that you created appears in the list of apps. You can now assign it to groups that you choose. For help, see [How to assign apps to groups](apps-deploy.md).

- Learn more about the ways in which you can monitor the properties and assignment of your app. See [How to monitor app information and assignments](apps-monitor.md).

- Learn more about the context of your app in Intune. See [Overview of device and app lifecycles](../fundamentals/device-lifecycle.md).
