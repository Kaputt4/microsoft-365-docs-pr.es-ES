---
title: Roles y responsabilidades del escritorio administrado por Microsoft
description: En este tema se describen los roles y las responsabilidades que proporciona Microsoft para el escritorio administrado por Microsoft.
keywords: Escritorio administrado de Microsoft, Microsoft 365, Service, Documentation
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 161be07907754cdd7a0cd88dd3342d4b5e3c72e4
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283563"
---
# <a name="microsoft-managed-desktop-roles-and-responsibilities"></a>Roles y responsabilidades del escritorio administrado por Microsoft


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/admin-access); do not delete.-->
<!-- from Roles and responsibilities -->

Cuando su organización está inscrito en el escritorio administrado de Microsoft, ¿qué hace Microsoft por usted? ¿Cuáles son las responsabilidades de su organización?

## <a name="microsofts-roles-and-responsibilities"></a>Funciones y responsabilidades de Microsoft

A continuación se muestran algunas de las funciones y responsabilidades clave que le proporcionará Microsoft.

Rol o responsabilidad | Descripción
--- | ---
Administración de directivas de MDM | Microsoft aplicará directivas de MDM de acuerdo con los procedimientos recomendados y considerará las solicitudes de cambios de directiva. También realizaremos cambios en su espacio empresarial tal y como se indica en [directivas de dispositivo](../service-description/device-policies.md).
Compatibilidad con usuarios finales | Microsoft proporcionará compatibilidad con el usuario final para dispositivos, Windows y el conjunto de productos de Office para todos los usuarios inscritos a través de la aplicación obtener ayuda que está preinstalada en todos los dispositivos de escritorio administrados por Microsoft. 
Soporte técnico del servicio de escritorio administrado de Microsoft | Microsoft proporcionará soporte técnico a los departamentos de TI del cliente a través de un equipo de operaciones de escritorio administrado por Microsoft. Este equipo será compatible con la solución de problemas técnicos, las solicitudes de cambio y la administración de incidentes para el entorno de escritorio administrado por Microsoft del cliente. Para obtener más información, consulte [soporte de administración para escritorio administrado de Microsoft](../working-with-managed-desktop/admin-support.md).
Supervisión de seguridad | Microsoft supervisará los dispositivos de escritorio administrados por Microsoft para clientes con ATP de Windows Defender. Si se detecta una amenaza en el centro de operaciones de seguridad de escritorio administrada de Microsoft (SOC), Microsoft notificará al cliente, aislará el dispositivo y rectificará el problema de forma remota. Para obtener más información, consulte [seguridad](../service-description/security.md).
Actualización de la supervisión y la administración | Microsoft supervisará activamente los dispositivos de escritorio administrados por Microsoft para asegurarse de que están instaladas las últimas actualizaciones de calidad y características para Microsoft Windows y Microsoft Office. Para obtener más información, vea [cómo se administran las actualizaciones](../service-description/updates.md).
Agrupación de usuarios y dispositivos | El equipo de operaciones de escritorio administrado por Microsoft creará y administrará el dispositivo y los grupos de usuarios necesarios como parte de las operaciones de ti. No se permiten cambios de configuración ni pertenencia a estos grupos. La modificación de estos grupos puede llevar a la configuración inesperada de los dispositivos y la pérdida de funcionalidad. Para cualquier problema o pregunta sobre estos grupos una vez que se ha establecido, los administradores de TI pueden ponerse en contacto con las operaciones de escritorio administradas de Microsoft. Para obtener más información, consulte [soporte de administración para escritorio administrado de Microsoft](../working-with-managed-desktop/admin-support.md).

## <a name="your-roles-and-responsibilities"></a>Sus roles y responsabilidades

A continuación se muestra un conjunto adicional de roles y responsabilidades comunes que no proporciona Microsoft, pero que son necesarios para una implementación correcta. No es exhaustivo pero es aplicable a la mayoría de las organizaciones. Hay algunos elementos por debajo de los cuales tanto Microsoft como el recurso compartido de cliente RESPONSIBILTIES. 

