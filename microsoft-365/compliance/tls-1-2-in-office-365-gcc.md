---
title: Deshabilitar TLS 1.0 y 1.1 en Microsoft 365 GCC High y DoD
description: Describe cómo Microsoft deshabilita la compatibilidad con TLS 1.1 y 1.0 en entornos GCC High y DoD en Microsoft 365.
author: kccross
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.collection: M365-security-compliance
ms.service: information-protection
ms.topic: article
ms.reviewer: krowley
ms.author: krowley
appliesto:
- Office 365 Business
ms.openlocfilehash: 16a02985107c5f578d6d6c21bf2efc6e80297951
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919346"
---
# <a name="disabling-tls-10-and-11-in-microsoft-365-gcc-high-and-dod"></a><span data-ttu-id="1b15c-103">Deshabilitar TLS 1.0 y 1.1 en Microsoft 365 GCC High y DoD</span><span class="sxs-lookup"><span data-stu-id="1b15c-103">Disabling TLS 1.0 and 1.1 in Microsoft 365 GCC High and DoD</span></span>

## <a name="summary"></a><span data-ttu-id="1b15c-104">Resumen</span><span class="sxs-lookup"><span data-stu-id="1b15c-104">Summary</span></span>

<span data-ttu-id="1b15c-105">Para cumplir con los últimos estándares de cumplimiento del Programa federal de administración de riesgos y autorización (FedRAMP), deshabilitamos las versiones 1.1 y 1.0 de Seguridad de la capa de transporte (TLS) en Microsoft 365 para entornos de GCC High y DoD.</span><span class="sxs-lookup"><span data-stu-id="1b15c-105">In order to comply with the latest compliance standards for the Federal Risk and Authorization Management Program (FedRAMP), we are disabling Transport Layer Security (TLS) versions 1.1 and 1.0 in Microsoft 365 for GCC High and DoD environments.</span></span> <span data-ttu-id="1b15c-106">Este cambio se anunció anteriormente a través del soporte técnico de Microsoft en [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="1b15c-106">This change was previously announced through Microsoft Support in [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

<span data-ttu-id="1b15c-107">La seguridad de los datos es importante y estamos comprometidos con la transparencia sobre los cambios que podrían afectar al uso del servicio.</span><span class="sxs-lookup"><span data-stu-id="1b15c-107">The security of your data is important, and we are committed to transparency about changes that could affect your use of the service.</span></span>

<span data-ttu-id="1b15c-108">Aunque la [implementación de Microsoft TLS 1.0](https://support.microsoft.com/help/3117336) no tiene vulnerabilidades de seguridad conocidas, seguimos comprometidos con los estándares de cumplimiento de FedRAMP.</span><span class="sxs-lookup"><span data-stu-id="1b15c-108">Although the [Microsoft TLS 1.0 implementation](https://support.microsoft.com/help/3117336) has no known security vulnerabilities, we remain committed to the FedRAMP compliance standards.</span></span> <span data-ttu-id="1b15c-109">Por lo tanto, deshabilitamos TLS 1.1 y 1.0 en Microsoft 365 en entornos GCC High y DoD el 15 de enero de 2020.</span><span class="sxs-lookup"><span data-stu-id="1b15c-109">Therefore, we disabled TLS 1.1 and 1.0 in Microsoft 365 in GCC High and DoD environments on January 15, 2020.</span></span> <span data-ttu-id="1b15c-110">Para obtener información sobre cómo quitar dependencias de TLS 1.1 y 1.0, consulte las siguientes instrucciones:</span><span class="sxs-lookup"><span data-stu-id="1b15c-110">For information about how to remove TLS 1.1 and 1.0 dependencies, see the following white paper:</span></span>

[<span data-ttu-id="1b15c-111">Solución del problema tls 1.0</span><span class="sxs-lookup"><span data-stu-id="1b15c-111">Solving the TLS 1.0 problem</span></span>](https://www.microsoft.com/download/details.aspx?id=55266)

## <a name="more-information"></a><span data-ttu-id="1b15c-112">Más información</span><span class="sxs-lookup"><span data-stu-id="1b15c-112">More information</span></span>

<span data-ttu-id="1b15c-113">A partir del 15 de enero de 2020, Microsoft 365 en los entornos GCC High y DoD deshabilitará TLS 1.1 y 1.0.</span><span class="sxs-lookup"><span data-stu-id="1b15c-113">Starting on January 15, 2020, Microsoft 365 in the GCC High and DoD environments will disable TLS 1.1 and 1.0.</span></span>

<span data-ttu-id="1b15c-114">Para el 15 de enero de 2020, todas las combinaciones de servidores cliente y servidores de explorador deben usar TLS versión 1.2 (o una versión posterior) para asegurarse de que todas las conexiones se pueden realizar sin problemas con Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1b15c-114">By January 15, 2020, all combinations of client servers and browser servers should use TLS version 1.2 (or a later version) to make sure that all connections can be made without issues to Microsoft 365.</span></span> <span data-ttu-id="1b15c-115">Esto puede requerir actualizaciones de determinadas combinaciones de servidores cliente y servidores de explorador.</span><span class="sxs-lookup"><span data-stu-id="1b15c-115">This may require updates to certain combinations of client servers and browser servers.</span></span>

<span data-ttu-id="1b15c-116">Para SharePoint y OneDrive, deberá actualizar y configurar .NET para admitir TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="1b15c-116">For SharePoint and OneDrive, you'll need to update and configure .NET to support TLS 1.2.</span></span> <span data-ttu-id="1b15c-117">Para obtener información, [vea How to enable TLS 1.2 on clients](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span><span class="sxs-lookup"><span data-stu-id="1b15c-117">For information, see [How to enable TLS 1.2 on clients](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span>

<span data-ttu-id="1b15c-118">Debe actualizar los equipos cliente para asegurarse de mantener el acceso ininterrumpido a Office 365 GCC High y DoD.</span><span class="sxs-lookup"><span data-stu-id="1b15c-118">You must update your client computers to make sure that you maintain uninterrupted access to Office 365 GCC High and DoD.</span></span>

<span data-ttu-id="1b15c-119">Deberá actualizar las aplicaciones que llaman a las API de Microsoft 365 a través de TLS 1.0 o TLS 1.1 para usar TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="1b15c-119">You'll need to update applications that call Microsoft 365 APIs over TLS 1.0 or TLS 1.1 to use TLS 1.2.</span></span> <span data-ttu-id="1b15c-120">.NET 4.5 tiene como valor predeterminado TLS 1.1.</span><span class="sxs-lookup"><span data-stu-id="1b15c-120">.NET 4.5 defaults to TLS 1.1.</span></span> <span data-ttu-id="1b15c-121">Para actualizar la configuración de .NET, vea [How to enable Transport Layer Security (TLS) 1.2 on clients](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span><span class="sxs-lookup"><span data-stu-id="1b15c-121">To update your .NET configuration, see [How to enable Transport Layer Security (TLS) 1.2 on clients](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span> <span data-ttu-id="1b15c-122">Para obtener más información, vea [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="1b15c-122">For more information, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

<span data-ttu-id="1b15c-123">Sabemos que las siguientes aplicaciones cliente no pueden usar TLS 1.2:</span><span class="sxs-lookup"><span data-stu-id="1b15c-123">We know that the following client applications cannot use TLS 1.2:</span></span>

- <span data-ttu-id="1b15c-124">Android 4.3 y versiones anteriores</span><span class="sxs-lookup"><span data-stu-id="1b15c-124">Android 4.3 and earlier versions</span></span>
- <span data-ttu-id="1b15c-125">Firefox versión 5.0 y versiones anteriores</span><span class="sxs-lookup"><span data-stu-id="1b15c-125">Firefox version 5.0 and earlier versions</span></span>
- <span data-ttu-id="1b15c-126">Internet Explorer 8–10 en Windows 7 y versiones anteriores</span><span class="sxs-lookup"><span data-stu-id="1b15c-126">Internet Explorer 8–10 on Windows 7 and earlier versions</span></span>
- <span data-ttu-id="1b15c-127">Internet Explorer 10 en Windows Phone 8.0</span><span class="sxs-lookup"><span data-stu-id="1b15c-127">Internet Explorer 10 on Windows Phone 8.0</span></span>
- <span data-ttu-id="1b15c-128">Safari 6.0.4/OS X 10.8.4 y versiones anteriores</span><span class="sxs-lookup"><span data-stu-id="1b15c-128">Safari 6.0.4/OS X 10.8.4 and earlier versions</span></span>

<span data-ttu-id="1b15c-129">Aunque el análisis actual de las conexiones a los servicios de Microsoft Online muestra que la mayoría de los servicios y puntos de conexión ven muy poco uso de TLS 1.1 y 1.0, estamos dando aviso de este cambio para que pueda actualizar los clientes o servidores afectados según sea necesario antes de que finalice la compatibilidad con TLS 1.1 y 1.0.</span><span class="sxs-lookup"><span data-stu-id="1b15c-129">Although current analysis of connections to Microsoft Online services shows that most services and endpoints see very little TLS 1.1 and 1.0 usage, we're providing notice of this change so that you can update any affected clients or servers as necessary before support for TLS 1.1 and 1.0 ends.</span></span> <span data-ttu-id="1b15c-130">Si usa alguna infraestructura local para escenarios híbridos o servicios de federación de Active Directory (AD FS), asegúrese de que la infraestructura puede admitir conexiones entrantes y salientes que usen TLS 1.2 (o una versión posterior).</span><span class="sxs-lookup"><span data-stu-id="1b15c-130">If you are using any on-premises infrastructure for hybrid scenarios or Active Directory Federation Services (AD FS), make sure that the infrastructure can support both inbound and outbound connections that use TLS 1.2 (or a later version).</span></span>

<span data-ttu-id="1b15c-131">Además de las interrupciones que puede experimentar si usa los clientes enumerados que no pueden usar TLS 1.2, quitar TLS 1.1 y 1.0 le impedirá usar el siguiente producto de Microsoft:</span><span class="sxs-lookup"><span data-stu-id="1b15c-131">In addition to the outages that you might experience if you use the listed clients that cannot use TLS 1.2, removing TLS 1.1 and 1.0 will prevent you from being able to use the following Microsoft product:</span></span>

- <span data-ttu-id="1b15c-132">Teléfono Lync</span><span class="sxs-lookup"><span data-stu-id="1b15c-132">Lync phone</span></span>

## <a name="references"></a><span data-ttu-id="1b15c-133">Referencias</span><span class="sxs-lookup"><span data-stu-id="1b15c-133">References</span></span>

<span data-ttu-id="1b15c-134">Para obtener instrucciones y referencias para asegurarse de que los clientes usan TLS 1.2, vea [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="1b15c-134">For guidance and references to help make sure that your clients are using TLS 1.2, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>