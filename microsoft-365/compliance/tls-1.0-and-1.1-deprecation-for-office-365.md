---
title: Deshabilitar TLS 1.0 y 1.1 para Microsoft 365
description: Describe el desuso y la deshabilitación de TLS 1.0 y 1.1 para Microsoft 365.
author: workshay
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: fasqiu
ms.reviewer: krowley
appliesto:
- Microsoft 365 Apps for enterprise
- Office 365 Business
- Office 365 Personal
- Office Online Server
- Office Web Apps
ms.openlocfilehash: 669ab53739bfd108bdbe9077762272e6a4901865
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233102"
---
# <a name="disabling-tls-10-and-11-for-microsoft-365"></a><span data-ttu-id="1f12a-103">Deshabilitar TLS 1.0 y 1.1 para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1f12a-103">Disabling TLS 1.0 and 1.1 for Microsoft 365</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1f12a-104">Hemos detenido temporalmente la deshabilitación de TLS 1.0 y 1.1 para los clientes comerciales debido a COVID-19.</span><span class="sxs-lookup"><span data-stu-id="1f12a-104">We temporarily halted disablement of TLS 1.0 and 1.1 for commercial customers due to COVID-19.</span></span> <span data-ttu-id="1f12a-105">A medida que las cadenas de suministro se han ajustado y se abren algunos países, reiniciamos el lanzamiento de aplicación de TLS 1.2 el 15 de octubre de 2020.</span><span class="sxs-lookup"><span data-stu-id="1f12a-105">As supply chains have adjusted and certain countries open back up, we restarted the TLS 1.2 enforcement rollout on October 15, 2020.</span></span> <span data-ttu-id="1f12a-106">El lanzamiento continuará en las siguientes semanas y meses.</span><span class="sxs-lookup"><span data-stu-id="1f12a-106">Rollout will continue over the following weeks and months.</span></span>

<span data-ttu-id="1f12a-107">A partir del 31 de octubre de 2018, los protocolos Seguridad de la capa de transporte (TLS) 1.0 y 1.1 están en desuso para el servicio de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1f12a-107">As of October 31, 2018, the Transport Layer Security (TLS) 1.0 and 1.1 protocols are deprecated for the Microsoft 365 service.</span></span> <span data-ttu-id="1f12a-108">El efecto para los usuarios finales es mínimo.</span><span class="sxs-lookup"><span data-stu-id="1f12a-108">The effect for end-users is minimal.</span></span> <span data-ttu-id="1f12a-109">Este cambio se ha hecho público durante más de dos años, con el primer anuncio público realizado en diciembre de 2017.</span><span class="sxs-lookup"><span data-stu-id="1f12a-109">This change has been publicized for over two years, with the first public announcement made in December 2017.</span></span> <span data-ttu-id="1f12a-110">Este artículo solo está pensado para cubrir el cliente local de Office 365 en relación con el servicio de Office 365, pero también puede aplicarse a problemas de TLS locales con Office y Office Online Server/Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="1f12a-110">This article is only intended to cover the Office 365 local client in relation to the Office 365 service but can also apply to on-premises TLS issues with Office and Office Online Server/Office Web Apps.</span></span>

<span data-ttu-id="1f12a-111">Para SharePoint y OneDrive, tendrá que actualizar y configurar .NET para que admita TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="1f12a-111">For SharePoint and OneDrive, you'll need to update and configure .NET to support TLS 1.2.</span></span> <span data-ttu-id="1f12a-112">Para obtener información, [consulte Cómo habilitar TLS 1.2 en los clientes.](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)</span><span class="sxs-lookup"><span data-stu-id="1f12a-112">For information, see [How to enable TLS 1.2 on clients](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span>

## <a name="office-365-and-tls-overview"></a><span data-ttu-id="1f12a-113">Información general sobre Office 365 y TLS</span><span class="sxs-lookup"><span data-stu-id="1f12a-113">Office 365 and TLS overview</span></span>

<span data-ttu-id="1f12a-114">El cliente de Office se basa en el servicio web de Windows (WINHTTP) para enviar y recibir tráfico a través de protocolos TLS.</span><span class="sxs-lookup"><span data-stu-id="1f12a-114">The Office client relies on the Windows web service (WINHTTP) to send and receive traffic over TLS protocols.</span></span> <span data-ttu-id="1f12a-115">El cliente de Office puede usar TLS 1.2 si el servicio web del equipo local puede usar TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="1f12a-115">The Office client can use TLS 1.2 if the web service of the local computer can use TLS 1.2.</span></span> <span data-ttu-id="1f12a-116">Todos los clientes de Office pueden usar protocolos TLS, ya que los protocolos TLS y SSL forman parte del sistema operativo y no son específicos del cliente de Office.</span><span class="sxs-lookup"><span data-stu-id="1f12a-116">All Office clients can use TLS protocols, as TLS and SSL protocols are part of the operating system and not specific to the Office client.</span></span>

