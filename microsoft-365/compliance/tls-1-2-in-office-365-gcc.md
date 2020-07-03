---
title: Desuso de TLS 1,0 y 1,1 en Office 365 GCC High y DoD
description: Describe cómo Microsoft pasa la fecha hacia adelante para descontinuar la compatibilidad con TLS 1,1 y 1,0 en los entornos altos y DoD de GCC en Office 365 y preparar el uso de TLS 1,2.
author: simonxjx
manager: dcscontentpm
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: v-six
ms.reviewer: lobrion
appliesto:
- Office 365 Business
ms.openlocfilehash: f61c0a809c4666981ee0f2d67eea21474b83a675
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024842"
---
# <a name="deprecating-tls-10-and-11-in-office-365-gcc-high-and-dod"></a><span data-ttu-id="71e26-103">Desuso de TLS 1,0 y 1,1 en Office 365 GCC High y DoD</span><span class="sxs-lookup"><span data-stu-id="71e26-103">Deprecating TLS 1.0 and 1.1 in Office 365 GCC High and DoD</span></span>

> [!IMPORTANT]
> <span data-ttu-id="71e26-104">El mundo se encuentra inmerso en una pandemia, y en Microsoft somos conscientes de las repercusiones para nuestros clientes y socios.</span><span class="sxs-lookup"><span data-stu-id="71e26-104">The world is in the middle of a pandemic, and we at Microsoft are aware of the impact on our customers and partners.</span></span> <span data-ttu-id="71e26-105">Para aligerar la carga de nuestros clientes comerciales, hemos detenido temporalmente el cumplimiento de la obsolescencia de TLS 1.0 y 1.1.</span><span class="sxs-lookup"><span data-stu-id="71e26-105">To lighten the burden on our commercial customers, we have temporarily halted any deprecation enforcement of TLS 1.0 and 1.1.</span></span> <span data-ttu-id="71e26-106">Una vez que se estabilice la situación actual, enviaremos una actualización con una escala de tiempo revisada.</span><span class="sxs-lookup"><span data-stu-id="71e26-106">An update will be sent on a revised timeline after the current crisis stabilizes.</span></span> <span data-ttu-id="71e26-107">(Este artículo se ha corregido para reflejar el cambio).</span><span class="sxs-lookup"><span data-stu-id="71e26-107">(This article is revised to reflect the change.)</span></span>

## <a name="summary"></a><span data-ttu-id="71e26-108">Resumen</span><span class="sxs-lookup"><span data-stu-id="71e26-108">Summary</span></span>

