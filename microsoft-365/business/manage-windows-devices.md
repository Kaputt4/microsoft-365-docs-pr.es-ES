---
title: Habilitar dispositivos de Windows 10 unido a un dominio administrado por Microsoft 365 empresarial
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Obtenga información sobre cómo habilitar Microsoft 365 proteger AD local se unió a dispositivos de Windows 10.
ms.openlocfilehash: 6e66a2c5417c9037232c1ada654d4cac3c520607
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871308"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="d8d55-103">Habilitar dispositivos de Windows 10 unido a un dominio administrado por Microsoft 365 empresarial</span><span class="sxs-lookup"><span data-stu-id="d8d55-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="d8d55-p101">Si su organización usa Windows Server Active Directory local, puede configurar Microsoft 365 empresarial para proteger los dispositivos de Windows 10, al tiempo que mantiene el acceso a los recursos locales que requieren autenticación local. Puede configurar esto mediante la primera sincronización de Active Directory con Azure Active Directory, seguido de registrar los dispositivos de Windows 10 con Azure AD y realizar una inscripción para administración de dispositivos móviles por Microsoft 365 empresarial.</span><span class="sxs-lookup"><span data-stu-id="d8d55-p101">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication. You can set this up by first synchronizing your Active Directory with Azure Active Directory, followed by registering the Windows 10 devices with Azure AD and enrolling them for mobile device management by Microsoft 365 Business.</span></span>
  
## <a name="set-up-domain-joined-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="d8d55-106">Configurar dispositivos unido a un dominio para ser administrado por Microsoft 365 empresarial</span><span class="sxs-lookup"><span data-stu-id="d8d55-106">Set up domain-joined devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="d8d55-p102">Para configurar los dispositivos unido a un dominio de la organización para sacar partido de las funciones proporcionadas por Azure Active Directory además de Active Directory local, puede implementar **híbrida Azure AD se unió a dispositivos**. Estos son los dispositivos que se unen tanto a su Active Directory local y Azure Active Directory. Híbrido Azure AD se unió a dispositivos estén protegidos y administrados por Microsoft 365 Business..</span><span class="sxs-lookup"><span data-stu-id="d8d55-p102">To set up your organization's domain-joined devices to benefit from the capabilities provided by Azure Active Directory in addition to on-premises Active Directory, you can implement **Hybrid Azure AD joined devices**. These are devices that are joined both to your on-premises Active Directory and your Azure Active Directory. Hybrid Azure AD joined devices can be protected and managed by Microsoft 365 Business..</span></span> 
  
<span data-ttu-id="d8d55-110">Complete los pasos siguientes para hacer que los dispositivos de Windows 10 híbrida Azure AD Unido y administrados por Microsoft 365 empresarial.</span><span class="sxs-lookup"><span data-stu-id="d8d55-110">Complete the steps below to make your Windows 10 devices Hybrid Azure AD joined and managed by Microsoft 365 Business.</span></span>
  
1. <span data-ttu-id="d8d55-111">Para sincronizar los usuarios, grupos y contactos de Active Directory local en Azure Active Directory, ejecute el Asistente para la sincronización de Active Directory y Azure Active Directory Connect tal como se describe en [Configurar la sincronización de Active directory para Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span><span class="sxs-lookup"><span data-stu-id="d8d55-111">To synchronize your users, groups and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure Active Directory Connect as described in [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d8d55-112">Los pasos son exactamente los mismos para la empresa de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d8d55-112">The steps are exactly the same for Microsoft 365 Business.</span></span> 
  
2. <span data-ttu-id="d8d55-113">Antes de completar el paso 3 para habilitar los dispositivos de Windows 10 para ser híbrida se unió Azure AD, debe asegurarse de que cumple los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="d8d55-113">Before you complete step 3 to enable Windows 10 devices to be Hybrid Azure AD joined, you need to make sure that you meet the following prerequisites:</span></span>
    
   - <span data-ttu-id="d8d55-114">Está ejecutando la versión más reciente de Azure AD conectarse.</span><span class="sxs-lookup"><span data-stu-id="d8d55-114">You are running the latest version of Azure AD connect.</span></span>
    
   - <span data-ttu-id="d8d55-p103">Conectar Azure AD se ha sincronizado con todos los objetos de equipo de los dispositivos que desea que sean híbrida se unió Azure AD. Si los objetos de equipo pertenecen a determinadas unidades organizativas (OU), a continuación, asegúrese de que estas unidades organizativas se establecen para la sincronización en Azure AD conectarse así como.</span><span class="sxs-lookup"><span data-stu-id="d8d55-p103">Azure AD connect has synchronized all the computer objects of the devices you want to be hybrid Azure AD joined. If the computer objects belong to specific organizational units (OU), then make sure these OUs are set for synchronization in Azure AD connect as well.</span></span>
    
3. <span data-ttu-id="d8d55-117">Registre los dispositivos de Windows 10 unido a un dominio existentes para ser híbrida se unió Azure AD y les inscribirse en administración de dispositivos móviles mediante Intune (Microsoft 365 Business):</span><span class="sxs-lookup"><span data-stu-id="d8d55-117">Register existing domain-joined Windows 10 devices to be hybrid Azure AD Joined and enroll them for mobile device management by Intune (Microsoft 365 Business):</span></span>
    
4. <span data-ttu-id="d8d55-p104">Siga las instrucciones paso a paso [cómo configurar los dispositivos de Azure Active Directory se unió a híbrida](https://go.microsoft.com/fwlink/p/?linkid=872870). Esto permitirá que la sincronización de Active Directory local se unió a equipos Windows 10 y hacerlas está preparada para la nube.</span><span class="sxs-lookup"><span data-stu-id="d8d55-p104">Follow the step by step instructions in [How to configure hybrid Azure Active Directory joined devices](https://go.microsoft.com/fwlink/p/?linkid=872870). This will enable the synchronization of your on-premises Active Directory joined Windows 10 computers and make them cloud ready.</span></span>
    
5. <span data-ttu-id="d8d55-p105">Para poder inscribirse un dispositivo de Windows 10 para administración de dispositivos móviles, vea [inscribirse en un dispositivo de Windows 10 con Intune mediante el uso de una directiva de grupo](https://go.microsoft.com/fwlink/p/?linkid=872871) para obtener instrucciones. Puede establecer la directiva de grupo en un equipo local nivel o para las operaciones masivas, puede crear esta configuración de directiva de grupo en el servidor de controlador de dominio.</span><span class="sxs-lookup"><span data-stu-id="d8d55-p105">In order to enroll a Windows 10 device for mobile device management, see [Enroll a Windows 10 device with Intune by using a Group Policy](https://go.microsoft.com/fwlink/p/?linkid=872871) for instructions. You can set the Group Policy at a local computer level or for bulk operations, you can create this group policy setting on your domain controller server.</span></span> 
    

