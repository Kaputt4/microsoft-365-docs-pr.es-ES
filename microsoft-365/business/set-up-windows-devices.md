---
title: Configurar dispositivos con Windows para usuarios de Microsoft 365 Business
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: 'Obtenga información sobre cómo configurar los dispositivos Windows que ejecutan Windows 10 Pro para los usuarios de Microsoft 365 empresa. '
ms.openlocfilehash: 427e1c25b5c6ad52ab280502133a0e2808bb48b1
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42090774"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-users"></a><span data-ttu-id="31360-103">Configurar dispositivos con Windows para usuarios de Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="31360-103">Set up Windows devices for Microsoft 365 Business users</span></span>

## <a name="prerequisites"></a><span data-ttu-id="31360-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="31360-104">Prerequisites</span></span>

<span data-ttu-id="31360-p101">Para poder configurar dispositivos Windows para los usuarios de Microsoft 365 Business, asegúrese de que todos los dispositivos Windows estén ejecutando la versión 1703 de Windows 10 Pro (Creators Update). Windows 10 Pro es un requisito previo para implementar Windows 10 Business, que es un conjunto de servicios en la nube y funciones de administración de dispositivos que funciona como complemento de Windows 10 Pro y, además, proporciona una administración centralizada y controles de seguridad de Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="31360-p101">Before you can set up Windows devices for Microsoft 365 Business users, make sure all the Windows devices are running Windows 10 Pro, version 1703 (Creators Update). Windows 10 Pro is a prerequisite for deploying Windows 10 Business, which is a set of cloud services and device management capabilities that complement Windows 10 Pro and enable the centralized management and security controls of Microsoft 365 Business.</span></span>
  
<span data-ttu-id="31360-107">Si tiene dispositivos Windows que ejecutan Windows 7 Pro, Windows 8 Pro o Windows 8.1 Pro, su suscripción de Microsoft 365 Business le permite hacer una actualización a Windows 10.</span><span class="sxs-lookup"><span data-stu-id="31360-107">If you have Windows devices running Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your Microsoft 365 Business subscription entitles you to a Windows 10 upgrade.</span></span>
  
