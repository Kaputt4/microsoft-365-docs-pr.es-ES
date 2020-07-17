---
title: Desuso de TLS 1,0 y 1,1 en Office 365 GCC High y DoD
description: Describe cómo Microsoft pasa la fecha hacia adelante para descontinuar la compatibilidad con TLS 1,1 y 1,0 en los entornos altos y DoD de GCC en Office 365 y preparar el uso de TLS 1,2.
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
ms.openlocfilehash: 76e9b203e58ba7fa23942ea42810456e3bee377d
ms.sourcegitcommit: 42b618231e9f608f3ae7226a313b0366601d0ea2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/17/2020
ms.locfileid: "45158885"
---
# <a name="deprecating-tls-10-and-11-in-office-365-gcc-high-and-dod"></a><span data-ttu-id="1c146-103">Desuso de TLS 1,0 y 1,1 en Office 365 GCC High y DoD</span><span class="sxs-lookup"><span data-stu-id="1c146-103">Deprecating TLS 1.0 and 1.1 in Office 365 GCC High and DoD</span></span>

## <a name="summary"></a><span data-ttu-id="1c146-104">Resumen</span><span class="sxs-lookup"><span data-stu-id="1c146-104">Summary</span></span>

<span data-ttu-id="1c146-105">Para cumplir con los últimos estándares de cumplimiento para el programa de administración de riesgos y autorización Federal (FedRAMP), estamos descartando las versiones 1,1 y 1,0 de seguridad de la capa de transporte (TLS) en Microsoft Office 365 para los entornos de GCC altos y DoD.</span><span class="sxs-lookup"><span data-stu-id="1c146-105">In order to comply with the latest compliance standards for the Federal Risk and Authorization Management Program (FedRAMP), we are deprecating Transport Layer Security (TLS) versions 1.1 and 1.0 in Microsoft Office 365 for GCC High and DoD environments.</span></span> <span data-ttu-id="1c146-106">Este cambio se anunció anteriormente a través del soporte técnico de Microsoft [para preparar el uso obligatorio de TLS 1,2 en Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="1c146-106">This change was previously announced through Microsoft Support in [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

<span data-ttu-id="1c146-107">La seguridad de los datos es importante y estamos comprometidos con la transparencia de los cambios que puedan afectar al uso del servicio.</span><span class="sxs-lookup"><span data-stu-id="1c146-107">The security of your data is important, and we are committed to transparency about changes that could affect your use of the service.</span></span>

<span data-ttu-id="1c146-108">Aunque la [implementación de Microsoft TLS 1,0](https://support.microsoft.com/help/3117336) no tiene vulnerabilidades de seguridad conocidas, seguimos comprometidos con los estándares de cumplimiento de FedRAMP.</span><span class="sxs-lookup"><span data-stu-id="1c146-108">Although the [Microsoft TLS 1.0 implementation](https://support.microsoft.com/help/3117336) has no known security vulnerabilities, we remain committed to the FedRAMP compliance standards.</span></span> <span data-ttu-id="1c146-109">Por lo tanto, se dejará de usar TLS 1,1 y 1,0 en Office 365 en los entornos alto y DoD de GCC a partir del 15 de enero de 2020.</span><span class="sxs-lookup"><span data-stu-id="1c146-109">Therefore, we will deprecate TLS 1.1 and 1.0 in Office 365 in GCC High and DoD environments starting on January 15, 2020.</span></span> <span data-ttu-id="1c146-110">Para obtener información acerca de cómo quitar dependencias TLS 1,1 y 1,0, consulte las siguientes notas del producto:</span><span class="sxs-lookup"><span data-stu-id="1c146-110">For information about how to remove TLS 1.1 and 1.0 dependencies, see the following white paper:</span></span>

[<span data-ttu-id="1c146-111">Solución del problema de TLS 1,0</span><span class="sxs-lookup"><span data-stu-id="1c146-111">Solving the TLS 1.0 problem</span></span>](https://www.microsoft.com/download/details.aspx?id=55266)

<span data-ttu-id="1c146-112">Al preparar este cambio para TLS 1,1 y 1,0, recomendamos que use TLS versión 1,2 en su lugar.</span><span class="sxs-lookup"><span data-stu-id="1c146-112">In preparing for this change for TLS 1.1 and 1.0, we recommend that you use TLS version 1.2 instead.</span></span> <span data-ttu-id="1c146-113">Para obtener más información, vea [preparación para el uso obligatorio de TLS 1,2 en Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="1c146-113">For more information, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

## <a name="more-information"></a><span data-ttu-id="1c146-114">Más información</span><span class="sxs-lookup"><span data-stu-id="1c146-114">More information</span></span>

<span data-ttu-id="1c146-115">A partir del 15 de enero de 2020, Office 365 en los entornos alto y DoD de GCC dejará de estar en desuso las características TLS 1,1 y 1,0.</span><span class="sxs-lookup"><span data-stu-id="1c146-115">Starting on January 15, 2020, Office 365 in the GCC High and DoD environments will deprecate TLS 1.1 and 1.0.</span></span>

<span data-ttu-id="1c146-116">Por el 15 de enero de 2020, todas las combinaciones de servidores cliente y servidores de explorador deben usar TLS versión 1,2 (o una versión posterior) para asegurarse de que se pueden realizar todas las conexiones sin problemas con los servicios de Office 365.</span><span class="sxs-lookup"><span data-stu-id="1c146-116">By January 15, 2020, all combinations of client servers and browser servers should use TLS version 1.2 (or a later version) to make sure that all connections can be made without issues to Office 365 services.</span></span> <span data-ttu-id="1c146-117">Esto puede requerir actualizaciones a determinadas combinaciones de servidores cliente y servidores de explorador.</span><span class="sxs-lookup"><span data-stu-id="1c146-117">This may require updates to certain combinations of client servers and browser servers.</span></span>

<span data-ttu-id="1c146-118">Si no actualiza a la versión 1,2 de TLS (o a una versión posterior) antes del 15 de enero de 2020, tendrá problemas cuando intente conectarse a Office 365.</span><span class="sxs-lookup"><span data-stu-id="1c146-118">If you do not update to TLS version 1.2 (or a later version) by January 15, 2020, you will experience issues when you try to connect to Office 365.</span></span> <span data-ttu-id="1c146-119">Además, se le pedirá que actualice a TLS 1,2 (o una versión posterior) como parte de la solución.</span><span class="sxs-lookup"><span data-stu-id="1c146-119">Additionally, you will be required to update to TLS 1.2 (or a later version) as part of the resolution.</span></span>

<span data-ttu-id="1c146-120">Sabemos que los siguientes clientes no pueden usar TLS 1,2:</span><span class="sxs-lookup"><span data-stu-id="1c146-120">We know that the following clients cannot use TLS 1.2:</span></span>

- <span data-ttu-id="1c146-121">Android 4.3 y versiones anteriores</span><span class="sxs-lookup"><span data-stu-id="1c146-121">Android 4.3 and earlier versions</span></span>
- <span data-ttu-id="1c146-122">Firefox versión 5.0 y versiones anteriores</span><span class="sxs-lookup"><span data-stu-id="1c146-122">Firefox version 5.0 and earlier versions</span></span>
- <span data-ttu-id="1c146-123">Internet Explorer 8 – 10 en Windows 7 y versiones anteriores</span><span class="sxs-lookup"><span data-stu-id="1c146-123">Internet Explorer 8–10 on Windows 7 and earlier versions</span></span>
- <span data-ttu-id="1c146-124">Internet Explorer 10 en Windows Phone 8,0</span><span class="sxs-lookup"><span data-stu-id="1c146-124">Internet Explorer 10 on Windows Phone 8.0</span></span>
- <span data-ttu-id="1c146-125">Safari 6.0.4/OS X 10.8.4 y versiones anteriores</span><span class="sxs-lookup"><span data-stu-id="1c146-125">Safari 6.0.4/OS X 10.8.4 and earlier versions</span></span>

<span data-ttu-id="1c146-126">Le recomendamos que actualice los clientes para asegurarse de que mantiene un acceso ininterrumpido a Office 365 GCC High y DoD.</span><span class="sxs-lookup"><span data-stu-id="1c146-126">We recommend that you update your clients to make sure that you maintain uninterrupted access to Office 365 GCC High and DoD.</span></span>

<span data-ttu-id="1c146-127">Aunque el análisis actual de las conexiones a Microsoft Online Services muestra que la mayoría de los servicios y extremos ven muy poco TLS 1,1 y el uso de 1,0, hemos proporcionado este cambio para que pueda actualizar los clientes o servidores afectados según sea necesario antes de que finalice la compatibilidad con TLS 1,1 y 1,0.</span><span class="sxs-lookup"><span data-stu-id="1c146-127">Although current analysis of connections to Microsoft Online services shows that most services and endpoints see very little TLS 1.1 and 1.0 usage, we are providing notice of this change so that you can update any affected clients or servers as necessary before support for TLS 1.1 and 1.0 ends.</span></span> <span data-ttu-id="1c146-128">Si usa una infraestructura local para entornos híbridos o servicios de Federación de Active Directory (AD FS), asegúrese de que la infraestructura puede admitir conexiones entrantes y salientes que usen TLS 1,2 (o una versión posterior).</span><span class="sxs-lookup"><span data-stu-id="1c146-128">If you are using any on-premises infrastructure for hybrid scenarios or Active Directory Federation Services (AD FS), make sure that the infrastructure can support both inbound and outbound connections that use TLS 1.2 (or a later version).</span></span>

<span data-ttu-id="1c146-129">Además de las interrupciones que puede experimentar si usa los clientes enumerados que no pueden usar TLS 1,2, quitar TLS 1,1 y 1,0 le impedirá usar el siguiente producto de Microsoft:</span><span class="sxs-lookup"><span data-stu-id="1c146-129">In addition to the outages that you might experience if you use the listed clients that cannot use TLS 1.2, removing TLS 1.1 and 1.0 will prevent you from being able to use the following Microsoft product:</span></span>

- <span data-ttu-id="1c146-130">Lync Phone</span><span class="sxs-lookup"><span data-stu-id="1c146-130">Lync phone</span></span>

## <a name="references"></a><span data-ttu-id="1c146-131">Referencias</span><span class="sxs-lookup"><span data-stu-id="1c146-131">References</span></span>

<span data-ttu-id="1c146-132">El siguiente artículo de soporte técnico describe las instrucciones y referencias que le ayudarán a asegurarse de que los clientes usan TLS 1,2:</span><span class="sxs-lookup"><span data-stu-id="1c146-132">The following support article describes guidance and references to help make sure that your clients are using TLS 1.2:</span></span>

[<span data-ttu-id="1c146-133">Preparación del uso obligatorio de TLS 1,2 en Office 365</span><span class="sxs-lookup"><span data-stu-id="1c146-133">Preparing for the mandatory use of TLS 1.2 in Office 365</span></span>](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
