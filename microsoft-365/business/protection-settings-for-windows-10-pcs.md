---
title: Establecer la configuración de protección de dispositivos para equipos con Windows 10
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: bd66c26c-73a4-45a8-8642-3ea4ee7cd89d
description: Obtenga información sobre la configuración predeterminada y otras opciones disponibles en Microsoft 365 Business para proteger los dispositivos Windows 10.
ms.openlocfilehash: f9e890cde7a8290a9a8e81720d32a6a2889c312f
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285936"
---
# <a name="set-device-protection-settings-for-windows-10-pcs"></a><span data-ttu-id="8044a-103">Establecer la configuración de protección de dispositivos para equipos con Windows 10</span><span class="sxs-lookup"><span data-stu-id="8044a-103">Set device protection settings for Windows 10 PCs</span></span>

## <a name="secure-windows-10-devices"></a><span data-ttu-id="8044a-104">Proteger dispositivos con Windows 10</span><span class="sxs-lookup"><span data-stu-id="8044a-104">Secure Windows 10 devices</span></span>

<span data-ttu-id="8044a-105">Vea un vídeo sobre cómo proteger los dispositivos Windows 10 con Microsoft 365 Business:</span><span class="sxs-lookup"><span data-stu-id="8044a-105">View a video on how to secure Windows 10 devices with Microsoft 365 Business:</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/a5734146-620a-4cec-8618-536b3ca37972?autoplay=false]
  
