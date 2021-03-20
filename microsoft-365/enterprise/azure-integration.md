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
# <a name="azure-integration-with-microsoft-365"></a><span data-ttu-id="26f0e-103">Integración de Azure con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="26f0e-103">Azure integration with Microsoft 365</span></span>

<span data-ttu-id="26f0e-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="26f0e-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="26f0e-105">Microsoft 365 usa Azure Active Directory (Azure AD) para administrar identidades de usuario en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="26f0e-105">Microsoft 365 uses Azure Active Directory (Azure AD) to manage user identities behind the scenes.</span></span> <span data-ttu-id="26f0e-106">La suscripción a Microsoft 365 incluye una suscripción gratuita de Azure AD para que pueda integrar los Servicios de dominio de Active Directory (AD DS) locales para sincronizar cuentas de usuario y contraseñas o configurar el inicio de sesión único.</span><span class="sxs-lookup"><span data-stu-id="26f0e-106">Your Microsoft 365 subscription includes a free Azure AD subscription so that you can integrate your on-premises Active Directory Domain Services (AD DS) to synchronize user accounts and passwords or set up single sign-on.</span></span> <span data-ttu-id="26f0e-107">También puedes comprar características avanzadas para administrar mejor tus cuentas.</span><span class="sxs-lookup"><span data-stu-id="26f0e-107">You can also purchase advanced features to better manage your accounts.</span></span>
  
<span data-ttu-id="26f0e-108">Azure AD también ofrece otras funciones, como administrar aplicaciones integradas, que puedes usar para ampliar y personalizar las suscripciones de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="26f0e-108">Azure AD also offers other functionality, like managing integrated apps, that you can use to extend and customize your Microsoft 365 subscriptions.</span></span>
  
