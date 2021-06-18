---
title: Introducción a Microsoft 365 Business Premium Security
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
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Obtenga información sobre las características de seguridad incluidas con Microsoft 365 para empresas.
ms.openlocfilehash: c0890f097177848ef5a75c7c139c7dbc69e4eba1
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007098"
---
# <a name="overview-of-security"></a>Información general sobre la seguridad

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4mzxI?autoplay=false]

Microsoft 365 Empresa Premium proporciona características de protección contra amenazas, protección de datos y administración de dispositivos para ayudarle a proteger su empresa de amenazas en línea y acceso no autorizado, así como proteger y administrar los datos de la empresa en sus teléfonos, tabletas y equipos.

|![Protección contra amenazas](../media/m365-business-security-threat-protection.png)<br/>[Protección contra amenazas](#threat-protection)|![Colaborar con un cliente](../media/m365-business-security-data-protection.png) <br/>[Protección de datos](#data-protection) | ![Administración de dispositivos](../media/m365-business-security-device-management.png) <br/>[Administración de dispositivos](#device-management) |
|--|--|--|

## <a name="threat-protection"></a>Protección contra amenazas

Microsoft 365 Empresa Premium incluye Protección contra amenazas avanzada [(ATP) de Office 365,](safe-links.md)un servicio de filtrado de correo electrónico basado en la nube que le protege contra malware, ransomware, vínculos dañinos y mucho más. Los vínculos seguros de ATP le protegen de las direcciones URL malintencionadas de los documentos de Office o de correo electrónico. Los datos adjuntos seguros de ATP le protegen contra malware y virus adjuntos a mensajes o documentos.

[La autenticación multifactor (MFA)](turn-on-mfa.md)o la comprobación en dos pasos requiere que presente una segunda forma de autenticación, como un código de verificación, para confirmar su identidad antes de poder acceder a los recursos.

[Windows Defender](/windows/security/threat-protection/overview-of-threat-mitigations-in-windows-10) proporciona protección completa para el sistema, los archivos y las actividades en línea contra virus, malware, spyware y otras amenazas.

## <a name="data-protection"></a>Protección de datos

Las características de protección de datos de Microsoft 365 Empresa Premium ayudan a garantizar que los datos importantes se mantienen seguros y solo las personas autorizadas tienen acceso a ella.

Puede usar directivas de prevención de pérdida de datos [(DLP)](set-up-dlp.md) para identificar y administrar información confidencial, como números de tarjeta de crédito o seguridad social, para que no se comparta por error.

El cifrado de mensajes de [Office 365](/microsoft-365/compliance/ome) combina funcionalidades de derechos de acceso y cifrado para garantizar que solo los destinatarios previstos puedan ver el contenido del mensaje. El cifrado de mensajes de Office 365 funciona con Outlook.com, Yahoo!, Gmail y otros servicios de correo electrónico.

[Archivado de Exchange Online](/office365/servicedescriptions/exchange-online-archiving-service-description/exchange-online-archiving-service-description) es una solución de archivado basada en la nube que funciona con Microsoft Exchange o Exchange Online para proporcionar capacidades avanzadas de archivado, incluidas las retenciones y la redundancia de datos. Puede usar directivas de retención para ayudar a su organización a reducir las responsabilidades asociadas con el correo electrónico y otras comunicaciones. Si su empresa tiene que conservar las comunicaciones relacionadas con litigios, puede usar las In-Place y las retenciones por juicio para conservar el correo electrónico relacionado.

## <a name="device-management"></a>Administración de dispositivos

Las características avanzadas de administración de dispositivos de Microsoft 365 Empresa Premium te permiten supervisar y controlar lo que los usuarios pueden hacer con los dispositivos inscritos. Estas características incluyen acceso condicional, [Administración de dispositivos móviles (MDM),](/microsoft-365/admin/basic-mobility-security/manage-enrolled-devices)BitLocker y actualizaciones automáticas.

Puede usar directivas de acceso condicional para requerir medidas de seguridad adicionales para determinados usuarios y tareas. Por ejemplo, puede requerir [autenticación multifactor (MFA)](/microsoft-365/business-video/turn-on-mfa) o bloquear clientes que no admitan el acceso condicional.

Con MDM, puedes proteger y administrar los dispositivos móviles de los usuarios como iPhones, iPads, Android y teléfonos Windows. Puedes crear y administrar directivas de seguridad de dispositivos, borrar de forma remota un dispositivo para quitar todos los datos de la empresa, restablecer un dispositivo a la configuración de fábrica y ver informes de dispositivos detallados.

Puedes habilitar el cifrado de BitLocker para ayudar a proteger los datos en caso de que se pierda o robe un dispositivo, y habilitar Windows Exploit Guard para proporcionar protección avanzada contra ransomware.

Puedes configurar las actualizaciones automáticas para que las últimas características y actualizaciones de seguridad se apliquen a todos los dispositivos de usuario.

## <a name="recommended-security-guidance"></a>Instrucciones de seguridad recomendadas

Si tiene Microsoft Empresa Premium, la forma más rápida de configurar la seguridad y empezar a colaborar de forma segura es seguir las instrucciones de esta biblioteca: [Microsoft 365 para empresas y campañas pequeñas](../campaigns/index.md). Esta guía fue desarrollada en asociación con el equipo de Microsoft Defending Democracy para proteger a todos los clientes de empresas pequeñas de las amenazas cibernéticas por parte de hackers sofisticados.
