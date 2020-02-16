---
title: Establecer la configuración de protección de dispositivos para equipos con Windows 10
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
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
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: bd66c26c-73a4-45a8-8642-3ea4ee7cd89d
description: Obtenga información sobre la configuración predeterminada y otras opciones disponibles en Microsoft 365 Business para proteger los dispositivos Windows 10.
ms.openlocfilehash: 1b424fe6a85ad23b2914ea29f47d1dc16b333c94
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42064980"
---
# <a name="set-device-protection-settings-for-windows-10-pcs"></a>Establecer la configuración de protección de dispositivos para equipos con Windows 10

## <a name="secure-windows-10-devices"></a>Proteger dispositivos con Windows 10

Vea un vídeo sobre cómo proteger los dispositivos Windows 10 con Microsoft 365 Business:
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/a5734146-620a-4cec-8618-536b3ca37972?autoplay=false]
  
1. Vaya al centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>. 
    
2. En el panel de navegación izquierdo, elija **Agregar** **directivas** \> de **dispositivos** \> .
  
3. En el panel **Agregar directiva**, escriba un nombre único para esta directiva. 
    
4. En **Tipo de directiva**, elija **Configuración de dispositivos Windows 10**.
    
5. Expanda **Proteger dispositivos Windows 10** \> configure las opciones como quiera. Para obtener más información, consulte [configuración disponible](#available-settings). 
    
    Siempre puede usar el vínculo **Restablecer la configuración predeterminada** para volver a la configuración predeterminada. 
    
    ![Add policy pane with Windows 10 Device configuration selected](../media/fa9e2dc2-7eae-4c96-af34-765a1f641ecf.png)
  
6. Después, decida **a qué usuarios se aplica esta configuración**. Si no quiere usar el grupo de seguridad predeterminado **Todos los usuarios**, elija **Cambiar**, busque los grupos de seguridad que recibirán esta configuración \> **Seleccionar**.
    
7. Por último, elija **Listo** para guardar la directiva y asignarla a los dispositivos. 
    
## <a name="available-settings"></a>Configuración disponible

De forma predeterminada, todas las opciones de configuración están **activadas**. Estas son las opciones de configuración disponibles.
  
Para obtener más información, consulte [Cómo se asignan las características de protección de Microsoft 365 Business a la configuración de Intune](map-protection-features-to-intune-settings.md). 
  
|||
|:-----|:-----|
|Configuración  <br/> |Descripción  <br/> |
|Proteger los equipos PC de virus y otras amenazas con el antivirus Windows Defender  <br/> |Es necesario que el antivirus Windows Defender esté activado para proteger los equipos PC de los peligros de estar conectados a Internet.  <br/> |
|Proteger los equipos PC de amenazas basadas en web en Microsoft Edge  <br/> |Activa opciones de configuración en Edge para proteger a los usuarios de sitios y descargas malintencionados.  <br/> |
|Usar reglas que reducen la superficie expuesta a ataques de los dispositivos  <br/> |Al activar la reducción de la superficie expuesta a ataques, se bloquean acciones y aplicaciones que suelen usarse en ataques de malware para infectar dispositivos. Esta opción solo está disponible si el Antivirus de Windows Defender está activado. Para obtener más información, vea [Reducir las superficies expuestas a ataques](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/exploit-protection).  <br/> |
|Proteger carpetas de amenazas como ransomware  <br/> |Esta opción usa el acceso controlado a las carpetas para proteger los datos de la compañía ante la modificación de aplicaciones sospechosas, malintencionadas, como ransomware. Se impide que estos tipos de aplicaciones puedan realizar cambios en las carpetas protegidas. Esta opción solo está disponible si el Antivirus de Windows Defender está activado. Consulte [proteger carpetas con el acceso a la carpeta controlada](https://docs.microsoft.com/configmgr/protect/deploy-use/create-deploy-exploit-guard-policy#bkmk_CFA) para obtener más información.  <br/> |
|Impedir el acceso a la red a contenido potencialmente malintencionado en Internet  <br/> |Use esta opción para bloquear las conexiones de usuario saliente a ubicaciones de Internet de baja reputación que puedan hospedar estafas de suplantación de identidad (phishing), vulnerabilidades de abuso u otros contenidos malintencionados. Esta configuración solo está disponible si el antivirus de Windows Defender está establecido en **activado**. Para obtener más información, consulte [proteger la red](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-real-time-protection-windows-defender-antivirus).  <br/> |
|Ayudar a proteger archivos y carpetas en equipos PC ante el acceso no autorizado con BitLocker  <br/> |BitLocker protege los datos al cifrar los discos duros del equipo y proteger ante la exposición de datos en caso del robo o pérdida de un equipo. Para obtener más información, consulte [preguntas más frecuentes de BitLocker](https://go.microsoft.com/fwlink/?linkid=871000).  <br/> |
|Permitir a los usuarios descargar aplicaciones desde la Microsoft Store  <br/> |Permite a los usuarios descargar e instalar aplicaciones desde la Microsoft Store. Las aplicaciones pueden ser de cualquier tipo, desde juegos hasta herramientas de productividad, por lo que dejamos esta configuración **activada**, pero puede desactivarla para obtener una capa de seguridad adicional.  <br/> |
|Permitir a los usuarios acceder a Cortana  <br/> |Cortana puede ser muy útil. Cortana puede activar o desactivar la configuración para ti, dar indicaciones y garantizar que estás a tiempo para las citas, por lo que mantenemos esta configuración **activada** de forma predeterminada.  <br/> |
|Permitir a los usuarios recibir sugerencias de Windows y anuncios de Microsoft  <br/> |Las sugerencias de Windows pueden ser útiles y orientar a los usuarios cuando se publiquen nuevas características.  <br/> |
|Mantener actualizados automáticamente los dispositivos con Windows 10  <br/> |Garantiza que los dispositivos con Windows 10 reciban automáticamente las actualizaciones más recientes.  <br/> |
|Apagar la pantalla del dispositivo cuando esté inactivo durante esta cantidad de tiempo  <br/> |Garantiza que los datos de la compañía estén protegidos si un usuario está inactivo. Puede que un usuario trabaje en una ubicación pública, como una cafetería, y se aparte o se distraiga durante un momento, lo que dejaría su dispositivo vulnerable ante miradas indiscretas. Esta configuración le permite controlar cuánto tiempo puede estar inactivo un usuario antes de que se apague la pantalla.  <br/> |
