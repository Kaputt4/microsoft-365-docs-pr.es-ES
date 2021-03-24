---
title: Puntuación de seguridad de Microsoft
description: Describe puntuación segura de Microsoft en el centro de seguridad de Microsoft 365, cómo mejorar la posición de seguridad y qué pueden esperar los administradores de seguridad.
keywords: puntuación segura de microsoft, puntuación segura, puntuación segura de office 365, puntuación de seguridad de Microsoft, centro de seguridad de Microsoft 365, acciones de mejora
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
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
ms.technology: m365d
ms.openlocfilehash: 98f335a38b2e4f581d4b08def39353e53e1bafd4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072648"
---
# <a name="microsoft-secure-score"></a>Puntuación de seguridad de Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

La Puntuación de seguridad de Microsoft es una medida de la actitud de seguridad de una organización, donde un número más alto indica que se han tomado más acciones de mejora. Se puede encontrar en el Centro de https://security.microsoft.com/securescore [seguridad de Microsoft 365](overview-security-center.md).

Seguir las recomendaciones de la puntuación de seguridad puede proteger a su organización de amenazas. Desde un panel centralizado en el centro de seguridad de Microsoft 365, las organizaciones pueden supervisar y trabajar en la seguridad de sus identidades, aplicaciones y dispositivos de Microsoft 365.

La puntuación de seguridad ayuda a las organizaciones a:  

* Informar sobre el estado actual de la situación en materia de seguridad de la organización.
* Mejorar la situación de seguridad proporcionando capacidad de descubrimiento, visibilidad, orientación y control.  
* Comparar con puntos de referencia y establecer indicadores clave de rendimiento (KPI).

Las organizaciones obtienen acceso a visualizaciones sólidas de métricas y tendencias, integración con otros productos de Microsoft, comparación de puntuaciones con organizaciones similares y mucho más. La puntuación también puede reflejar cuándo las soluciones de terceros han abordado las acciones recomendadas.

