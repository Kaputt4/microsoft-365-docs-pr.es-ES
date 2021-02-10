---
title: Deshabilitar TLS 1.0 y 1.1 en Office 365 GCC High y DoD
description: Describe cómo Microsoft deshabilita la compatibilidad con TLS 1.1 y 1.0 en entornos GCC High y DoD en Microsoft 365.
author: workshay
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.collection: M365-security-compliance
ms.service: information-protection
ms.topic: article
ms.reviewer: krowley
ms.author: shmehta
appliesto:
- Office 365 Business
ms.openlocfilehash: 006f81ee5b17baca4f42a78c5a87a59e8e90648f
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166445"
---
# <a name="disabling-tls-10-and-11-in-office-365-gcc-high-and-dod"></a><span data-ttu-id="66e22-103">Deshabilitar TLS 1.0 y 1.1 en Office 365 GCC High y DoD</span><span class="sxs-lookup"><span data-stu-id="66e22-103">Disabling TLS 1.0 and 1.1 in Office 365 GCC High and DoD</span></span>

## <a name="summary"></a><span data-ttu-id="66e22-104">Resumen</span><span class="sxs-lookup"><span data-stu-id="66e22-104">Summary</span></span>

<span data-ttu-id="66e22-105">Para cumplir con los estándares de cumplimiento más recientes para el Programa federal de administración de riesgos y autorización (FedRAMP), estamos deshabilitando las versiones 1.1 y 1.0 de Seguridad de la capa de transporte (TLS) en Microsoft 365 para entornos GCC High y DoD.</span><span class="sxs-lookup"><span data-stu-id="66e22-105">In order to comply with the latest compliance standards for the Federal Risk and Authorization Management Program (FedRAMP), we are disabling Transport Layer Security (TLS) versions 1.1 and 1.0 in Microsoft 365 for GCC High and DoD environments.</span></span> <span data-ttu-id="66e22-106">Este cambio se anunció anteriormente a través del soporte técnico de Microsoft en la preparación para el uso obligatorio de [TLS 1.2 en Office 365.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="66e22-106">This change was previously announced through Microsoft Support in [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

<span data-ttu-id="66e22-107">La seguridad de los datos es importante y nos comprometemos a transparencia sobre los cambios que podrían afectar al uso del servicio.</span><span class="sxs-lookup"><span data-stu-id="66e22-107">The security of your data is important, and we are committed to transparency about changes that could affect your use of the service.</span></span>

<span data-ttu-id="66e22-108">Aunque la [implementación de Microsoft TLS 1.0](https://support.microsoft.com/help/3117336) no tiene vulnerabilidades de seguridad conocidas, seguimos comprometidos con los estándares de cumplimiento de FedRAMP.</span><span class="sxs-lookup"><span data-stu-id="66e22-108">Although the [Microsoft TLS 1.0 implementation](https://support.microsoft.com/help/3117336) has no known security vulnerabilities, we remain committed to the FedRAMP compliance standards.</span></span> <span data-ttu-id="66e22-109">Por lo tanto, deshabilitamos TLS 1.1 y 1.0 en Office 365 en entornos GCC High y DoD el 15 de enero de 2020.</span><span class="sxs-lookup"><span data-stu-id="66e22-109">Therefore, we disabled TLS 1.1 and 1.0 in Office 365 in GCC High and DoD environments on January 15, 2020.</span></span> <span data-ttu-id="66e22-110">Para obtener información acerca de cómo quitar dependencias de TLS 1.1 y 1.0, consulte las siguientes white paper:</span><span class="sxs-lookup"><span data-stu-id="66e22-110">For information about how to remove TLS 1.1 and 1.0 dependencies, see the following white paper:</span></span>

[<span data-ttu-id="66e22-111">Solución del problema de TLS 1.0</span><span class="sxs-lookup"><span data-stu-id="66e22-111">Solving the TLS 1.0 problem</span></span>](https://www.microsoft.com/download/details.aspx?id=55266)

<span data-ttu-id="66e22-112">Debe usar tls versión 1.2 en su lugar.</span><span class="sxs-lookup"><span data-stu-id="66e22-112">You must use TLS version 1.2 instead.</span></span> <span data-ttu-id="66e22-113">Para obtener más información, vea Prepararse para el uso obligatorio de [TLS 1.2 en Office 365.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="66e22-113">For more information, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

<span data-ttu-id="66e22-114">Para SharePoint y OneDrive, tendrá que actualizar y configurar .NET para admitir TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="66e22-114">For SharePoint and OneDrive, you'll need to update and configure .NET to support TLS 1.2.</span></span> <span data-ttu-id="66e22-115">Para obtener información, [consulte Cómo habilitar TLS 1.2 en los clientes.](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)</span><span class="sxs-lookup"><span data-stu-id="66e22-115">For information, see [How to enable TLS 1.2 on clients](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span>

## <a name="more-information"></a><span data-ttu-id="66e22-116">Más información</span><span class="sxs-lookup"><span data-stu-id="66e22-116">More information</span></span>

<span data-ttu-id="66e22-117">A partir del 15 de enero de 2020, Office 365 en los entornos GCC High y DoD dejará de usar TLS 1.1 y 1.0.</span><span class="sxs-lookup"><span data-stu-id="66e22-117">Starting on January 15, 2020, Office 365 in the GCC High and DoD environments will deprecate TLS 1.1 and 1.0.</span></span>

<span data-ttu-id="66e22-118">Antes del 15 de enero de 2020, todas las combinaciones de servidores cliente y servidores de explorador deben usar TLS versión 1.2 (o una versión posterior) para asegurarse de que se pueden realizar todas las conexiones sin problemas con los servicios de Office 365.</span><span class="sxs-lookup"><span data-stu-id="66e22-118">By January 15, 2020, all combinations of client servers and browser servers should use TLS version 1.2 (or a later version) to make sure that all connections can be made without issues to Office 365 services.</span></span> <span data-ttu-id="66e22-119">Esto puede requerir actualizaciones de determinadas combinaciones de servidores cliente y servidores de explorador.</span><span class="sxs-lookup"><span data-stu-id="66e22-119">This may require updates to certain combinations of client servers and browser servers.</span></span>

<span data-ttu-id="66e22-120">Si no actualiza a TLS versión 1.2 (o una versión posterior) antes del 15 de enero de 2020, experimentará problemas al intentar conectarse a Office 365.</span><span class="sxs-lookup"><span data-stu-id="66e22-120">If you do not update to TLS version 1.2 (or a later version) by January 15, 2020, you will experience issues when you try to connect to Office 365.</span></span> <span data-ttu-id="66e22-121">Además, tendrá que actualizar a TLS 1.2 (o una versión posterior) como parte de la resolución.</span><span class="sxs-lookup"><span data-stu-id="66e22-121">Additionally, you will be required to update to TLS 1.2 (or a later version) as part of the resolution.</span></span>

<span data-ttu-id="66e22-122">Sabemos que los siguientes clientes no pueden usar TLS 1.2:</span><span class="sxs-lookup"><span data-stu-id="66e22-122">We know that the following clients cannot use TLS 1.2:</span></span>

- <span data-ttu-id="66e22-123">Android 4.3 y versiones anteriores</span><span class="sxs-lookup"><span data-stu-id="66e22-123">Android 4.3 and earlier versions</span></span>
- <span data-ttu-id="66e22-124">Firefox versión 5.0 y versiones anteriores</span><span class="sxs-lookup"><span data-stu-id="66e22-124">Firefox version 5.0 and earlier versions</span></span>
- <span data-ttu-id="66e22-125">Internet Explorer 8–10 en Windows 7 y versiones anteriores</span><span class="sxs-lookup"><span data-stu-id="66e22-125">Internet Explorer 8–10 on Windows 7 and earlier versions</span></span>
- <span data-ttu-id="66e22-126">Internet Explorer 10 en Windows Phone 8.0</span><span class="sxs-lookup"><span data-stu-id="66e22-126">Internet Explorer 10 on Windows Phone 8.0</span></span>
- <span data-ttu-id="66e22-127">Safari 6.0.4/OS X 10.8.4 y versiones anteriores</span><span class="sxs-lookup"><span data-stu-id="66e22-127">Safari 6.0.4/OS X 10.8.4 and earlier versions</span></span>

<span data-ttu-id="66e22-128">Le recomendamos que actualice los clientes para asegurarse de mantener un acceso ininterrumpido a Office 365 GCC High y DoD.</span><span class="sxs-lookup"><span data-stu-id="66e22-128">We recommend that you update your clients to make sure that you maintain uninterrupted access to Office 365 GCC High and DoD.</span></span>

<span data-ttu-id="66e22-129">Aunque el análisis actual de las conexiones a los servicios de Microsoft Online muestra que la mayoría de los servicios y puntos de conexión ven muy poco uso de TLS 1.1 y 1.0, estamos proporcionando aviso de este cambio para que pueda actualizar los clientes o servidores afectados según sea necesario antes de que finalice la compatibilidad con TLS 1.1 y 1.0.</span><span class="sxs-lookup"><span data-stu-id="66e22-129">Although current analysis of connections to Microsoft Online services shows that most services and endpoints see very little TLS 1.1 and 1.0 usage, we are providing notice of this change so that you can update any affected clients or servers as necessary before support for TLS 1.1 and 1.0 ends.</span></span> <span data-ttu-id="66e22-130">Si usa alguna infraestructura local para escenarios híbridos o servicios de federación de Active Directory (AD FS), asegúrese de que la infraestructura admite conexiones entrantes y salientes que usan TLS 1.2 (o una versión posterior).</span><span class="sxs-lookup"><span data-stu-id="66e22-130">If you are using any on-premises infrastructure for hybrid scenarios or Active Directory Federation Services (AD FS), make sure that the infrastructure can support both inbound and outbound connections that use TLS 1.2 (or a later version).</span></span>

<span data-ttu-id="66e22-131">Además de las interrupciones que puede experimentar si usa los clientes enumerados que no pueden usar TLS 1.2, quitar TLS 1.1 y 1.0 le impedirá usar el siguiente producto de Microsoft:</span><span class="sxs-lookup"><span data-stu-id="66e22-131">In addition to the outages that you might experience if you use the listed clients that cannot use TLS 1.2, removing TLS 1.1 and 1.0 will prevent you from being able to use the following Microsoft product:</span></span>

- <span data-ttu-id="66e22-132">Teléfono Lync</span><span class="sxs-lookup"><span data-stu-id="66e22-132">Lync phone</span></span>

## <a name="references"></a><span data-ttu-id="66e22-133">Referencias</span><span class="sxs-lookup"><span data-stu-id="66e22-133">References</span></span>

<span data-ttu-id="66e22-134">En el siguiente artículo de soporte técnico se describen instrucciones y referencias para ayudar a garantizar que los clientes usan TLS 1.2:</span><span class="sxs-lookup"><span data-stu-id="66e22-134">The following support article describes guidance and references to help make sure that your clients are using TLS 1.2:</span></span>

[<span data-ttu-id="66e22-135">Preparación para el uso obligatorio de TLS 1.2 en Office 365</span><span class="sxs-lookup"><span data-stu-id="66e22-135">Preparing for the mandatory use of TLS 1.2 in Office 365</span></span>](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
