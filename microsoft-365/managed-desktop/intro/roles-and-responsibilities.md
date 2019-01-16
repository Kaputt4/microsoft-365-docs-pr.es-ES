---
title: Responsabilidades y funciones de escritorio administrado de Microsoft
description: En este tema se describe las funciones y responsabilidades proporcionadas por Microsoft para Microsoft Managed Desktop.
keywords: Servicio de escritorio administrado de Microsoft, Microsoft 365, documentación
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 96131f7577e0e655067c70bffdd75163ba790adf
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
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
Soporte técnico del usuario final | Microsoft proporcionará soporte técnico para el usuario final para Office, Windows y dispositivos de conjunto de productos para todos los usuarios inscritos a través de la aplicación para obtener ayuda que está preinstalado en todos los dispositivos de escritorio administrado de Microsoft. 
Compatibilidad con el servicio de escritorio administrado de Microsoft | Microsoft proporcionará soporte técnico al cliente de TI departamentos a través de un equipo de operaciones de escritorio administrado de Microsoft. Este equipo va a admitir la solución de problemas técnicos, solicitudes de cambio y administración de incidentes para el entorno del cliente administrado de escritorio de Microsoft. Para obtener más información, vea [administración admitir para escritorio administrado de Microsoft](../working-with-managed-desktop/admin-support.md).
Supervisión de la seguridad | Microsoft va a supervisar los dispositivos de escritorio administrado de Microsoft de cliente mediante Windows Defender ATP. Si se detecta una amenaza por el Microsoft administrados escritorio seguridad operaciones centro (seguridad social), Microsoft le notificará al cliente, aislar el dispositivo y corregir el problema de forma remota. Para obtener más información, vea [seguridad](../service-description/security.md).
Actualice la supervisión y administración | Microsoft va a supervisar activamente los dispositivos de escritorio administrado de Microsoft de cliente para asegurarse de que se instalan las actualizaciones más recientes de la calidad y la característica de Microsoft Windows y Microsoft Office. Para obtener más información, vea [cómo se controlan las actualizaciones](../service-description/updates.md).
Agrupación de dispositivo y de usuario | Equipo de operaciones de escritorio de Microsoft administrado va a crear y administrar dispositivo requerido y grupos de usuarios como parte de las operaciones de TI. No debe ser los cambios realizados en estos grupos sin la aprobación del equipo de operaciones de escritorio de Microsoft administrado.

## <a name="your-roles-and-responsibilities"></a>Sus funciones y responsabilidades

A continuación es un conjunto adicional de funciones comunes y responsabilidades que no son proporcionadas por Microsoft, pero que son necesarios para una implementación correcta. No es exhaustiva pero es aplicable para la mayoría de las organizaciones. Hay algunos elementos debajo de que tanto el cliente de Microsoft compartan responsibilties. 

Función o responsabilidad | Descripción
--- | ---
Administración de cambios | Microsoft le notificará a los clientes, de antemano, cuando los cambios deben realizarse para su entorno de escritorio administrado de Microsoft. El cliente es necesario tener su propia administración de cambio tiene un contacto establecido con el equipo de operaciones de escritorio administrado de Microsoft y el proceso. También se requiere que el cliente dispone de recursos para revisar y aprobar estos cambios. Para obtener más información, vea [las operaciones y supervisión](../service-description/operations-and-monitoring.md).  
Administración de identidades | El cliente es responsable de la creación de cuentas de usuario, asignar a usuarios a grupos y mantener actualizados los metadatos. 
Administración y configuración de office 365 | Microsoft es responsable de garantizar se implementan las aplicaciones de Office a los usuarios finales y las aplicaciones se mantienen actualizadas. <br><br> El cliente es responsable de administrar los servicios de Office 365 y políticas, incluidas las responsabilidades de administración Exchange Online:<br>-Administración correo electrónico<br>-Configuración de regla y mailbox<br>-Exchange local administración<br><br>El cliente también es responsable de las herramientas de colaboración, administración de SharePoint server, administración de dominio, las directivas de información de seguridad y establecer en el portal de administración de Office 365. 
Soporte técnico del usuario final | El cliente es responsable de proporcionar soporte técnico para el usuario final para: <br>-En la infraestructura del sitio: todos los conectividad de red e internet, VPN configuración de infraestructura y cliente, equipamiento de sala de conferencias locales, impresoras, servidor proxy y configuración, los servidores de seguridad.<br><br>Recursos de empresa en la nube: correo electrónico, SharePoint, servicios de colaboración y otras infraestructuras de nube que se relación con el alcance de la tecnología de toda la compañía.<br><br>-Línea de negocio y otras aplicaciones específicas de la empresa.
Aplicaciones | Microsoft le ofrece una guía de implementación para las aplicaciones aprobadas mediante Intune a petición.<br><br>El cliente es responsable de:<br>-Que proporciona una lista de aplicaciones para su organización (fuera de aplicaciones de Office 365)<br>-Administración de licencias de aplicación<br>– Tener el tipo de derecho y la cantidad de licencias<br>-Asignación app<br>– Asignación de aplicaciones a grupos de usuarios de Azure AD<br>-Las actualizaciones de aplicaciones<br>– Supervisión, empaquetar e implementar las actualizaciones de seguridad y la característica de aplicaciones<br>-Aplicación de usuario pruebas (UAT)<br>-Proporcionar un paquete implementable adecuado<br><br>Para obtener más información, vea [aplicaciones](../get-ready/apps.md)
Supervisión de la seguridad y la respuesta | El cliente es responsable de la investigación y resolución de incidentes para los dispositivos que no sean Microsoft administrados escritorio y asegurarse de que el equipo de operaciones de escritorio administrado de Microsoft se le informa de los problemas que pueden afectar el servicio.
Soporte de operaciones | El cliente es responsable de proporcionar una lista de contactos del cliente preferido y expertos en la materia. Microsoft necesita estos en caso de que hay un incidente operativas que no sean - Microsoft Managed Desktop. <br><br>El cliente también es responsable de la investigación y resolución de incidentes para los dispositivos que no sean - administrados escritorio de Microsoft y los servicios y asegurarse de que siempre se informa al equipo de operaciones de escritorio administrado Microsoft.
Infraestructura de red, incluida la VPN | El cliente es responsable del programa de instalación, configuración y administración (incluida la depuración y solución de problemas) de todos los infraestructura relacionadas con las redes y servicios, incluida la conectividad de internet, la red controles, configuración de proxy y remoto infraestructura de conectividad.<br><br>Si se configura un servidor proxy (en hardware o software), hay una colección de direcciones URL que debe ser permitida por el proxy. El cliente es responsable de la solución de problemas de los conflictos o incompatibilidades debido a varios servidores proxy.<br><br>Para obtener más información, vea [Configuración de Proxy](../get-ready/network.md).
Impresión | El cliente es responsable de la instalación, mantenimiento y administración de impresoras y colas de impresión. En la nube impresión es una solución recomendada, pero no es necesaria. 