![Página principal de puntuación segura](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a>Cómo funciona

Se le dan puntos para las siguientes acciones:

- Configuración de características de seguridad recomendadas
- Realizar tareas relacionadas con la seguridad
- Abordar la acción de mejora con una aplicación o software de terceros, o una mitigación alternativa

Algunas acciones de mejora solo dan puntos cuando se completan por completo. Algunos dan puntos parciales si se completan para algunos dispositivos o usuarios. Si no puede o no desea aplicar una de las acciones de mejora, puede optar por aceptar el riesgo o el riesgo restante.

Si tiene una licencia para uno de los productos de Microsoft compatibles, verá recomendaciones para esos productos. Le mostramos el conjunto completo de mejoras posibles para un producto, independientemente de la edición de licencia, la suscripción o el plan. De esta forma, puede comprender los procedimientos recomendados de seguridad y mejorar su puntuación. Su posición de seguridad absoluta, representada por Puntuación segura, permanece igual independientemente de las licencias que su organización posee para un producto específico. Tenga en cuenta que la seguridad debe estar equilibrada con la facilidad de uso, y no todas las recomendaciones funcionarán en su entorno.

La puntuación se actualiza en tiempo real para reflejar la información presentada en las páginas de acción de visualización y mejora. Puntuación segura también se sincroniza diariamente para recibir datos del sistema sobre los puntos alcanzados para cada acción.

### <a name="key-scenarios"></a>Escenarios clave

- [Comprobar la puntuación actual](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [Comparar la puntuación con organizaciones como la tuyo](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [Ver acciones de mejora y decidir un plan de acción](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [Iniciar flujos de trabajo para investigar o implementar](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)

### <a name="how-improvement-actions-are-scored"></a>Cómo se puntuan las acciones de mejora

Cada acción de mejora tiene un valor de 10 puntos o menos, y la mayoría se puntuan de forma binaria. Si implementas la acción de mejora, como crear una nueva directiva o activar una configuración específica, obtienes el 100 % de los puntos. Para otras acciones de mejora, los puntos se dan como un porcentaje de la configuración total.

Por ejemplo, una acción de mejora indica que obtienes 10 puntos protegiendo a todos los usuarios con autenticación multifactor. Solo tiene 50 de 100 usuarios totales protegidos, por lo que obtiene una puntuación parcial de 5 puntos (50 protegido / 100 total * 10 pts máximo = 5 pts).

### <a name="products-included-in-secure-score"></a>Productos incluidos en Puntuación segura

Actualmente hay recomendaciones para los siguientes productos:

- Microsoft 365 (incluido Exchange Online)
- Azure Active Directory
- Microsoft Defender para punto de conexión
- Microsoft Defender for Identity
- Cloud App Security
- Microsoft Teams

Próximamente se ofrece una serie de recomendaciones para otros productos de seguridad. Las recomendaciones no cubren todas las superficies de ataque asociadas con cada producto, pero son una buena línea base. También puede marcar las acciones de mejora según lo cubierto por una mitigación alternativa o de terceros.

### <a name="security-defaults"></a>Valores predeterminados de seguridad

Microsoft Secure Score ha actualizado las acciones de mejora para admitir los valores predeterminados de seguridad en [Azure Active Directory,](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)lo que facilita la protección de su organización con opciones de seguridad preconfiguradas para ataques comunes.

Si activas los valores predeterminados de seguridad, se te concederán puntos completos para las siguientes acciones de mejora:

- Asegurarse de que todos los usuarios pueden completar la autenticación multifactor para un acceso seguro (9 puntos)
- Requerir MFA para roles administrativos (10 puntos)
- Habilitar la directiva para bloquear la autenticación heredada (7 puntos)

>[!IMPORTANT]
>Los valores predeterminados de seguridad incluyen características de seguridad que proporcionan una seguridad similar a las acciones de mejora "Directiva de riesgo de inicio de sesión" y "Directiva de riesgo de usuario". En lugar de configurar estas directivas encima de los valores predeterminados de seguridad, se recomienda actualizar sus estados a "Resuelto mediante mitigación alternativa".

## <a name="required-permissions"></a>Permisos necesarios

Para tener permiso para obtener acceso a La puntuación segura de Microsoft, debe tener asignado uno de los siguientes roles en Azure Active Directory.

### <a name="read-and-write-roles"></a>Roles de lectura y escritura

Con el acceso de lectura y escritura, puede realizar cambios e interactuar directamente con puntuación segura. También puede asignar acceso de solo lectura a otros usuarios.

* Administrador global
* Administrador de seguridad
* Administrador de Exchange
* Administrador de SharePoint
* Administrador de cuentas

### <a name="read-only-roles"></a>Roles de solo lectura

Con el acceso de solo lectura, no puedes editar el estado ni las notas de una acción de mejora, editar zonas de puntuación o editar comparaciones personalizadas.

* Administrador del departamento de soporto técnico
* Administrador de usuarios
* Administrador de servicios
* Lector de seguridad
* Operador de seguridad
* Lector global

## <a name="risk-awareness"></a>Concienciación de riesgos

Puntuación segura de Microsoft es un resumen numérico de la posición de seguridad basada en las configuraciones del sistema, el comportamiento del usuario y otras medidas relacionadas con la seguridad. No es una medida absoluta de la probabilidad de que el sistema o los datos se incumplen. En su lugar, representa el grado en que ha adoptado controles de seguridad en su entorno de Microsoft que pueden ayudar a compensar el riesgo de vulneración. Ningún servicio en línea es inmune a las infracciones de seguridad y la puntuación segura no debe interpretarse como una garantía contra la infracción de seguridad de ninguna manera.

## <a name="we-want-to-hear-from-you"></a>Queremos escuchar sus comentarios

Si tiene algún problema, háganoslo saber publicando en la comunidad [seguridad, privacidad & cumplimiento.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) Estamos supervisando la comunidad y proporcionaremos ayuda.

## <a name="related-resources"></a>Recursos relacionados

- [Evaluar su postura de seguridad](microsoft-secure-score-improvement-actions.md)
- [Realizar un seguimiento del historial de puntuación segura de Microsoft y cumplir objetivos](microsoft-secure-score-history-metrics-trends.md)
- [Próximas novedades](microsoft-secure-score-whats-coming.md)
- [Novedades](microsoft-secure-score-whats-new.md)