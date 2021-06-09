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
description: Integre Microsoft 365 con Azure AD si desea la sincronización de contraseñas o el inicio de sesión único con el entorno local.
ms.openlocfilehash: f977969634401d59d7598136f9323cb0e37f9ece
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905337"
---
# <a name="azure-integration-with-microsoft-365"></a><span data-ttu-id="ebcbd-103">Integración de Azure con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ebcbd-103">Azure integration with Microsoft 365</span></span>

<span data-ttu-id="ebcbd-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="ebcbd-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="ebcbd-105">Microsoft 365 usa Azure Active Directory (Azure AD) para administrar identidades de usuario en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="ebcbd-105">Microsoft 365 uses Azure Active Directory (Azure AD) to manage user identities behind the scenes.</span></span> <span data-ttu-id="ebcbd-106">La suscripción Microsoft 365 incluye una suscripción gratuita de Azure AD para que pueda integrar los Servicios de dominio de Active Directory (AD DS) locales para sincronizar cuentas de usuario y contraseñas o configurar el inicio de sesión único.</span><span class="sxs-lookup"><span data-stu-id="ebcbd-106">Your Microsoft 365 subscription includes a free Azure AD subscription so that you can integrate your on-premises Active Directory Domain Services (AD DS) to synchronize user accounts and passwords or set up single sign-on.</span></span> <span data-ttu-id="ebcbd-107">También puedes comprar características avanzadas para administrar mejor tus cuentas.</span><span class="sxs-lookup"><span data-stu-id="ebcbd-107">You can also purchase advanced features to better manage your accounts.</span></span>
  
<span data-ttu-id="ebcbd-108">Azure AD también ofrece otras funciones, como la administración de aplicaciones integradas, que puedes usar para ampliar y personalizar tus Microsoft 365 suscripciones.</span><span class="sxs-lookup"><span data-stu-id="ebcbd-108">Azure AD also offers other functionality, like managing integrated apps, that you can use to extend and customize your Microsoft 365 subscriptions.</span></span>
  
