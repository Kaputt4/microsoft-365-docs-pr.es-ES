---
title: Ver el estado de sincronización de directorios en Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
ms.assetid: 18be3b98-34ae-47be-9337-ab6c3fb372ac
description: En este artículo, obtenga información sobre cómo comprobar el estado de la sincronización de directorios en Office 365.
ms.openlocfilehash: cbaae8bbd31f6124c2b0f4984b9a625ffbde538f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924665"
---
# <a name="view-directory-synchronization-status-in-microsoft-365"></a><span data-ttu-id="d8d23-103">Ver el estado de sincronización de directorios en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d8d23-103">View directory synchronization status in Microsoft 365</span></span>

<span data-ttu-id="d8d23-104">Si ha integrado los Servicios de dominio de Active Directory (AD DS) locales con Azure Active Directory (Azure AD) sincronizando el entorno local con Microsoft 365, también puede comprobar el estado de la sincronización.</span><span class="sxs-lookup"><span data-stu-id="d8d23-104">If you have integrated your on-premises Active Directory Domain Services (AD DS) with Azure Active Directory (Azure AD) by synchronizing your on-premises environment with Microsoft 365, you can also check the status of your synchronization.</span></span>
  
## <a name="view-directory-synchronization-status"></a><span data-ttu-id="d8d23-105">Ver el estado de sincronización de directorios</span><span class="sxs-lookup"><span data-stu-id="d8d23-105">View directory synchronization status</span></span>