<span data-ttu-id="71e26-109">Para cumplir con los últimos estándares de cumplimiento del programa federal de administración de riesgos y autorización (FedRAMP), estamos pasando a desuso de las versiones 1,1 y 1,0 de seguridad de la capa de transporte (TLS) en Microsoft Office 365 para los entornos de GCC altos y DoD.</span><span class="sxs-lookup"><span data-stu-id="71e26-109">In order to comply with the latest compliance standards for the Federal Risk and Authorization Management Program (FedRAMP), we are moving to deprecate Transport Layer Security (TLS) versions 1.1 and 1.0 in Microsoft Office 365 for GCC High and DoD environments.</span></span> <span data-ttu-id="71e26-110">Este cambio se anunció anteriormente a través del soporte técnico de Microsoft [para preparar el uso obligatorio de TLS 1,2 en Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="71e26-110">This change was previously announced through Microsoft Support in [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

<span data-ttu-id="71e26-111">Somos conscientes de que la seguridad de los datos es importante y estamos comprometidos con la transparencia de los cambios que puedan afectar al uso del servicio.</span><span class="sxs-lookup"><span data-stu-id="71e26-111">We understand that the security of your data is important, and we are committed to transparency about changes that could affect your use of the service.</span></span>

<span data-ttu-id="71e26-112">Aunque la [implementación de Microsoft TLS 1,0](https://support.microsoft.com/help/3117336) no tiene vulnerabilidades de seguridad conocidas, seguimos comprometidos con los estándares de cumplimiento de FedRAMP.</span><span class="sxs-lookup"><span data-stu-id="71e26-112">Although the [Microsoft TLS 1.0 implementation](https://support.microsoft.com/help/3117336) has no known security vulnerabilities, we remain committed to the FedRAMP compliance standards.</span></span> <span data-ttu-id="71e26-113">Por lo tanto, se dejará de usar TLS 1,1 y 1,0 en Office 365 en los entornos alto y DoD de GCC a partir del 15 de enero de 2020.</span><span class="sxs-lookup"><span data-stu-id="71e26-113">Therefore, we will deprecate TLS 1.1 and 1.0 in Office 365 in GCC High and DoD environments starting on January 15, 2020.</span></span> <span data-ttu-id="71e26-114">Para obtener información acerca de cómo quitar dependencias TLS 1,1 y 1,0, consulte las siguientes notas del producto:</span><span class="sxs-lookup"><span data-stu-id="71e26-114">For information about how to remove TLS 1.1 and 1.0 dependencies, see the following white paper:</span></span>

[<span data-ttu-id="71e26-115">Solución del problema de TLS 1,0</span><span class="sxs-lookup"><span data-stu-id="71e26-115">Solving the TLS 1.0 problem</span></span>](https://www.microsoft.com/download/details.aspx?id=55266)

<span data-ttu-id="71e26-116">Al preparar este cambio para TLS 1,1 y 1,0, recomendamos que use TLS versión 1,2 en su lugar.</span><span class="sxs-lookup"><span data-stu-id="71e26-116">In preparing for this change for TLS 1.1 and 1.0, we recommend that you use TLS version 1.2 instead.</span></span> <span data-ttu-id="71e26-117">Para obtener más información, vea [preparación para el uso obligatorio de TLS 1,2 en Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="71e26-117">For more information, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>

## <a name="more-information"></a><span data-ttu-id="71e26-118">Más información</span><span class="sxs-lookup"><span data-stu-id="71e26-118">More information</span></span>

<span data-ttu-id="71e26-119">A partir del 15 de enero de 2020, Office 365 en los entornos alto y DoD de GCC dejará de estar en desuso las características TLS 1,1 y 1,0.</span><span class="sxs-lookup"><span data-stu-id="71e26-119">Starting on January 15, 2020, Office 365 in the GCC High and DoD environments will deprecate TLS 1.1 and 1.0.</span></span>

<span data-ttu-id="71e26-120">Por el 15 de enero de 2020, todas las combinaciones de servidores cliente y servidores de explorador deben usar TLS versión 1,2 (o una versión posterior) para asegurarse de que se pueden realizar todas las conexiones sin problemas con los servicios de Office 365.</span><span class="sxs-lookup"><span data-stu-id="71e26-120">By January 15, 2020, all combinations of client servers and browser servers should use TLS version 1.2 (or a later version) to make sure that all connections can be made without issues to Office 365 services.</span></span> <span data-ttu-id="71e26-121">Esto puede requerir actualizaciones a determinadas combinaciones de servidores cliente y servidores de explorador.</span><span class="sxs-lookup"><span data-stu-id="71e26-121">This may require updates to certain combinations of client servers and browser servers.</span></span>

<span data-ttu-id="71e26-122">Si no actualiza a la versión 1,2 de TLS (o a una versión posterior) antes del 15 de enero de 2020, tendrá problemas cuando intente conectarse a Office 365.</span><span class="sxs-lookup"><span data-stu-id="71e26-122">If you do not update to TLS version 1.2 (or a later version) by January 15, 2020, you will experience issues when you try to connect to Office 365.</span></span> <span data-ttu-id="71e26-123">Además, se le pedirá que actualice a TLS 1,2 (o una versión posterior) como parte de la solución.</span><span class="sxs-lookup"><span data-stu-id="71e26-123">Additionally, you will be required to update to TLS 1.2 (or a later version) as part of the resolution.</span></span>

<span data-ttu-id="71e26-124">Sabemos que los siguientes clientes no pueden usar TLS 1,2:</span><span class="sxs-lookup"><span data-stu-id="71e26-124">We know that the following clients cannot use TLS 1.2:</span></span>

- <span data-ttu-id="71e26-125">Android 4.3 y versiones anteriores</span><span class="sxs-lookup"><span data-stu-id="71e26-125">Android 4.3 and earlier versions</span></span>
- <span data-ttu-id="71e26-126">Firefox versión 5.0 y versiones anteriores</span><span class="sxs-lookup"><span data-stu-id="71e26-126">Firefox version 5.0 and earlier versions</span></span>
- <span data-ttu-id="71e26-127">Internet Explorer 8 – 10 en Windows 7 y versiones anteriores</span><span class="sxs-lookup"><span data-stu-id="71e26-127">Internet Explorer 8–10 on Windows 7 and earlier versions</span></span>
- <span data-ttu-id="71e26-128">Internet Explorer 10 en Windows Phone 8,0</span><span class="sxs-lookup"><span data-stu-id="71e26-128">Internet Explorer 10 on Windows Phone 8.0</span></span>
- <span data-ttu-id="71e26-129">Safari 6.0.4/OS X 10.8.4 y versiones anteriores</span><span class="sxs-lookup"><span data-stu-id="71e26-129">Safari 6.0.4/OS X 10.8.4 and earlier versions</span></span>

<span data-ttu-id="71e26-130">Le recomendamos que actualice los clientes para asegurarse de que mantiene un acceso ininterrumpido a Office 365 GCC High y DoD.</span><span class="sxs-lookup"><span data-stu-id="71e26-130">We recommend that you update your clients to make sure that you maintain uninterrupted access to Office 365 GCC High and DoD.</span></span>

<span data-ttu-id="71e26-131">Aunque el análisis actual de las conexiones a Microsoft Online Services muestra que la mayoría de los servicios y extremos ven muy poco TLS 1,1 y el uso de 1,0, hemos proporcionado este cambio para que pueda actualizar los clientes o servidores afectados según sea necesario antes de que finalice la compatibilidad con TLS 1,1 y 1,0.</span><span class="sxs-lookup"><span data-stu-id="71e26-131">Although current analysis of connections to Microsoft Online services shows that most services and endpoints see very little TLS 1.1 and 1.0 usage, we are providing notice of this change so that you can update any affected clients or servers as necessary before support for TLS 1.1 and 1.0 ends.</span></span> <span data-ttu-id="71e26-132">Si usa una infraestructura local para entornos híbridos o servicios de Federación de Active Directory (AD FS), asegúrese de que la infraestructura puede admitir conexiones entrantes y salientes que usen TLS 1,2 (o una versión posterior).</span><span class="sxs-lookup"><span data-stu-id="71e26-132">If you are using any on-premises infrastructure for hybrid scenarios or Active Directory Federation Services (AD FS), make sure that the infrastructure can support both inbound and outbound connections that use TLS 1.2 (or a later version).</span></span>

<span data-ttu-id="71e26-133">Además de las interrupciones que puede experimentar si usa los clientes enumerados que no pueden usar TLS 1,2, quitar TLS 1,1 y 1,0 le impedirá usar el siguiente producto de Microsoft:</span><span class="sxs-lookup"><span data-stu-id="71e26-133">In addition to the outages that you might experience if you use the listed clients that cannot use TLS 1.2, removing TLS 1.1 and 1.0 will prevent you from being able to use the following Microsoft product:</span></span>

- <span data-ttu-id="71e26-134">Lync Phone</span><span class="sxs-lookup"><span data-stu-id="71e26-134">Lync phone</span></span>

## <a name="references"></a><span data-ttu-id="71e26-135">Referencias</span><span class="sxs-lookup"><span data-stu-id="71e26-135">References</span></span>

<span data-ttu-id="71e26-136">El siguiente artículo de soporte técnico describe las instrucciones y referencias que le ayudarán a asegurarse de que los clientes usan TLS 1,2:</span><span class="sxs-lookup"><span data-stu-id="71e26-136">The following support article describes guidance and references to help make sure that your clients are using TLS 1.2:</span></span>

[<span data-ttu-id="71e26-137">Preparación del uso obligatorio de TLS 1,2 en Office 365</span><span class="sxs-lookup"><span data-stu-id="71e26-137">Preparing for the mandatory use of TLS 1.2 in Office 365</span></span>](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
