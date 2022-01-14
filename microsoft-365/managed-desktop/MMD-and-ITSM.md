---
title: Escritorio administrado de Microsoft e ITIL
description: Correlaciona las fases de ITIL con la información y los artículos de Escritorio administrado de Microsoft
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación, ITISM
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: b9984e308b6681512297e484817f95206283385e
ms.sourcegitcommit: a6651b841f111ea2776cab88bf2c80f805fa8e09
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2022
ms.locfileid: "62035093"
---
# <a name="microsoft-managed-desktop-and-itil"></a>Escritorio administrado de Microsoft e ITIL

Muchas organizaciones encuentran valioso estructurar sus servicios de TI en la línea de un modelo de servicio de TI (ITSM) formalizado, como [ITIL.](https://www.axelos.com/best-practice-solutions/itil) 

Microsoft Managed Desktop permite a su organización cumplir con muchos aspectos clave de estos modelos ITSM formalizados. Con ITIL como ejemplo, este artículo le ayuda a ver las conexiones entre fases y procesos comunes de ITIL y las características equivalentes de Escritorio administrado de Microsoft, cuando corresponda. Esta información solo se aplica a la parte de Escritorio administrado de Microsoft de la organización.

Para obtener información más completa sobre ITIL y sus fases y proceso, consulte su [documentación](https://www.axelos.com/best-practice-solutions/itil).


## <a name="service-design"></a>Diseño de servicio

En esta tabla se relacionan las fases y procesos clave de ITIL con las características de Escritorio administrado de Microsoft, con vínculos a nuestra documentación para obtener más información:



|Proceso itil |Descripción  |Documentación |
|---------|---------|---------|
|Administración de nivel de servicio     | Los tiempos de respuesta se definen para solicitudes e incidentes de soporte técnico de administrador.  |  [Soporte técnico de administrador para Escritorio administrado de Microsoft](working-with-managed-desktop/admin-support.md)  |
|Administración del catálogo de servicios     | La descripción del servicio que detalla los componentes del servicio se mantiene fiel al estado del servicio, disponible para todos los clientes actuales e interesados.<br><br>Requisitos previos detallados para comprender lo que se necesita para operar el servicio.  | - [Descripción del servicio de Escritorio administrado de Microsoft](service-description/index.md)<br><br>- [Prepárese para la inscripción en Microsoft Managed Desktop](get-ready/index.md)  |
|Administración de seguridad de la información     | Información de seguridad, incluida la seguridad de la información del servicio.<br><br> Directivas relacionadas con la seguridad y otra información sobre cómo se configuran los dispositivos.   | - [Seguridad en El escritorio administrado de Microsoft](service-description/security.md)<br><br>- [Configuración del dispositivo](service-description/device-policies.md)  |
|Administración de disponibilidad     |  Microsoft Managed Desktop equilibra la responsabilidad con su organización para garantizar la disponibilidad del servicio.<br><br>Los administradores y los usuarios tienen rutas para el soporte técnico respectivo si hay problemas de disponibilidad o servicio. | - [Supervisión y operaciones de Escritorio administrado de Microsoft](service-description/operations-and-monitoring.md)<br><br>- [Compatibilidad con administradores para Escritorio administrado de Microsoft](working-with-managed-desktop/admin-support.md)<br>- [Obtener ayuda para los usuarios](working-with-managed-desktop/end-user-support.md)  |



## <a name="service-transition"></a>Transición de servicio


|Proceso itil |Descripción  |Documentación |
|---------|---------|---------|
|Administración de cambios     | Equilibrio definido de responsabilidad, información general del proceso y tipos relacionados con la administración de cambios disponibles.  | [Supervisión y operaciones de Escritorio administrado de Microsoft](service-description/operations-and-monitoring.md#change-management) |
|Administración de lanzamiento e implementación     |  Microsoft Managed Desktop administra las actualizaciones de los dispositivos inscritos en el servicio.  | [Cómo se controlan las actualizaciones en Microsoft Managed Desktop](service-description/updates.md)        |
|Administración de activos de servicio y configuración     | La información sobre la implementación de Microsoft Managed Desktop de su organización está disponible en el portal de administración de TI.  | [Soporte técnico de administrador para Escritorio administrado de Microsoft](working-with-managed-desktop/admin-support.md) |
|Administración del conocimiento     | La información sobre el servicio de Escritorio administrado de Microsoft se mantiene actualizada en este sitio.   | [Historial de cambios de la documentación del Escritorio administrado de Microsoft](change-history-managed-desktop.md)        |



## <a name="service-operation"></a>Operación de servicio


|Proceso itil |Descripción  |Documentación  |
|---------|---------|---------|
|Administración de eventos     |  Se proporcionan detalles sobre la supervisión de dispositivos.<br><br>Se detallan los procedimientos operativos estándar para el servicio de Escritorio administrado de Microsoft. |  - [Seguridad en El escritorio administrado de Microsoft](service-description/security.md)<br>- [Supervisión y operaciones de Escritorio administrado de Microsoft](service-description/operations-and-monitoring.md)       |
|Administración de incidencias  | El Escritorio administrado de Microsoft investigará y actuará en caso de incidentes por definiciones de gravedad definidas.  |  [Definiciones de gravedad de solicitud de soporte técnico](working-with-managed-desktop/admin-support.md#support-request-severity-definitions)       |
|Administración de cumplimiento de solicitudes     |  Se definen los procesos de solicitudes de información y solicitudes de cambio relacionadas con el servicio de Escritorio administrado de Microsoft.         |[Soporte técnico de administrador para Escritorio administrado de Microsoft](working-with-managed-desktop/admin-support.md)         |
|Administración de problemas     | Cualquier problema con el servicio debe dirigirse a su equipo de cuenta local en este momento. | Documentación en desarrollo |
|Administración de acceso     | Acceso a los componentes de administración y responsabilidades del cliente para garantizar que la funcionalidad se detalla.  | [Administración de identidad y acceso](service-description/security.md#identity-and-access-management)        |
