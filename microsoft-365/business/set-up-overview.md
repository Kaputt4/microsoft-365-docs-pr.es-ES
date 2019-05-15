---
title: Información general sobre la configuración
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Información general sobre la configuración de los pasos para Microsoft 365 Business.
ms.openlocfilehash: efa4d352b00ebba0cb9754c93e773d1ddaef19df
ms.sourcegitcommit: 720881c1a9c5f708e1b4adf7e5ea4ff8da48ea99
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "33970457"
---
# <a name="overview-of-setup"></a><span data-ttu-id="63260-103">Información general sobre el programa de instalación</span><span class="sxs-lookup"><span data-stu-id="63260-103">Overview of setup</span></span>

<span data-ttu-id="63260-104">La mayoría de los pasos de configuración pueden realizarse en el Asistente de configuración, pero también se incluyen otras opciones.</span><span class="sxs-lookup"><span data-stu-id="63260-104">Most of the set up steps can be done in the setup wizard, but the other options are also listed.</span></span>


## <a name="step-1-add-your-domain-and-users"></a><span data-ttu-id="63260-105">Paso 1: agregar el dominio y los usuarios</span><span class="sxs-lookup"><span data-stu-id="63260-105">Step 1: Add your domain and users</span></span>

   - <span data-ttu-id="63260-106">**[Agregar el dominio](set-up.md#add-your-domain-to-personalize-sign-in)** (si ha comprado su dominio durante el [Inicio de sesión](sign-up.md), este paso ya se ha realizado).</span><span class="sxs-lookup"><span data-stu-id="63260-106">**[Add your domain](set-up.md#add-your-domain-to-personalize-sign-in)** (if you bought your domain during [sign up](sign-up.md), this step is already done.)</span></span>

    - <span data-ttu-id="63260-107">**Agregar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="63260-107">**Add users**.</span></span> <span data-ttu-id="63260-108">Puede hacerlo de las tres maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="63260-108">You can do this in any of the three ways:</span></span>
        - <span data-ttu-id="63260-109">En el [Asistente](set-up.md#add-users-in-the-wizard).</span><span class="sxs-lookup"><span data-stu-id="63260-109">In the [wizard](set-up.md#add-users-in-the-wizard).</span></span>
        - <span data-ttu-id="63260-110">Use la sincronización de directorios para [Agregar usuarios con Azure ad Connect](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) si tiene un Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="63260-110">Use directory synchronization to [add users by using Azure AD Connect](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) if you have an on-premises Active directory.</span></span>
        - <span data-ttu-id="63260-111">También puede [Agregar usuarios más adelante](add-users-m365b.md) en el centro de administración.</span><span class="sxs-lookup"><span data-stu-id="63260-111">You can also [add users later](add-users-m365b.md) in the admin center.</span></span>
## <a name="step-2-set-up-security-policies-and-configure-devices"></a><span data-ttu-id="63260-112">Paso 2: configurar directivas de seguridad y configurar dispositivos</span><span class="sxs-lookup"><span data-stu-id="63260-112">Step 2: Set up security policies and configure devices</span></span> 

  - <span data-ttu-id="63260-113">Use el [Asistente de configuración](set-up.md#set-up-security-policies-and-device-configurations) para configurar las directivas de dispositivo y seguridad.</span><span class="sxs-lookup"><span data-stu-id="63260-113">Use the [Setup wizard](set-up.md#set-up-security-policies-and-device-configurations) to configure device and security policies.</span></span> 
  - <span data-ttu-id="63260-114">También puede agregar más o editarlos más adelante en el [centro de administración](view-policies-and-devices.md) y en el [portal](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal)de Intune.</span><span class="sxs-lookup"><span data-stu-id="63260-114">You can also add more or edit them later in the [admin center](view-policies-and-devices.md) and in the [Intune portal](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).</span></span>
  - <span data-ttu-id="63260-115">Además de la configuración de seguridad del asistente de configuración, puede aumentar la seguridad si agrega las siguientes opciones de configuración:</span><span class="sxs-lookup"><span data-stu-id="63260-115">In addition to the security settings in the setup wizard, you can increase your security by adding the following settings:</span></span>

      - <span data-ttu-id="63260-116">**Protección contra malware de correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="63260-116">**Email malware protection**</span></span>
      - <span data-ttu-id="63260-117">**Vínculos seguros de la protección contra amenazas avanzada (ATP)**</span><span class="sxs-lookup"><span data-stu-id="63260-117">**Advanced Threat Protection (ATP) Safe links**</span></span>
      - <span data-ttu-id="63260-118">**Datos adjuntos seguros ATP**</span><span class="sxs-lookup"><span data-stu-id="63260-118">**ATP Safe Attachments**</span></span>
      - <span data-ttu-id="63260-119">**Contra la suplantación de identidad ATP**</span><span class="sxs-lookup"><span data-stu-id="63260-119">**ATP anti-phishing**</span></span>
      - <span data-ttu-id="63260-120">**Archivado de Exchange Online**</span><span class="sxs-lookup"><span data-stu-id="63260-120">**Exchange Online Archiving**</span></span>
      - <span data-ttu-id="63260-121">**Data Loss Prevention (DLP)**</span><span class="sxs-lookup"><span data-stu-id="63260-121">**Data Loss Prevention (DLP)**</span></span>
      - <span data-ttu-id="63260-122">**Azure Information Protection (Plan1**)</span><span class="sxs-lookup"><span data-stu-id="63260-122">**Azure Information Protection (Plan1**)</span></span>

          <span data-ttu-id="63260-123">Para empezar, vea [configurar las directivas de seguridad avanzada](set-up-advanced-security.md).</span><span class="sxs-lookup"><span data-stu-id="63260-123">To get started see, [set up advanced security policies](set-up-advanced-security.md).</span></span>

        <span data-ttu-id="63260-124">Consulte también [las 10 formas principales de proteger su empresa de Microsoft 365](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) para obtener una guía de los procedimientos de seguridad recomendados.</span><span class="sxs-lookup"><span data-stu-id="63260-124">See also [top 10 ways to secure your Microsoft 365 Business](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) for a roadmap of best security practices.</span></span>

## <a name="step-3-set-up-and-manage-windows-10-devices"></a><span data-ttu-id="63260-125">Paso 3: configurar y administrar dispositivos con Windows 10</span><span class="sxs-lookup"><span data-stu-id="63260-125">Step 3: Set up and manage Windows 10 devices</span></span>

   <span data-ttu-id="63260-126">Cuando se une a un dispositivo de Windows 10 a Azure AD, se le aplican las directivas que configuró en el [paso 2](#step-2-set-up-security-policies-and-configure-devices) .</span><span class="sxs-lookup"><span data-stu-id="63260-126">When you join a Windows 10 device to Azure AD, the policies you set up in [Step 2](#step-2-set-up-security-policies-and-configure-devices) get applied to it.</span></span>

   - <span data-ttu-id="63260-127">Windows 10 Pro es un [requisito](pre-requisites-for-data-protection.md) previo para Microsoft 365 Business, pero si tiene Windows 7 Pro, Windows 8 Pro o Windows 8,1 Pro, su suscripción le da derecho a una [actualización a Windows 10 Pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).</span><span class="sxs-lookup"><span data-stu-id="63260-127">Windows 10 Pro is a [pre-requisite](pre-requisites-for-data-protection.md) for Microsoft 365 Business, but if you have Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your subscription entitles you to an [upgrade to  Windows 10 Pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).</span></span>
    - <span data-ttu-id="63260-128">Use el [Asistente](set-up.md#set-up-security-policies-and-device-configurations) para la instalación para configurar directivas para dispositivos con Windows 10.</span><span class="sxs-lookup"><span data-stu-id="63260-128">Use the [setup wizard](set-up.md#set-up-security-policies-and-device-configurations) to configure policies for Windows 10 devices.</span></span>

## <a name="stes-4-install-office-365-business"></a><span data-ttu-id="63260-129">Stes 4: instalar Office 365 Business</span><span class="sxs-lookup"><span data-stu-id="63260-129">Stes 4: Install Office 365 Business</span></span>
- <span data-ttu-id="63260-130">Puede instalar Office automáticamente en los dispositivos Windows mediante el Asistente de [configuración](set-up.md#deploy-office-365-client-apps).</span><span class="sxs-lookup"><span data-stu-id="63260-130">You can automatically install Office in the Windows devices by using the [setup wizard](set-up.md#deploy-office-365-client-apps).</span></span>
- <span data-ttu-id="63260-131">[Instalar Office](auto-install-or-uninstall-office.md) automáticamente desde el centro de administración.</span><span class="sxs-lookup"><span data-stu-id="63260-131">Automatically [install Office](auto-install-or-uninstall-office.md) from the admin center.</span></span>
- <span data-ttu-id="63260-132">Permita que los usuarios [instalen aplicaciones de Office](https://docs.microsoft.com/office365/admin/setup/install-applications) para Windows y dispositivos.</span><span class="sxs-lookup"><span data-stu-id="63260-132">Let users [install Office apps](https://docs.microsoft.com/office365/admin/setup/install-applications) for Windows and devices.</span></span>
     
## <a name="advanced"></a><span data-ttu-id="63260-133">Avanzadas</span><span class="sxs-lookup"><span data-stu-id="63260-133">Advanced</span></span>
- <span data-ttu-id="63260-134">**Usar AutoPilot para configurar nuevos dispositivos**</span><span class="sxs-lookup"><span data-stu-id="63260-134">**Use Autopilot to set up new devices**</span></span>
            
     <span data-ttu-id="63260-135">Puede usar [Windows AutoPilot](add-autopilot-devices-and-profile.md) para preconfigurar automáticamente los **nuevos** dispositivos Windows 10 para un usuario, pero podría ser más fácil obtener un [asociado](https://www.microsoft.com/solution-providers/search) que lo haga por usted.</span><span class="sxs-lookup"><span data-stu-id="63260-135">You can use [Windows Autopilot](add-autopilot-devices-and-profile.md) to automatically pre-configure **new** Windows 10 devices for a user, but it might be easier to get a [partner](https://www.microsoft.com/solution-providers/search) who can do this for you.</span></span> <span data-ttu-id="63260-136">También puede ir a [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) y solicitar a un experto en la tecnología de la nube que configure los nuevos dispositivos que compre para usted.</span><span class="sxs-lookup"><span data-stu-id="63260-136">You can also go to [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) and ask a cloud technology expert set up new devices you purchase for you.</span></span>

- <span data-ttu-id="63260-137">**Acceso a recursos locales**</span><span class="sxs-lookup"><span data-stu-id="63260-137">**Access on-premises resources**</span></span>

     - <span data-ttu-id="63260-138">Si su organización usa Windows Server Active Directory local, puede configurar Microsoft 365 Business para proteger sus dispositivos con Windows 10 y mantener al mismo tiempo el acceso a los recursos locales que requieren autenticación local.</span><span class="sxs-lookup"><span data-stu-id="63260-138">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="63260-139">Siga los pasos descritos en [enable Domain-joined Domain-Windows 10 Devices to be Managed Microsoft 365 Business](manage-windows-devices.md) to Configure this.</span><span class="sxs-lookup"><span data-stu-id="63260-139">Follow the steps in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business](manage-windows-devices.md) to set this up.</span></span> <span data-ttu-id="63260-140">Este es el método preferido y los dispositivos en este estado se denominan dispositivos híbridos Unidos de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="63260-140">This is the preferred method and devices in this state are called Hybrid Azure AD joined devices.</span></span>

    - <span data-ttu-id="63260-141">Si su empresa tiene un Active Directory local que contiene algunos recursos locales (como impresoras y recursos compartidos de archivos), puede dar acceso a estos recursos a los dispositivos de Azure AD siguiendo los pasos que se indican a continuación: [acceso a recursos locales desde un Dispositivo unido a Azure AD en Microsoft 365 Business](access-resources.md).</span><span class="sxs-lookup"><span data-stu-id="63260-141">If your business has a local Active Directory that contains some on-premises resources (such as file shares and printers) , you can give your Azure AD-joined devices access to these resources by following the steps here: [Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business](access-resources.md).</span></span>

  