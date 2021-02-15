---
title: Integración de Azure con Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-identity-device-management
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: a5efce5d-9c9c-4190-b61b-fd273c1d425f
description: Integre Microsoft 365 con Azure AD si desea sincronizar la contraseña o el inicio de sesión único con su entorno local.
ms.openlocfilehash: b1f20ebc692421ed6df0d6f7c31a4d80347133e3
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384745"
---
# <a name="azure-integration-with-microsoft-365"></a><span data-ttu-id="7f79c-103">Integración de Azure con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7f79c-103">Azure integration with Microsoft 365</span></span>

<span data-ttu-id="7f79c-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="7f79c-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="7f79c-105">Microsoft 365 usa Azure Active Directory (Azure AD) para administrar identidades de usuario en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="7f79c-105">Microsoft 365 uses Azure Active Directory (Azure AD) to manage user identities behind the scenes.</span></span> <span data-ttu-id="7f79c-106">Su suscripción de Microsoft 365 incluye una suscripción gratuita de Azure AD para que pueda integrar los Servicios de dominio de Active Directory (AD DS) locales para sincronizar las cuentas de usuario y contraseñas o configurar el inicio de sesión único.</span><span class="sxs-lookup"><span data-stu-id="7f79c-106">Your Microsoft 365 subscription includes a free Azure AD subscription so that you can integrate your on-premises Active Directory Domain Services (AD DS) to synchronize user accounts and passwords or set up single sign-on.</span></span> <span data-ttu-id="7f79c-107">También puedes comprar características avanzadas para administrar mejor tus cuentas.</span><span class="sxs-lookup"><span data-stu-id="7f79c-107">You can also purchase advanced features to better manage your accounts.</span></span>
  
<span data-ttu-id="7f79c-108">Azure AD también ofrece otras funciones, como la administración de aplicaciones integradas, que puede usar para ampliar y personalizar las suscripciones de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7f79c-108">Azure AD also offers other functionality, like managing integrated apps, that you can use to extend and customize your Microsoft 365 subscriptions.</span></span>
  