### <a name="on-windows-8-and-later-versions"></a><span data-ttu-id="1f12a-117">En Windows 8 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="1f12a-117">On Windows 8 and later versions</span></span>

<span data-ttu-id="1f12a-118">De forma predeterminada, los protocolos TLS 1.2 y 1.1 están disponibles si no hay ningún dispositivo de red configurado para rechazar el tráfico TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="1f12a-118">By default, the TLS 1.2 and 1.1 protocols are available if no network devices are configured to reject TLS 1.2 traffic.</span></span>

### <a name="on-windows-7"></a><span data-ttu-id="1f12a-119">En Windows 7</span><span class="sxs-lookup"><span data-stu-id="1f12a-119">On Windows 7</span></span>

<span data-ttu-id="1f12a-120">Los protocolos TLS 1.1 y 1.2 no están disponibles sin la actualización [kb 3140245.](https://support.microsoft.com/help/3140245)</span><span class="sxs-lookup"><span data-stu-id="1f12a-120">TLS 1.1 and 1.2 protocols are not available without the [KB 3140245](https://support.microsoft.com/help/3140245) update.</span></span> <span data-ttu-id="1f12a-121">La actualización soluciona este problema y agrega la siguiente subclave del Registro:</span><span class="sxs-lookup"><span data-stu-id="1f12a-121">The update addresses this issue and adds the following registry sub key:</span></span>

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> <span data-ttu-id="1f12a-122">Los usuarios de Windows 7 que no tengan esta actualización se verán afectados a partir del 31 de octubre de 2018.</span><span class="sxs-lookup"><span data-stu-id="1f12a-122">Windows 7 users who do not have this update are affected as of October 31, 2018.</span></span> <span data-ttu-id="1f12a-123">[KB 3140245](https://support.microsoft.com/help/3140245) tiene detalles sobre cómo cambiar la configuración de WINHTTP para habilitar protocolos TLS.</span><span class="sxs-lookup"><span data-stu-id="1f12a-123">[KB 3140245](https://support.microsoft.com/help/3140245) has details about how to change WINHTTP settings to enable TLS protocols.</span></span>

#### <a name="more-information"></a><span data-ttu-id="1f12a-124">Más información</span><span class="sxs-lookup"><span data-stu-id="1f12a-124">More information</span></span>

<span data-ttu-id="1f12a-125">El valor de la clave del Registro **DefaultSecureProtocols** que describe el artículo de KB determina qué protocolos de red se pueden usar:</span><span class="sxs-lookup"><span data-stu-id="1f12a-125">The value of the **DefaultSecureProtocols** registry key that the KB article describes determines which network protocols can be used:</span></span>

|<span data-ttu-id="1f12a-126">Valor defaultSecureProtocols</span><span class="sxs-lookup"><span data-stu-id="1f12a-126">DefaultSecureProtocols Value</span></span>|<span data-ttu-id="1f12a-127">Protocolo habilitado</span><span class="sxs-lookup"><span data-stu-id="1f12a-127">Protocol enabled</span></span>|
|-|-|
|<span data-ttu-id="1f12a-128">0x00000008</span><span class="sxs-lookup"><span data-stu-id="1f12a-128">0x00000008</span></span>|<span data-ttu-id="1f12a-129">Habilita SSL 2.0 de manera predeterminada</span><span class="sxs-lookup"><span data-stu-id="1f12a-129">Enable SSL 2.0 by default</span></span>|
|<span data-ttu-id="1f12a-130">0x00000020</span><span class="sxs-lookup"><span data-stu-id="1f12a-130">0x00000020</span></span>|<span data-ttu-id="1f12a-131">Habilita SSL 3.0 de manera predeterminada</span><span class="sxs-lookup"><span data-stu-id="1f12a-131">Enable SSL 3.0 by default</span></span>|
|<span data-ttu-id="1f12a-132">0x00000080</span><span class="sxs-lookup"><span data-stu-id="1f12a-132">0x00000080</span></span>|<span data-ttu-id="1f12a-133">Habilita TLS 1.0 de manera predeterminada</span><span class="sxs-lookup"><span data-stu-id="1f12a-133">Enable TLS 1.0 by default</span></span>|
|<span data-ttu-id="1f12a-134">0x00000200</span><span class="sxs-lookup"><span data-stu-id="1f12a-134">0x00000200</span></span>|<span data-ttu-id="1f12a-135">Habilita TLS 1.1 de manera predeterminada</span><span class="sxs-lookup"><span data-stu-id="1f12a-135">Enable TLS 1.1 by default</span></span>|
|<span data-ttu-id="1f12a-136">0x00000800</span><span class="sxs-lookup"><span data-stu-id="1f12a-136">0x00000800</span></span>|<span data-ttu-id="1f12a-137">Habilita TLS 1.2 de manera predeterminada</span><span class="sxs-lookup"><span data-stu-id="1f12a-137">Enable TLS 1.2 by default</span></span>|

## <a name="office-clients-and-tls-registry-keys"></a><span data-ttu-id="1f12a-138">Clientes de Office y claves del Registro TLS</span><span class="sxs-lookup"><span data-stu-id="1f12a-138">Office clients and TLS registry keys</span></span>

<span data-ttu-id="1f12a-139">Puede consultar [KB 4057306 Preparación](https://support.microsoft.com/help/4057306)para el uso obligatorio de TLS 1.2 en Office 365 .</span><span class="sxs-lookup"><span data-stu-id="1f12a-139">You can refer to [KB 4057306 Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306).</span></span> <span data-ttu-id="1f12a-140">Este es un artículo general para administradores de TI y es documentación oficial sobre el cambio de TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="1f12a-140">This is a general article for IT administrators, and it's official documentation about the TLS 1.2 change.</span></span>

<span data-ttu-id="1f12a-141">En la tabla siguiente se muestran los valores de clave del Registro adecuados en los clientes de Office 365 después del 31 de octubre de 2018.</span><span class="sxs-lookup"><span data-stu-id="1f12a-141">The following table shows the appropriate registry key values in Office 365 clients after October 31, 2018.</span></span>

|<span data-ttu-id="1f12a-142">Protocolos habilitados para el servicio de Office 365 después del 31 de octubre de 2018</span><span class="sxs-lookup"><span data-stu-id="1f12a-142">Enabled protocols for Office 365 service after October 31, 2018</span></span>|<span data-ttu-id="1f12a-143">Valor hexadecimal</span><span class="sxs-lookup"><span data-stu-id="1f12a-143">Hexadecimal value</span></span>|
|-|-|
|<span data-ttu-id="1f12a-144">TLS 1.0 + 1.1 + 1.2</span><span class="sxs-lookup"><span data-stu-id="1f12a-144">TLS 1.0 + 1.1 + 1.2</span></span>|<span data-ttu-id="1f12a-145">0x00000A80</span><span class="sxs-lookup"><span data-stu-id="1f12a-145">0x00000A80</span></span>|
|<span data-ttu-id="1f12a-146">TLS 1.1 + 1.2</span><span class="sxs-lookup"><span data-stu-id="1f12a-146">TLS 1.1 + 1.2</span></span>|<span data-ttu-id="1f12a-147">0x00000A00</span><span class="sxs-lookup"><span data-stu-id="1f12a-147">0x00000A00</span></span>|
|<span data-ttu-id="1f12a-148">TLS 1.0 + 1.2</span><span class="sxs-lookup"><span data-stu-id="1f12a-148">TLS 1.0 + 1.2</span></span>|<span data-ttu-id="1f12a-149">0x00000880</span><span class="sxs-lookup"><span data-stu-id="1f12a-149">0x00000880</span></span>|
|<span data-ttu-id="1f12a-150">TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="1f12a-150">TLS 1.2</span></span>|<span data-ttu-id="1f12a-151">0x00000800</span><span class="sxs-lookup"><span data-stu-id="1f12a-151">0x00000800</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="1f12a-152">No use los protocolos SSL 2.0 y 3.0, que también se pueden establecer mediante la clave **DefaultSecureProtocols.**</span><span class="sxs-lookup"><span data-stu-id="1f12a-152">Don't use the SSL 2.0 and 3.0 protocols, which can also be set by using the **DefaultSecureProtocols** key.</span></span> <span data-ttu-id="1f12a-153">SSL 2.0 y 3.0 se consideran protocolos obsoletos e inseguros.</span><span class="sxs-lookup"><span data-stu-id="1f12a-153">SSL 2.0 and 3.0 are considered outdated and insecure protocols.</span></span> <span data-ttu-id="1f12a-154">El procedimiento recomendado es finalizar el uso de SSL 2.0 y SSL 3.0, aunque la decisión de hacerlo depende en última instancia de lo que mejor se adapte a las necesidades de su producto.</span><span class="sxs-lookup"><span data-stu-id="1f12a-154">The best practice is to end the use of SSL 2.0 and SSL 3.0, although the decision to do this ultimately depends on what best meets your product needs.</span></span> <span data-ttu-id="1f12a-155">Para obtener más información acerca de las vulnerabilidades de SSL 3.0, consulte [KB 3009008](https://support.microsoft.com/help/3009008).</span><span class="sxs-lookup"><span data-stu-id="1f12a-155">For more information about SSL 3.0 vulnerabilities, refer to [KB 3009008](https://support.microsoft.com/help/3009008).</span></span>

<span data-ttu-id="1f12a-156">Puedes usar la Calculadora de Windows predeterminada en modo programador para configurar los mismos valores de clave del Registro de referencia.</span><span class="sxs-lookup"><span data-stu-id="1f12a-156">You can use the default Windows Calculator in Programmer mode to set up the same reference registry key values.</span></span> <span data-ttu-id="1f12a-157">Para obtener más información, consulte [KB 3140245 Update para habilitar TLS 1.1 y TLS 1.2](https://support.microsoft.com/help/3140245)como protocolos seguros predeterminados en WinHTTP en Windows.</span><span class="sxs-lookup"><span data-stu-id="1f12a-157">For more information, see [KB 3140245 Update to enable TLS 1.1 and TLS 1.2 as a default secure protocols in WinHTTP in Windows](https://support.microsoft.com/help/3140245).</span></span>

<span data-ttu-id="1f12a-158">Independientemente de si la actualización de Windows 7 ([KB 3140245](https://support.microsoft.com/help/3140245)) está instalada o no, la subclave del Registro DefaultSecureProtocols no está presente y debe agregarse manualmente o a través de un objeto de directiva de grupo (GPO).</span><span class="sxs-lookup"><span data-stu-id="1f12a-158">Regardless if the Windows 7 update ([KB 3140245](https://support.microsoft.com/help/3140245)) is installed or not, the DefaultSecureProtocols registry sub key isn't present and must be added manually or through a group policy object (GPO).</span></span> <span data-ttu-id="1f12a-159">Es decir, a menos que tenga que personalizar qué protocolos seguros están habilitados o restringidos, esta clave no es necesaria.</span><span class="sxs-lookup"><span data-stu-id="1f12a-159">That is, unless you have to customize what secure protocols are enabled or restricted, this key is not required.</span></span> <span data-ttu-id="1f12a-160">Solo necesita la actualización de Windows 7 SP1 ([KB 3140245).](https://support.microsoft.com/help/3140245)</span><span class="sxs-lookup"><span data-stu-id="1f12a-160">You only need the Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)) update.</span></span>

## <a name="update-and-configure-the-net-framework-to-support-tls-12"></a><span data-ttu-id="1f12a-161">Actualizar y configurar .NET Framework para admitir TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="1f12a-161">Update and configure the .NET Framework to support TLS 1.2</span></span>

<span data-ttu-id="1f12a-162">Deberá actualizar las aplicaciones que llaman a las API de Microsoft 365 a través de TLS 1.0 o TLS 1.1 para usar TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="1f12a-162">You'll need to update applications that call Microsoft 365 APIs over TLS 1.0 or TLS 1.1 to use TLS 1.2.</span></span> <span data-ttu-id="1f12a-163">.NET 4.5 tiene el valor predeterminado TLS 1.1.</span><span class="sxs-lookup"><span data-stu-id="1f12a-163">.NET 4.5 defaults to TLS 1.1.</span></span> <span data-ttu-id="1f12a-164">Para actualizar la configuración de .NET, consulte Cómo habilitar seguridad de la capa de transporte [(TLS) 1.2 en los clientes.](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)</span><span class="sxs-lookup"><span data-stu-id="1f12a-164">To update your .NET configuration, see [How to enable Transport Layer Security (TLS) 1.2 on clients](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span>

## <a name="more-information"></a><span data-ttu-id="1f12a-165">Más información</span><span class="sxs-lookup"><span data-stu-id="1f12a-165">More information</span></span>

<span data-ttu-id="1f12a-166">Para obtener más información, vea Prepararse para el uso obligatorio de [TLS 1.2 en Office 365.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="1f12a-166">For more information, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>
