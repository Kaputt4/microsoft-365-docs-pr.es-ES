---
title: Desuso de TLS 1.0 y 1.1 para Office 365
description: Describe el desuso de TLS 1,0 y 1,1 para Office 365.
author: workshay
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: shmehta
ms.reviewer: krowley
appliesto:
- Microsoft 365 Apps for enterprise
- Office 365 Business
- Office 365 Personal
- Office Online Server
- Office Web Apps
ms.openlocfilehash: 622d783011defcf9c84061087b7d05f2a117172e
ms.sourcegitcommit: 3bf4f1c0d3a8515cca651b2a520217195f89457f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2021
ms.locfileid: "49777063"
---
# <a name="tls-10-and-11-deprecation-for-office-365"></a><span data-ttu-id="09774-103">Desuso de TLS 1.0 y 1.1 para Office 365</span><span class="sxs-lookup"><span data-stu-id="09774-103">TLS 1.0 and 1.1 deprecation for Office 365</span></span>
> [!IMPORTANT]
> <span data-ttu-id="09774-104">Se ha detenido temporalmente la aplicación de la degradación de TLS 1,0 y 1,1 para los clientes comerciales debido a la COVID-19, pero a medida que se han ajustado las cadenas de suministro y que algunos países han abierto la copia de seguridad, estamos restableciendo el cumplimiento de TLS para que comience el 15 de octubre de 2020 y la implementación continuará durante las siguientes semanas y meses.</span><span class="sxs-lookup"><span data-stu-id="09774-104">We temporarily halted deprecation enforcement of TLS 1.0 and 1.1 for commercial customers due to COVID-19, but as supply chains have adjusted and certain countries open back up, we are resetting the TLS enforcement to begin October 15, 2020, and rollout will continue over the following weeks and months.</span></span> 

<span data-ttu-id="09774-105">A partir del 31 de octubre de 2018, los protocolos de seguridad de la capa de transporte (TLS) 1,0 y 1,1 están en desuso para el servicio de Office 365.</span><span class="sxs-lookup"><span data-stu-id="09774-105">As of October 31, 2018, the Transport Layer Security (TLS) 1.0 and 1.1 protocols are deprecated for the Office 365 service.</span></span> <span data-ttu-id="09774-106">Se espera que el efecto de los usuarios finales sea mínimo.</span><span class="sxs-lookup"><span data-stu-id="09774-106">The effect for end-users is expected to be minimal.</span></span> <span data-ttu-id="09774-107">Este cambio ha sido público durante más de dos años, con el primer anuncio público realizado en diciembre de 2017.</span><span class="sxs-lookup"><span data-stu-id="09774-107">This change has been publicized for over two years, with the first public announcement made in December 2017.</span></span> <span data-ttu-id="09774-108">Este artículo solo se diseñó para cubrir el cliente local de Office 365 en relación con el servicio Office 365, pero también se puede aplicar a problemas de TLS locales con Office y Office Online Server/Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="09774-108">This article is only intended to cover the Office 365 local client in relation to the Office 365 service but can also apply to on-premises TLS issues with Office and Office Online Server/Office Web Apps.</span></span>

## <a name="office-and-tls-overview"></a><span data-ttu-id="09774-109">Información general de Office y TLS</span><span class="sxs-lookup"><span data-stu-id="09774-109">Office and TLS overview</span></span>

<span data-ttu-id="09774-110">El cliente de Office se basa en el servicio Web de Windows (WINHTTP) para enviar y recibir tráfico a través de protocolos TLS.</span><span class="sxs-lookup"><span data-stu-id="09774-110">The Office client relies on the Windows web service (WINHTTP) to send and receive traffic over TLS protocols.</span></span> <span data-ttu-id="09774-111">El cliente de Office puede usar TLS 1,2 Si el servicio Web del equipo local puede usar TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="09774-111">The Office client can use TLS 1.2 if the web service of the local computer can use TLS 1.2.</span></span> <span data-ttu-id="09774-112">Todos los clientes de Office pueden usar protocolos TLS, ya que los protocolos TLS y SSL forman parte del sistema operativo y no son específicos del cliente de Office.</span><span class="sxs-lookup"><span data-stu-id="09774-112">All Office clients can use TLS protocols, as TLS and SSL protocols are part of the operating system and not specific to the Office client.</span></span>

### <a name="on-windows-8-and-later-versions"></a><span data-ttu-id="09774-113">En Windows 8 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="09774-113">On Windows 8 and later versions</span></span>

<span data-ttu-id="09774-114">De forma predeterminada, los protocolos TLS 1,2 y 1,1 están disponibles si no hay ningún dispositivo de red configurado para rechazar el tráfico de TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="09774-114">By default, the TLS 1.2 and 1.1 protocols are available if no network devices are configured to reject TLS 1.2 traffic.</span></span>

### <a name="on-windows-7"></a><span data-ttu-id="09774-115">En Windows 7</span><span class="sxs-lookup"><span data-stu-id="09774-115">On Windows 7</span></span>

