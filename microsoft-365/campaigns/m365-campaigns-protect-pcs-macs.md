---
title: Proteger equipos con Windows 10 PC y Mac no administrados
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
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Protéjase contra el phishing y otros ataques con Microsoft 365 para las campañas.
ms.openlocfilehash: 7cb09d0cadcc70b96c5f1404defa5d0387947ca8
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594801"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs"></a><span data-ttu-id="d0e44-103">Proteger equipos con Windows 10 PC y Mac no administrados</span><span class="sxs-lookup"><span data-stu-id="d0e44-103">Protect unmanaged Windows 10 PCs and Macs</span></span>

<span data-ttu-id="d0e44-104">Para administrar equipos con Windows 10 y equipos Mac, puede inscribirse en Microsoft Intune, lo que le permite asegurarse de que son correctos y seguros antes de obtener acceso a los datos de su entorno.</span><span class="sxs-lookup"><span data-stu-id="d0e44-104">You can manage Windows 10 PCs and Macs by enrolling them in Microsoft Intune, which allows you to ensure they're healthy and secure before accessing data in your environment.</span></span> <span data-ttu-id="d0e44-105">Sin embargo, muchas campañas y pequeñas empresas incluyen el personal que lleva sus propios dispositivos (BYOD), que no se administrará en la organización.</span><span class="sxs-lookup"><span data-stu-id="d0e44-105">However, many campaigns and small businesses include staff who bring their own devices (byod), which will not be managed by the organization.</span></span> <span data-ttu-id="d0e44-106">Para estos equipos PC y Mac no administrados, use este artículo para asegurarse de que las capacidades de seguridad mínima están configuradas.</span><span class="sxs-lookup"><span data-stu-id="d0e44-106">For these unmanaged PCs and Macs, use this article to ensure that minimum security capabilities are configured.</span></span> 

<!--A Windows 10 PC is considered managed after you have completed the following two steps:

1. You (or the admin) set up device and data protection policies in the [setup  wizard](../business/set-up.md).

2. You have [connected your computer to Azure Active Directory](../business/set-up-windows-devices.md) and use your Microsoft 365 Business username and password to sign in.
3. --> 

## <a name="protect-a-computer-running-windows-10-or-a-mac"></a><span data-ttu-id="d0e44-107">Proteger un equipo que ejecuta Windows 10 o un Mac</span><span class="sxs-lookup"><span data-stu-id="d0e44-107">Protect a computer running Windows 10 or a Mac</span></span>

<!--If you have a PC that is running Windows 10 that is not connected to Microsoft 365 Business, or a Mac, the Microsoft 365 Business protections do not apply to it, but here are some things you can do to keep your data secure on these devices as well:
-->
<span data-ttu-id="d0e44-108">Si tu organización no administra tu PC con Windows 10 o Mac, asegúrate de configurar estas funciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="d0e44-108">If your Windows 10 PC or Mac is not managed by your organization, be sure to configure these security capabilities.</span></span>

## <a name="windows-10tabwindows10"></a>[<span data-ttu-id="d0e44-109">Windows 10</span><span class="sxs-lookup"><span data-stu-id="d0e44-109">Windows 10</span></span>](#tab/Windows10)
<span data-ttu-id="d0e44-110">**Activar el cifrado del dispositivo**</span><span class="sxs-lookup"><span data-stu-id="d0e44-110">**Turn on device encryption**</span></span><p>

<span data-ttu-id="d0e44-111">El cifrado de dispositivos está disponible en una amplia gama de dispositivos Windows y ayuda a proteger los datos cifrándolos.</span><span class="sxs-lookup"><span data-stu-id="d0e44-111">Device encryption is available on a wide range of Windows devices and helps protect your data by encrypting it.</span></span> <span data-ttu-id="d0e44-112">Si activa el cifrado del dispositivo, solo podrán tener acceso a su dispositivo y a sus datos los usuarios autorizados.</span><span class="sxs-lookup"><span data-stu-id="d0e44-112">If you turn on device encryption, only authorized individuals will be able to access your device and data.</span></span> <span data-ttu-id="d0e44-113">Consulte [activar el cifrado del dispositivo](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="d0e44-113">See [turn on device encryption](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) for instructions.</span></span>

 <span data-ttu-id="d0e44-114">Si el cifrado del dispositivo no está disponible en el dispositivo, puede activar el [cifrado de BitLocker](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) estándar en su lugar.</span><span class="sxs-lookup"><span data-stu-id="d0e44-114">If device encryption isn't available on your device, you can turn on standard [BitLocker encryption](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) instead.</span></span> <span data-ttu-id="d0e44-115">(BitLocker no está disponible en Windows 10 Home Edition).</span><span class="sxs-lookup"><span data-stu-id="d0e44-115">(BitLocker isn't available on Windows 10 Home edition.)</span></span> 