<span data-ttu-id="26f0e-109">Puede usar los asesores de implementación de Azure AD para una experiencia de configuración y configuración guiada en el Centro de administración de Microsoft 365 (debe haber iniciado sesión en Microsoft 365):</span><span class="sxs-lookup"><span data-stu-id="26f0e-109">You can use the Azure AD deployment advisors for a guided setup and configuration experience in the Microsoft 365 admin center (you must be signed in to Microsoft 365):</span></span>

 - [<span data-ttu-id="26f0e-110">Asesor de Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="26f0e-110">Azure AD Connect advisor</span></span>](https://aka.ms/aadconnectpwsync)
 - [<span data-ttu-id="26f0e-111">Asesor de implementación de AD FS</span><span class="sxs-lookup"><span data-stu-id="26f0e-111">AD FS deployment advisor</span></span>](https://aka.ms/adfsguidance)
 - [<span data-ttu-id="26f0e-112">Guía de configuración de Azure AD</span><span class="sxs-lookup"><span data-stu-id="26f0e-112">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a><span data-ttu-id="26f0e-113">Ediciones de Azure AD y administración de identidades de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="26f0e-113">Azure AD editions and Microsoft 365 identity management</span></span>

<span data-ttu-id="26f0e-114">Si tienes una suscripción de pago a Microsoft 365, también tienes una suscripción gratuita a Azure AD.</span><span class="sxs-lookup"><span data-stu-id="26f0e-114">If you have a paid subscription to Microsoft 365, you also have a free Azure AD subscription.</span></span> <span data-ttu-id="26f0e-115">Puede usar Azure AD para crear y administrar cuentas de usuario y grupo.</span><span class="sxs-lookup"><span data-stu-id="26f0e-115">You can use Azure AD to create and manage user and group accounts.</span></span> <span data-ttu-id="26f0e-116">Para activar esta suscripción, debe completar un registro único.</span><span class="sxs-lookup"><span data-stu-id="26f0e-116">To activate this subscription, you have to complete a one-time registration.</span></span> <span data-ttu-id="26f0e-117">Después, puede obtener acceso a Azure AD desde el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="26f0e-117">Afterward, you can access Azure AD from your Microsoft 365 admin center.</span></span> 

<span data-ttu-id="26f0e-118">Para obtener instrucciones para registrar la suscripción gratuita de Azure AD, consulta [Usar la suscripción gratuita de Azure AD](../compliance/use-your-free-azure-ad-subscription-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="26f0e-118">For instructions to register your free Azure AD subscription, see [use your free Azure AD subscription](../compliance/use-your-free-azure-ad-subscription-in-office-365.md).</span></span> <span data-ttu-id="26f0e-119">No vaya directamente a azure.microsoft.com para registrarse o terminará con una suscripción de prueba o de pago a Microsoft Azure que sea independiente de su suscripción gratuita de Azure AD con Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="26f0e-119">Don't go directly to azure.microsoft.com to sign up or you'll end up with a trial or paid subscription to Microsoft Azure that is separate from your free Azure AD subscription with Microsoft 365.</span></span> 
  
<span data-ttu-id="26f0e-120">Con la suscripción gratuita, puede sincronizar con directorios locales, configurar el inicio de sesión único y sincronizar con muchos software como aplicaciones de servicio, como Salesforce, DropBox y muchos más.</span><span class="sxs-lookup"><span data-stu-id="26f0e-120">With the free subscription you can synchronize with on-premises directories, set up single sign-on, and synchronize with many software as service applications, such as Salesforce, DropBox, and many more.</span></span>
  
<span data-ttu-id="26f0e-121">Si quieres mejorar la funcionalidad de AD DS, la sincronización bidireccional y otras funciones de administración, puedes actualizar tu suscripción gratuita a una suscripción premium de pago.</span><span class="sxs-lookup"><span data-stu-id="26f0e-121">If you want enhanced AD DS functionality, bi-directional synchronization, and other management capabilities, you can upgrade your free subscription to a paid premium subscription.</span></span> <span data-ttu-id="26f0e-122">Para obtener más información, [consulte Ediciones de Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="26f0e-122">For the details, see [Azure Active Directory editions](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>
  
<span data-ttu-id="26f0e-123">Para obtener más información acerca de Microsoft 365 y Azure AD, vea Modelos de [identidad de Microsoft 365](about-microsoft-365-identity.md).</span><span class="sxs-lookup"><span data-stu-id="26f0e-123">For more information about Microsoft 365 and Azure AD, see [Microsoft 365 identity models](about-microsoft-365-identity.md).</span></span>
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a><span data-ttu-id="26f0e-124">Ampliar las capacidades de su inquilino de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="26f0e-124">Extend the capabilities of your Microsoft 365 tenant</span></span>

|<span data-ttu-id="26f0e-125">**Característica**</span><span class="sxs-lookup"><span data-stu-id="26f0e-125">**Feature**</span></span>|<span data-ttu-id="26f0e-126">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="26f0e-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="26f0e-127">Aplicaciones integradas</span><span class="sxs-lookup"><span data-stu-id="26f0e-127">Integrated apps</span></span>  <br/> |<span data-ttu-id="26f0e-128">Puedes conceder acceso a aplicaciones individuales a los datos de Microsoft 365, como correo, calendarios, contactos, usuarios, grupos, archivos y carpetas.</span><span class="sxs-lookup"><span data-stu-id="26f0e-128">You can grant individual apps access to your Microsoft 365 data, such as mail, calendars, contacts, users, groups, files, and folders.</span></span> <span data-ttu-id="26f0e-129">También puede autorizar estas aplicaciones a nivel de administrador global y hacer que estén disponibles para toda la empresa registrando las aplicaciones en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="26f0e-129">You can also authorize these apps at global admin level and make them available to your entire company by registering the apps in Azure AD.</span></span> <span data-ttu-id="26f0e-130">Para obtener más información, vea [Aplicaciones integradas y Azure AD para administradores de Microsoft 365](integrated-apps-and-azure-ads.md).</span><span class="sxs-lookup"><span data-stu-id="26f0e-130">Formore information, see [Integrated Apps and Azure AD for Microsoft 365 administrators](integrated-apps-and-azure-ads.md).</span></span>  <br/> <span data-ttu-id="26f0e-131">Vea también [Inicio de sesión único](/azure/active-directory/manage-apps/what-is-single-sign-on).</span><span class="sxs-lookup"><span data-stu-id="26f0e-131">Also see [Single sign-on](/azure/active-directory/manage-apps/what-is-single-sign-on).</span></span>  <br/> |
|<span data-ttu-id="26f0e-132">PowerApps</span><span class="sxs-lookup"><span data-stu-id="26f0e-132">PowerApps</span></span>  <br/> | <span data-ttu-id="26f0e-133">Las aplicaciones de energía son aplicaciones centradas para dispositivos móviles que pueden conectarse a los orígenes de datos existentes, como listas de SharePoint y otras aplicaciones de datos.</span><span class="sxs-lookup"><span data-stu-id="26f0e-133">Power apps are focused apps for mobile devices that can connect to your existing data sources like SharePoint lists and other data apps.</span></span> <span data-ttu-id="26f0e-134">Vea [Create a PowerApp for a list in SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) y la página [PowerApps](https://powerapps.microsoft.com/) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="26f0e-134">See [Create a PowerApp for a list in SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) and the [PowerApps page](https://powerapps.microsoft.com/) for details.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="26f0e-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="26f0e-135">See also</span></span>

[<span data-ttu-id="26f0e-136">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="26f0e-136">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)