<span data-ttu-id="ebcbd-109">Puede usar los asesores de implementación de Azure AD para una experiencia de configuración y configuración guiada en el Centro de administración de Microsoft 365 (debe haber iniciado sesión en Microsoft 365):</span><span class="sxs-lookup"><span data-stu-id="ebcbd-109">You can use the Azure AD deployment advisors for a guided setup and configuration experience in the Microsoft 365 admin center (you must be signed in to Microsoft 365):</span></span>

 - [<span data-ttu-id="ebcbd-110">Asesor de Conectar Azure AD</span><span class="sxs-lookup"><span data-stu-id="ebcbd-110">Azure AD Connect advisor</span></span>](https://aka.ms/aadconnectpwsync)
 - [<span data-ttu-id="ebcbd-111">Asesor de implementación de AD FS</span><span class="sxs-lookup"><span data-stu-id="ebcbd-111">AD FS deployment advisor</span></span>](https://aka.ms/adfsguidance)
 - [<span data-ttu-id="ebcbd-112">Guía de configuración de Azure AD</span><span class="sxs-lookup"><span data-stu-id="ebcbd-112">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a><span data-ttu-id="ebcbd-113">Ediciones de Azure AD y administración Microsoft 365 identidades</span><span class="sxs-lookup"><span data-stu-id="ebcbd-113">Azure AD editions and Microsoft 365 identity management</span></span>

<span data-ttu-id="ebcbd-114">Si tiene una suscripción de pago a Microsoft 365, también tiene una suscripción gratuita de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ebcbd-114">If you have a paid subscription to Microsoft 365, you also have a free Azure AD subscription.</span></span> <span data-ttu-id="ebcbd-115">Puede usar Azure AD para crear y administrar cuentas de usuario y grupo.</span><span class="sxs-lookup"><span data-stu-id="ebcbd-115">You can use Azure AD to create and manage user and group accounts.</span></span> <span data-ttu-id="ebcbd-116">Para activar esta suscripción, debe completar un registro único.</span><span class="sxs-lookup"><span data-stu-id="ebcbd-116">To activate this subscription, you have to complete a one-time registration.</span></span> <span data-ttu-id="ebcbd-117">Después, puede obtener acceso a Azure AD desde el centro Microsoft 365 administración.</span><span class="sxs-lookup"><span data-stu-id="ebcbd-117">Afterward, you can access Azure AD from your Microsoft 365 admin center.</span></span> 

<span data-ttu-id="ebcbd-118">Para obtener instrucciones para registrar la suscripción gratuita de Azure AD, consulta [Usar la suscripción gratuita de Azure AD](../compliance/use-your-free-azure-ad-subscription-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="ebcbd-118">For instructions to register your free Azure AD subscription, see [use your free Azure AD subscription](../compliance/use-your-free-azure-ad-subscription-in-office-365.md).</span></span> <span data-ttu-id="ebcbd-119">No vaya directamente a azure.microsoft.com para registrarse o terminará con una suscripción de prueba o de pago a Microsoft Azure que sea independiente de su suscripción gratuita de Azure AD con Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ebcbd-119">Don't go directly to azure.microsoft.com to sign up or you'll end up with a trial or paid subscription to Microsoft Azure that is separate from your free Azure AD subscription with Microsoft 365.</span></span> 
  
<span data-ttu-id="ebcbd-120">Con la suscripción gratuita, puede sincronizar con directorios locales, configurar el inicio de sesión único y sincronizar con muchos software como aplicaciones de servicio, como Salesforce, DropBox y muchos más.</span><span class="sxs-lookup"><span data-stu-id="ebcbd-120">With the free subscription you can synchronize with on-premises directories, set up single sign-on, and synchronize with many software as service applications, such as Salesforce, DropBox, and many more.</span></span>
  
<span data-ttu-id="ebcbd-121">Si quieres mejorar la funcionalidad de AD DS, la sincronización bidireccional y otras funciones de administración, puedes actualizar tu suscripción gratuita a una suscripción premium de pago.</span><span class="sxs-lookup"><span data-stu-id="ebcbd-121">If you want enhanced AD DS functionality, bi-directional synchronization, and other management capabilities, you can upgrade your free subscription to a paid premium subscription.</span></span> <span data-ttu-id="ebcbd-122">Para obtener más información, [vea Azure Active Directory ediciones](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="ebcbd-122">For the details, see [Azure Active Directory editions](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>
  
<span data-ttu-id="ebcbd-123">Para obtener más información sobre Microsoft 365 y Azure AD, vea [Microsoft 365 identity models](about-microsoft-365-identity.md).</span><span class="sxs-lookup"><span data-stu-id="ebcbd-123">For more information about Microsoft 365 and Azure AD, see [Microsoft 365 identity models](about-microsoft-365-identity.md).</span></span>
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a><span data-ttu-id="ebcbd-124">Ampliar las capacidades de su Microsoft 365 inquilino</span><span class="sxs-lookup"><span data-stu-id="ebcbd-124">Extend the capabilities of your Microsoft 365 tenant</span></span>

|<span data-ttu-id="ebcbd-125">**Característica**</span><span class="sxs-lookup"><span data-stu-id="ebcbd-125">**Feature**</span></span>|<span data-ttu-id="ebcbd-126">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="ebcbd-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ebcbd-127">Aplicaciones integradas</span><span class="sxs-lookup"><span data-stu-id="ebcbd-127">Integrated apps</span></span>  <br/> |<span data-ttu-id="ebcbd-128">Puedes conceder acceso a aplicaciones individuales a tus Microsoft 365, como correo, calendarios, contactos, usuarios, grupos, archivos y carpetas.</span><span class="sxs-lookup"><span data-stu-id="ebcbd-128">You can grant individual apps access to your Microsoft 365 data, such as mail, calendars, contacts, users, groups, files, and folders.</span></span> <span data-ttu-id="ebcbd-129">También puede autorizar estas aplicaciones a nivel de administrador global y hacer que estén disponibles para toda la empresa registrando las aplicaciones en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ebcbd-129">You can also authorize these apps at global admin level and make them available to your entire company by registering the apps in Azure AD.</span></span> <span data-ttu-id="ebcbd-130">Para obtener más información, vea [Integrated Apps and Azure AD for Microsoft 365 administrators](integrated-apps-and-azure-ads.md).</span><span class="sxs-lookup"><span data-stu-id="ebcbd-130">Formore information, see [Integrated Apps and Azure AD for Microsoft 365 administrators](integrated-apps-and-azure-ads.md).</span></span>  <br/> <span data-ttu-id="ebcbd-131">Vea también [Inicio de sesión único](/azure/active-directory/manage-apps/what-is-single-sign-on).</span><span class="sxs-lookup"><span data-stu-id="ebcbd-131">Also see [Single sign-on](/azure/active-directory/manage-apps/what-is-single-sign-on).</span></span>  <br/> |
|<span data-ttu-id="ebcbd-132">PowerApps</span><span class="sxs-lookup"><span data-stu-id="ebcbd-132">PowerApps</span></span>  <br/> | <span data-ttu-id="ebcbd-133">Las aplicaciones de energía son aplicaciones centradas para dispositivos móviles que pueden conectarse a los orígenes de datos existentes, como SharePoint listas de datos y otras aplicaciones de datos.</span><span class="sxs-lookup"><span data-stu-id="ebcbd-133">Power apps are focused apps for mobile devices that can connect to your existing data sources like SharePoint lists and other data apps.</span></span> <span data-ttu-id="ebcbd-134">Consulta [Crear una PowerApp para obtener una](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) lista en SharePoint Online y la página [PowerApps](https://powerapps.microsoft.com/) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="ebcbd-134">See [Create a PowerApp for a list in SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) and the [PowerApps page](https://powerapps.microsoft.com/) for details.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="ebcbd-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ebcbd-135">See also</span></span>

[<span data-ttu-id="ebcbd-136">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ebcbd-136">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)