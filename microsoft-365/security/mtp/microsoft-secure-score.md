---
title: Puntuación de seguridad de Microsoft
description: Describe la puntuación de seguridad de Microsoft en el Centro de seguridad de Microsoft 365, cómo mejorar su posición de seguridad y lo que los administradores de seguridad pueden esperar.
keywords: puntuación de seguridad de microsoft, puntuación de seguridad, puntuación de seguridad de Office 365, puntuación de seguridad de Microsoft, centro de seguridad de Microsoft 365, acciones de mejora
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: a0f4307cc0ed42a8ed53cdeefdb0a7b32eb36d35
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930587"
---
# <a name="microsoft-secure-score"></a>Puntuación de seguridad de Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Puntuación de seguridad de Microsoft es una medida de la posición de seguridad de una organización, con un número mayor que indica más acciones de mejora tomadas. Puede encontrarse en el Centro de seguridad https://security.microsoft.com/securescore [de Microsoft 365.](overview-security-center.md)

Seguir las recomendaciones de puntuación segura puede proteger a su organización de las amenazas. Desde un panel centralizado en el Centro de seguridad de Microsoft 365, las organizaciones pueden supervisar y trabajar en la seguridad de sus identidades, aplicaciones y dispositivos de Microsoft 365.

Puntuación segura ayuda a las organizaciones:  

* Informe sobre el estado actual de la posición de seguridad de la organización.
* Mejorar su posición de seguridad proporcionando detectabilidad, visibilidad, orientación y control.  
* Comparar con indicadores y establecer indicadores clave de rendimiento (KPI).

Las organizaciones obtienen acceso a visualizaciones sólidas de métricas y tendencias, integración con otros productos de Microsoft, comparación de puntuaciones con organizaciones similares y mucho más. La puntuación también puede reflejar cuándo las soluciones de terceros han abordado las acciones recomendadas.

