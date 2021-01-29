---
title: Proteger equipos Windows 10 y Mac no administrados
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Proteger dispositivos no administrados o bring your own devices (BYOD) con Microsoft 365.
ms.openlocfilehash: 5c27b29b5bb4fb445655e671d8c654ad8e9abc6b
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044389"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs"></a><span data-ttu-id="6047f-103">Proteger equipos Windows 10 y Mac no administrados</span><span class="sxs-lookup"><span data-stu-id="6047f-103">Protect unmanaged Windows 10 PCs and Macs</span></span>

<span data-ttu-id="6047f-104">Puedes administrar equipos Windows 10 y Mac inscribándolos en Microsoft Intune, lo que te permite asegurarte de que están en buen estado y seguros antes de acceder a los datos de tu entorno.</span><span class="sxs-lookup"><span data-stu-id="6047f-104">You can manage Windows 10 PCs and Macs by enrolling them in Microsoft Intune, which allows you to ensure they're healthy and secure before accessing data in your environment.</span></span> <span data-ttu-id="6047f-105">Sin embargo, muchas campañas y pequeñas empresas incluyen personal que lleva sus propios dispositivos (BYOD), que la organización no administrará.</span><span class="sxs-lookup"><span data-stu-id="6047f-105">However, many campaigns and small businesses include staff who bring their own devices (BYOD), which will not be managed by the organization.</span></span> <span data-ttu-id="6047f-106">Para estos equipos y Mac no administrados, use este artículo para asegurarse de que se configuran las funcionalidades de seguridad mínimas.</span><span class="sxs-lookup"><span data-stu-id="6047f-106">For these unmanaged PCs and Macs, use this article to ensure that minimum security capabilities are configured.</span></span>

<!--A Windows 10 PC is considered managed after you have completed the following two steps:

1. You (or the admin) set up device and data protection policies in the [setup  wizard](../business/set-up.md).

2. You have [connected your computer to Azure Active Directory](../business/set-up-windows-devices.md) and use your Microsoft 365 username and password to sign in.
3. --> 

## <a name="protect-a-computer-running-windows-10-or-a-mac"></a><span data-ttu-id="6047f-107">Proteger un equipo que ejecute Windows 10 o mac</span><span class="sxs-lookup"><span data-stu-id="6047f-107">Protect a computer running Windows 10 or a Mac</span></span>

<!--If you have a PC that is running Windows 10 that is not connected to Microsoft 365, or a Mac, the Microsoft 365 protections do not apply to it, but here are some things you can do to keep your data secure on these devices as well:
-->
<span data-ttu-id="6047f-108">Si tu equipo Windows 10 o Mac no está administrado por tu organización, asegúrate de configurar estas funcionalidades de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6047f-108">If your Windows 10 PC or Mac is not managed by your organization, be sure to configure these security capabilities.</span></span>

## <a name="windows-10"></a>[<span data-ttu-id="6047f-109">Windows 10</span><span class="sxs-lookup"><span data-stu-id="6047f-109">Windows 10</span></span>](#tab/Windows10)

<span data-ttu-id="6047f-110">**Activar el cifrado de dispositivos**</span><span class="sxs-lookup"><span data-stu-id="6047f-110">**Turn on device encryption**</span></span><p>

<span data-ttu-id="6047f-111">El cifrado de dispositivos está disponible en una amplia variedad de dispositivos Windows y ayuda a proteger los datos mediante su cifrado.</span><span class="sxs-lookup"><span data-stu-id="6047f-111">Device encryption is available on a wide range of Windows devices and helps protect your data by encrypting it.</span></span> <span data-ttu-id="6047f-112">Si activas el cifrado del dispositivo, solo las personas autorizadas podrán acceder a tu dispositivo y datos.</span><span class="sxs-lookup"><span data-stu-id="6047f-112">If you turn on device encryption, only authorized individuals will be able to access your device and data.</span></span> <span data-ttu-id="6047f-113">Consulta [activar el cifrado del dispositivo](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="6047f-113">See [turn on device encryption](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) for instructions.</span></span>

 <span data-ttu-id="6047f-114">Si el cifrado del dispositivo no está disponible en el dispositivo, puedes activar el cifrado [de BitLocker](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) estándar en su lugar.</span><span class="sxs-lookup"><span data-stu-id="6047f-114">If device encryption isn't available on your device, you can turn on standard [BitLocker encryption](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) instead.</span></span> <span data-ttu-id="6047f-115">(BitLocker no está disponible en Windows 10 Home Edition).</span><span class="sxs-lookup"><span data-stu-id="6047f-115">(BitLocker isn't available on Windows 10 Home edition.)</span></span> 