<span data-ttu-id="31360-108">Para obtener más información sobre cómo actualizar los dispositivos Windows a Windows 10 Pro Creators Update, siga los pasos indicados en este tema: [Actualizar dispositivos Windows a Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md)</span><span class="sxs-lookup"><span data-stu-id="31360-108">For more information on how to upgrade Windows devices to Windows 10 Pro Creators Update, follow the steps in this topic: [Upgrade Windows devices to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>
  
<span data-ttu-id="31360-109">Consulte [comprobar que el dispositivo está conectado a Azure ad](#verify-the-device-is-connected-to-azure-ad) para comprobar que tiene la actualización o para asegurarse de que la actualización ha funcionado.</span><span class="sxs-lookup"><span data-stu-id="31360-109">See [Verify the device is connected to Azure AD](#verify-the-device-is-connected-to-azure-ad) to verify you have the upgrade, or to make sure the upgrade worked.</span></span>

<span data-ttu-id="31360-110">Vea un breve vídeo sobre cómo conectar Windows a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="31360-110">Watch a short video about connecting Windows to Microsoft 365.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3yXh3] 

<span data-ttu-id="31360-111">Si este vídeo le ha sido de ayuda, consulte la [serie completa de aprendizaje para las pequeñas empresas y las novedades de Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span><span class="sxs-lookup"><span data-stu-id="31360-111">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a><span data-ttu-id="31360-112">Unir dispositivos Windows 10 en la cuenta de Azure AD de una organización</span><span class="sxs-lookup"><span data-stu-id="31360-112">Join Windows 10 devices to your organization's Azure AD</span></span>

<span data-ttu-id="31360-113">Cuando todos los dispositivos Windows de su organización se hayan actualizado a Windows 10 Pro Creators Update o ya ejecuten la actualización de Windows 10 Pro Creators, puede unir estos dispositivos al Azure Active Directory de la organización.</span><span class="sxs-lookup"><span data-stu-id="31360-113">When all Windows devices in your organization have either been upgraded to Windows 10 Pro Creators Update or are already running Windows 10 Pro Creators Update, you can join these devices to your organization's Azure Active Directory.</span></span> <span data-ttu-id="31360-114">Una vez que se hayan unido los dispositivos, se actualizarán automáticamente a Windows 10 Business, que forma parte de su suscripción de Microsoft 365 empresa.</span><span class="sxs-lookup"><span data-stu-id="31360-114">Once the devices are joined, they'll be automatically upgraded to Windows 10 Business, which is part of your Microsoft 365 Business subscription.</span></span>
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a><span data-ttu-id="31360-115">Dispositivos Windows 10 Pro nuevos o actualizados recientemente</span><span class="sxs-lookup"><span data-stu-id="31360-115">For a brand new, or newly upgraded, Windows 10 Pro device</span></span>

<span data-ttu-id="31360-116">En el caso de los dispositivos nuevos que ejecuten Windows 10 Pro Creators Update, o en el de los dispositivos que se hayan actualizado a dicho producto pero no hayan pasado por el proceso de configuración de dispositivos Windows 10, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="31360-116">For a brand new device running Windows 10 Pro Creators Update, or for a device that was upgraded to Windows 10 Pro Creators Update but has not gone through Windows 10 device setup, follow these steps.</span></span>
  
1. <span data-ttu-id="31360-117">Siga el proceso de configuración de dispositivos Windows 10 hasta que llegue a la página **¿Cómo quiere realizar la configuración?**.</span><span class="sxs-lookup"><span data-stu-id="31360-117">Go through Windows 10 device setup until you get to the **How would you like to set up?** page.</span></span> 
    
    ![On the How would you like to set up page, choose Set up for an organization](../media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. <span data-ttu-id="31360-119">Elija **Configurar para una organización** y, después, escriba el nombre de usuario y contraseña de Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="31360-119">Here, choose **Set up for an organization** and then enter your username and password for Microsoft 365 Business.</span></span> 
    
3. <span data-ttu-id="31360-120">Finalice la configuración del dispositivo Windows 10.</span><span class="sxs-lookup"><span data-stu-id="31360-120">Finish Windows 10 device setup.</span></span>
    
   <span data-ttu-id="31360-p103">Una vez que haya terminado, el usuario se conectará a la cuenta de Azure AD de su organización. Para asegurarse de que la configuración es correcta, consulte [Comprobar que un dispositivo está conectado a Azure AD](#verify-the-device-is-connected-to-azure-ad).</span><span class="sxs-lookup"><span data-stu-id="31360-p103">Once you're done, the user will be connected to your organization's Azure AD. See [Verify the device is connected to Azure AD](#verify-the-device-is-connected-to-azure-ad) to make sure.</span></span> 
  
### <a name="for-a-device-already-set-up-and-running-windows-10-pro"></a><span data-ttu-id="31360-123">Dispositivos ya configurados con Windows 10 Pro</span><span class="sxs-lookup"><span data-stu-id="31360-123">For a device already set up and running Windows 10 Pro</span></span>

 <span data-ttu-id="31360-124">**Conectar usuarios a Azure AD:**</span><span class="sxs-lookup"><span data-stu-id="31360-124">**Connect users to Azure AD:**</span></span>
  
1. <span data-ttu-id="31360-125">En el equipo Windows del usuario, que está ejecutando Windows 10 Pro, versión 1703 (Creators Update) (vea [Requisitos previos](pre-requisites-for-data-protection.md)), haga clic en el logotipo de Windows y, después, en el icono Configuración.</span><span class="sxs-lookup"><span data-stu-id="31360-125">In your user's Windows PC, that is running Windows 10 Pro, version 1703 (Creators Update) (see [pre-requisites](pre-requisites-for-data-protection.md)), click the Windows logo, and then the Settings icon.</span></span>
  
   ![In the Start menu, click Windows Settings icon](../media/74e1ce9a-1554-4761-beb9-330b176e9b9d.png)
  
2. <span data-ttu-id="31360-127">En **Configuración**, vaya a **Cuentas**.</span><span class="sxs-lookup"><span data-stu-id="31360-127">In **Settings**, go to **Accounts**.</span></span>
  
   ![In Windows Settings, go to Accounts](../media/472fd688-d111-4788-9fbb-56a00fbdc24d.png)
  
3. <span data-ttu-id="31360-129">En la página **Tu información**, haga clic en **Obtener acceso a trabajo o escuela** \> **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="31360-129">On **Your info** page, click **Access work or school** \> **Connect**.</span></span>
  
   ![Choose Connect under Access work or school](../media/af3a4e3f-f9b9-4969-b3e2-4ef99308090c.png)
  
4. <span data-ttu-id="31360-131">En el cuadro de diálogo **Configurar una cuenta de trabajo o escuela**, en **Acciones alternativas**, elija **Unir este dispositivo a Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="31360-131">On the **Set up a work or school account** dialog, under **Alternate actions**, choose **Join this device to Azure Active Directory**.</span></span>
  
   ![Click Join this device to Azure Active Directory](../media/fb709a1b-05a9-4750-9cb9-e097f4412cba.png)
  
5. <span data-ttu-id="31360-133">En la página **Vamos a iniciar sesión**, escriba su cuenta profesional o educativa \> **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="31360-133">On the **Let's get you signed in** page, enter your work or school account \> **Next**.</span></span>
  
   <span data-ttu-id="31360-134">En la página **Escribir contraseña**, escriba la contraseña \> **Iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="31360-134">On the **Enter password** page, enter your password \> **Sign in**.</span></span>
  
   ![Enter your work or school email on the Let's get you signed in page](../media/f70eb148-b1d2-4ba3-be38-7317eaf0321a.png)
  
6. <span data-ttu-id="31360-136">En la página Asegúrese de que **es su organización** , compruebe que la información es correcta y haga clic en **unirse**.</span><span class="sxs-lookup"><span data-stu-id="31360-136">On the **Make sure this is your organization** page, verify that the information is correct, and click **Join**.</span></span>
  
   <span data-ttu-id="31360-p104">En la página **Listo**, haga clic en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="31360-p104">On the **You're all set!** page, click **Done**.</span></span>
  
   ![On the Make sure this is your organization screen, click Join](../media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
<span data-ttu-id="31360-140">Si ha cargado archivos a OneDrive para la Empresa, vuelva a sincronizarlos.</span><span class="sxs-lookup"><span data-stu-id="31360-140">If you uploaded files to OneDrive for Business, sync them back down.</span></span> <span data-ttu-id="31360-141">Si ha usado una herramienta de terceros para migrar perfiles y archivos, sincronice también los archivos con el nuevo perfil.</span><span class="sxs-lookup"><span data-stu-id="31360-141">If you used a third-party tool to migrate profile and files, also sync those to the new profile.</span></span>
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a><span data-ttu-id="31360-142">Comprobar que un dispositivo está conectado a Azure AD</span><span class="sxs-lookup"><span data-stu-id="31360-142">Verify the device is connected to Azure AD</span></span>

<span data-ttu-id="31360-p106">Para comprobar el estado de sincronización, en la página **Obtener acceso a trabajo o escuela** de **Configuración**, haga clic en el área **Conectado a** _ \<organization name\> _ para mostrar los botones **Información** y **Desconectar**. Haga clic en **Información** para obtener el estado de sincronización.</span><span class="sxs-lookup"><span data-stu-id="31360-p106">To verify your sync status, on the **Access work or school** page in **Settings**, click in the **Connected to** _ \<organization name\> _ area to expose the buttons **Info** and **Disconnect**. Click on **Info** to get your synchronization status.</span></span> 
  
<span data-ttu-id="31360-145">En la página Estado de sincronización, haga clic en Sincronizar para recibir las directivas de administración de dispositivos móviles más recientes en el equipo.</span><span class="sxs-lookup"><span data-stu-id="31360-145">On the Sync status page, click Sync to get the latest mobile device management policies onto the PC.</span></span>
  
<span data-ttu-id="31360-146">Para empezar a usar la cuenta de Microsoft 365 Business, vaya al botón **Inicio** de Windows, haga clic con el botón secundario en la imagen de cuenta actual y, a continuación, **cambie de cuenta**.</span><span class="sxs-lookup"><span data-stu-id="31360-146">To start using the Microsoft 365 Business account, go to the Windows **Start** button, right-click your current account picture, and then **Switch account**.</span></span> <span data-ttu-id="31360-147">Inicie sesión con el correo electrónico y la contraseña de la organización.</span><span class="sxs-lookup"><span data-stu-id="31360-147">Sign in by using your organization email and password.</span></span>
  
![Click Info button to view synchronization status](../media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-device-is-upgraded-to-windows-10-business"></a><span data-ttu-id="31360-149">Comprobar que un dispositivo está actualizado a Windows 10 Business</span><span class="sxs-lookup"><span data-stu-id="31360-149">Verify the device is upgraded to Windows 10 Business</span></span>

<span data-ttu-id="31360-150">Compruebe que los dispositivos Windows 10 unidos a Azure AD se hayan actualizado a Windows 10 Business como parte de una suscripción a Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="31360-150">Verify that your Azure AD joined Windows 10 devices were upgraded to Windows 10 Business as part of your Microsoft 365 Business subscription.</span></span>
  
1. <span data-ttu-id="31360-151">Vaya a **Configuración** \> **Sistema** \> **Acerca de**.</span><span class="sxs-lookup"><span data-stu-id="31360-151">Go to **Settings** \> **System** \> **About**.</span></span>
    
2. <span data-ttu-id="31360-152">Confirme que la **Edición** es **Windows 10 Business**.</span><span class="sxs-lookup"><span data-stu-id="31360-152">Confirm that the **Edition** shows **Windows 10 Business**.</span></span>
    
    ![Verify that Windows edition is Windows 10 Business.](../media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a><span data-ttu-id="31360-154">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="31360-154">Next steps</span></span>

<span data-ttu-id="31360-155">Para configurar dispositivos móviles, vea [Configurar dispositivos móviles para los usuarios de Microsoft 365 Business](set-up-mobile-devices.md). Para establecer las directivas de protección de dispositivos o de aplicaciones, consulte [Administrar Microsoft 365 Business](manage.md).</span><span class="sxs-lookup"><span data-stu-id="31360-155">To set up your mobile devices, see [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md), To set device protection or app protection policies, see [Manage Microsoft 365 Business](manage.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="31360-156">Consulte también</span><span class="sxs-lookup"><span data-stu-id="31360-156">See also</span></span>

[<span data-ttu-id="31360-157">Vídeos de aprendizaje de Microsoft 365 Empresa</span><span class="sxs-lookup"><span data-stu-id="31360-157">Microsoft 365 Business training videos</span></span>](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
