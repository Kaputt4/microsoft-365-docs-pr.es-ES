---
title: Responsabilidades y funciones de escritorio administrado de Microsoft
description: En este tema se describe las funciones y responsabilidades proporcionadas por Microsoft para Microsoft Managed Desktop.
keywords: Servicio de escritorio administrado de Microsoft, Microsoft 365, documentación
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 923cde6353e4ff5122317f2c053fef244ee7e1b6
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871800"
---
# <a name="microsoft-managed-desktop-roles-and-responsibilities"></a>Responsabilidades y funciones de escritorio administrado de Microsoft


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/admin-access); do not delete.-->
<!-- from Roles and responsibilities -->

Cuando la organización está inscrito en el escritorio de Microsoft administrado, ¿qué hace Microsoft para usted? Y ¿cuáles son las responsabilidades de la organización?

## <a name="microsofts-roles-and-responsibilities"></a>Los roles y responsabilidades de Microsoft

Las siguientes son algunas funciones claves y responsabilidades que va a ser proporcionadas por Microsoft.

Función o responsabilidad | Descripción
--- | ---
Administración de directivas de MDM | Microsoft va a aplicar directivas MDM según las recomendaciones y tenga en cuenta las solicitudes de cambios de directiva. También se va a realizar cambios en el inquilino tal y como se explica en [las directivas de dispositivo](../service-description/device-policies.md).
Implementación de aplicaciones | Microsoft va a implementar las aplicaciones aprobadas para dispositivos de escritorio de Microsoft administrado del cliente mediante Intune. Para obtener más información, vea [Apps](../get-ready/apps.md). 
Soporte técnico del usuario final | Microsoft proporcionará soporte técnico para el usuario final para Office, Windows y dispositivos de conjunto de productos para todos los usuarios inscritos. 
Compatibilidad con el servicio de escritorio administrado de Microsoft | Microsoft proporcionará soporte técnico al cliente de TI departamentos a través de un equipo de operaciones de escritorio administrado de Microsoft. Este equipo va a admitir la solución de problemas técnicos, solicitudes de cambio y administración de incidentes para el entorno del cliente administrado de escritorio de Microsoft. Para obtener más información, vea [obtener soporte técnico](../service-description/support.md).
Supervisión de la seguridad | Microsoft va a supervisar los dispositivos de escritorio administrado de Microsoft de cliente mediante Windows Defender ATP. Si se detecta una amenaza por el Microsoft administrados escritorio seguridad operaciones centro (seguridad social), Microsoft le notificará al cliente, aislar el dispositivo y corregir el problema de forma remota. Para obtener más información, vea [seguridad](../service-description/security.md).
Actualice la supervisión y administración | Microsoft va a supervisar activamente los dispositivos de escritorio administrado de Microsoft de cliente para asegurarse de que se instalan las actualizaciones más recientes de calidad, la característica y definición de Microsoft Windows y Microsoft Office. Para obtener más información, vea [cómo se controlan las actualizaciones](../service-description/updates.md).
Adquisición de dispositivo | Microsoft entrega ordenada los dispositivos de escritorio administrado de Microsoft para los usuarios finales o el punto de distribución de TI de su elección. Para obtener más información, vea [dispositivos](../get-started/devices.md).

## <a name="your-roles-and-responsibilities"></a>Sus funciones y responsabilidades

A continuación es un conjunto adicional de funciones comunes que no son proporcionados por Microsoft, pero son necesarios para una implementación correcta. No es exhaustiva pero es típica para la mayoría de las organizaciones. 