<span data-ttu-id="d0e44-116">**Proteger el dispositivo con la seguridad de Windows**</span><span class="sxs-lookup"><span data-stu-id="d0e44-116">**Protect your device with Windows Security**</span></span><p>
<span data-ttu-id="d0e44-117">Si tiene Windows 10, obtendrá la protección antivirus más reciente con la seguridad de Windows.</span><span class="sxs-lookup"><span data-stu-id="d0e44-117">If you have Windows 10, you’ll get the latest antivirus protection with Windows Security.</span></span> <span data-ttu-id="d0e44-118">Al iniciar Windows 10 por primera vez, la seguridad de Windows está activa y ayudando activamente a proteger tu equipo mediante la detección de malware (software malintencionado), virus y amenazas de seguridad.</span><span class="sxs-lookup"><span data-stu-id="d0e44-118">When you start up Windows 10 for the first time, Windows Security is on and actively helping to protect your PC by scanning for malware (malicious software), viruses, and security threats.</span></span> <span data-ttu-id="d0e44-119">La seguridad de Windows usa la protección en tiempo real para analizar todo lo que descarga o ejecuta en el equipo.</span><span class="sxs-lookup"><span data-stu-id="d0e44-119">Windows Security uses real-time protection to scan everything you download or run on your PC.</span></span>

<span data-ttu-id="d0e44-120">Windows Update descarga automáticamente las actualizaciones para la seguridad de Windows para ayudar a mantener tu PC seguro y protegerlo de amenazas.</span><span class="sxs-lookup"><span data-stu-id="d0e44-120">Windows Update downloads updates for Windows Security automatically to help keep your PC safe and protect it from threats.</span></span>

<span data-ttu-id="d0e44-121">Si tiene una versión anterior de Windows y usa Microsoft Security Essentials, es una buena idea cambiar a la seguridad de Windows.</span><span class="sxs-lookup"><span data-stu-id="d0e44-121">If you have an earlier version of Windows and are using Microsoft Security Essentials, it’s a good idea to move to Windows Security.</span></span> <span data-ttu-id="d0e44-122">Para obtener más información, consulte [ayudar a proteger el dispositivo con la seguridad de Windows](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security).</span><span class="sxs-lookup"><span data-stu-id="d0e44-122">For more information, see [help protect my device with Windows Security](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security).</span></span>

<span data-ttu-id="d0e44-123">**Activar Firewall de Windows**</span><span class="sxs-lookup"><span data-stu-id="d0e44-123">**Turn on Windows Firewall**</span></span><p>
<span data-ttu-id="d0e44-124">Siempre debe ejecutar Firewall de Windows incluso si tiene activado otro Firewall.</span><span class="sxs-lookup"><span data-stu-id="d0e44-124">You should always run Windows Firewall even if you have another firewall turned on.</span></span> <span data-ttu-id="d0e44-125">Si se desactiva el Firewall de Windows, es posible que el dispositivo (y la red, si tiene uno) sean más vulnerables a un acceso no autorizado.</span><span class="sxs-lookup"><span data-stu-id="d0e44-125">Turning off Windows Firewall might make your device (and your network, if you have one) more vulnerable to unauthorized access.</span></span> <span data-ttu-id="d0e44-126">Consulte [activar o desactivar Firewall de Windows](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) para obtener instrucciones</span><span class="sxs-lookup"><span data-stu-id="d0e44-126">See [Turn Windows Firewall on or off](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) for instructions</span></span>