Rol o responsabilidad | Descripción
--- | ---
Administración de cambios | Microsoft notificará a los clientes, por anticipado, Cuándo deben realizarse cambios en el entorno de escritorio administrado de Microsoft. El cliente debe tener su propio proceso de administración de cambios y tener un contacto establecido con el equipo de operaciones de escritorio administradas de Microsoft. También es necesario que el cliente tenga recursos para revisar y aprobar estos cambios. Para obtener más información, consulte [Operations and Monitoring](../service-description/operations-and-monitoring.md).  
Administración de identidades | El cliente es responsable de la creación de cuentas de usuario, la asignación de usuarios a grupos y la actualización de los metadatos. 
Configuración y administración de Office 365 | Microsoft es responsable de garantizar que las aplicaciones de Office se implementan en los usuarios finales y de que dichas aplicaciones se mantienen al día. <br><br> El cliente es responsable de administrar las directivas y los servicios de Office 365, incluidas las responsabilidades de administración de Exchange Online:<br>-Administración de correo electrónico<br>-Configuración de buzones y reglas<br>-Administración local de Exchange<br><br>El cliente también es responsable de las herramientas de colaboración, la administración de SharePoint Server, la administración de dominios, las directivas de seguridad y de información establecidas en el portal de administración de Office 365. 
Compatibilidad con usuarios finales | El cliente es responsable de proporcionar soporte técnico al usuario final para: <br>-En la infraestructura del sitio: toda la conectividad de red y de Internet, infraestructura de VPN y configuración de clientes, equipos locales de salas de conferencias, impresoras, servidor proxy y configuración, firewalls.<br><br>-Recursos de la nube de toda la empresa: correo electrónico, SharePoint, servicios de colaboración y otra infraestructura en la nube que se relaciona con el espacio tecnológico de toda la empresa.<br><br>-Línea de negocio y cualquier otra aplicación específica de la compañía.
Aplicaciones | Microsoft proporcionará instrucciones para la implementación de aplicaciones aprobadas con Intune on request.<br><br>El cliente es responsable de:<br>-Proporciona una lista de aplicaciones para su organización (fuera de las aplicaciones de Office 365)<br>-Administración de licencias de aplicaciones<br>– Tener el tipo y la cantidad de licencias correctos<br>-Asignación de aplicación<br>– Asignación de aplicaciones a grupos de usuarios de Azure AD<br>-Actualizaciones de aplicaciones<br>– Supervisión, empaquetado e implementación de actualizaciones de seguridad y características de la aplicación<br>-Pruebas de aplicaciones de usuario (UAT)<br>-Proporciona un paquete implementable adecuado<br><br>Para obtener más información, vea [aplicaciones](../get-ready/apps.md)
Supervisión y respuesta de seguridad | El cliente es responsable de investigar y resolver los incidentes para los dispositivos de escritorio administrados que no son de Microsoft y de garantizar que el equipo de operaciones de escritorio administrado de Microsoft esté informado de cualquier problema que pueda afectar al servicio.
Compatibilidad con operaciones | El cliente es responsable de ofrecer una lista de contactos de clientes preferidos y expertos en el tema. Microsoft las necesita en caso de que haya un incidente operativo de escritorio no administrado por Microsoft. <br><br>El cliente también es responsable de investigar y resolver los incidentes de servicios y dispositivos de escritorio que no sean de Microsoft y de garantizar que el equipo de operaciones de escritorio administrado de Microsoft esté siempre informado.
Infraestructura de red, incluida la VPN | El cliente es responsable de la configuración, la configuración y la administración (como la solución de problemas y la depuración) de toda la infraestructura y los servicios relacionados con la red, incluidos la conectividad de Internet, los controles de red, la configuración de proxy y la remota infraestructura de conectividad.<br><br>Si un proxy está configurado (en hardware o software), hay una colección de direcciones URL que debe permitir el proxy. El cliente es responsable de solucionar cualquier conflicto o incompatibilidad debido a varios servidores proxy. Puede agregar servidores proxy de red específicos a su organización mediante la configuración configurable. Para obtener más información, consulte [configuración configurable](../working-with-managed-desktop/config-setting-ref.md#proxy).<br><br>Para obtener más información, consulte [configuración de proxy](../get-ready/network.md).
Impresión | El cliente es responsable de instalar, mantener y administrar las colas de impresión y las impresoras. La impresión en la nube es una solución recomendada, pero no es necesaria. 