- <span data-ttu-id="d8d23-106">Inicie sesión en el [centro Microsoft 365 administración y](https://admin.microsoft.com) elija Estado de **DirSync** en la página principal.</span><span class="sxs-lookup"><span data-stu-id="d8d23-106">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) and choose **DirSync Status** on the home page.</span></span>
- <span data-ttu-id="d8d23-107">Como alternativa, puede ir a **Usuarios** usuarios activos y, en la \> página **Usuarios activos,** elija **Más sincronización** de \> **directorios.**</span><span class="sxs-lookup"><span data-stu-id="d8d23-107">Alternately, you can go to **Users** \> **Active users**, and on the **Active users** page, choose **More** \> **Directory synchronization**.</span></span> <span data-ttu-id="d8d23-108">En el panel **Sincronización de** directorios, elija Ir a Administración **de DirSync**.</span><span class="sxs-lookup"><span data-stu-id="d8d23-108">On the **Directory Synchronization** pane, choose **Go to DirSync management**.</span></span>

## <a name="information-on-the-manage-directory-synchronization-page"></a><span data-ttu-id="d8d23-109">Información en la página Administrar sincronización de directorios</span><span class="sxs-lookup"><span data-stu-id="d8d23-109">Information on the Manage directory synchronization page</span></span>

<span data-ttu-id="d8d23-110">En la tabla siguiente se enumeran las características de las que puede obtener información en la página.</span><span class="sxs-lookup"><span data-stu-id="d8d23-110">The following table lists the features you can get information about on the page.</span></span>
  
<span data-ttu-id="d8d23-111">Si hay un problema con la sincronización de directorios, los errores también se enumeran en esta página.</span><span class="sxs-lookup"><span data-stu-id="d8d23-111">If there is a problem with your directory synchronization, the errors are listed on this page as well.</span></span> <span data-ttu-id="d8d23-112">Para obtener más información acerca de los diferentes errores que puede encontrar, vea Identificar errores de sincronización de [directorios en Microsoft 365](identify-directory-synchronization-errors.md).</span><span class="sxs-lookup"><span data-stu-id="d8d23-112">For more information about different errors you might encounter, see [Identify directory synchronization errors in Microsoft 365](identify-directory-synchronization-errors.md).</span></span>
  
|<span data-ttu-id="d8d23-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="d8d23-113">Item</span></span>|<span data-ttu-id="d8d23-114">Para qué sirve</span><span class="sxs-lookup"><span data-stu-id="d8d23-114">What it's for</span></span>|
|:-----|:-----|
|<span data-ttu-id="d8d23-115">**Dominios comprobados**</span><span class="sxs-lookup"><span data-stu-id="d8d23-115">**Domains verified**</span></span> | <span data-ttu-id="d8d23-116">Número de dominios de su Microsoft 365 inquilino que ha comprobado que es propietario.</span><span class="sxs-lookup"><span data-stu-id="d8d23-116">Number of domains in your Microsoft 365 tenant that you have verified you own.</span></span> |
|<span data-ttu-id="d8d23-117">**Dominios no comprobados**</span><span class="sxs-lookup"><span data-stu-id="d8d23-117">**Domains not verified**</span></span> | <span data-ttu-id="d8d23-118">Dominios que ha agregado, pero no comprobados.</span><span class="sxs-lookup"><span data-stu-id="d8d23-118">Domains you have added, but not verified.</span></span> |
|<span data-ttu-id="d8d23-119">**Sincronización de directorios habilitada**</span><span class="sxs-lookup"><span data-stu-id="d8d23-119">**Directory sync enabled**</span></span> |<span data-ttu-id="d8d23-120">Verdadero o Falso</span><span class="sxs-lookup"><span data-stu-id="d8d23-120">True or False.</span></span> <span data-ttu-id="d8d23-121">Especifica si ha habilitado la sincronización de directorios.</span><span class="sxs-lookup"><span data-stu-id="d8d23-121">Specifies whether you have enabled directory sync.</span></span> |
|<span data-ttu-id="d8d23-122">**Sincronización de directorios más reciente**</span><span class="sxs-lookup"><span data-stu-id="d8d23-122">**Latest directory sync**</span></span> | <span data-ttu-id="d8d23-123">Última vez que se ejecutó la sincronización de directorios.</span><span class="sxs-lookup"><span data-stu-id="d8d23-123">Last time directory sync ran.</span></span> <span data-ttu-id="d8d23-124">Mostrará una advertencia y un vínculo a una herramienta de solución de problemas si la última sincronización fue hace más de tres días.</span><span class="sxs-lookup"><span data-stu-id="d8d23-124">Will display a warning and a link to a troubleshooting tool if the last sync was more than three days ago.</span></span> |
|<span data-ttu-id="d8d23-125">**Sincronización de contraseña habilitada**</span><span class="sxs-lookup"><span data-stu-id="d8d23-125">**Password sync enabled**</span></span> | <span data-ttu-id="d8d23-126">Verdadero o Falso</span><span class="sxs-lookup"><span data-stu-id="d8d23-126">True or False.</span></span> <span data-ttu-id="d8d23-127">Especifica si tiene sincronización hash de contraseña entre nuestro espacio empresarial local y Microsoft 365 local.</span><span class="sxs-lookup"><span data-stu-id="d8d23-127">Specifies whether you have password hash sync between our on-premises and your Microsoft 365 tenant.</span></span> |
|<span data-ttu-id="d8d23-128">**Last Password Sync**</span><span class="sxs-lookup"><span data-stu-id="d8d23-128">**Last Password Sync**</span></span> | <span data-ttu-id="d8d23-129">La última vez que se ejecutó la sincronización de hash de contraseña.</span><span class="sxs-lookup"><span data-stu-id="d8d23-129">Last time password hash sync ran.</span></span> <span data-ttu-id="d8d23-130">Mostrará una advertencia y un vínculo a una herramienta de solución de problemas si la última sincronización fue hace más de tres días.</span><span class="sxs-lookup"><span data-stu-id="d8d23-130">Will display a warning and a link to a troubleshooting tool if the last sync was more than three days ago.</span></span> |
|<span data-ttu-id="d8d23-131">**Versión del cliente de sincronización de directorios**</span><span class="sxs-lookup"><span data-stu-id="d8d23-131">**Directory sync client version**</span></span> | <span data-ttu-id="d8d23-132">Contiene un vínculo de descarga si se ha publicado una nueva versión Conectar azure AD.</span><span class="sxs-lookup"><span data-stu-id="d8d23-132">Contains a download link if a new version of Azure AD Connect has been released.</span></span> |
|<span data-ttu-id="d8d23-133">**Cuenta de servicio de sincronización de directorios**</span><span class="sxs-lookup"><span data-stu-id="d8d23-133">**Directory sync service account**</span></span> | <span data-ttu-id="d8d23-134">Muestra el nombre de la cuenta de servicio Microsoft 365 de sincronización de directorios.</span><span class="sxs-lookup"><span data-stu-id="d8d23-134">Displays the name of your Microsoft 365 directory sync service account.</span></span> |
|||

## <a name="monitor-synchronization-health"></a><span data-ttu-id="d8d23-135">Supervisión del estado de sincronización</span><span class="sxs-lookup"><span data-stu-id="d8d23-135">Monitor synchronization health</span></span>

<span data-ttu-id="d8d23-136">En esta sección, deberá instalar a un agente de Azure AD Connect Health en cada uno de los controladores de dominio AD DS locales para supervisar su infraestructura de identidades y los servicios de sincronización proporcionados por Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="d8d23-136">In this section, you'll install an Azure AD Connect Health agent on each of your on-premises AD DS domain controllers to monitor your identity infrastructure and the synchronization services provided by Azure AD Connect.</span></span> <span data-ttu-id="d8d23-137">En el portal de Azure AD Connect Health podrá consultar la información de supervisión, y se pueden ver alertas, supervisión del rendimiento y análisis de uso, entre otros datos.</span><span class="sxs-lookup"><span data-stu-id="d8d23-137">The monitoring information is made available in an Azure AD Connect Health portal, where you can view alerts, performance monitoring, usage analytics, and other information.</span></span>

<span data-ttu-id="d8d23-138">La decisión de diseño clave sobre cómo usar Azure AD Connect Health se basa en la forma en que use Azure AD Connect:</span><span class="sxs-lookup"><span data-stu-id="d8d23-138">The key design decision of how to use Azure AD Connect Health is based on how you are using Azure AD Connect:</span></span>

- <span data-ttu-id="d8d23-139">Si usa la opción de **autenticación administrada**, vea primero [Usar Azure AD Connect Health con sincronización](/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) para comprender y configurar Azure AD Connect Health.</span><span class="sxs-lookup"><span data-stu-id="d8d23-139">If you’re using the **managed authentication** option, start with [Using Azure AD Connect Health with sync](/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) to understand and configure Azure AD Connect Health.</span></span>
- <span data-ttu-id="d8d23-140">Si solo sincroniza los nombres de las cuentas y los grupos mediante la **autenticación federada** con Servicios de federación de Active Directory (AD FS), empiece con [Usar Azure AD Connect Health con AD FS](/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) para comprender y configurar Azure AD Connect Health.</span><span class="sxs-lookup"><span data-stu-id="d8d23-140">If you're synchronizing just the names of the accounts and groups using **federated authentication** with Active Directory Federation Services (AD FS), start with [Using Azure AD Connect Health with AD FS](/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) to understand and configure Azure AD Connect Health.</span></span>

<span data-ttu-id="d8d23-141">Cuando se complete, tendrá:</span><span class="sxs-lookup"><span data-stu-id="d8d23-141">When complete, you’ll have:</span></span>

- <span data-ttu-id="d8d23-142">El agente de Azure AD Connect Health instalado en los servidores de proveedor de identidades locales.</span><span class="sxs-lookup"><span data-stu-id="d8d23-142">The Azure AD Connect Health agent installed on your on-premises identity provider servers.</span></span>
- <span data-ttu-id="d8d23-143">En el portal de Azure AD Connect Health, se mostrará el estado actual de la infraestructura local y las actividades de sincronización con el espacio empresarial de Azure AD para su suscripción de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d8d23-143">The Azure AD Connect Health portal displaying the current state of your on-premises infrastructure and synchronization activities with the Azure AD tenant for your Microsoft 365 subscription.</span></span>