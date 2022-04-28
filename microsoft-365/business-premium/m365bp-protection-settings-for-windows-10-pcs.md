---
title: Editar o crear la configuración de protección de dispositivos para equipos Windows 10
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
- adminvideo
search.appverid:
- BCS160
- MET150
ms.assetid: bd66c26c-73a4-45a8-8642-3ea4ee7cd89d
description: Obtenga información sobre la configuración disponible en Microsoft 365 para empresas para proteger los dispositivos Windows 10.
ms.openlocfilehash: ef4df7b308c52275db8d43c1c0619a64594ed690
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65096247"
---
# <a name="edit-or-create-device-protection-settings-for-windows-10-pcs"></a>Editar o crear la configuración de protección de dispositivos para equipos Windows 10

Este artículo aplica a Microsoft 365 Empresa Premium.

> [!NOTE]
> Microsoft Defender para Empresas se está implementando para los clientes de Microsoft 365 Empresa Premium desde el 1 de marzo de 2022. Esta oferta proporciona características de seguridad adicionales para los dispositivos. [Más información sobre Defender para Empresas](../security/defender-business/mdb-overview.md).

Después de establecer la configuración predeterminada de protección de Windows en la página configuración, puede agregar otras nuevas que se apliquen a todos los usuarios o a un conjunto de usuarios. También puede editar cualquiera de las que haya creado.

## <a name="watch-create-protection-settings-for-windows-10-devices"></a>Vea: Crear la configuración de protección para dispositivos Windows 10

Vea un vídeo sobre cómo proteger dispositivos Windows 10 con Microsoft 365 Empresa Premium:
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/a5734146-620a-4cec-8618-536b3ca37972?autoplay=false]
  
1. Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>. 

2. En el panel de navegación izquierdo, elija **Dispositivos** \> **Directivas** \> **Agregar**.

3. En el panel **Agregar directiva**, escriba un nombre único para esta directiva. 

4. En **Tipo de directiva**, elija **Configuración de dispositivos Windows 10**.

5. Expanda **Proteger dispositivos Windows 10** \> y configure las opciones como quiera. Vea [Configuración disponible](#available-settings) para obtener más información. 
    
    Siempre puede usar el vínculo **Restablecer la configuración predeterminada** para volver a la configuración predeterminada. 
    
    ![Panel Agregar directiva con Configuración de dispositivo Windows 10 seleccionada.](./../media/fa9e2dc2-7eae-4c96-af34-765a1f641ecf.png)
  
6. Después, decida **a qué usuarios se aplica esta configuración**. Si no quiere usar el grupo de seguridad predeterminado **Todos los usuarios**, elija **Cambiar**, busque los grupos de seguridad que recibirán esta configuración \> **Seleccionar**.

7. Por último, elija **Listo** para guardar la directiva y asignarla a los dispositivos. 

## <a name="edit-windows-10-protection-settings"></a>Editar la configuración de protección de Windows 10
 
1. Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.     

2. En el panel de navegación izquierdo, elija **Dispositivos** \> **Directivas**.

3. Elija una directiva de dispositivo Windows existente y, a continuación, **Edite**.

4. Elija **Editar** junto a una configuración que quiera cambiar y, luego, **Guardar**.

## <a name="available-settings"></a>Configuración disponible

De forma predeterminada, todas las opciones de configuración están **activadas**. Estas son las opciones de configuración disponibles.
  
Para obtener más información, consulte [Cómo se asignan las características de protección de Microsoft 365 Premium a la configuración de Intune](m365bp-map-protection-features-to-intune-settings.md). 


|Configuración  |Descripción  |
|:-----|:-----|
|Proteger los equipos PC de virus y otras amenazas con el antivirus Windows Defender  |Es necesario que el antivirus Windows Defender esté activado para proteger los equipos PC de los peligros de estar conectados a Internet.  |
|Proteger los equipos PC de amenazas basadas en web en Microsoft Edge  |Activa opciones de configuración en Edge para proteger a los usuarios de sitios y descargas malintencionados.  |
|Usar reglas que reducen la superficie expuesta a ataques de los dispositivos  |Al activar la reducción de la superficie expuesta a ataques, se bloquean acciones y aplicaciones que suelen usarse en ataques de malware para infectar dispositivos. Esta opción solo está disponible si el Antivirus de Windows Defender está activado. Para obtener más información, vea [Reducir las superficies expuestas a ataques](/windows/security/threat-protection/microsoft-defender-atp/exploit-protection).    |
|Proteger carpetas de amenazas como ransomware  |Esta opción usa el acceso controlado a las carpetas para proteger los datos de la compañía ante la modificación por parte de aplicaciones sospechosas o malintencionadas, como ransomware. Se impide que estos tipos de aplicaciones puedan realizar cambios en las carpetas protegidas. Esta opción solo está disponible si el Antivirus de Windows Defender está activado. Para obtener más información, vea [Proteger carpetas con acceso controlado a las carpetas](/mem/configmgr/protect/deploy-use/create-deploy-exploit-guard-policy#bkmk_CFA).  |
|Impedir el acceso a la red a contenido potencialmente malintencionado en Internet  |Use esta opción para bloquear las conexiones salientes de usuario a ubicaciones de Internet de baja reputación que puedan hospedar estafas de suplantación de identidad (phishing), vulnerabilidades de seguridad u otro contenido malintencionado. Esta opción solo está disponible si el Antivirus de Windows Defender está **activado**. Para obtener más información, consulte [Proteger la red](/windows/security/threat-protection/windows-defender-antivirus/configure-real-time-protection-windows-defender-antivirus).  |
|Ayudar a proteger archivos y carpetas en equipos PC ante el acceso no autorizado con BitLocker  |BitLocker protege los datos al cifrar los discos duros del equipo y proteger ante la exposición de datos en caso de robo o pérdida de un equipo. Para obtener más información, vea [Preguntas más frecuentes sobre BitLocker](/windows/security/information-protection/BitLocker/BitLocker-frequently-asked-questions).  |
|Permitir a los usuarios descargar aplicaciones desde la Microsoft Store  |Permite a los usuarios descargar e instalar aplicaciones desde la Microsoft Store. Las aplicaciones pueden ser de cualquier tipo, desde juegos hasta herramientas de productividad, por lo que dejamos esta configuración **activada**, pero puede desactivarla para obtener una capa de seguridad adicional.    |
|Permitir a los usuarios acceder a Cortana  |Cortana puede ser muy útil. Permite activar o desactivar opciones automáticamente, ofrece indicaciones y se asegura de que llegue a tiempo a las citas, por lo que está opción está **activada** de forma predeterminada.  |
|Permitir a los usuarios recibir sugerencias de Windows y anuncios de Microsoft  |Las sugerencias de Windows pueden ser útiles y orientar a los usuarios cuando se publiquen nuevas características.  |
|Mantener actualizados automáticamente los dispositivos con Windows 10  |Garantiza que los dispositivos con Windows 10 reciban automáticamente las actualizaciones más recientes.  |
|Apagar la pantalla del dispositivo cuando esté inactivo durante esta cantidad de tiempo  |Garantiza que los datos de la compañía estén protegidos si un usuario está inactivo. Puede que un usuario trabaje en una ubicación pública, como una cafetería, y se aparte o se distraiga durante un momento, lo que dejaría su dispositivo vulnerable ante miradas indiscretas. Esta configuración le permite controlar cuánto tiempo puede estar inactivo un usuario antes de que se apague la pantalla.  |

## <a name="see-also"></a>Vea también

[10 formas de proteger con planes de Microsoft 365 para empresas](../admin/security-and-compliance/secure-your-business-data.md) 