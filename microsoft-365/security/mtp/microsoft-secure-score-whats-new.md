---
title: Novedades de la puntuación segura de Microsoft
description: Describe los cambios que han sucedido a la puntuación segura de Microsoft en el centro de seguridad de Microsoft 365.
keywords: puntuación segura de Microsoft, calificación segura, puntuación segura de Office 365, puntuación de seguridad de Microsoft, centro de seguridad de Microsoft 365
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
ms.openlocfilehash: 253e85da7bb85a0722831851f00051a50a96153e
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688416"
---
# <a name="whats-new-in-microsoft-secure-score"></a>Novedades de la puntuación segura de Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Para convertir la puntuación segura de Microsoft en un mejor representante de su postura de seguridad, hemos realizado algunos cambios. Para obtener información sobre los cambios planeados, consulte [¿qué viene con la puntuación segura de Microsoft?](microsoft-secure-score-whats-coming.md)

Se puede encontrar la puntuación segura de Microsoft en https://security.microsoft.com/securescore el [centro de seguridad de Microsoft 365](overview-security-center.md).

## <a name="december-2020"></a>Diciembre de 2020

### <a name="added-6-accounts-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a>Se han agregado 6 acciones de mejora relacionadas con las cuentas para Microsoft defender para el extremo (ATP anterior de Microsoft defender):

- Establezca ' longitud mínima de contraseña ' en ' 14 o más caracteres '
- Establezca ' exigir historial de contraseñas ' en ' 24 contraseñas ' o más (s)
- Establezca "vigencia máxima de la contraseña" en "60 o menos días, pero no es 0"
- Establezca ' vigencia mínima de la contraseña ' en ' 1 o más días '
- Deshabilitar la cuenta integrada de administrador
- Deshabilitar la cuenta de invitado integrada

## <a name="november-2020"></a>Noviembre de 2020

### <a name="removed-the-ability-to-create-servicenow-tickets-through-secure-score"></a>Se ha quitado la capacidad de crear vales de ServiceNow a través de la puntuación segura 

La capacidad de crear vales de ServiceNow a través de la calificación segura yendo a **compartir > ServiceNow** ya no está disponible. Gracias por sus comentarios y el soporte técnico continuo mientras determinamos los siguientes pasos.

### <a name="added-3-services-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a>Se agregaron 3 acciones de mejora relacionadas con los servicios para Microsoft defender para el punto de conexión (ATP anterior de Microsoft defender):

- Corregir la ruta del servicio sin comillas para los servicios de Windows
- Cambiar la ruta de acceso del ejecutable del servicio a una ubicación común protegida
- Cambiar la cuenta de servicio para evitar la contraseña almacenada en caché en el registro de Windows

## <a name="october-2020"></a>Octubre de 2020

### <a name="remove-improvement-action-related-to-microsoft-defender-for-endpoint"></a>Quitar la acción de mejora relacionada con Microsoft defender para el punto de conexión

- Establecer la comprobación de contenido Web de aplicación de la tienda Windows de Microsoft defender para advertir

## <a name="august-2020"></a>Agosto de 2020

### <a name="updated-improvement-action-for-azure-active-directory"></a>Se actualizó la acción de mejora para Azure Active Directory

- Habilitar la Directiva para bloquear la autenticación heredada

## <a name="incompatibility-with-identity-secure-score-and-graph-api"></a>Incompatibilidad con la puntuación segura de la identidad y la API de Graph

En la versión más reciente de la puntuación segura de Microsoft, se ha lanzado un modelo de resultados mejorado. Estos cambios permiten una vista más flexible y precisa de la postura de seguridad. Sin embargo, estas actualizaciones han hecho que la puntuación segura de Microsoft sea incompatible temporalmente con la puntuación segura de identidad y la API de Graph.

En el tiempo, la calificación de identidad segura y la API de Graph adoptarán el nuevo modelo de calificación. Hasta entonces, los clientes verán las diferencias en los resultados indicados por la puntuación segura de Microsoft, la puntuación segura de identidad y la API de Graph. Lamentamos las molestias y los motivos para garantizar que estas experiencias sean más compatibles en el futuro.

## <a name="updated-improvement-actions"></a>Acciones de mejora actualizadas

- Se agregaron acciones de mejora de Azure Active Directory
- Se agregaron las acciones de Microsoft defender para mejorar la identidad
- Soporte para la amenaza de Microsoft defender para la amenaza de extremo & recomendaciones de seguridad para la [Administración de vulnerabilidades](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
    - Todas las recomendaciones de seguridad emitidas suministradas por TVM ya están disponibles

## <a name="updated-interface-and-functionality"></a>Interfaz y funciones actualizadas

* Todas las nuevas métricas y vistas de tendencias para CISO y discusiones de nivel de liderazgo
* Nuevas formas de realizar un seguimiento y evaluar su puntuación
* Mejor seguimiento y comprensión de las regresiones de puntuación
* Filtrar, etiquetar, buscar y agrupar las acciones de mejora
* Administrar hacia sus metas futuras mediante proyecciones de puntuación y acciones planeadas
* Y mucho más.

## <a name="we-want-to-hear-from-you"></a>Queremos escuchar sus comentarios

Si tiene algún problema, háganoslo saber mediante la publicación de la comunidad de [seguridad, privacidad & cumplimiento](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) . Estamos supervisando la comunidad y le proporcionaremos ayuda.

## <a name="related-resources"></a>Recursos relacionados

- [Evaluar su postura de seguridad](microsoft-secure-score-improvement-actions.md)
- [Realizar un seguimiento del historial de puntuación segura de Microsoft y cumplir los objetivos](microsoft-secure-score-history-metrics-trends.md)
- [Próximas novedades](microsoft-secure-score-whats-coming.md)