Función o reponsibility | Descripción
--- | ---
Administración de cambios | Escritorio administrado de Microsoft notificará a los clientes, de antemano, cuando los cambios deben realizarse para su entorno de escritorio administrado de Microsoft. Los clientes necesitan tener su propio proceso de administración de cambios y son necesarios para que un contacto con Microsoft Managed Desktop. Se requiere que el cliente dispone de recursos para revisar y aprobar estos cambios. Para obtener más información, vea [las operaciones y supervisión](../service-description/operations-and-monitoring.md).  
Administración de identidades | Creación de cuentas de usuario, asignar a usuarios a grupos y mantener actualizados los metadatos. 
Administración y configuración de office 365 | Administración de Oonline de Exchange, incluidos:<br>-Administración correo electrónico<br>-Configuración de regla y mailbox<br>-Exchange local administración<br><br>Herramientas de colaboración, administración de SharePoint server, administración de dominio, las directivas de información de seguridad y establecer en el portal de administración de Office 365 (Microsoft Managed Desktop asegurará las aplicaciones de Office se implementan en los dispositivos de usuario final y mantengan al día). 
Soporte técnico del usuario final | El cliente proporcionará soporte técnico para el usuario final para: <br>-En la infraestructura del sitio: todos los conectividad de red e internet, VPN configuración de infraestructura y cliente, equipamiento de sala de conferencias locales, impresoras, servidor proxy y configuración, los servidores de seguridad.<br><br>Recursos de empresa en la nube: correo electrónico, SharePoint, servicios de colaboración y otras infraestructuras de nube que se relación con el alcance de la tecnología de toda la compañía.<br><br>Las aplicaciones de línea-de negocio: software personalizado, software de terceros 3rd, software de enterprise resource planning (ERP), herramientas de diseño y no especificar nada en este documento.
Agrupación de dispositivo y de usuario | Equipo de operaciones de escritorio de Microsoft administrado va a crear y administrar dispositivo requerido y grupos de usuarios como parte de las operaciones de TI. El cliente no va a realizar cambios en estas agrupaciones sin primero ponerse en contacto con las operaciones de TI a través de canales admitidos. Todos los detectados cambios se pueden revertir.
Aplicaciones | Los clientes proporcionará una lista de aplicaciones que desea usar en su organización (más allá de aplicaciones que se incluyen con licencia de Microsoft 365). Los clientes también proporcionan un paquete implementable (Appx o MSI)<br>El cliente es responsable de:<br>-Administración de licencias app – tener el tipo de derecho y la cantidad de licencias<br>-Asignación app – asignar aplicaciones a grupos de usuarios de Azure AD<br>-Actualizaciones de app: supervisión, empaquetar e implementar las actualizaciones de seguridad y la característica de aplicaciones<br>-Aplicación de usuario pruebas (UAT)<br><br>Para obtener más información, vea [aplicaciones](../get-ready/apps.md)
Supervisión de la seguridad y la respuesta | Si se detecta un incidente de seguridad que está fuera del ámbito de operaciones de escritorio administrado de Microsoft, se necesitará una lista de contactos del cliente preferido en función de la gravedad del problema.<br><br>El cliente es responsable de la investigación y resolución de incidentes para los dispositivos que no sean Microsoft administrados escritorio y asegurarse de que el equipo de operaciones de escritorio administrado de Microsoft se le informa de los problemas que pueden afectar el servicio.
Soporte de operaciones | Operaciones de escritorio de Microsoft administrado necesita una lista de contactos del cliente preferido y expertos en la materia. Necesitamos estos en caso de que hay un incidente operativas que no sean - Microsoft Managed Desktop. <br><br>El cliente es responsable de la investigación y resolución de incidentes para los dispositivos que no sean - administrados escritorio de Microsoft y los servicios y asegurarse de que siempre se informa al equipo de operaciones de escritorio administrado Microsoft.
Infraestructura de red, incluida la VPN | El programa de instalación, configuración y administración (incluida la depuración y solución de problemas) de la infraestructura de todas las relacionadas con las redes y servicios, incluida la conectividad de internet, la red controles, la configuración de proxy y la infraestructura de conectividad remota.<br><br>De forma predeterminada, Microsoft Managed Desktop no especificar o requieren a un servidor proxy. Sin embargo, si hay uno configurado (en hardware o software), es una colección de direcciones URL que se debe permitir el proxy. El cliente es responsable de la solución de problemas de los conflictos o incompatibilidades debido a varios servidores proxy.<br><br>Para obtener más información, vea [Configuración de Proxy](../get-ready/network.md).
Impresión | Instalar, mantener y administrar las impresoras y colas de impresión. En la nube impresión es una solución recomendada, pero no es necesaria. 
Dispositivos móviles | Dispositivos y accesorios no proporcionados por Microsoft Managed Desktop. Equipo de operaciones de escritorio administrado de Microsoft sólo es compatible con el dispositivo de escritorio de Microsoft administrado, estación de acoplamiento y Accesorios incluidos.




