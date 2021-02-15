---
title: Escritorio administrado de Microsoft e ITIL
description: Correlaciona las fases de ITIL con la información y los artículos de Escritorio administrado de Microsoft
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación, ITISM
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.openlocfilehash: e545b64670bb92c40465f1c50b2cb46b9fd7a8d8
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841440"
---
# <a name="microsoft-managed-desktop-and-itil"></a>Escritorio administrado de Microsoft e ITIL

Muchas organizaciones encuentran valioso estructurar sus servicios de TI según un modelo de servicio de TI (ITSM) formalizado, como [ITIL](https://www.axelos.com/best-practice-solutions/itil). 

Escritorio administrado de Microsoft permite a su organización cumplir con muchos aspectos clave de estos modelos DE ITSM formalizados. Con ITIL como ejemplo, este artículo le ayuda a ver las conexiones entre fases y procesos comunes de ITIL y las características equivalentes de Escritorio administrado de Microsoft, si procede. Esta información solo se aplica a la parte de Escritorio administrado de Microsoft de su organización.

Para obtener información más completa sobre ITIL y sus fases y procesos, consulte su [documentación.](https://www.axelos.com/best-practice-solutions/itil)


## <a name="service-design"></a>Diseño de servicio

En esta tabla se relacionan las fases y procesos clave de ITIL con las características de Escritorio administrado de Microsoft, con vínculos a nuestra documentación para obtener más información:



|Proceso ITIL |Description  |Documentación |
|---------|---------|---------|
|Administración de nivel de servicio     | Los tiempos de respuesta se definen para solicitudes e incidentes de soporte técnico de administrador.  |  [Soporte técnico de administrador para Escritorio administrado de Microsoft](working-with-managed-desktop/admin-support.md)  |
|Administración del catálogo de servicios     | La descripción del servicio que detalla los componentes del servicio se mantiene en el estado del servicio, disponible para todos los clientes actuales e interesados.<br><br>Requisitos previos detallados para comprender lo que se necesita para operar el servicio.  | - [Descripción del servicio de Escritorio administrado de Microsoft](service-description/index.md)<br><br>- [Prepararse para la inscripción en el Escritorio administrado de Microsoft](get-ready/index.md)  |
|Administración de seguridad de la información     | Información de seguridad, incluida la seguridad de la información del servicio.<br><br> Directivas relacionadas con la seguridad y otra información sobre cómo se configuran los dispositivos.   | - [Seguridad en escritorio administrado de Microsoft](service-description/security.md)<br><br>- [Configuración de dispositivos](service-description/device-policies.md)  |
|Administración de disponibilidad     |  Escritorio administrado de Microsoft equilibra la responsabilidad con su organización para garantizar la disponibilidad del servicio.<br><br>Los administradores y usuarios tienen rutas para el soporte técnico respectivo si hay problemas de disponibilidad o servicio. | - [Supervisión y operaciones de Escritorio administrado de Microsoft](service-description/operations-and-monitoring.md)<br><br>- [Soporte técnico para administradores para Escritorio administrado de Microsoft](working-with-managed-desktop/admin-support.md)<br>- [Obtener ayuda para los usuarios](working-with-managed-desktop/end-user-support.md)  |



## <a name="service-transition"></a>Transición de servicio


|Proceso ITIL |Description  |Documentación |
|---------|---------|---------|
|Administración de cambios     | Equilibrio definido de responsabilidad, información general del proceso y tipos relacionados con la administración de cambios disponibles.  | [Supervisión y operaciones de Escritorio administrado de Microsoft](service-description/operations-and-monitoring.md#change-management) |
|Administración de lanzamientos e implementación     |  Escritorio administrado de Microsoft administra las actualizaciones de los dispositivos inscritos en el servicio.  | [Cómo se controlan las actualizaciones en el Escritorio administrado de Microsoft](service-description/updates.md)        |
|Administración de activos de servicio y configuración     | La información sobre la implementación de Escritorio administrado de Microsoft de su organización está disponible en el portal de administración de TI.  | [Soporte técnico de administrador para Escritorio administrado de Microsoft](working-with-managed-desktop/admin-support.md) |
|Administración del conocimiento     | La información sobre el servicio de escritorio administrado de Microsoft se mantiene actualizada en este sitio.   | [Historial de cambios de la documentación del Escritorio administrado de Microsoft](change-history-managed-desktop.md)        |



## <a name="service-operation"></a>Operación de servicio


|Proceso ITIL |Description  |Documentación  |
|---------|---------|---------|
|Administración de eventos     |  Se proporcionan detalles sobre la supervisión de dispositivos.<br><br>Se detallan los procedimientos operativos estándar para el servicio de escritorio administrado de Microsoft. |  - [Seguridad en escritorio administrado de Microsoft](service-description/security.md)<br>- [Supervisión y operaciones de Escritorio administrado de Microsoft](service-description/operations-and-monitoring.md)       |
|Administración de incidencias  | Escritorio administrado de Microsoft investigará y actuará en caso de incidentes según las definiciones de gravedad definidas.  |  [Admitir definiciones de gravedad de solicitud](working-with-managed-desktop/admin-support.md#support-request-severity-definitions)       |
|Administración del suministro de solicitudes     |  Se define el proceso de solicitudes de información y solicitudes de cambio relacionadas con el servicio de escritorio administrado de Microsoft.         |[Soporte técnico de administrador para Escritorio administrado de Microsoft](working-with-managed-desktop/admin-support.md)         |
|Administración de problemas     | Cualquier problema con el servicio debe dirigirse a su equipo de cuenta local en este momento. | Documentación en desarrollo |
|Administración de acceso     | Componentes de administración de acceso y responsabilidades del cliente para garantizar que se detalla la funcionalidad.  | [Administración de identidad y acceso](service-description/security.md#identity-and-access-management)        |
