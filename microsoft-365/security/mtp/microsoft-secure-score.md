---
title: Puntuación de seguridad de Microsoft
description: Describe la puntuación segura de Microsoft en el centro de seguridad 365 de Microsoft, cómo mejorar su postura de seguridad y qué administradores de seguridad pueden esperar.
keywords: puntuación segura de Microsoft, calificación segura, puntuación segura de Office 365, puntuación de seguridad de Microsoft, centro de seguridad de Microsoft 365, acciones de mejora
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
ms.openlocfilehash: 7fe5be065ee45700a1f08a39c8050757c3843f7b
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682576"
---
# <a name="microsoft-secure-score"></a>Puntuación de seguridad de Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

La calificación segura de Microsoft es una medida de la postura de seguridad de una organización, con un número más alto que indica que se han realizado más acciones de mejora. Puede encontrarse en https://security.microsoft.com/securescore el [centro de seguridad de Microsoft 365](overview-security-center.md).

Seguir las recomendaciones de puntuación segura puede proteger a su organización de las amenazas. Desde un panel centralizado en el centro de seguridad de Microsoft 365, las organizaciones pueden supervisar y trabajar en la seguridad de sus identidades, aplicaciones y dispositivos de Microsoft 365.

La puntuación segura ayuda a las organizaciones a:  

* Informe sobre el estado actual de la postura de seguridad de la organización.
* Mejorar su postura de seguridad proporcionando detección, visibilidad, orientación y control.  
* Comparar con benchmarks y establecer indicadores clave de rendimiento (KPI).

Las organizaciones obtienen acceso a las sólidas visualizaciones de métricas y tendencias, la integración con otros productos de Microsoft, la puntuación con organizaciones similares y mucho más. La puntuación también puede reflejar Cuándo las soluciones de terceros han tratado las acciones recomendadas.

