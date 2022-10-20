---
title: Puntuación de seguridad de Microsoft
description: Describe la Puntuación de seguridad de Microsoft en el portal de Microsoft 365 Defender, cómo mejorar la posición de seguridad y qué pueden esperar los administradores de seguridad.
keywords: puntuación de seguridad de microsoft, puntuación de seguridad, puntuación de seguridad de office 365, puntuación de seguridad de Microsoft, Microsoft 365 Defender portal, acciones de mejora
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- Adm_TOC
- tier2
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 84a7aee597a324b1c9d916a9befa25d3857f3c33
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68622428"
---
# <a name="microsoft-secure-score"></a>Puntuación de seguridad de Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

La Puntuación de seguridad de Microsoft es una medida de la actitud de seguridad de una organización, donde un número más alto indica que se han tomado más acciones de mejora. Se puede encontrar en https://security.microsoft.com/securescore el [portal de Microsoft 365 Defender](microsoft-365-defender-portal.md).

Seguir las recomendaciones de la puntuación de seguridad puede proteger a su organización de amenazas. Desde un panel centralizado en el portal de Microsoft 365 Defender, las organizaciones pueden supervisar y trabajar en la seguridad de sus identidades, aplicaciones y dispositivos de Microsoft 365.

La puntuación de seguridad ayuda a las organizaciones a:  

* Informar sobre el estado actual de la situación en materia de seguridad de la organización.
* Mejorar la situación de seguridad proporcionando capacidad de descubrimiento, visibilidad, orientación y control.  
* Comparar con puntos de referencia y establecer indicadores clave de rendimiento (KPI).

Vea este vídeo para obtener una introducción rápida a la puntuación segura.
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWUPrP]

Las organizaciones obtienen acceso a visualizaciones sólidas de métricas y tendencias, integración con otros productos de Microsoft, comparación de puntuaciones con organizaciones similares y mucho más. La puntuación también puede reflejar cuándo las soluciones de terceros han abordado las acciones recomendadas.

:::image type="content" source="../../media/secure-score/secure-score-home-page.png" alt-text="Página principal de Puntuación de seguridad de Microsoft en el portal de Microsoft 365 Defender" lightbox="../../media/secure-score/secure-score-home-page.png":::

## <a name="how-it-works"></a>Cómo funciona

Se le proporcionan puntos para las siguientes acciones:

- Configuración de características de seguridad recomendadas
- Realizar tareas relacionadas con la seguridad
- Abordar la acción de mejora con una aplicación o software de terceros, o una mitigación alternativa

Algunas acciones de mejora solo proporcionan puntos cuando se completan por completo. Algunos proporcionan puntos parciales si se completan para algunos dispositivos o usuarios. Si no puede o no quiere implementar una de las acciones de mejora, puede optar por aceptar el riesgo o el riesgo restante.

Si tiene una licencia para uno de los productos de Microsoft compatibles, verá recomendaciones para esos productos. Le mostramos el conjunto completo de posibles mejoras para un producto, independientemente de la edición de licencia, la suscripción o el plan. De este modo, puede comprender los procedimientos recomendados de seguridad y mejorar la puntuación. Su posición de seguridad absoluta, representada por puntuación segura, permanece igual independientemente de las licencias que posea su organización para un producto específico. Tenga en cuenta que la seguridad debe estar equilibrada con la facilidad de uso, y no todas las recomendaciones funcionarán en su entorno.

La puntuación se actualiza en tiempo real para reflejar la información presentada en las páginas de visualizaciones y acciones de mejora. Puntuación segura también se sincroniza diariamente para recibir datos del sistema sobre los puntos alcanzados para cada acción.

### <a name="key-scenarios"></a>Escenarios clave

