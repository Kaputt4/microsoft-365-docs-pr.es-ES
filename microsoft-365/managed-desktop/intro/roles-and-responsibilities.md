---
title: Roles y responsabilidades del Escritorio administrado de Microsoft
description: En este artículo se describen los roles y responsabilidades proporcionados por Microsoft para Escritorio administrado de Microsoft.
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 94389fbb9a13b9a880b0c4dcaf67d8adcaff0f98
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841320"
---
# <a name="microsoft-managed-desktop-roles-and-responsibilities"></a>Roles y responsabilidades del Escritorio administrado de Microsoft


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/admin-access); do not delete.-->
<!-- from Roles and responsibilities -->

Cuando su organización está inscrita en Escritorio administrado de Microsoft, ¿qué hace Microsoft por usted? ¿Y cuáles son las responsabilidades de su organización?

## <a name="microsofts-roles-and-responsibilities"></a>Roles y responsabilidades de Microsoft

Microsoft proporciona estos roles y responsabilidades clave:

Rol o responsabilidad | Descripción
--- | ---
Administración de directivas MDM | Microsoft aplicará directivas MDM de acuerdo con los procedimientos recomendados y tendrá en cuenta las solicitudes de cambios de directiva. También realizaremos cambios en el espacio empresarial según lo establecido en [Directivas de dispositivo.](../service-description/device-policies.md)
compatibilidad con usuarios | Proporcionamos soporte al usuario para dispositivos, Windows y el conjunto de productos de Aplicaciones Microsoft 365 para empresas para todos los usuarios inscritos Obtener ayuda través de la aplicación Obtener ayuda preinstalada en todos los dispositivos Escritorio administrado de Microsoft cliente. 
Escritorio administrado de Microsoft servicio de soporte técnico | Microsoft proporcionará soporte técnico a su departamento de TI a través de Escritorio administrado de Microsoft Operations Team. Este equipo admitirá la solución de problemas técnicos, las solicitudes de cambio y la administración de incidentes para el entorno de Escritorio administrado de Microsoft cliente. Para obtener más información, vea [Admin support for Escritorio administrado de Microsoft](../working-with-managed-desktop/admin-support.md).
Supervisión de seguridad | Microsoft supervisará los dispositivos Escritorio administrado de Microsoft con Microsoft Defender para endpoint. Si el centro Escritorio administrado de Microsoft operaciones de seguridad (SOC) detecta una amenaza, le notificaremos, aislaremos el dispositivo y corregiremos el problema de forma remota. Para obtener más información, vea [Security](../service-description/security.md).
Supervisión y administración de actualizaciones | Supervisamos activamente los dispositivos Escritorio administrado de Microsoft para garantizar que se instalen las actualizaciones de características y de calidad más recientes para Microsoft Windows y Microsoft Office. Para obtener más información, vea [How updates are handled](../service-description/updates.md).
Agrupación de usuarios y dispositivos | Escritorio administrado de Microsoft de operaciones creará y administrará los grupos de usuarios y dispositivos necesarios como parte de las operaciones de TI. No se permiten cambios de configuración o pertenencia a estos grupos. La modificación de estos grupos puede provocar una configuración inesperada de los dispositivos y la pérdida de funcionalidad. Para cualquier problema o pregunta sobre estos grupos una vez establecido, los administradores de TI pueden ponerse en contacto Escritorio administrado de Microsoft operaciones. Para obtener más información, vea [Admin support for Escritorio administrado de Microsoft](../working-with-managed-desktop/admin-support.md).

## <a name="your-roles-and-responsibilities"></a>Sus roles y responsabilidades

Este conjunto de roles y responsabilidades comunes es necesario para la implementación, pero Microsoft no lo proporciona. No es exhaustivo, pero es aplicable para la mayoría de las organizaciones. Hay algunos elementos de los que tanto usted como Microsoft comparten responsabilidad. 

