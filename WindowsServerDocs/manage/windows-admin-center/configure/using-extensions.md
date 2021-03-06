---
title: Install and Manage Extensions
description: Install and Manage Extensions in Windows Admin Center (Project Honolulu)
ms.technology: manage
ms.topic: article
author: daniellee-msft
ms.author: jol
ms.date: 06/18/2018
ms.localizationpriority: medium
ms.prod: windows-server-threshold
---
# Install and Manage Extensions

>Applies To: Windows Admin Center, Windows Admin Center Preview

Windows Admin Center is built as an extensible platform where each connection type and tool is an extension that you can install, uninstall and update individually. You can search for new extensions published by Microsoft and other developers, and install and update them individually without having to update the entire Windows Admin Center installation. You can also configure a separate NuGet feed or file share and distribute extensions to use internally within your organization.

> [!IMPORTANT]
> Some of the features described in this article are only available in Windows Admin Center Preview. [How do I get this version?](http://aka.ms/windowsadmincenter)

## Installing an extension

Windows Admin Center will show extensions available from the specified NuGet feed. By default, Windows Admin Center points to the Microsoft official NuGet feed which hosts extensions published by Microsoft and other developers.

1. *On Windows Admin Center Preview*, click the **Settings** button in the top-right > In the left pane, click **Extensions**. 

    *On Windows Admin Center*, click the **Settings** button in the top-right > In the **General** tab, click **Manage Extensions**.

2. The **Available Extensions** tab will list the extensions on the feed that are available for installation.
3. Click on an extension to view the extension description, version, publisher and other information in the **Details** pane.
4. Click **Install** to install an extension. You may encounter an error that the gateway must run in elevated mode to make this change and then will be presented with a UAC elevation prompt. If you provide consent, Windows Admin Center will be opened in a new browser tab in elevated mode. Repeat these steps in the elevated session to change the feed.

After installation is complete, your browser will automatically be refreshed and Windows Admin Center will be reloaded with the new extension installed.

> [!NOTE]
> The Extension manager has the following limitations. We are planning to improve this in future updates.
> 
> Limitations in Windows Admin Center Preview:
> - Installed extensions are currently not persisted when you upgrade to a newer version of Windows Admin Center. You will need to manually reinstall extensions after upgrade for now.
>
> Limitations in Windows Admin Center. These are fixed in Windows Admin Center Preview:
> - Windows Admin Center does not currently notify you when an update is available for a previously installed extension.
> - Windows Admin Center does not currently support upgrade of extensions. You will need to uninstall the previous version and install the newer version manually.

## Installing extensions from a different feed - Windows Admin Center Preview

Windows Admin Center Preview supports multiple feeds and you can view and manage packages from more than one feed at a time. Any NuGet feed that supports the NuGet V2 APIs or a file share can be added to Windows Admin Center for installing extensions from.

1. Click the **Settings** button in the top-right > In the left pane, click **Extensions**.
2. On the right pane, click the **Feeds** tab.
3. Click the **Add** button to add another feed. For a NuGet feed, enter the NuGet V2 feed URL. The NuGet feed provider or administrator should be able to provide the URL information. For a file share, enter the full path of the file share in which the extension package files (.nupkg) are stored.
4. Click **Add**. You may encounter an error that the gateway must run in elevated mode to make this change and then will be presented with a UAC elevation prompt. If you provide consent, Windows Admin Center will be opened in a new browser tab in elevated mode. Repeat these steps in the elevated session to change the feed.

The **Available Extensions** list will show extensions from all registered feeds. You can check which feed each extension is from using the **Package Feed** column.

## Installing extensions from a different feed - Windows Admin Center

Windows Admin Center supports a single extension feed. You can configure Windows Admin Center to show extensions from any NuGet feed that supports the NuGet V2 APIs or a file share.

1. Click the **Settings** button in the top-right. > In the **General** tab, click **Manage Extensions**.
2. In the **Available Extensions** tab, click **Settings**.
3. For a NuGet feed, enter the NuGet V2 feed URL. The NuGet feed provider or administrator should be able to provide the URL information. For a file share, enter the full path of the file share in which the extension package files (.nupkg) are stored.
4. Click **Save**. You may encounter an error that the gateway must run in elevated mode to make this change and then will be presented with a UAC elevation prompt. If you provide consent, Windows Admin Center will be opened in a new browser tab in elevated mode. Repeat these steps in the elevated session to change the feed.
5. Click **Close**.

The **Available Extensions** list will show extensions from the new feed or file share.

Since Windows Admin Center currently supports a single feed, you will no longer see extensions from the Windows Admin Center feed if you change the feed URI to a different location. In order to configure to the Windows Admin Center feed again, change the feed URI to be blank and click **Save**.

## Uninstalling an extension

You can uninstall any extensions you have previously installed, or even uninstall any tools that were pre-installed as part of the Windows Admin Center installation.

1. *On Windows Admin Center Preview*, click the **Settings** button in the top-right > In the left pane, click **Extensions**. 

    *On Windows Admin Center*, click the **Settings** button in the top-right > In the **General** tab, click **Manage Extensions**.

2. Click the **Installed Extensions** tab to view all installed extensions.
3. Choose an extension to uninstall, then click **Uninstall**.

After uninstall is complete, your browser will automatically be refreshed and Windows Admin Center will be reloaded with the extension removed. If you uninstalled a tool that was pre-installed as part of Windows Admin Center, the tool will be available for reinstallation in the **Available Extensions** tab.

[Learn more about building an extension with the Windows Admin Center SDK](../extend/extensibility-overview.md).