1. <span data-ttu-id="8044a-106">Inicie sesión en el [centro de administración](https://go.microsoft.com/fwlink/p/?linkid=837890) con credenciales de administrador global.</span><span class="sxs-lookup"><span data-stu-id="8044a-106">Sign in to [admin center](https://go.microsoft.com/fwlink/p/?linkid=837890) with global admin credentials.</span></span> 
    
2. <span data-ttu-id="8044a-107">En el panel de navegación izquierdo, elija **Agregar** **directivas** \> de **dispositivos** \> .</span><span class="sxs-lookup"><span data-stu-id="8044a-107">On the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>
  
3. <span data-ttu-id="8044a-108">En el panel **Agregar directiva**, escriba un nombre único para esta directiva.</span><span class="sxs-lookup"><span data-stu-id="8044a-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="8044a-109">En **Tipo de directiva**, elija **Configuración de dispositivos Windows 10**.</span><span class="sxs-lookup"><span data-stu-id="8044a-109">Under **Policy type**, choose **Windows 10 Device Configuration**.</span></span>
    
5. <span data-ttu-id="8044a-p101">Expanda **Proteger dispositivos Windows 10** \> configure las opciones como quiera. Vea [Configuración disponible](#available-settings) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="8044a-p101">Expand **Secure Windows 10 Devices** \> configure the settings how you would like. See [Available settings](#available-settings) for more information.</span></span> 
    
    <span data-ttu-id="8044a-112">Siempre puede usar el vínculo **Restablecer la configuración predeterminada** para volver a la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="8044a-112">You can alway use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Add policy pane with Windows 10 Device configuration selected](media/fa9e2dc2-7eae-4c96-af34-765a1f641ecf.png)
  
6. <span data-ttu-id="8044a-p102">Después, decida **a qué usuarios se aplica esta configuración**. Si no quiere usar el grupo de seguridad predeterminado **Todos los usuarios**, elija **Cambiar**, busque los grupos de seguridad que recibirán esta configuración \> **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="8044a-p102">Next decide **Who will get these settings?** If you don't want to use the default **All users** security group, Choose **Change**, search for the security group who will get these settings \> **Select**.</span></span>
    
7. <span data-ttu-id="8044a-116">Por último, elija **Listo** para guardar la directiva y asignarla a los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="8044a-116">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="8044a-117">Configuración disponible</span><span class="sxs-lookup"><span data-stu-id="8044a-117">Available settings</span></span>

<span data-ttu-id="8044a-p103">De forma predeterminada, todas las opciones de configuración están **activadas**. Estas son las opciones de configuración disponibles.</span><span class="sxs-lookup"><span data-stu-id="8044a-p103">By default all settings are **On**. The following settings are available.</span></span>
  
<span data-ttu-id="8044a-120">Para obtener más información, vea [Asignar características de protección de Microsoft 365 Empresa a la configuración de Intune](map-protection-features-to-intune-settings.md).</span><span class="sxs-lookup"><span data-stu-id="8044a-120">See [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md) for more information.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="8044a-121">Configuración</span><span class="sxs-lookup"><span data-stu-id="8044a-121">Setting</span></span>  <br/> |<span data-ttu-id="8044a-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="8044a-122">Description</span></span>  <br/> |
|<span data-ttu-id="8044a-123">Proteger los equipos PC de virus y otras amenazas con el antivirus Windows Defender</span><span class="sxs-lookup"><span data-stu-id="8044a-123">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="8044a-124">Es necesario que el antivirus Windows Defender esté activado para proteger los equipos PC de los peligros de estar conectados a Internet.</span><span class="sxs-lookup"><span data-stu-id="8044a-124">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="8044a-125">Proteger los equipos PC de amenazas basadas en web en Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="8044a-125">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="8044a-126">Activa opciones de configuración en Edge para proteger a los usuarios de sitios y descargas malintencionados.</span><span class="sxs-lookup"><span data-stu-id="8044a-126">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="8044a-127">Usar reglas que reducen la superficie expuesta a ataques de los dispositivos</span><span class="sxs-lookup"><span data-stu-id="8044a-127">Use rules that reduce the attack surface of devices</span></span>  <br/> |<span data-ttu-id="8044a-p104">Al activar la reducción de la superficie expuesta a ataques, se bloquean acciones y aplicaciones que suelen usarse en ataques de malware para infectar dispositivos. Esta opción solo está disponible si el Antivirus de Windows Defender está activado. Para obtener más información, vea [Reducir las superficies expuestas a ataques](https://go.microsoft.com/fwlink/?linkid=870417).  </span><span class="sxs-lookup"><span data-stu-id="8044a-p104">When turned On, attack surface reduction helps block actions and apps typically used by malware to infect devices. This setting is only available if Windows Defender Antivirus is set to On. See [Reduce attack surfaces](https://go.microsoft.com/fwlink/?linkid=870417) to learn more.  </span></span><br/> |
|<span data-ttu-id="8044a-131">Proteger carpetas de amenazas como ransomware</span><span class="sxs-lookup"><span data-stu-id="8044a-131">Protect folders from threats such as ransomware</span></span>  <br/> |<span data-ttu-id="8044a-p105">Esta opción usa el acceso controlado a las carpetas para proteger los datos de la compañía ante la modificación de aplicaciones sospechosas, malintencionadas, como ransomware. Se impide que estos tipos de aplicaciones puedan realizar cambios en las carpetas protegidas. Esta opción solo está disponible si el Antivirus de Windows Defender está activado. Para obtener más información, vea [Proteger carpetas con acceso controlado a las carpetas](https://go.microsoft.com/fwlink/?linkid=870418).  </span><span class="sxs-lookup"><span data-stu-id="8044a-p105">This setting uses controlled folder access to protect company data from modification by suspicious or malicious apps, such as ransomware. These types of apps are blocked from making changes in protected folders. This setting is only available if Windows Defender Antivirus is set to On. See [Protect folders with COntrolled folder access](https://go.microsoft.com/fwlink/?linkid=870418) to learn more.  </span></span><br/> |
|<span data-ttu-id="8044a-136">Impedir el acceso a la red a contenido potencialmente malintencionado en Internet</span><span class="sxs-lookup"><span data-stu-id="8044a-136">Prevent network access to potentially malicious content on the Internet</span></span>  <br/> |<span data-ttu-id="8044a-p106">Use está opción para bloquear las conexiones de usuario de salida a ubicaciones de Internet de baja reputación que puedan hospedar estafas de suplantación de identidad (phishing), vulnerabilidades de seguridad u otro contenido malintencionado. Esta opción solo está disponible si el Antivirus de Windows Defender está activado. Para obtener más información, vea [Proteger la red](https://go.microsoft.com/fwlink/?linkid=870419).  </span><span class="sxs-lookup"><span data-stu-id="8044a-p106">Use this setting to block outbound user connections to low-reputation Internet locations that may host phishing scams, exploits or other malicious content. This setting is only available if Windows Defender Antivirus is set to On. See [Protect your network](https://go.microsoft.com/fwlink/?linkid=870419) for more information.  </span></span><br/> |
|<span data-ttu-id="8044a-140">Ayudar a proteger archivos y carpetas en equipos PC ante el acceso no autorizado con BitLocker</span><span class="sxs-lookup"><span data-stu-id="8044a-140">Help protect files and folders on PCs from unauthorized access with BitLocker</span></span>  <br/> |<span data-ttu-id="8044a-p107">BitLocker protege los datos al cifrar los discos duros del equipo y proteger ante la exposición de datos en caso del robo o pérdida de un equipo. Para obtener más información, vea [Preguntas más frecuentes sobre BitLocker](https://go.microsoft.com/fwlink/?linkid=871000).  </span><span class="sxs-lookup"><span data-stu-id="8044a-p107">Bitlocker protects data by encrypting the computer hard drives and protect against data exposure if a computer is lost or stolen. See [Bitlocker FAQ](https://go.microsoft.com/fwlink/?linkid=871000) for more information.  </span></span><br/> |
|<span data-ttu-id="8044a-143">Permitir a los usuarios descargar aplicaciones desde la Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="8044a-143">Allow users to download apps from Microsoft Store</span></span>  <br/> |<span data-ttu-id="8044a-p108">Permite a los usuarios descargar e instalar aplicaciones desde la Microsoft Store. Las aplicaciones pueden ser de cualquier tipo, desde juegos hasta herramientas de productividad, por lo que dejamos esta configuración **activada**, pero puede desactivarla para obtener una capa de seguridad adicional.  </span><span class="sxs-lookup"><span data-stu-id="8044a-p108">Lets users download and install apps from the Microsoft Store. Apps include everything from games to productivity tools, so we leave this setting **On**, but you can turn it off for extra security.  </span></span><br/> |
|<span data-ttu-id="8044a-146">Permitir a los usuarios acceder a Cortana</span><span class="sxs-lookup"><span data-stu-id="8044a-146">Allow users to access Cortana</span></span>  <br/> |<span data-ttu-id="8044a-p109">Cortana puede ser muy útil. Permite activar o desactivar opciones automáticamente, ofrece indicaciones y se asegura de que llegue a tiempo a las citas, por lo que mantenemos **activada** esta opción de forma predeterminada.  </span><span class="sxs-lookup"><span data-stu-id="8044a-p109">Cortana can be very helpful! She can turn settings on or off for you, give directions, and make sure you're on time for appointments, so we keep this **On** by default.  </span></span><br/> |
|<span data-ttu-id="8044a-149">Permitir a los usuarios recibir sugerencias de Windows y anuncios de Microsoft</span><span class="sxs-lookup"><span data-stu-id="8044a-149">Allow users to receive Windows tips and advertisements from Microsoft</span></span>  <br/> |<span data-ttu-id="8044a-150">Las sugerencias de Windows pueden ser útiles y orientar a los usuarios cuando se publiquen nuevas características.</span><span class="sxs-lookup"><span data-stu-id="8044a-150">Windows tips can be handy and help orient users when new features are released.</span></span>  <br/> |
|<span data-ttu-id="8044a-151">Mantener actualizados automáticamente los dispositivos con Windows 10</span><span class="sxs-lookup"><span data-stu-id="8044a-151">Keep Windows 10 devices up to date automatically</span></span>  <br/> |<span data-ttu-id="8044a-152">Garantiza que los dispositivos con Windows 10 reciban automáticamente las actualizaciones más recientes.</span><span class="sxs-lookup"><span data-stu-id="8044a-152">Makes sure that Windows 10 devices automatically receive the latest updates.</span></span>  <br/> |
|<span data-ttu-id="8044a-153">Apagar la pantalla del dispositivo cuando esté inactivo durante esta cantidad de tiempo</span><span class="sxs-lookup"><span data-stu-id="8044a-153">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="8044a-p110">Garantiza que los datos de la compañía estén protegidos si un usuario está inactivo. Puede que un usuario trabaje en una ubicación pública, como una cafetería, y se aparte o se distraiga durante un momento, lo que dejaría su dispositivo vulnerable ante miradas indiscretas. Esta configuración le permite controlar cuánto tiempo puede estar inactivo un usuario antes de que se apague la pantalla.</span><span class="sxs-lookup"><span data-stu-id="8044a-p110">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
   
  