<span data-ttu-id="7f79c-109">Puede usar los asesores de implementación de Azure AD para una experiencia de configuración y configuración guiada en el Centro de administración de Microsoft 365 (debe haber iniciado sesión en Microsoft 365):</span><span class="sxs-lookup"><span data-stu-id="7f79c-109">You can use the Azure AD deployment advisors for a guided setup and configuration experience in the Microsoft 365 admin center (you must be signed in to Microsoft 365):</span></span>

 - [<span data-ttu-id="7f79c-110">Asesor de Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="7f79c-110">Azure AD Connect advisor</span></span>](https://aka.ms/aadconnectpwsync)
 - [<span data-ttu-id="7f79c-111">Asesor de implementación de AD FS</span><span class="sxs-lookup"><span data-stu-id="7f79c-111">AD FS deployment advisor</span></span>](https://aka.ms/adfsguidance)
 - [<span data-ttu-id="7f79c-112">Guía de configuración de Azure AD</span><span class="sxs-lookup"><span data-stu-id="7f79c-112">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a><span data-ttu-id="7f79c-113">Ediciones de Azure AD y administración de identidades de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7f79c-113">Azure AD editions and Microsoft 365 identity management</span></span>

<span data-ttu-id="7f79c-114">Si tiene una suscripción de pago a Microsoft 365, también tiene una suscripción gratuita de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7f79c-114">If you have a paid subscription to Microsoft 365, you also have a free Azure AD subscription.</span></span> <span data-ttu-id="7f79c-115">Puede usar Azure AD para crear y administrar cuentas de usuario y grupo.</span><span class="sxs-lookup"><span data-stu-id="7f79c-115">You can use Azure AD to create and manage user and group accounts.</span></span> <span data-ttu-id="7f79c-116">Para activar esta suscripción, debe completar un registro único.</span><span class="sxs-lookup"><span data-stu-id="7f79c-116">To activate this subscription, you have to complete a one-time registration.</span></span> <span data-ttu-id="7f79c-117">Después, puede acceder a Azure AD desde el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7f79c-117">Afterward, you can access Azure AD from your Microsoft 365 admin center.</span></span> 

<span data-ttu-id="7f79c-118">Para obtener instrucciones para registrar tu suscripción gratuita de Azure AD, consulta usar la suscripción gratuita [de Azure AD.](../compliance/use-your-free-azure-ad-subscription-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="7f79c-118">For instructions to register your free Azure AD subscription, see [use your free Azure AD subscription](../compliance/use-your-free-azure-ad-subscription-in-office-365.md).</span></span> <span data-ttu-id="7f79c-119">No vaya directamente a azure.microsoft.com para registrarse o terminará con una suscripción de prueba o de pago a Microsoft Azure que sea independiente de su suscripción gratuita de Azure AD con Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7f79c-119">Don't go directly to azure.microsoft.com to sign up or you'll end up with a trial or paid subscription to Microsoft Azure that is separate from your free Azure AD subscription with Microsoft 365.</span></span> 
  
<span data-ttu-id="7f79c-120">Con la suscripción gratuita puede sincronizarse con directorios locales, configurar el inicio de sesión único y sincronizarse con muchos software como aplicaciones de servicio, como Salesforce, DropBox y muchos más.</span><span class="sxs-lookup"><span data-stu-id="7f79c-120">With the free subscription you can synchronize with on-premises directories, set up single sign-on, and synchronize with many software as service applications, such as Salesforce, DropBox, and many more.</span></span>
  
<span data-ttu-id="7f79c-121">Si quieres mejorar la funcionalidad de AD DS, la sincronización bidireccional y otras funcionalidades de administración, puedes actualizar tu suscripción gratuita a una suscripción premium de pago.</span><span class="sxs-lookup"><span data-stu-id="7f79c-121">If you want enhanced AD DS functionality, bi-directional synchronization, and other management capabilities, you can upgrade your free subscription to a paid premium subscription.</span></span> <span data-ttu-id="7f79c-122">Para obtener más información, [vea las ediciones de Azure Active Directory.](https://azure.microsoft.com/pricing/details/active-directory/)</span><span class="sxs-lookup"><span data-stu-id="7f79c-122">For the details, see [Azure Active Directory editions](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>
  
<span data-ttu-id="7f79c-123">Para obtener más información acerca de Microsoft 365 y Azure AD, vea modelos de [identidad de Microsoft 365.](about-microsoft-365-identity.md)</span><span class="sxs-lookup"><span data-stu-id="7f79c-123">For more information about Microsoft 365 and Azure AD, see [Microsoft 365 identity models](about-microsoft-365-identity.md).</span></span>
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a><span data-ttu-id="7f79c-124">Ampliar las capacidades de su inquilino de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7f79c-124">Extend the capabilities of your Microsoft 365 tenant</span></span>

|<span data-ttu-id="7f79c-125">**Característica**</span><span class="sxs-lookup"><span data-stu-id="7f79c-125">**Feature**</span></span>|<span data-ttu-id="7f79c-126">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="7f79c-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7f79c-127">Aplicaciones integradas</span><span class="sxs-lookup"><span data-stu-id="7f79c-127">Integrated apps</span></span>  <br/> |<span data-ttu-id="7f79c-128">Puede conceder acceso a aplicaciones individuales a los datos de Microsoft 365, como correo, calendarios, contactos, usuarios, grupos, archivos y carpetas.</span><span class="sxs-lookup"><span data-stu-id="7f79c-128">You can grant individual apps access to your Microsoft 365 data, such as mail, calendars, contacts, users, groups, files, and folders.</span></span> <span data-ttu-id="7f79c-129">También puedes autorizar estas aplicaciones en el nivel de administrador global y hacer que estén disponibles para toda la empresa registrando las aplicaciones en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7f79c-129">You can also authorize these apps at global admin level and make them available to your entire company by registering the apps in Azure AD.</span></span> <span data-ttu-id="7f79c-130">Para obtener más información, vea [Aplicaciones integradas y Azure AD para administradores de Microsoft 365.](integrated-apps-and-azure-ads.md)</span><span class="sxs-lookup"><span data-stu-id="7f79c-130">Formore information, see [Integrated Apps and Azure AD for Microsoft 365 administrators](integrated-apps-and-azure-ads.md).</span></span>  <br/> <span data-ttu-id="7f79c-131">Consulta también [Inicio de sesión único.](https://go.microsoft.com/fwlink/p/?LinkId=698604)</span><span class="sxs-lookup"><span data-stu-id="7f79c-131">Also see [Single sign-on](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span></span>  <br/> |
|<span data-ttu-id="7f79c-132">PowerApps</span><span class="sxs-lookup"><span data-stu-id="7f79c-132">PowerApps</span></span>  <br/> | <span data-ttu-id="7f79c-133">Las aplicaciones power son aplicaciones centradas para dispositivos móviles que pueden conectarse a los orígenes de datos existentes, como listas de SharePoint y otras aplicaciones de datos.</span><span class="sxs-lookup"><span data-stu-id="7f79c-133">Power apps are focused apps for mobile devices that can connect to your existing data sources like SharePoint lists and other data apps.</span></span> <span data-ttu-id="7f79c-134">Para obtener más información, vea Crear una PowerApp para obtener una lista [en SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) y la página de [PowerApps.](https://powerapps.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="7f79c-134">See [Create a PowerApp for a list in SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) and the [PowerApps page](https://powerapps.microsoft.com/) for details.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="7f79c-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="7f79c-135">See also</span></span>

[<span data-ttu-id="7f79c-136">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="7f79c-136">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