<span data-ttu-id="09774-116">Los protocolos TLS 1,1 y 1,2 no están disponibles sin la actualización [KB 3140245](https://support.microsoft.com/help/3140245) .</span><span class="sxs-lookup"><span data-stu-id="09774-116">TLS 1.1 and 1.2 protocols are not available without the [KB 3140245](https://support.microsoft.com/help/3140245) update.</span></span> <span data-ttu-id="09774-117">La actualización soluciona este problema y agrega la siguiente subclave del registro:</span><span class="sxs-lookup"><span data-stu-id="09774-117">The update addresses this issue and adds the following registry sub key:</span></span>

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> <span data-ttu-id="09774-118">Los usuarios de Windows 7 que no tienen esta actualización se ven afectados desde el 31 de octubre de 2018.</span><span class="sxs-lookup"><span data-stu-id="09774-118">Windows 7 users who do not have this update are affected as of October 31, 2018.</span></span> <span data-ttu-id="09774-119">[KB 3140245](https://support.microsoft.com/help/3140245) tiene detalles sobre cómo cambiar la configuración de WinHTTP para habilitar los protocolos TLS.</span><span class="sxs-lookup"><span data-stu-id="09774-119">[KB 3140245](https://support.microsoft.com/help/3140245) has details about how to change WINHTTP settings to enable TLS protocols.</span></span>

#### <a name="more-information"></a><span data-ttu-id="09774-120">Más información</span><span class="sxs-lookup"><span data-stu-id="09774-120">More information</span></span>

<span data-ttu-id="09774-121">El valor de la clave del registro **DefaultSecureProtocols** que describe el artículo de KB determina qué protocolos de red se pueden usar:</span><span class="sxs-lookup"><span data-stu-id="09774-121">The value of the **DefaultSecureProtocols** registry key that the KB article describes determines which network protocols can be used:</span></span>

|<span data-ttu-id="09774-122">Valor DefaultSecureProtocols</span><span class="sxs-lookup"><span data-stu-id="09774-122">DefaultSecureProtocols Value</span></span>|<span data-ttu-id="09774-123">Protocolo habilitado</span><span class="sxs-lookup"><span data-stu-id="09774-123">Protocol enabled</span></span>|
|-|-|
|<span data-ttu-id="09774-124">0x00000008</span><span class="sxs-lookup"><span data-stu-id="09774-124">0x00000008</span></span>|<span data-ttu-id="09774-125">Habilita SSL 2.0 de manera predeterminada</span><span class="sxs-lookup"><span data-stu-id="09774-125">Enable SSL 2.0 by default</span></span>|
|<span data-ttu-id="09774-126">0x00000020</span><span class="sxs-lookup"><span data-stu-id="09774-126">0x00000020</span></span>|<span data-ttu-id="09774-127">Habilita SSL 3.0 de manera predeterminada</span><span class="sxs-lookup"><span data-stu-id="09774-127">Enable SSL 3.0 by default</span></span>|
|<span data-ttu-id="09774-128">0x00000080</span><span class="sxs-lookup"><span data-stu-id="09774-128">0x00000080</span></span>|<span data-ttu-id="09774-129">Habilita TLS 1.0 de manera predeterminada</span><span class="sxs-lookup"><span data-stu-id="09774-129">Enable TLS 1.0 by default</span></span>|
|<span data-ttu-id="09774-130">0x00000200</span><span class="sxs-lookup"><span data-stu-id="09774-130">0x00000200</span></span>|<span data-ttu-id="09774-131">Habilita TLS 1.1 de manera predeterminada</span><span class="sxs-lookup"><span data-stu-id="09774-131">Enable TLS 1.1 by default</span></span>|
|<span data-ttu-id="09774-132">0x00000800</span><span class="sxs-lookup"><span data-stu-id="09774-132">0x00000800</span></span>|<span data-ttu-id="09774-133">Habilita TLS 1.2 de manera predeterminada</span><span class="sxs-lookup"><span data-stu-id="09774-133">Enable TLS 1.2 by default</span></span>|

## <a name="office-clients-and-tls-registry-keys"></a><span data-ttu-id="09774-134">Clientes de Office y claves de registro de TLS</span><span class="sxs-lookup"><span data-stu-id="09774-134">Office clients and TLS registry keys</span></span>

<span data-ttu-id="09774-135">Puede consultar [KB 4057306 preparar el uso obligatorio de TLS 1,2 en Office 365](https://support.microsoft.com/help/4057306).</span><span class="sxs-lookup"><span data-stu-id="09774-135">You can refer to [KB 4057306 Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306).</span></span> <span data-ttu-id="09774-136">Este es un artículo general para los administradores de ti y es documentación oficial sobre el cambio de TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="09774-136">This is a general article for IT administrators, and it's official documentation about the TLS 1.2 change.</span></span>

<span data-ttu-id="09774-137">En la siguiente tabla se muestran los valores de clave del registro correspondientes en los clientes de Office 365 después del 31 de octubre de 2018.</span><span class="sxs-lookup"><span data-stu-id="09774-137">The following table shows the appropriate registry key values in Office 365 clients after October 31, 2018.</span></span>

|<span data-ttu-id="09774-138">Protocolos habilitados para el servicio de Office 365 después del 31 de octubre de 2018</span><span class="sxs-lookup"><span data-stu-id="09774-138">Enabled protocols for Office 365 service after October 31, 2018</span></span>|<span data-ttu-id="09774-139">Valor hexadecimal</span><span class="sxs-lookup"><span data-stu-id="09774-139">Hexadecimal value</span></span>|
|-|-|
|<span data-ttu-id="09774-140">TLS 1,0 + 1,1 + 1,2</span><span class="sxs-lookup"><span data-stu-id="09774-140">TLS 1.0 + 1.1 + 1.2</span></span>|<span data-ttu-id="09774-141">0x00000A80</span><span class="sxs-lookup"><span data-stu-id="09774-141">0x00000A80</span></span>|
|<span data-ttu-id="09774-142">TLS 1,1 + 1,2</span><span class="sxs-lookup"><span data-stu-id="09774-142">TLS 1.1 + 1.2</span></span>|<span data-ttu-id="09774-143">0x00000A00</span><span class="sxs-lookup"><span data-stu-id="09774-143">0x00000A00</span></span>|
|<span data-ttu-id="09774-144">TLS 1,0 + 1,2</span><span class="sxs-lookup"><span data-stu-id="09774-144">TLS 1.0 + 1.2</span></span>|<span data-ttu-id="09774-145">0x00000880</span><span class="sxs-lookup"><span data-stu-id="09774-145">0x00000880</span></span>|
|<span data-ttu-id="09774-146">TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="09774-146">TLS 1.2</span></span>|<span data-ttu-id="09774-147">0x00000800</span><span class="sxs-lookup"><span data-stu-id="09774-147">0x00000800</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="09774-148">No se recomienda usar los protocolos SSL 2,0 y 3,0, que también se pueden establecer mediante la clave **DefaultSecureProtocols** .</span><span class="sxs-lookup"><span data-stu-id="09774-148">We don't recommend that you use the SSL 2.0 and 3.0 protocols, which can also be set by using the **DefaultSecureProtocols** key.</span></span> <span data-ttu-id="09774-149">SSL 2,0 y 3,0 se consideran protocolos en desuso.</span><span class="sxs-lookup"><span data-stu-id="09774-149">SSL 2.0 and 3.0 are considered deprecated protocols.</span></span> <span data-ttu-id="09774-150">El procedimiento recomendado es finalizar el uso de SSL 2,0 y SSL 3,0, aunque la decisión de hacerlo en última instancia depende de lo que mejor se adapte a las necesidades del producto.</span><span class="sxs-lookup"><span data-stu-id="09774-150">The best practice is to end the use of SSL 2.0 and SSL 3.0, although the decision to do this ultimately depends on what best meets your product needs.</span></span> <span data-ttu-id="09774-151">Para obtener más información acerca de las vulnerabilidades de 3,0 de SSL, consulte [KB 3009008](https://support.microsoft.com/help/3009008).</span><span class="sxs-lookup"><span data-stu-id="09774-151">For more information about SSL 3.0 vulnerabilities, refer to [KB 3009008](https://support.microsoft.com/help/3009008).</span></span>

<span data-ttu-id="09774-152">Puede usar la calculadora de Windows predeterminada en el modo de programador para configurar los mismos valores de clave del registro de referencia.</span><span class="sxs-lookup"><span data-stu-id="09774-152">You can use the default Windows Calculator in Programmer mode to set up the same reference registry key values.</span></span> <span data-ttu-id="09774-153">Para obtener más información, consulte [KB 3140245 Update para habilitar tls 1,1 y tls 1,2 como protocolos seguros predeterminados en WinHTTP en Windows](https://support.microsoft.com/help/3140245).</span><span class="sxs-lookup"><span data-stu-id="09774-153">For more information, see [KB 3140245 Update to enable TLS 1.1 and TLS 1.2 as a default secure protocols in WinHTTP in Windows](https://support.microsoft.com/help/3140245).</span></span>

<span data-ttu-id="09774-154">Independientemente de si la actualización de Windows 7 ([KB 3140245](https://support.microsoft.com/help/3140245)) está instalada o no, la subclave del registro DefaultSecureProtocols no está presente y debe agregarse de forma manual o a través de un objeto de directiva de grupo (GPO).</span><span class="sxs-lookup"><span data-stu-id="09774-154">Regardless if the Windows 7 update ([KB 3140245](https://support.microsoft.com/help/3140245)) is installed or not, the DefaultSecureProtocols registry sub key isn't present and must be added manually or through a group policy object (GPO).</span></span> <span data-ttu-id="09774-155">Es decir, a menos que tenga que personalizar Qué protocolos seguros están habilitados o restringidos, esta clave no es necesaria.</span><span class="sxs-lookup"><span data-stu-id="09774-155">That is, unless you have to customize what secure protocols are enabled or restricted, this key is not required.</span></span> <span data-ttu-id="09774-156">Solo necesita la actualización de Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)).</span><span class="sxs-lookup"><span data-stu-id="09774-156">You only need the Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)) update.</span></span>