- [Comprobación de la puntuación actual](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [Comparar la puntuación con organizaciones como la suya](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [Ver acciones de mejora y decidir un plan de acción](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [Iniciar flujos de trabajo para investigar o implementar](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)

### <a name="how-improvement-actions-are-scored"></a>Puntuación de las acciones de mejora

Cada acción de mejora vale 10 puntos o menos, y la mayoría se puntúa de forma binaria. Si implementa la acción de mejora, como crear una nueva directiva o activar una configuración específica, obtendrá el 100 % de los puntos. Para otras acciones de mejora, los puntos se proporcionan como un porcentaje de la configuración total.

Por ejemplo, una acción de mejora indica que obtiene 10 puntos al proteger a todos los usuarios con la autenticación multifactor. Solo tiene 50 de 100 usuarios totales protegidos, por lo que obtendría una puntuación parcial de 5 puntos (50 protegidos / 100 en total * 10 puntos máximos = 5 pts).

### <a name="products-included-in-secure-score"></a>Productos incluidos en la puntuación segura

Actualmente hay recomendaciones para los siguientes productos:

- Microsoft 365 (incluidos los Exchange Online)
- Azure Active Directory
- Microsoft Defender para punto de conexión
- Microsoft Defender for Identity
- Defender for Cloud Apps
- Microsoft Teams

Las recomendaciones para otros productos de seguridad llegarán próximamente. Las recomendaciones no cubren todas las superficies de ataque asociadas a cada producto, pero son una buena línea base. También puede marcar las acciones de mejora como cubiertas por un tercero o una mitigación alternativa.

### <a name="security-defaults"></a>Valores predeterminados de seguridad

Puntuación de seguridad de Microsoft ha actualizado las acciones de mejora para admitir [los valores predeterminados de seguridad en Azure Active Directory](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), lo que facilita la protección de su organización con la configuración de seguridad preconfigurada para ataques comunes.

Si activa los valores predeterminados de seguridad, se le concederán puntos completos para las siguientes acciones de mejora:

- Asegúrese de que todos los usuarios pueden completar la autenticación multifactor para un acceso seguro (9 puntos)
- Requerir MFA para roles administrativos (10 puntos)
- Habilitar la directiva para bloquear la autenticación heredada (7 puntos)

>[!IMPORTANT]
>Los valores predeterminados de seguridad incluyen características de seguridad que proporcionan una seguridad similar a las acciones de mejora "directiva de riesgo de inicio de sesión" y "directiva de riesgo de usuario". En lugar de configurar estas directivas por encima de los valores predeterminados de seguridad, se recomienda actualizar sus estados a "Resuelto mediante mitigación alternativa".

## <a name="required-permissions"></a>Permisos necesarios

Para tener permiso para acceder a La puntuación segura de Microsoft, debe tener asignado uno de los siguientes roles en Azure Active Directory.

### <a name="read-and-write-roles"></a>Roles de lectura y escritura

Con el acceso de lectura y escritura, puede realizar cambios e interactuar directamente con La puntuación segura. También puede asignar acceso de solo lectura a otros usuarios.

* Administrador global
* Administrador de seguridad
* Administrador de Exchange
* Administrador de SharePoint

### <a name="read-only-roles"></a>Roles de solo lectura

Con el acceso de solo lectura, no puede editar el estado ni las notas de una acción de mejora, editar zonas de puntuación ni editar comparaciones personalizadas.

* Administrador del departamento de soporto técnico
* Administrador de usuarios
* Administrador de soporte técnico del servicio
* Lector de seguridad
* Operador de seguridad
* Lector global

## <a name="risk-awareness"></a>Reconocimiento del riesgo

Puntuación de seguridad de Microsoft es un resumen numérico de la posición de seguridad en función de las configuraciones del sistema, el comportamiento del usuario y otras medidas relacionadas con la seguridad. No es una medida absoluta de la probabilidad de que se vulnere el sistema o los datos. En su lugar, representa la medida en que ha adoptado controles de seguridad en el entorno de Microsoft que pueden ayudar a compensar el riesgo de que se vulnere. Ningún servicio en línea es inmune a las infracciones de seguridad y la puntuación de seguridad no debe interpretarse como una garantía contra las infracciones de seguridad de ninguna manera.

## <a name="we-want-to-hear-from-you"></a>Queremos escuchar sus comentarios

Si tiene algún problema, háganoslo saber publicando en la comunidad [seguridad, privacidad & cumplimiento](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) . Estamos supervisando la comunidad y proporcionaremos ayuda.

## <a name="related-resources"></a>Recursos relacionados

- [Evaluar su posición de seguridad](microsoft-secure-score-improvement-actions.md)
- [Seguimiento del historial de puntuación segura de Microsoft y cumplimiento de objetivos](microsoft-secure-score-history-metrics-trends.md)
- [Próximas novedades](microsoft-secure-score-whats-coming.md)
- [Novedades](microsoft-secure-score-whats-new.md)
