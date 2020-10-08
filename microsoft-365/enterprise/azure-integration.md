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
description: Integre Microsoft 365 con Azure AD si desea la sincronización de contraseña o el inicio de sesión único con el entorno local.
ms.openlocfilehash: b1f20ebc692421ed6df0d6f7c31a4d80347133e3
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384745"
---
# <a name="azure-integration-with-microsoft-365"></a><span data-ttu-id="fdd8a-103">Integración de Azure con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fdd8a-103">Azure integration with Microsoft 365</span></span>

<span data-ttu-id="fdd8a-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="fdd8a-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="fdd8a-105">Microsoft 365 usa Azure Active Directory (Azure AD) para administrar las identidades de usuario en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="fdd8a-105">Microsoft 365 uses Azure Active Directory (Azure AD) to manage user identities behind the scenes.</span></span> <span data-ttu-id="fdd8a-106">Su suscripción a Microsoft 365 incluye una suscripción gratuita a Azure AD para que pueda integrar los servicios de dominio de Active Directory (AD DS) locales para sincronizar las cuentas de usuario y las contraseñas o configurar el inicio de sesión único.</span><span class="sxs-lookup"><span data-stu-id="fdd8a-106">Your Microsoft 365 subscription includes a free Azure AD subscription so that you can integrate your on-premises Active Directory Domain Services (AD DS) to synchronize user accounts and passwords or set up single sign-on.</span></span> <span data-ttu-id="fdd8a-107">También puede comprar características avanzadas para administrar mejor sus cuentas.</span><span class="sxs-lookup"><span data-stu-id="fdd8a-107">You can also purchase advanced features to better manage your accounts.</span></span>
  
<span data-ttu-id="fdd8a-108">Azure AD también ofrece otras funciones, como la administración de aplicaciones integradas, que puede usar para ampliar y personalizar sus suscripciones de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fdd8a-108">Azure AD also offers other functionality, like managing integrated apps, that you can use to extend and customize your Microsoft 365 subscriptions.</span></span>
  