<span data-ttu-id="6047f-116">**Proteger el dispositivo con seguridad de Windows**</span><span class="sxs-lookup"><span data-stu-id="6047f-116">**Protect your device with Windows Security**</span></span><p>
<span data-ttu-id="6047f-117">Si tienes Windows 10, tendrás la protección antivirus más reciente con Seguridad de Windows.</span><span class="sxs-lookup"><span data-stu-id="6047f-117">If you have Windows 10, you'll get the latest antivirus protection with Windows Security.</span></span> <span data-ttu-id="6047f-118">Cuando inicias Windows 10 por primera vez, Seguridad de Windows está activado y ayuda activamente a proteger tu equipo mediante el análisis de malware (software malintencionado), virus y amenazas de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6047f-118">When you start up Windows 10 for the first time, Windows Security is on and actively helping to protect your PC by scanning for malware (malicious software), viruses, and security threats.</span></span> <span data-ttu-id="6047f-119">Seguridad de Windows usa la protección en tiempo real para examinar todo lo que descargues o ejecutes en el equipo.</span><span class="sxs-lookup"><span data-stu-id="6047f-119">Windows Security uses real-time protection to scan everything you download or run on your PC.</span></span>

<span data-ttu-id="6047f-120">Windows Update descarga automáticamente las actualizaciones de Seguridad de Windows para ayudar a mantener su equipo seguro y protegerlo contra amenazas.</span><span class="sxs-lookup"><span data-stu-id="6047f-120">Windows Update downloads updates for Windows Security automatically to help keep your PC safe and protect it from threats.</span></span>

<span data-ttu-id="6047f-121">Si tienes una versión anterior de Windows y usas Microsoft Security Essentials, es una buena idea pasar a Seguridad de Windows.</span><span class="sxs-lookup"><span data-stu-id="6047f-121">If you have an earlier version of Windows and are using Microsoft Security Essentials, it's a good idea to move to Windows Security.</span></span> <span data-ttu-id="6047f-122">Para obtener más información, [consulta la ayuda para proteger mi dispositivo con Seguridad de Windows.](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security)</span><span class="sxs-lookup"><span data-stu-id="6047f-122">For more information, see [help protect my device with Windows Security](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security).</span></span>

<span data-ttu-id="6047f-123">**Activar Firewall de Windows**</span><span class="sxs-lookup"><span data-stu-id="6047f-123">**Turn on Windows Firewall**</span></span><p>
<span data-ttu-id="6047f-124">Siempre debe ejecutar Firewall de Windows incluso si tiene otro firewall activado.</span><span class="sxs-lookup"><span data-stu-id="6047f-124">You should always run Windows Firewall even if you have another firewall turned on.</span></span> <span data-ttu-id="6047f-125">Desactivar Firewall de Windows puede hacer que tu dispositivo (y tu red, si tienes uno) sean más vulnerables al acceso no autorizado.</span><span class="sxs-lookup"><span data-stu-id="6047f-125">Turning off Windows Firewall might make your device (and your network, if you have one) more vulnerable to unauthorized access.</span></span> <span data-ttu-id="6047f-126">Consulta [Activar o desactivar Firewall de Windows para](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) obtener instrucciones</span><span class="sxs-lookup"><span data-stu-id="6047f-126">See [Turn Windows Firewall on or off](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) for instructions</span></span>

