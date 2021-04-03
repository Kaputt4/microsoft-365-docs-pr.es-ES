---
title: Editar o crear la configuración de protección de dispositivos para equipos con Windows 10
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: bd66c26c-73a4-45a8-8642-3ea4ee7cd89d
description: Obtén información sobre la configuración disponible en Microsoft 365 para empresas para proteger dispositivos Windows 10.
ms.openlocfilehash: acfb27b2e4592d4ed1e446a63c9495ae07d916de
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578235"
---
# <a name="edit-or-create-device-protection-settings-for-windows-10-pcs"></a>Editar o crear la configuración de protección de dispositivos para equipos con Windows 10

Este artículo se aplica a Microsoft 365 Empresa Premium.

Después de configurar la configuración predeterminada de Windows Protection en la página Configuración, puedes agregar otras nuevas que se apliquen a todos los usuarios o a un conjunto de usuarios. También puede editar cualquiera de las que haya creado.

## <a name="create-protection-settings-for-windows-10-devices"></a>Crear configuración de protección para dispositivos Windows 10

Vea un vídeo sobre cómo proteger dispositivos Windows 10 con Microsoft 365 Empresa Premium:
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/a5734146-620a-4cec-8618-536b3ca37972?autoplay=false]
  
1. Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>. 
2. En la navegación izquierda, elija **Directivas** \> **de** \> **dispositivos Agregar**.
3. En el panel **Agregar directiva**, escriba un nombre único para esta directiva. 
4. En **Tipo de directiva**, elija **Configuración de dispositivos Windows 10**.
5. Expanda **Proteger dispositivos Windows 10** \> configure las opciones como quiera. Para obtener más información, vea [Configuración disponible](#available-settings). 
    
    Siempre puede usar el vínculo **Restablecer la configuración predeterminada** para volver a la configuración predeterminada. 
    
    ![Add policy pane with Windows 10 Device configuration selected](../media/fa9e2dc2-7eae-4c96-af34-765a1f641ecf.png)
  
6. Después, decida **a qué usuarios se aplica esta configuración**. Si no quiere usar el grupo de seguridad predeterminado **Todos los usuarios**, elija **Cambiar**, busque los grupos de seguridad que recibirán esta configuración \> **Seleccionar**.
7. Por último, elija **Listo** para guardar la directiva y asignarla a los dispositivos. 

## <a name="edit-windows-10-protection-settings"></a>Editar la configuración de protección de Windows 10
 
1. Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.     
2. En el panel de navegación izquierdo, elija **Directivas de** \> **dispositivos** .
1. Elija una directiva de dispositivo Windows existente y, a **continuación, Edit**.
1. Elija **Editar** junto a una configuración que desea cambiar y, a continuación, **Guardar**.

## <a name="available-settings"></a>Configuración disponible

De forma predeterminada, todas las opciones de configuración están **activadas**. Estas son las opciones de configuración disponibles.
  
Para obtener más información, vea [How do protection features in Microsoft 365 Premium map to Intune settings](map-protection-features-to-intune-settings.md). 
  
|||
|:-----|:-----|
|Configuración  <br/> |Descripción  <br/> |
|Proteger los equipos PC de virus y otras amenazas con el antivirus Windows Defender  <br/> |Es necesario que el antivirus Windows Defender esté activado para proteger los equipos PC de los peligros de estar conectados a Internet.  <br/> |
|Proteger los equipos PC de amenazas basadas en web en Microsoft Edge  <br/> |Activa opciones de configuración en Edge para proteger a los usuarios de sitios y descargas malintencionados.  <br/> |
|Usar reglas que reducen la superficie expuesta a ataques de los dispositivos  <br/> |Al activar la reducción de la superficie expuesta a ataques, se bloquean acciones y aplicaciones que suelen usarse en ataques de malware para infectar dispositivos. Esta opción solo está disponible si el Antivirus de Windows Defender está activado. Para obtener más información, vea [Reducir las superficies expuestas a ataques](/windows/security/threat-protection/microsoft-defender-atp/exploit-protection).  <br/> |
|Proteger carpetas de amenazas como ransomware  <br/> |Esta opción usa el acceso controlado a las carpetas para proteger los datos de la compañía ante la modificación de aplicaciones sospechosas, malintencionadas, como ransomware. Se impide que estos tipos de aplicaciones puedan realizar cambios en las carpetas protegidas. Esta opción solo está disponible si el Antivirus de Windows Defender está activado. Consulta [Proteger carpetas con acceso controlado a carpetas](/mem/configmgr/protect/deploy-use/create-deploy-exploit-guard-policy#bkmk_CFA) para obtener más información.  <br/> |
|Impedir el acceso a la red a contenido potencialmente malintencionado en Internet  <br/> |Use esta configuración para bloquear las conexiones de usuario salientes a ubicaciones de Internet de baja reputación que pueden hospedar estafas de phishing, vulnerabilidades de seguridad u otro contenido malintencionado. Esta configuración solo está disponible si Windows Defender Antivirus está establecido en **On**. Para obtener más información, vea [Protect your network](/windows/security/threat-protection/windows-defender-antivirus/configure-real-time-protection-windows-defender-antivirus).  <br/> |
|Ayudar a proteger archivos y carpetas en equipos PC ante el acceso no autorizado con BitLocker  <br/> |BitLocker protege los datos al cifrar los discos duros del equipo y proteger ante la exposición de datos en caso del robo o pérdida de un equipo. Para obtener más información, consulta [Preguntas más frecuentes de Bitlocker](/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions).  <br/> |
|Permitir a los usuarios descargar aplicaciones desde la Microsoft Store  <br/> |Permite a los usuarios descargar e instalar aplicaciones desde la Microsoft Store. Las aplicaciones pueden ser de cualquier tipo, desde juegos hasta herramientas de productividad, por lo que dejamos esta configuración **activada**, pero puede desactivarla para obtener una capa de seguridad adicional.  <br/> |
|Permitir a los usuarios acceder a Cortana  <br/> |Cortana puede ser muy útil. Cortana puede activar o desactivar la configuración, dar instrucciones y asegurarse de que está a tiempo para las citas, por lo que esta configuración se mantiene activa de **forma** predeterminada.  <br/> |
|Permitir a los usuarios recibir sugerencias de Windows y anuncios de Microsoft  <br/> |Las sugerencias de Windows pueden ser útiles y orientar a los usuarios cuando se publiquen nuevas características.  <br/> |
|Mantener actualizados automáticamente los dispositivos con Windows 10  <br/> |Garantiza que los dispositivos con Windows 10 reciban automáticamente las actualizaciones más recientes.  <br/> |
|Apagar la pantalla del dispositivo cuando esté inactivo durante esta cantidad de tiempo  <br/> |Garantiza que los datos de la compañía estén protegidos si un usuario está inactivo. Puede que un usuario trabaje en una ubicación pública, como una cafetería, y se aparte o se distraiga durante un momento, lo que dejaría su dispositivo vulnerable ante miradas indiscretas. Esta configuración le permite controlar cuánto tiempo puede estar inactivo un usuario antes de que se apague la pantalla.  <br/> |