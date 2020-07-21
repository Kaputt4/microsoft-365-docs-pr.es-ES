---
title: Novedades de la puntuación segura de Microsoft
description: Describe los cambios que han sucedido a la puntuación segura de Microsoft en el centro de seguridad de Microsoft 365.
keywords: seguridad, malware, Microsoft 365, M365, calificación segura, centro de seguridad, acciones de mejora
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 4f9f4f40b9cd88cad1676417d467d04367eaa0be
ms.sourcegitcommit: a08103bc120bdec7cfeaf67c1be4e221241e69ad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2020
ms.locfileid: "45200171"
---
# <a name="whats-new-in-microsoft-secure-score"></a>Novedades de la puntuación segura de Microsoft

Para convertir la puntuación segura de Microsoft en un mejor representante de su postura de seguridad, hemos realizado algunos cambios. Para obtener información sobre los cambios planeados, consulte [¿qué viene con la puntuación segura de Microsoft?](microsoft-secure-score-whats-coming.md).

## <a name="june-2020"></a>Junio de 2020

### <a name="removed-improvement-action-for-microsoft-defender-advanced-threat-protection"></a>Se quitó la acción de mejora para la protección contra amenazas avanzada de Microsoft defender

* Activar las reglas de reducción de la superficie de ataque

### <a name="added-improvement-actions-for-microsoft-defender-advanced-threat-protection"></a>Acciones de mejora agregadas para la protección contra amenazas avanzada de Microsoft defender

* Impedir que Adobe Reader cree procesos secundarios
* Usar protección avanzada contra ransomware
* Bloquear todas las aplicaciones de Office para crear procesos secundarios
* Impedir que las aplicaciones de Office creen contenido ejecutable
* Impedir que JavaScript o VBScript inicien contenido ejecutable descargado
* Bloquear la ejecución de scripts potencialmente ofuscados
* Bloquear contenido ejecutable del cliente de correo electrónico y Webmail
* Impedir que la aplicación de comunicación de Office cree procesos secundarios
* Bloquear procesos no habilitados y no firmados que se ejecutan desde USB
* Bloquear la persistencia a través de la suscripción de eventos WMI
* Impedir que las aplicaciones de Office inserten código en otros procesos
* Bloquear la ejecución de los archivos ejecutables a menos que cumplan un criterio de predominio, edad o lista de confianza
* Bloquear creaciones de procesos procedentes de PSExec y comandos WMI
* Bloquear credenciales de robo desde el subsistema de la autoridad de seguridad local de Windows (lsass.exe)
* Bloquear llamadas a la API Win32 desde macros de Office

## <a name="incompatibility-with-identity-secure-score-and-graph-api"></a>Incompatibilidad con la puntuación segura de la identidad y la API de Graph

En la versión más reciente de la puntuación segura de Microsoft, se ha lanzado un modelo de resultados mejorado. Estos cambios permiten una vista más flexible y precisa de la postura de seguridad. Sin embargo, estas actualizaciones han hecho que la puntuación segura de Microsoft sea incompatible temporalmente con la puntuación segura de identidad y la API de Graph.

En el tiempo, la calificación de identidad segura y la API de Graph adoptarán el nuevo modelo de calificación. Hasta entonces, los clientes verán las diferencias en los resultados indicados por la puntuación segura de Microsoft, la puntuación segura de identidad y la API de Graph. Lamentamos las molestias y los motivos para garantizar que estas experiencias sean más compatibles en el futuro.

## <a name="updated-improvement-actions"></a>Acciones de mejora actualizadas

- Se agregaron acciones de mejora de Azure Active Directory
- Se agregaron acciones de mejora de protección contra amenazas avanzada de Azure
- Compatibilidad con las recomendaciones de seguridad de la [vulnerabilidad ATP & vulnerabilidad](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) de Microsoft defender
    - Todas las recomendaciones de seguridad emitidas suministradas por TVM ya están disponibles

## <a name="updated-interface-and-functionality"></a>Interfaz y funciones actualizadas

* Todas las nuevas métricas y vistas de tendencias para CISO y discusiones de nivel de liderazgo
* Nuevas formas de realizar un seguimiento y evaluar su puntuación
* Mejor seguimiento y comprensión de las regresiones de puntuación
* Filtrar, etiquetar, buscar y agrupar las acciones de mejora
* Administrar hacia sus metas futuras mediante proyecciones de puntuación y acciones planeadas
* Y mucho más.

## <a name="we-want-to-hear-from-you"></a>Queremos conocer su opinión

Si tiene algún problema, háganoslo saber mediante la publicación de la comunidad de [seguridad, privacidad & cumplimiento](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) . Estamos supervisando la comunidad y le proporcionaremos ayuda.

## <a name="related-resources"></a>Recursos relacionados

- [Evaluación de la postura de seguridad](microsoft-secure-score-improvement-actions.md)
- [Realizar un seguimiento del historial de puntuación segura de Microsoft y cumplir los objetivos](microsoft-secure-score-history-metrics-trends.md)
- [Próximas novedades](microsoft-secure-score-whats-coming.md)