![Página principal de puntuación segura](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a>Cómo funciona

Se le proporcionan puntos para las siguientes acciones:

- Configuración de las características de seguridad recomendadas
- Realización de tareas relacionadas con la seguridad
- Solucionar la acción de mejora con una aplicación o software de terceros, o una mitigación alternativa

Algunas acciones de mejora solo proporcionan puntos cuando se completan completamente. Algunos proporcionan puntos parciales si están completos para algunos dispositivos o usuarios. Si no puede o no desea activar una de las acciones de mejora, puede optar por aceptar el riesgo o el riesgo restante.

Si tiene una licencia para uno de los productos de Microsoft admitidos, verá recomendaciones para esos productos. Le mostramos el conjunto completo de mejoras posibles para un producto, independientemente de la edición de licencia, la suscripción o el plan. De este modo, puede comprender los procedimientos recomendados de seguridad y mejorar su calificación. La postura absoluta de seguridad, representada por la puntuación segura, sigue siendo la misma independientemente de las licencias que posea su organización para un producto específico. Tenga en cuenta que la seguridad debe sopesarse con facilidad de uso y no todas las recomendaciones pueden funcionar en su entorno.

La puntuación se actualiza en tiempo real para reflejar la información que se presenta en las páginas de acciones de visualización y de mejora. La puntuación segura también se sincroniza diariamente para recibir datos del sistema sobre los puntos alcanzados para cada acción.

### <a name="key-scenarios"></a>Escenarios clave

- [Comprobar el resultado actual](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [Comparar su calificación con organizaciones como la suya](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [Ver acciones de mejora y decidir un plan de acción](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [Iniciar flujos de trabajo para investigar o implementar](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)
    - [Microsoft 365 Security Center and ServiceNow Integration](tickets-security-center.md)

### <a name="how-improvement-actions-are-scored"></a>Cómo se puntuan las acciones de mejora

Cada acción de mejora vale 10 puntos o menos, y la mayoría se puntúa de una manera binaria. Si implementa la acción de mejora, como crear una nueva Directiva o activar una configuración específica, obtendrá un 100% de los puntos. Para otras acciones de mejora, los puntos se dan como un porcentaje de la configuración total.

Por ejemplo, los Estados de acción de mejora obtienen 10 puntos al proteger a todos los usuarios con la autenticación multifactor. Solo tiene un 50 de 100 total de usuarios protegidos, por lo que obtendrá una puntuación parcial de 5 puntos (50 protegido/100 total * 10 máx PTS = 5 PTS).

### <a name="products-included-in-secure-score"></a>Productos incluidos en la puntuación segura

Actualmente hay recomendaciones para Microsoft 365 (incluido Exchange Online), Azure Active Directory, Microsoft defender para extremo, Microsoft defender para identidad y Cloud App Security. Pronto estarán disponibles recomendaciones para otros productos de seguridad. Las recomendaciones no cubren todas las superficies de ataque asociadas con cada producto, pero son una buena línea de base. También puede marcar las acciones de mejora como cubiertas por un tercero o una mitigación alternativa.

### <a name="security-defaults"></a>Valores predeterminados de seguridad

La calificación segura de Microsoft tiene acciones de mejora actualizadas para admitir los [valores predeterminados de seguridad en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), que facilitan la protección de la organización con una configuración de seguridad preconfigurada para ataques comunes.

Si activa los valores predeterminados de seguridad, se le otorgarán puntos completos para las siguientes acciones de mejora:

- Asegurarse de que todos los usuarios puedan completar la autenticación multifactor para el acceso seguro (9 puntos)
- Requerir MFA para roles administrativos (10 puntos)
- Habilitar la Directiva para bloquear la autenticación heredada (7 puntos)

>[!IMPORTANT]
>Los valores predeterminados de seguridad incluyen características de seguridad que proporcionan seguridad similar a las acciones de mejora "Directiva de riesgo de inicio de sesión" y "Directiva de riesgos de usuario". En lugar de configurar estas directivas sobre los valores predeterminados de seguridad, se recomienda actualizar sus Estados a "resuelto a través de una mitigación alternativa".

## <a name="required-permissions"></a>Permisos necesarios

Para tener permiso de acceso a la puntuación segura de Microsoft, debe tener asignado uno de los siguientes roles en Azure Active Directory.

### <a name="read-and-write-roles"></a>Lectura y escritura de roles

Con acceso de lectura y escritura, puede realizar cambios e interactuar directamente con la calificación segura. También puede asignar acceso de solo lectura a otros usuarios.

* Administrador global
* Administrador de seguridad
* Administrador de Exchange
* Administrador de SharePoint
* Administrador de la cuenta

### <a name="read-only-roles"></a>Solo lectura roles

Con acceso de solo lectura, no puede editar el estado o las notas para una acción de mejora, editar zonas de puntuación o editar comparaciones personalizadas.

* Administrador del departamento de soporto técnico
* Administrador de usuarios
* Administrador de servicios
* Lector de seguridad
* Operador de seguridad
* Lector global

## <a name="risk-awareness"></a>Conocimiento de riesgos

La puntuación segura de Microsoft es un resumen numérico de la postura de seguridad en función de la configuración del sistema, el comportamiento del usuario y otras medidas relacionadas con la seguridad. No es una medida absoluta de la probabilidad de que se infrinja el sistema o sus datos. En su lugar, representa en qué medida ha adoptado controles de seguridad en su entorno de Microsoft que pueden ayudar a compensar el riesgo de infracción. Ningún servicio en línea está completamente inmune a las infracciones de seguridad y la puntuación segura no se debe interpretar como una garantía contra la infracción de seguridad de ninguna manera.

## <a name="we-want-to-hear-from-you"></a>Queremos escuchar sus comentarios

Si tiene algún problema, háganoslo saber mediante la publicación de la comunidad de [seguridad, privacidad & cumplimiento](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) . Estamos supervisando la comunidad y le proporcionaremos ayuda.

## <a name="related-resources"></a>Recursos relacionados

- [Evaluar su postura de seguridad](microsoft-secure-score-improvement-actions.md)
- [Realizar un seguimiento del historial de puntuación segura de Microsoft y cumplir los objetivos](microsoft-secure-score-history-metrics-trends.md)
- [Próximas novedades](microsoft-secure-score-whats-coming.md)
- [Novedades](microsoft-secure-score-whats-new.md)
