---
title: Habilitar los dispositivos Windows 10 Unidos a un dominio para que los administre Microsoft 365 Business
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
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Obtenga información sobre cómo habilitar Microsoft 365 para proteger dispositivos locales Unidos a Windows 10.
ms.openlocfilehash: af0e78ef6e79bfd612b11a16538e7afcd377ffb0
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "34071558"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="b2b89-103">Habilitar los dispositivos Windows 10 Unidos a un dominio para que los administre Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="b2b89-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="b2b89-104">Si su organización usa Windows Server Active Directory local, puede configurar Microsoft 365 Business para proteger sus dispositivos con Windows 10 y mantener al mismo tiempo el acceso a los recursos locales que requieren autenticación local.</span><span class="sxs-lookup"><span data-stu-id="b2b89-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="b2b89-105">Para configurar esto primero, sincronice Active Directory con Azure Active Directory y, a continuación, registre los dispositivos Windows 10 con Azure AD y Inscríbase para la administración de dispositivos móviles en Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="b2b89-105">You can set this up by first synchronizing your Active Directory with Azure Active Directory, followed by registering the Windows 10 devices with Azure AD and enrolling them for mobile device management by Microsoft 365 Business.</span></span>
  
## <a name="set-up-domain-joined-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="b2b89-106">Configurar dispositivos Unidos a un dominio para que los administre Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="b2b89-106">Set up domain-joined devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="b2b89-107">Para configurar los dispositivos Unidos a un dominio de su organización con el fin de beneficiarse de las funciones que ofrece Azure Active Directory además de Active Directory local, puede implementar **dispositivos híbridos de Azure ad híbridos**.</span><span class="sxs-lookup"><span data-stu-id="b2b89-107">To set up your organization's domain-joined devices to benefit from the capabilities provided by Azure Active Directory in addition to on-premises Active Directory, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="b2b89-108">Se trata de dispositivos que se unen a la implementación local de Active Directory y a Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b2b89-108">These are devices that are joined both to your on-premises Active Directory and your Azure Active Directory.</span></span> <span data-ttu-id="b2b89-109">Microsoft 365 Business puede proteger y administrar los dispositivos de Azure AD Unidos híbridos.</span><span class="sxs-lookup"><span data-stu-id="b2b89-109">Hybrid Azure AD joined devices can be protected and managed by Microsoft 365 Business.</span></span> 
  
<span data-ttu-id="b2b89-110">Complete los pasos siguientes para que los dispositivos con Windows 10 Hybrid Azure AD se unan y administren con Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="b2b89-110">Complete the steps below to make your Windows 10 devices Hybrid Azure AD joined and managed by Microsoft 365 Business.</span></span>
  
1. <span data-ttu-id="b2b89-111">Para sincronizar los usuarios, los grupos y los contactos de Active Directory local a Azure Active Directory, ejecute el Asistente para sincronización de directorios y Azure Active Directory Connect como se describe en [configurar la sincronización de directorios para Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span><span class="sxs-lookup"><span data-stu-id="b2b89-111">To synchronize your users, groups and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure Active Directory Connect as described in [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b2b89-112">Los pasos son exactamente iguales para Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="b2b89-112">The steps are exactly the same for Microsoft 365 Business.</span></span> 
  
2. <span data-ttu-id="b2b89-113">Antes de completar el paso 3 para habilitar los dispositivos Windows 10 para que sean Unidos a Azure AD híbrido, debe asegurarse de que cumple los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="b2b89-113">Before you complete step 3 to enable Windows 10 devices to be Hybrid Azure AD joined, you need to make sure that you meet the following prerequisites:</span></span>

   - <span data-ttu-id="b2b89-114">Está ejecutando la última versión de Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="b2b89-114">You are running the latest version of Azure AD connect.</span></span>

   - <span data-ttu-id="b2b89-115">Azure AD Connect ha sincronizado todos los objetos de equipo de los dispositivos que desea que sean Unidos a Azure AD híbrido.</span><span class="sxs-lookup"><span data-stu-id="b2b89-115">Azure AD connect has synchronized all the computer objects of the devices you want to be hybrid Azure AD joined.</span></span> <span data-ttu-id="b2b89-116">Si los objetos de equipo pertenecen a unidades organizativas específicas (OU), asegúrese de que estas ou estén configuradas para la sincronización en Azure AD Connect también.</span><span class="sxs-lookup"><span data-stu-id="b2b89-116">If the computer objects belong to specific organizational units (OU), then make sure these OUs are set for synchronization in Azure AD connect as well.</span></span>
    
3. <span data-ttu-id="b2b89-117">Registrar los dispositivos existentes de Windows 10 Unidos a un dominio para que estén Unidos a Azure AD híbridos e inscribirlos para la administración de dispositivos móviles mediante Intune (Microsoft 365 Business):</span><span class="sxs-lookup"><span data-stu-id="b2b89-117">Register existing domain-joined Windows 10 devices to be hybrid Azure AD Joined and enroll them for mobile device management by Intune (Microsoft 365 Business):</span></span>
    
4. <span data-ttu-id="b2b89-118">Siga las instrucciones paso a paso sobre [Cómo configurar los dispositivos Unidos de Azure Active Directory híbridos](https://go.microsoft.com/fwlink/p/?linkid=872870).</span><span class="sxs-lookup"><span data-stu-id="b2b89-118">Follow the step by step instructions in [How to configure hybrid Azure Active Directory joined devices](https://go.microsoft.com/fwlink/p/?linkid=872870).</span></span> <span data-ttu-id="b2b89-119">Esto permitirá la sincronización de los equipos Windows 10 locales Unidos a través de Active Directory y los pondrá a disposición en la nube.</span><span class="sxs-lookup"><span data-stu-id="b2b89-119">This will enable the synchronization of your on-premises Active Directory joined Windows 10 computers and make them cloud ready.</span></span>
    
5. <span data-ttu-id="b2b89-120">Para inscribir un dispositivo con Windows 10 para la administración de dispositivos móviles, consulte [inscribir un dispositivo con Windows 10 con Intune mediante una directiva de grupo](https://go.microsoft.com/fwlink/p/?linkid=872871) para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="b2b89-120">In order to enroll a Windows 10 device for mobile device management, see [Enroll a Windows 10 device with Intune by using a Group Policy](https://go.microsoft.com/fwlink/p/?linkid=872871) for instructions.</span></span> <span data-ttu-id="b2b89-121">Puede establecer la Directiva de grupo en el nivel de equipo local o en operaciones masivas, puede crear esta opción de directiva de grupo en el servidor del controlador de dominio.</span><span class="sxs-lookup"><span data-stu-id="b2b89-121">You can set the Group Policy at a local computer level or for bulk operations, you can create this group policy setting on your domain controller server.</span></span>