## <a name="mac"></a>[<span data-ttu-id="6047f-127">Mac</span><span class="sxs-lookup"><span data-stu-id="6047f-127">Mac</span></span>](#tab/Mac)

<span data-ttu-id="6047f-128">**Usar FileVault para cifrar el disco Mac**</span><span class="sxs-lookup"><span data-stu-id="6047f-128">**Use FileVault to encrypt your Mac disk**</span></span><p>
<span data-ttu-id="6047f-129">El cifrado de disco protege los datos cuando se pierden o roban dispositivos.</span><span class="sxs-lookup"><span data-stu-id="6047f-129">Disk encryption protects data when devices are lost or stolen.</span></span> <span data-ttu-id="6047f-130">El cifrado de disco completo de FileVault ayuda a evitar el acceso no autorizado a la información del disco de inicio.</span><span class="sxs-lookup"><span data-stu-id="6047f-130">FileVault full-disk encryption helps prevent unauthorized access to the information on your startup disk.</span></span> <span data-ttu-id="6047f-131">Consulta [usar FileVault para cifrar el disco de inicio en tu Mac](https://support.apple.com/HT204837) para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="6047f-131">See [use FileVault to encrypt the startup disk on your Mac](https://support.apple.com/HT204837) for instructions.</span></span>

<span data-ttu-id="6047f-132">**Proteger su mac contra malware**</span><span class="sxs-lookup"><span data-stu-id="6047f-132">**Protect your mac from malware**</span></span><p>
<span data-ttu-id="6047f-133">Microsoft recomienda instalar y usar software antivirus confiable en su Equipo Mac.</span><span class="sxs-lookup"><span data-stu-id="6047f-133">Microsoft recommends that you install and use reliable antivirus software on your Mac.</span></span> <span data-ttu-id="6047f-134">Vea el siguiente artículo para obtener una lista de opciones: [Best Mac antivirus 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/).</span><span class="sxs-lookup"><span data-stu-id="6047f-134">See the following article for a list of choices: [Best Mac antivirus 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/).</span></span>

<span data-ttu-id="6047f-135">También puede reducir el riesgo de malware mediante el uso de software solo de orígenes confiables.</span><span class="sxs-lookup"><span data-stu-id="6047f-135">You can also reduce the risk of malware by using software only from reliable sources.</span></span> <span data-ttu-id="6047f-136">La configuración de las & privacidad le permite especificar los orígenes de software instalados en su Equipo Mac.</span><span class="sxs-lookup"><span data-stu-id="6047f-136">The settings in Security & Privacy preferences allow you to specify the sources of software installed on your Mac.</span></span> <span data-ttu-id="6047f-137">Para obtener más información, [vea proteger su Equipo Mac contra malware.](https://support.apple.com/kb/PH25087)</span><span class="sxs-lookup"><span data-stu-id="6047f-137">For more information, see [protect your Mac from malware](https://support.apple.com/kb/PH25087).</span></span>

<span data-ttu-id="6047f-138">**Activar la protección del firewall**</span><span class="sxs-lookup"><span data-stu-id="6047f-138">**Turn on firewall protection**</span></span><p>
<span data-ttu-id="6047f-139">Usa la configuración del firewall para proteger tu Equipo Mac contra contactos no deseados iniciados por otros equipos cuando estás conectado a Internet o a una red.</span><span class="sxs-lookup"><span data-stu-id="6047f-139">Use firewall settings to protect your Mac from unwanted contact initiated by other computers when you're connected to the Internet or a network.</span></span> <span data-ttu-id="6047f-140">Sin esta protección, es posible que el equipo Mac sea más vulnerable al acceso no autorizado.</span><span class="sxs-lookup"><span data-stu-id="6047f-140">Without this protection, your Mac might be more vulnerable to unauthorized access.</span></span> <span data-ttu-id="6047f-141">Consulte [sobre el firewall de la aplicación](https://support.apple.com/HT201642) para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="6047f-141">See [about the application firewall](https://support.apple.com/HT201642) for instructions.</span></span>