## <a name="mactabmac"></a>[<span data-ttu-id="d0e44-127">Mac</span><span class="sxs-lookup"><span data-stu-id="d0e44-127">Mac</span></span>](#tab/Mac)
<span data-ttu-id="d0e44-128">**Usar FileVault para cifrar el disco Mac**</span><span class="sxs-lookup"><span data-stu-id="d0e44-128">**Use FileVault to encrypt your Mac disk**</span></span><p>
<span data-ttu-id="d0e44-129">El cifrado de disco protege los datos cuando se pierden o roban dispositivos.</span><span class="sxs-lookup"><span data-stu-id="d0e44-129">Disk encryption protects data when devices are lost or stolen.</span></span> <span data-ttu-id="d0e44-130">FileVault el cifrado de disco completo ayuda a impedir el acceso no autorizado a la información del disco de inicio.</span><span class="sxs-lookup"><span data-stu-id="d0e44-130">FileVault full-disk encryption helps prevent unauthorized access to the information on your startup disk.</span></span> <span data-ttu-id="d0e44-131">Consulte [usar FileVault para cifrar el disco de inicio en su Mac](https://support.apple.com/HT204837) para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="d0e44-131">See [use FileVault to encrypt the startup disk on your Mac](https://support.apple.com/HT204837) for instructions.</span></span>

<span data-ttu-id="d0e44-132">**Proteger su Mac del malware**</span><span class="sxs-lookup"><span data-stu-id="d0e44-132">**Protect your mac from malware**</span></span><p>
<span data-ttu-id="d0e44-133">Microsoft recomienda instalar y usar software antivirus fiable en su Mac.</span><span class="sxs-lookup"><span data-stu-id="d0e44-133">Microsoft recommends that you install and use reliable antivirus software on your Mac.</span></span> <span data-ttu-id="d0e44-134">Vea el siguiente artículo para obtener una lista de opciones: [Best Mac antivirus 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/).</span><span class="sxs-lookup"><span data-stu-id="d0e44-134">See the following article for a list of choices: [Best Mac antivirus 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/).</span></span>

<span data-ttu-id="d0e44-135">También puede reducir el riesgo del malware mediante el uso de software solo de orígenes confiables.</span><span class="sxs-lookup"><span data-stu-id="d0e44-135">You can also reduce the risk of malware by using software only from reliable sources.</span></span> <span data-ttu-id="d0e44-136">Las opciones de configuración de seguridad & preferencias de privacidad le permiten especificar los orígenes del software instalado en su Mac.</span><span class="sxs-lookup"><span data-stu-id="d0e44-136">The settings in Security & Privacy preferences allow you to specify the sources of software installed on your Mac.</span></span> <span data-ttu-id="d0e44-137">Para obtener más información, consulte [proteger su Mac del malware](https://support.apple.com/kb/PH25087).</span><span class="sxs-lookup"><span data-stu-id="d0e44-137">For more information, see [protect your Mac from malware](https://support.apple.com/kb/PH25087).</span></span>

<span data-ttu-id="d0e44-138">**Activar la protección del firewall**</span><span class="sxs-lookup"><span data-stu-id="d0e44-138">**Turn on firewall protection**</span></span><p>
<span data-ttu-id="d0e44-139">Use la configuración del firewall para proteger su Mac del contacto no deseado iniciados por otros equipos cuando esté conectado a Internet o a una red.</span><span class="sxs-lookup"><span data-stu-id="d0e44-139">Use firewall settings to protect your Mac from unwanted contact initiated by other computers when you’re connected to the Internet or a network.</span></span> <span data-ttu-id="d0e44-140">Sin esta protección, es posible que su Mac sea más vulnerable al acceso no autorizado.</span><span class="sxs-lookup"><span data-stu-id="d0e44-140">Without this protection, your Mac might be more vulnerable to unauthorized access.</span></span> <span data-ttu-id="d0e44-141">Consulte [acerca del firewall de la aplicación](https://support.apple.com/HT201642) para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="d0e44-141">See [about the application firewall](https://support.apple.com/HT201642) for instructions.</span></span>