![Página principal de puntuación segura](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a>Cómo funciona

Se le han dado puntos para las siguientes acciones:

- Configuración de características de seguridad recomendadas
- Realizar tareas relacionadas con la seguridad
- Abordar la acción de mejora con una aplicación o software de terceros, o una mitigación alternativa

Algunas acciones de mejora solo dan puntos cuando se completan. Algunos dan puntos parciales si se completan para algunos dispositivos o usuarios. Si no puede o no desea aplicar una de las acciones de mejora, puede elegir aceptar el riesgo o el riesgo restante.

Si tiene una licencia para uno de los productos de Microsoft compatibles, verá recomendaciones para esos productos. Le mostramos el conjunto completo de posibles mejoras para un producto, independientemente de la edición de licencia, suscripción o plan. De esta forma, puede comprender los procedimientos recomendados de seguridad y mejorar su puntuación. Su posición de seguridad absoluta, representada por la puntuación de seguridad, permanece igual independientemente de las licencias que posee su organización para un producto específico. Tenga en cuenta que la seguridad debe estar equilibrada con la facilidad de uso y no todas las recomendaciones pueden funcionar para su entorno.

La puntuación se actualiza en tiempo real para reflejar la información presentada en las páginas de acciones de mejora y visualizaciones. Puntuación segura también se sincroniza diariamente para recibir datos del sistema sobre los puntos obtenidos para cada acción.

### <a name="key-scenarios"></a>Escenarios clave

- [Comprobar la puntuación actual](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [Comparar tu puntuación con organizaciones como la tuyo](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [Ver acciones de mejora y decidir un plan de acción](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [Iniciar flujos de trabajo para investigar o implementar](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)

### <a name="how-improvement-actions-are-scored"></a>Cómo se puntuan las acciones de mejora

Cada acción de mejora vale 10 puntos o menos y la mayoría se puntua de forma binaria. Si implementas la acción de mejora, como crear una nueva directiva o activar una configuración específica, obtienes el 100 % de los puntos. Para otras acciones de mejora, los puntos se dan como un porcentaje de la configuración total.

Por ejemplo, una acción de mejora indica que obtiene 10 puntos al proteger a todos los usuarios con la autenticación multifactor. Solo tienes 50 de 100 usuarios totales protegidos, por lo que obtenerías una puntuación parcial de 5 puntos (50 protegido / 100 total * 10 pts máximo = 5 ptos).

### <a name="products-included-in-secure-score"></a>Productos incluidos en puntuación de seguridad

Actualmente hay recomendaciones para los siguientes productos:

- Microsoft 365 (incluido Exchange Online)
- Azure Active Directory
- Microsoft Defender para punto de conexión
- Microsoft Defender for Identity
- Cloud App Security

Próximamente se ofrece una serie de recomendaciones para otros productos de seguridad. Las recomendaciones no cubren todas las superficies de ataque asociadas con cada producto, pero son una buena línea base. También puedes marcar las acciones de mejora como cubiertas por un tercero o mitigación alternativa.

### <a name="security-defaults"></a>Valores predeterminados de seguridad

La puntuación de seguridad de Microsoft ha actualizado las acciones de mejora para admitir los valores predeterminados de seguridad en [Azure Active Directory,](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)lo que facilita la protección de su organización con opciones de seguridad preconfiguradas para ataques comunes.

Si activas los valores predeterminados de seguridad, se te concederán puntos completos para las siguientes acciones de mejora:

- Asegurarse de que todos los usuarios pueden completar la autenticación multifactor para el acceso seguro (9 puntos)
- Requerir MFA para roles administrativos (10 puntos)
- Habilitar la directiva para bloquear la autenticación heredada (7 puntos)

>[!IMPORTANT]
>Los valores predeterminados de seguridad incluyen características de seguridad que proporcionan seguridad similar a las acciones de mejora de la "directiva de riesgo de inicio de sesión" y la "directiva de riesgo de usuario". En lugar de configurar estas directivas en función de los valores predeterminados de seguridad, se recomienda actualizar sus estados a "Resuelto mediante mitigación alternativa".

## <a name="required-permissions"></a>Permisos necesarios

Para tener permiso para obtener acceso a la puntuación de seguridad de Microsoft, debe tener asignado uno de los siguientes roles en Azure Active Directory.

### <a name="read-and-write-roles"></a>Leer y escribir roles

Con el acceso de lectura y escritura, puede realizar cambios e interactuar directamente con la puntuación de seguridad. También puede asignar acceso de solo lectura a otros usuarios.

* Administrador global
* Administrador de seguridad
* Administrador de Exchange
* Administrador de SharePoint
* Administrador de cuentas

### <a name="read-only-roles"></a>Roles de solo lectura

Con el acceso de solo lectura, no es posible editar el estado o las notas de una acción de mejora, editar zonas de puntuación ni editar comparaciones personalizadas.

* Administrador del departamento de soporto técnico
* Administrador de usuarios
* Administrador de servicios
* Lector de seguridad
* Operador de seguridad
* Lector global

## <a name="risk-awareness"></a>Reconocimiento de riesgos

Puntuación de seguridad de Microsoft es un resumen numérico de su posición de seguridad en función de las configuraciones del sistema, el comportamiento del usuario y otras medidas relacionadas con la seguridad. No es una medida absoluta de la probabilidad de que se infracción el sistema o los datos. En su lugar, representa el grado en que ha adoptado controles de seguridad en su entorno de Microsoft que pueden ayudar a compensar el riesgo de que se infracción. Ningún servicio en línea es insocuo frente a las infracciones de seguridad y la puntuación de seguridad no debe interpretarse como una garantía contra las infracciones de seguridad de ninguna manera.

## <a name="we-want-to-hear-from-you"></a>Queremos escuchar sus comentarios

Si tiene algún problema, háganoslo saber publicando en la comunidad [seguridad, privacidad & cumplimiento.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) Estamos supervisando la comunidad y proporcionaremos ayuda.

## <a name="related-resources"></a>Recursos relacionados

- [Evaluar su postura de seguridad](microsoft-secure-score-improvement-actions.md)
- [Realizar un seguimiento del historial de puntuaciones seguras de Microsoft y cumplir los objetivos](microsoft-secure-score-history-metrics-trends.md)
- [Próximas novedades](microsoft-secure-score-whats-coming.md)
- [Novedades](microsoft-secure-score-whats-new.md)
