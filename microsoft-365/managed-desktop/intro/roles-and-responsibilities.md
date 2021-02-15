---
title: Roles y responsabilidades del Escritorio administrado de Microsoft
description: En este artículo se describen los roles y responsabilidades proporcionados por Microsoft para escritorio administrado de Microsoft.
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

Cuando su organización se inscribe en el Escritorio administrado de Microsoft, ¿qué hace Microsoft por usted? ¿Y cuáles son las responsabilidades de su organización?

## <a name="microsofts-roles-and-responsibilities"></a>Roles y responsabilidades de Microsoft

Microsoft proporciona estas funciones y responsabilidades clave:

Rol o responsabilidad | Description
--- | ---
Administración de directivas MDM | Microsoft aplicará directivas MDM de acuerdo con los procedimientos recomendados y tendrá en cuenta las solicitudes de cambios de directiva. También realizaremos cambios en el espacio empresarial según se indique en las [directivas de dispositivo.](../service-description/device-policies.md)
compatibilidad con usuarios | Proporcionamos soporte al usuario para dispositivos, Windows y el conjunto de productos Aplicaciones de Microsoft 365 para empresas para todos los usuarios inscritos a través de la aplicación Obtener ayuda preinstalada en todos los dispositivos de Escritorio administrado de Microsoft. 
Compatibilidad con el servicio de Escritorio administrado de Microsoft | Microsoft proporcionará soporte técnico a su departamento de TI a través de un equipo de operaciones de escritorio administrado de Microsoft. Este equipo admitirá la solución de problemas técnicos, las solicitudes de cambio y la administración de incidentes para el entorno de Escritorio administrado de Microsoft del cliente. Para obtener más información, vea [Soporte técnico para administradores de Escritorio administrado de Microsoft.](../working-with-managed-desktop/admin-support.md)
Supervisión de seguridad | Microsoft supervisará los dispositivos de Escritorio administrado de Microsoft con Microsoft Defender para Endpoint. Si el Centro de operaciones de seguridad de escritorio administrado (SOC) de Microsoft detecta una amenaza, le notificaremos, aislaremos el dispositivo y corregiremos el problema de forma remota. Para obtener más información, vea [Seguridad.](../service-description/security.md)
Supervisión y administración de actualizaciones | Supervisamos activamente los dispositivos de Escritorio administrado de Microsoft para garantizar que se instalen las actualizaciones de calidad y características más recientes para Microsoft Windows y Microsoft Office. Para obtener más información, vea [Cómo se controlan las actualizaciones.](../service-description/updates.md)
Agrupación de usuarios y dispositivos | El equipo de operaciones de Escritorio administrado de Microsoft creará y administrará los grupos de usuarios y dispositivos necesarios como parte de las operaciones de TI. No se permiten cambios de configuración ni pertenencia a estos grupos. La modificación de estos grupos puede provocar una configuración inesperada de dispositivos y la pérdida de funcionalidad. Para cualquier problema o pregunta sobre estos grupos una vez establecido, los administradores de TI pueden ponerse en contacto con las operaciones de Escritorio administrado de Microsoft. Para obtener más información, vea [Soporte técnico para administradores de Escritorio administrado de Microsoft.](../working-with-managed-desktop/admin-support.md)

## <a name="your-roles-and-responsibilities"></a>Sus roles y responsabilidades

Este conjunto de roles y responsabilidades comunes es necesario para la implementación, pero Microsoft no lo proporciona. No es exhaustivo, pero es aplicable para la mayoría de las organizaciones. Hay algunos elementos de los que usted y Microsoft comparten su responsabilidad. 