<span data-ttu-id="fdd8a-109">Puede usar los asesores de implementación de Azure AD para una instalación guiada y una experiencia de configuración en el centro de administración de Microsoft 365 (debe haber iniciado sesión en Microsoft 365):</span><span class="sxs-lookup"><span data-stu-id="fdd8a-109">You can use the Azure AD deployment advisors for a guided setup and configuration experience in the Microsoft 365 admin center (you must be signed in to Microsoft 365):</span></span>

 - [<span data-ttu-id="fdd8a-110">Azure AD Connect Advisor</span><span class="sxs-lookup"><span data-stu-id="fdd8a-110">Azure AD Connect advisor</span></span>](https://aka.ms/aadconnectpwsync)
 - [<span data-ttu-id="fdd8a-111">Asesor de implementación de AD FS</span><span class="sxs-lookup"><span data-stu-id="fdd8a-111">AD FS deployment advisor</span></span>](https://aka.ms/adfsguidance)
 - [<span data-ttu-id="fdd8a-112">Guía de configuración de Azure AD</span><span class="sxs-lookup"><span data-stu-id="fdd8a-112">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a><span data-ttu-id="fdd8a-113">Azure AD Editions y Microsoft 365 Identity Management</span><span class="sxs-lookup"><span data-stu-id="fdd8a-113">Azure AD editions and Microsoft 365 identity management</span></span>

<span data-ttu-id="fdd8a-114">Si tiene una suscripción de pago a Microsoft 365, también tiene una suscripción gratuita de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="fdd8a-114">If you have a paid subscription to Microsoft 365, you also have a free Azure AD subscription.</span></span> <span data-ttu-id="fdd8a-115">Puede usar Azure AD para crear y administrar cuentas de grupo y de usuario.</span><span class="sxs-lookup"><span data-stu-id="fdd8a-115">You can use Azure AD to create and manage user and group accounts.</span></span> <span data-ttu-id="fdd8a-116">Para activar esta suscripción, debe realizar un registro único.</span><span class="sxs-lookup"><span data-stu-id="fdd8a-116">To activate this subscription, you have to complete a one-time registration.</span></span> <span data-ttu-id="fdd8a-117">Después, puede obtener acceso a Azure AD desde el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fdd8a-117">Afterward, you can access Azure AD from your Microsoft 365 admin center.</span></span> 

<span data-ttu-id="fdd8a-118">Para obtener instrucciones sobre cómo registrar su suscripción gratuita a Azure AD, consulte [usar su suscripción gratuita a Azure ad](../compliance/use-your-free-azure-ad-subscription-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="fdd8a-118">For instructions to register your free Azure AD subscription, see [use your free Azure AD subscription](../compliance/use-your-free-azure-ad-subscription-in-office-365.md).</span></span> <span data-ttu-id="fdd8a-119">No vaya directamente a azure.microsoft.com para registrarse o obtendrá una suscripción de prueba o de pago a Microsoft Azure que es independiente de su suscripción gratuita a Azure AD con Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fdd8a-119">Don't go directly to azure.microsoft.com to sign up or you'll end up with a trial or paid subscription to Microsoft Azure that is separate from your free Azure AD subscription with Microsoft 365.</span></span> 
  
<span data-ttu-id="fdd8a-120">Con la suscripción gratuita, puede sincronizar con directorios locales, configurar el inicio de sesión único y sincronizar con muchos software como aplicaciones de servicio, como Salesforce, DropBox y muchos más.</span><span class="sxs-lookup"><span data-stu-id="fdd8a-120">With the free subscription you can synchronize with on-premises directories, set up single sign-on, and synchronize with many software as service applications, such as Salesforce, DropBox, and many more.</span></span>
  
<span data-ttu-id="fdd8a-121">Si desea funcionalidad de AD DS mejorada, sincronización bidireccional y otras capacidades de administración, puede actualizar su suscripción gratuita a una suscripción Premium de pago.</span><span class="sxs-lookup"><span data-stu-id="fdd8a-121">If you want enhanced AD DS functionality, bi-directional synchronization, and other management capabilities, you can upgrade your free subscription to a paid premium subscription.</span></span> <span data-ttu-id="fdd8a-122">Para obtener información detallada, consulte [Azure Active Directory Editions](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="fdd8a-122">For the details, see [Azure Active Directory editions](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>
  
<span data-ttu-id="fdd8a-123">Para obtener más información acerca de Microsoft 365 y Azure AD, consulte [modelos de identidad de 365 de Microsoft](about-microsoft-365-identity.md).</span><span class="sxs-lookup"><span data-stu-id="fdd8a-123">For more information about Microsoft 365 and Azure AD, see [Microsoft 365 identity models](about-microsoft-365-identity.md).</span></span>
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a><span data-ttu-id="fdd8a-124">Ampliar las capacidades de su inquilino de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fdd8a-124">Extend the capabilities of your Microsoft 365 tenant</span></span>

|<span data-ttu-id="fdd8a-125">**Característica**</span><span class="sxs-lookup"><span data-stu-id="fdd8a-125">**Feature**</span></span>|<span data-ttu-id="fdd8a-126">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="fdd8a-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fdd8a-127">Aplicaciones integradas</span><span class="sxs-lookup"><span data-stu-id="fdd8a-127">Integrated apps</span></span>  <br/> |<span data-ttu-id="fdd8a-128">Puede conceder acceso a aplicaciones individuales a sus datos de Microsoft 365, como correo, calendarios, contactos, usuarios, grupos, archivos y carpetas.</span><span class="sxs-lookup"><span data-stu-id="fdd8a-128">You can grant individual apps access to your Microsoft 365 data, such as mail, calendars, contacts, users, groups, files, and folders.</span></span> <span data-ttu-id="fdd8a-129">También puede autorizar estas aplicaciones en el nivel de administrador global y ponerlas a disposición de toda la empresa registrando las aplicaciones en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="fdd8a-129">You can also authorize these apps at global admin level and make them available to your entire company by registering the apps in Azure AD.</span></span> <span data-ttu-id="fdd8a-130">Formore información, vea [aplicaciones integradas y Azure ad para administradores de Microsoft 365](integrated-apps-and-azure-ads.md).</span><span class="sxs-lookup"><span data-stu-id="fdd8a-130">Formore information, see [Integrated Apps and Azure AD for Microsoft 365 administrators](integrated-apps-and-azure-ads.md).</span></span>  <br/> <span data-ttu-id="fdd8a-131">Consulte también [Inicio de sesión único (Single Sign-on)](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span><span class="sxs-lookup"><span data-stu-id="fdd8a-131">Also see [Single sign-on](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span></span>  <br/> |
|<span data-ttu-id="fdd8a-132">PowerApps</span><span class="sxs-lookup"><span data-stu-id="fdd8a-132">PowerApps</span></span>  <br/> | <span data-ttu-id="fdd8a-133">Las aplicaciones Power se centran en aplicaciones para dispositivos móviles que se pueden conectar a los orígenes de datos existentes, como las listas de SharePoint y otras aplicaciones de datos.</span><span class="sxs-lookup"><span data-stu-id="fdd8a-133">Power apps are focused apps for mobile devices that can connect to your existing data sources like SharePoint lists and other data apps.</span></span> <span data-ttu-id="fdd8a-134">Consulte [Create a PowerApp for a List in SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) y la [Página PowerApps](https://powerapps.microsoft.com/) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="fdd8a-134">See [Create a PowerApp for a list in SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) and the [PowerApps page](https://powerapps.microsoft.com/) for details.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="fdd8a-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fdd8a-135">See also</span></span>

[<span data-ttu-id="fdd8a-136">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="fdd8a-136">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