Rol o responsabilidad | Descripción
--- | ---
Administración de cambios | Microsoft notificará a los clientes, con antelación, cuándo es necesario realizar cambios en su entorno Escritorio administrado de Microsoft cliente. Para obtener más información, vea [service changes and communication](../service-description/servicechanges.md).<br><br>Debe tener su propio proceso de administración de cambios y tener un contacto establecido con el Escritorio administrado de Microsoft operaciones. También debe tener recursos para revisar y aprobar estos cambios. Para obtener más información, vea [Operaciones y supervisión.](../service-description/operations-and-monitoring.md)  
Administración de identidades | Es responsable de crear cuentas de usuario, asignar usuarios a grupos y mantener los metadatos actualizados. 
Aplicaciones Microsoft 365 para empresas configuración y administración | Microsoft es responsable de garantizar que Office aplicaciones se implementen en los usuarios y que dichas aplicaciones se mantienen actualizadas. <br><br> Usted es responsable de administrar Microsoft 365 y directivas, incluidas Exchange Online de administración:<br>- Administración de correo electrónico<br>- Configuración de buzones y reglas<br>- Exchange administración local<br><br>También es responsable de las herramientas de colaboración, SharePoint administración de servidores, administración de dominios y directivas de seguridad e información que se establecen en el centro Microsoft 365 administración. 
Soporte al usuario | Debe proporcionar soporte técnico al usuario para: <br>- Infraestructura local: toda la conectividad a Internet y de red, la infraestructura VPN y la configuración de cliente, el equipamiento de la sala de conferencias local, las impresoras, el servidor proxy y la configuración, y los firewalls.<br><br>- Recursos de nube de toda la empresa: correo electrónico, SharePoint, servicios de colaboración y otra infraestructura en la nube relacionada con la superficie tecnológica de toda la empresa.<br><br>- Línea de negocio y cualquier otra aplicación específica de la empresa.
Aplicaciones | Los roles y responsabilidades varían un poco para las aplicaciones proporcionadas como parte de Escritorio administrado de Microsoft frente a las aplicaciones que proporcionas. <br><br>Para las aplicaciones proporcionadas por Microsoft (Aplicaciones Microsoft 365 para empresas que incluyen Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype Empresarial, Teams y OneNote), **Microsoft** proporcionará un servicio completo para la implementación, actualización y soporte técnico. **Debes** obtener y asignar licencias para estas aplicaciones, agregar usuarios a grupos de seguridad y administrar el final de la vida útil e implementar los complementos que necesites.<br><br>Para las aplicaciones que proporciones (como las aplicaciones de línea de negocio), tanto si las empaquetas tú mismo como si participas con un proveedor que no es de Microsoft **para** hacerlo, eres responsable de estas acciones: <br><br>- Identificación de aplicaciones necesarias para grupos de usuarios dirigidos<br>- Creación y administración de grupos de Azure AD para la implementación de aplicaciones<br>- Empaquetar aplicaciones para cumplir Microsoft Intune estándares de implementación<br>- Cargar aplicaciones en Microsoft Intune<br>- Probar aplicaciones en Escritorio administrado de Microsoft entorno<br>- Probar aplicaciones con los usuarios<br>- Administración y asignación de usuarios a aplicaciones<br>- Identificar e implementar actualizaciones de aplicaciones a través de Microsoft Intune<br>- Desinstalación y eliminación de aplicaciones cuando se han retirado<br>- Obtención y asignación de licencias<br>- Proporcionar soporte al usuario para aplicaciones de línea de negocio<br>- Administrar la configuración de la aplicación de forma remota<br><br>**Microsoft** proporcionará Microsoft Intune de implementación para entregar las aplicaciones a clientes remotos.<br><br>Para obtener más información, vea [Aplicaciones](../get-ready/apps.md).
Control y respuesta de seguridad | Es responsable de investigar y resolver incidentes de dispositivos que no son dispositivos Escritorio administrado de Microsoft y de asegurarse de que el equipo de operaciones de Escritorio administrado de Microsoft esté informado de cualquier problema que pueda afectar al servicio.
Compatibilidad con operaciones | Debe proporcionar una lista de contactos preferidos y expertos en la materia en su organización. Necesitamos estos contactos si hay un incidente operativo no relacionado con Escritorio administrado de Microsoft. <br><br>También es responsable de investigar y resolver incidentes para dispositivos y servicios que no están en Escritorio administrado de Microsoft y asegurarse de que el equipo de operaciones de Escritorio administrado de Microsoft siempre esté informado.
Infraestructura de red, incluida VPN | Es responsable de la configuración, configuración y administración (incluida la solución de problemas y la depuración) de todas las infraestructuras y servicios relacionados con redes, incluida la conectividad a Internet, los controles de red, la configuración de proxy y la infraestructura de conectividad remota.<br><br>Si se configura un proxy (en hardware o software), hay una colección de direcciones URL que debe permitir el proxy. Eres responsable de solucionar cualquier conflicto o incompatibilidad debido a varios servidores proxy. Puede agregar servidores proxy de red específicos de su organización mediante la configuración configurable. Para obtener más información, vea [Configuración configurable](../working-with-managed-desktop/config-setting-ref.md#proxy).<br><br>Para obtener más información, vea [Configuración de proxy](../get-ready/network.md).
Impresión | Es responsable de instalar, mantener y administrar impresoras y colas de impresión. La impresión en la nube es una solución recomendada, pero no es necesaria. 




