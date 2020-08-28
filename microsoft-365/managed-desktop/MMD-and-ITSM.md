---
title: Escritorio administrado de Microsoft e ITIL
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Service, documentation, ITISM
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.openlocfilehash: 05bd5a2ee36633b7ccf9ae61e601988a7268bb2c
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289810"
---
# <a name="microsoft-managed-desktop-and-itil"></a>Escritorio administrado de Microsoft e ITIL

A muchas organizaciones les resulta útil estructurar sus servicios de ti junto con las líneas de un modelo de servicio de ti formalizado (ITSM), como [ITIL](https://www.axelos.com/best-practice-solutions/itil). 

Microsoft Managed Desktop permite a su organización cumplir con muchos aspectos clave de estos modelos ITSM formalizados. Utilizando ITIL como ejemplo, este tema le ayudará a ver las conexiones entre fases y procesos comunes de ITIL y las características de escritorio administrado de Microsoft equivalentes, cuando corresponda. Esto solo se aplica a la parte del escritorio administrado de Microsoft de la organización.

Para obtener más información sobre ITIL y sus fases y procesos, consulte su [documentación](https://www.axelos.com/best-practice-solutions/itil).


## <a name="service-design"></a>Diseño del servicio

Esta tabla relaciona los procesos y las fases clave de ITIL con las características del escritorio administrado por Microsoft, con vínculos a nuestra documentación para obtener más información:



|Proceso de ITIL |Descripción  |Documentación |
|---------|---------|---------|
|Administración de nivel de servicio     | Los tiempos de respuesta se definen para solicitudes y incidentes de soporte de administración.  |  [Soporte técnico de administrador para Escritorio administrado de Microsoft](working-with-managed-desktop/admin-support.md)  |
|Administración de catálogos de servicios     | Descripción del servicio los componentes del servicio se mantienen verdaderos al estado del servicio, disponible para todos los clientes actuales y interesados.<br><br>Requisitos previos detallados para comprender lo que se necesita para operar el servicio.  | - [Descripción del servicio de escritorio administrado de Microsoft](service-description/index.md)<br><br>- [Prepárese para la inscripción en el escritorio administrado de Microsoft](get-ready/index.md)  |
|Administración de seguridad de la información     | Información de seguridad, incluida la seguridad de la información del servicio.<br><br> Directivas relacionadas con la seguridad y otra información sobre cómo se configuran los dispositivos.   | - [Seguridad en el escritorio administrado por Microsoft](service-description/security.md)<br><br>- [Configuración de dispositivo](service-description/device-policies.md)  |
|Administración de la disponibilidad     |  Microsoft Managed Desktop equilibra la responsabilidad con su organización para garantizar la disponibilidad del servicio.<br><br>Los administradores y los usuarios tienen rutas para la asistencia correspondiente en caso de problemas de servicio o de disponibilidad. | - [Supervisión y operaciones de escritorio administradas de Microsoft](service-description/operations-and-monitoring.md)<br><br>- [Soporte de administración para escritorio administrado de Microsoft](working-with-managed-desktop/admin-support.md)<br>- [Obtener ayuda para usuarios](working-with-managed-desktop/end-user-support.md)  |



## <a name="service-transition"></a>Transición de servicio


|Proceso de ITIL |Descripción  |Documentación |
|---------|---------|---------|
|Administración de cambios     | El saldo de responsabilidades, la información general del proceso y los tipos definidos relacionados con la administración de cambios están disponibles.  | [Supervisión y operaciones de escritorio administradas de Microsoft](service-description/operations-and-monitoring.md#change-management) |
|Administración de versiones e implementaciones     |  Microsoft Managed Desktop administra actualizaciones para los dispositivos inscritos en el servicio.  | [Cómo se administran las actualizaciones en el escritorio administrado por Microsoft](service-description/updates.md)        |
|Administración de los activos y la configuración del servicio     | La información sobre la implementación de escritorio administrada de Microsoft de su organización está disponible en el portal de administración de ti.  | [Soporte técnico de administrador para Escritorio administrado de Microsoft](working-with-managed-desktop/admin-support.md) |
|Administración del conocimiento     | La información sobre el servicio de escritorio administrado de Microsoft se mantiene actualizada en este sitio.   | [Historial de cambios de la documentación del Escritorio administrado de Microsoft](change-history-managed-desktop.md)        |



## <a name="service-operation"></a>Operación del servicio


|Proceso de ITIL |Descripción  |Documentación  |
|---------|---------|---------|
|Administración de eventos     |  Se proporcionan detalles sobre la supervisión de dispositivos.<br><br>Se detallan los procedimientos de funcionamiento estándar para el servicio de escritorio administrado de Microsoft. |  - [Seguridad en el escritorio administrado por Microsoft](service-description/security.md)<br>- [Supervisión y operaciones de escritorio administradas de Microsoft](service-description/operations-and-monitoring.md)       |
|Administración de incidentes  | El escritorio administrado de Microsoft investigará y actuará en incidentes por definiciones de gravedad definidas.  |  [Definiciones de gravedad de solicitud de soporte](working-with-managed-desktop/admin-support.md#support-request-severity-definitions)       |
|Administración de solicitudes de cumplimiento     |  Se ha definido el proceso de solicitud de información y solicitudes de cambio relacionadas con el servicio de escritorio administrado de Microsoft.         |[Soporte técnico de administrador para Escritorio administrado de Microsoft](working-with-managed-desktop/admin-support.md)         |
|Administración de problemas     | Cualquier problema con el servicio debe dirigirse a su equipo de cuentas locales en este momento. | Documentación en desarrollo |
|Administración de acceso     | Obtener acceso a los componentes de administración y responsabilidades del cliente para garantizar que la funcionalidad se detalla.  | [Administración de identidad y acceso](service-description/security.md#identity-and-access-management)        |
