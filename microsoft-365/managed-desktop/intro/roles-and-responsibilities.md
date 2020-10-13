---
title: Roles y responsabilidades del Escritorio administrado de Microsoft
description: En este artículo se describen los roles y las responsabilidades que proporciona Microsoft para el escritorio administrado por Microsoft.
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 8ced46ea30c7225fd3e5c8f1309ef482542e51b2
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "48445788"
---
# <a name="microsoft-managed-desktop-roles-and-responsibilities"></a>Roles y responsabilidades del Escritorio administrado de Microsoft


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/admin-access); do not delete.-->
<!-- from Roles and responsibilities -->

Cuando su organización está inscrito en el escritorio administrado de Microsoft, ¿qué hace Microsoft por usted? ¿Cuáles son las responsabilidades de su organización?

## <a name="microsofts-roles-and-responsibilities"></a>Funciones y responsabilidades de Microsoft

Microsoft proporciona estas funciones y responsabilidades clave:

Rol o responsabilidad | Descripción
--- | ---
Administración de directivas de MDM | Microsoft aplicará directivas de MDM de acuerdo con los procedimientos recomendados y considerará las solicitudes de cambios de directiva. También realizaremos cambios en su espacio empresarial tal y como se indica en [directivas de dispositivo](../service-description/device-policies.md).
soporte para usuarios | Ofrecemos soporte al usuario para dispositivos, Windows y el conjunto de productos de Microsoft 365 apps for Enterprise para todos los usuarios inscritos a través de la aplicación obtener ayuda que está preinstalada en todos los dispositivos de escritorio administrados por Microsoft. 
Soporte técnico del servicio de escritorio administrado de Microsoft | Microsoft proporcionará soporte técnico a su Departamento de ti a través de un equipo de operaciones de escritorio administrado por Microsoft. Este equipo será compatible con la solución de problemas técnicos, las solicitudes de cambio y la administración de incidentes para el entorno de escritorio administrado por Microsoft del cliente. Para obtener más información, consulte [soporte de administración para escritorio administrado de Microsoft](../working-with-managed-desktop/admin-support.md).
Supervisión de seguridad | Microsoft supervisará sus dispositivos de escritorio administrados por Microsoft con ATP de Microsoft defender. Si Microsoft Managed Desktop Security Operations Center (SOC) detecta una amenaza, le notificaremos, aislará el dispositivo y rectificará el problema de forma remota. Para obtener más información, consulte [seguridad](../service-description/security.md).
Actualización de la supervisión y la administración | Supervisamos activamente sus dispositivos de escritorio administrados por Microsoft para asegurarse de que se instalan las últimas actualizaciones de calidad y características para Microsoft Windows y Microsoft Office. Para obtener más información, vea [cómo se administran las actualizaciones](../service-description/updates.md).
Agrupación de usuarios y dispositivos | El equipo de operaciones de escritorio administrado por Microsoft creará y administrará el dispositivo y los grupos de usuarios necesarios como parte de las operaciones de ti. No se permiten cambios de configuración ni pertenencia a estos grupos. La modificación de estos grupos puede llevar a la configuración inesperada de los dispositivos y la pérdida de funcionalidad. Para cualquier problema o pregunta sobre estos grupos una vez que se ha establecido, los administradores de TI pueden ponerse en contacto con las operaciones de escritorio administradas de Microsoft. Para obtener más información, consulte [soporte de administración para escritorio administrado de Microsoft](../working-with-managed-desktop/admin-support.md).

## <a name="your-roles-and-responsibilities"></a>Sus roles y responsabilidades

Este conjunto adicional de roles y responsabilidades comunes es necesario para la implementación, pero Microsoft no la proporciona. No es exhaustivo pero es aplicable a la mayoría de las organizaciones. Hay algunos elementos de los que usted y Microsoft comparten responsabilidad. 