Rol o responsabilidad | Description
--- | ---
Administración de cambios | Microsoft notificará a los clientes con antelación cuándo es necesario realizar cambios en su entorno de Escritorio administrado de Microsoft. Para obtener más información, vea [los cambios en el servicio y la comunicación.](../service-description/servicechanges.md)<br><br>Debe tener su propio proceso de administración de cambios y tener un contacto establecido con el equipo de operaciones de escritorio administrado de Microsoft. También debe tener recursos para revisar y aprobar estos cambios. Para obtener más información, vea [Operaciones y supervisión.](../service-description/operations-and-monitoring.md)  
Administración de identidades | Usted es responsable de crear cuentas de usuario, asignar usuarios a grupos y mantener actualizados los metadatos. 
Administración y configuración de Aplicaciones de Microsoft 365 para empresas | Microsoft es responsable de garantizar que las aplicaciones de Office se implementen en los usuarios y que dichas aplicaciones se mantienen actualizadas. <br><br> Usted es responsable de administrar los servicios y directivas de Microsoft 365, incluidas las responsabilidades de administración de Exchange Online:<br>- Administración de correo electrónico<br>- Configuración de buzones y reglas<br>- Administración local de Exchange<br><br>También es responsable de las herramientas de colaboración, la administración del servidor de SharePoint, la administración de dominios y las directivas de seguridad e información que se establecen en el Centro de administración de Microsoft 365. 
Soporte al usuario | Debe proporcionar soporte al usuario para: <br>- Infraestructura in situ: toda la conectividad de red e Internet, la infraestructura VPN y la configuración del cliente, el equipamiento de la sala de conferencias local, las impresoras, el servidor proxy y la configuración, y los firewalls.<br><br>- Recursos en la nube de toda la empresa: correo electrónico, SharePoint, servicios de colaboración y otra infraestructura en la nube relacionada con la superficie tecnológica de toda la empresa.<br><br>- Línea de negocio y cualquier otra aplicación específica de la empresa.
Aplicaciones | Los roles y responsabilidades varían en cierta medida para las aplicaciones proporcionadas como parte del Escritorio administrado de Microsoft frente a las aplicaciones que proporciona. <br><br>Para las aplicaciones proporcionadas por Microsoft (Aplicaciones de Microsoft 365 para empresas que incluyen Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype Empresarial, Teams y OneNote), **Microsoft** proporcionará un servicio completo para la implementación, actualización y soporte técnico. **Debes** obtener y asignar licencias para estas aplicaciones, agregar usuarios a grupos de seguridad, administrar el final del ciclo de vida e implementar los complementos que necesites.<br><br>En el caso de las aplicaciones que proporciones (como las aplicaciones de línea de negocio), tanto si las empaquetas tú mismo como si quieres que un proveedor que no sea de Microsoft lo **hagas,** eres responsable de estas acciones: <br><br>- Identificación de aplicaciones necesarias para grupos de usuarios de destino<br>- Crear y administrar grupos de Azure AD para la implementación de aplicaciones<br>- Empaquetar aplicaciones para cumplir con los estándares de implementación de Microsoft Intune<br>- Cargar aplicaciones en Microsoft Intune<br>- Probar aplicaciones en el entorno de Escritorio administrado de Microsoft<br>- Probar aplicaciones con los usuarios<br>- Administrar y asignar usuarios a aplicaciones<br>- Identificar e implementar actualizaciones de aplicaciones a través de Microsoft Intune<br>- Desinstalación y eliminación de aplicaciones cuando se han retirado<br>- Adquirir y asignar licencias<br>- Proporcionar soporte al usuario para aplicaciones de línea de negocio<br>- Administrar la configuración de la aplicación de forma remota<br><br>**Microsoft** proporcionará herramientas de implementación de Microsoft Intune para entregar las aplicaciones a clientes remotos.<br><br>Para obtener más información, vea [Aplicaciones.](../get-ready/apps.md)
Control y respuesta de seguridad | Usted es responsable de investigar y resolver incidentes para dispositivos que no son dispositivos de Escritorio administrado de Microsoft y asegurarse de que el equipo de operaciones de escritorio administrado de Microsoft esté informado de cualquier problema que pueda afectar al servicio.
Compatibilidad con operaciones | Debe proporcionar una lista de contactos preferidos y expertos en la materia de su organización. Necesitamos estos contactos si hay un incidente operativo no relacionado con el Escritorio administrado de Microsoft. <br><br>También es responsable de investigar y resolver incidentes para dispositivos y servicios que no están en el Escritorio administrado de Microsoft y asegurarse de que siempre se informa al equipo de operaciones de escritorio administrado de Microsoft.
Infraestructura de red, incluida VPN | Usted es responsable de la configuración, configuración y administración (incluida la solución de problemas y la depuración) de toda la infraestructura y los servicios relacionados con las redes, incluida la conectividad a Internet, los controles de red, la configuración de proxy y la infraestructura de conectividad remota.<br><br>Si se configura un proxy (en hardware o software), hay una colección de direcciones URL que el proxy debe permitir. Usted es responsable de solucionar los conflictos o incompatibilidades debido a varios servidores proxy. Puede agregar servidores proxy de red específicos de su organización mediante configuraciones configurables. Para obtener más información, vea [Configuración configurable.](../working-with-managed-desktop/config-setting-ref.md#proxy)<br><br>Para obtener más información, vea [Configuración de proxy.](../get-ready/network.md)
Impresión | Usted es responsable de instalar, mantener y administrar impresoras y colas de impresión. La impresión en la nube es una solución recomendada, pero no es necesaria. 