Rol o responsabilidad | Descripción
--- | ---
Administración de cambios | Microsoft notificará a los clientes, por anticipado, Cuándo deben realizarse cambios en el entorno de escritorio administrado de Microsoft. Para obtener más información, consulte [cambios de servicio y comunicación](../service-description/servicechanges.md).<br><br>Debe tener su propio proceso de administración de cambios y tener un contacto establecido con el equipo de operaciones de escritorio administradas de Microsoft. También debe disponer de recursos para revisar y aprobar estos cambios. Para obtener más información, consulte [Operations and Monitoring](../service-description/operations-and-monitoring.md).  
Administración de identidades | Usted es el responsable de la creación de cuentas de usuario, la asignación de usuarios a grupos y la actualización de los metadatos. 
Microsoft 365 apps for Enterprise Configuration and Management | Microsoft es responsable de garantizar que las aplicaciones de Office se implementan en los usuarios y esas aplicaciones se actualizan. <br><br> Usted es responsable de administrar las directivas y los servicios de Microsoft 365, incluidas las responsabilidades de administración de Exchange Online:<br>-Administración de correo electrónico<br>-Configuración de buzones y reglas<br>-Administración local de Exchange<br><br>También es responsable de las herramientas de colaboración, la administración de SharePoint Server, la administración de dominios y las directivas de seguridad e información que se establecen en el centro de administración de Microsoft 365. 
Soporte al usuario | Debe proporcionar soporte técnico al usuario para: <br>-Infraestructura de sitio: todas las conexiones de red y de Internet, la infraestructura de VPN y la configuración de clientes, el equipo local de la sala de conferencias, las impresoras, la configuración y el servidor proxy y los firewalls.<br><br>-Recursos de la nube de toda la empresa: correo electrónico, SharePoint, servicios de colaboración y otra infraestructura en la nube que se relaciona con el espacio tecnológico de toda la empresa.<br><br>-Línea de negocio y cualquier otra aplicación específica de la empresa.
Aplicaciones | Los roles y las responsabilidades varían en cierta medida para las aplicaciones proporcionadas como parte del escritorio administrado por Microsoft frente a las aplicaciones que se proporcionan. <br><br>Para las aplicaciones proporcionadas por Microsoft (aplicaciones de Microsoft 365 para empresas que incluyen Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype empresarial, Teams y OneNote), **Microsoft** proporcionará el servicio completo para la implementación, actualización y soporte. **Debe obtener** y asignar licencias para estas aplicaciones, agregar usuarios a grupos de seguridad y administrar el fin de vida e implementar los complementos que necesite.<br><br>Para las aplicaciones que proporcione (como las aplicaciones de línea de negocio), independientemente de si las empaqueta o contrata a un proveedor que no es de Microsoft para hacerlo, **usted** es responsable de estas acciones: <br><br>-Identificación de aplicaciones necesarias para grupos de usuarios de destino<br>-Creación y administración de grupos de Azure AD para la implementación de aplicaciones<br>-Empaquetado de aplicaciones para cumplir con los estándares de implementación de Microsoft Intune<br>-Carga de aplicaciones en Microsoft Intune<br>-Pruebas de aplicaciones en el entorno de escritorio administrado de Microsoft<br>-Probando aplicaciones con los usuarios<br>-Administración y asignación de usuarios a aplicaciones<br>-Identificación e implementación de actualizaciones de aplicaciones mediante Microsoft Intune<br>-Desinstalación y eliminación de aplicaciones cuando se han retirado<br>-Obtención y asignación de licencias<br>-Proporcionar soporte al usuario para las aplicaciones de línea de negocio<br>-Administración remota de la configuración de la aplicación<br><br>**Microsoft** proporcionará herramientas de implementación de Microsoft Intune para entregar las aplicaciones a clientes remotos.<br><br>Para obtener más información, vea [aplicaciones](../get-ready/apps.md).
Control y respuesta de seguridad | Usted es responsable de la investigación y la resolución de incidentes para dispositivos que no son dispositivos de escritorio administrados por Microsoft y que garantizan que el equipo de operaciones de escritorio administrado de Microsoft esté informado de cualquier problema que pueda afectar al servicio.
Compatibilidad con operaciones | Debe proporcionar una lista de contactos preferidos y expertos en la materia en su organización. Los necesitamos en caso de un incidente operativo que no esté relacionado con el escritorio administrado por Microsoft. <br><br>También es responsable de investigar y resolver los incidentes de los dispositivos y servicios que no están en el escritorio administrado por Microsoft y de garantizar que el equipo de operaciones de escritorio administrado de Microsoft esté siempre informado.
Infraestructura de red, incluida la VPN | Usted es responsable de la configuración, la configuración y la administración (incluida la solución de problemas y la depuración) de todos los servicios y la infraestructura relacionados con la red, como la conectividad de Internet, los controles de red, la configuración de proxy y la infraestructura de conectividad remota.<br><br>Si un proxy está configurado (en hardware o software), hay una colección de direcciones URL que debe permitir el proxy. Usted es responsable de solucionar cualquier conflicto o incompatibilidad debido a varios servidores proxy. Puede agregar servidores proxy de red específicos a su organización mediante la configuración configurable. Para obtener más información, consulte [configuración configurable](../working-with-managed-desktop/config-setting-ref.md#proxy).<br><br>Para obtener más información, consulte [configuración de proxy](../get-ready/network.md).
Impresión | Usted es responsable de instalar, mantener y administrar las colas de impresión y las impresoras. La impresión en la nube es una solución recomendada, pero no es necesaria. 




