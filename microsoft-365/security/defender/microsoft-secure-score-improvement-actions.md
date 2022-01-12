---
title: Evaluar la posición de seguridad a través de Puntuación segura de Microsoft
description: Describe cómo tomar medidas para mejorar la puntuación segura de Microsoft en el portal Microsoft 365 Defender web.
keywords: microsoft secure score, secure score, office 365 secure score, microsoft security score, Microsoft 365 Defender portal, improvement actions
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 6519cf97fb35bfb0eb7b325475d4ce350ec0c3bb
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/19/2021
ms.locfileid: "61936985"
---
# <a name="assess-your-security-posture-with-microsoft-secure-score"></a>Evaluar la posición de seguridad con Puntuación segura de Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

La Puntuación de seguridad de Microsoft es una medida de la actitud de seguridad de una organización, donde un número más alto indica que se han tomado más acciones de mejora. Se puede encontrar en https://security.microsoft.com/securescore el portal de Microsoft 365 Defender [.](microsoft-365-defender.md)

Para ayudarle a encontrar la información que necesita más rápidamente, las acciones de mejora de Microsoft se organizan en grupos:

- Identidad (Azure Active Directory cuentas & roles)
- Device (Microsoft Defender para endpoint, conocido como [Puntuación segura de Microsoft para dispositivos](/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices))
- Aplicaciones (correo electrónico y aplicaciones en la nube, incluidas Office 365 y Microsoft Defender para aplicaciones en la nube)

>[!NOTE]
>En la versión reciente de Puntuación segura de Microsoft, se ha publicado un modelo de puntuación mejorado que hizo que Puntuación segura de Microsoft sea temporalmente incompatible con la puntuación segura de identidad y la API Graph puntuación. [Ver detalles](microsoft-secure-score-whats-new.md)

En la página Introducción a la puntuación segura de Microsoft, vea cómo se dividen los puntos entre estos grupos y qué puntos están disponibles. También puedes obtener una vista general de la puntuación total, la tendencia histórica de tu puntuación segura con comparaciones comparativas comparativas y las acciones de mejora prioritarias que se pueden realizar para mejorar la puntuación.

![Página principal de puntuación segura.](../../media/secure-score/secure-score-home-page.png)

## <a name="check-your-current-score"></a>Comprobar la puntuación actual

Para comprobar la puntuación actual, vaya a la página de información general de puntuación segura de Microsoft y busque el icono que indica **La puntuación segura**. La puntuación se mostrará como un porcentaje, junto con el número de puntos que has logrado del total de puntos posibles.

Además, si selecciona el botón **Incluir** junto a la puntuación, puede elegir diferentes vistas de la puntuación. Estas diferentes vistas de puntuación se mostrarán en el gráfico en el icono de puntuación y en el gráfico de desglose de puntos.

Las siguientes son las puntuaciones que puedes agregar a tu vista de la puntuación general para ofrecerte una imagen más completa de la puntuación general:

- **Puntuación planeada:** mostrar la puntuación proyectada cuando se completan las acciones planeadas
- **Puntuación de licencia actual:** mostrar la puntuación que se puede lograr con la licencia de Microsoft actual
- **Puntuación alcanzable:** mostrar la puntuación que se puede lograr con las licencias de Microsoft y la aceptación del riesgo actual

Esta vista es la que tendrá si has incluido todas las vistas de puntuación posibles:

![Su puntuación segura, incluida la puntuación planeada, la puntuación de licencia actual y la puntuación alcanzable.](../../media/secure-score/secure-score-achievable.png)

## <a name="take-action-to-improve-your-score"></a>Tomar medidas para mejorar la puntuación

La **pestaña Acciones de** mejora enumera las recomendaciones de seguridad que abordan posibles superficies de ataque. También incluye su estado (para abordar, planear, aceptar riesgos, resolver a través de terceros, resolver mediante mitigación alternativa y completar). Puede buscar, filtrar y agrupar todas las acciones de mejora.  

### <a name="ranking"></a>Clasificación

La clasificación se basa en el número de puntos que queda por lograr, la dificultad de implementación, el impacto del usuario y la complejidad. Las acciones de mejora clasificadas más altas tienen un gran número de puntos restantes con dificultad baja, impacto del usuario y complejidad.

### <a name="view-improvement-action-details"></a>Ver detalles de la acción de mejora

Al seleccionar una acción de mejora específica, aparece un control desplegable de página completa.  

![Ejemplo de acción de mejora.](../../media/secure-score/secure-score-improvement-action-details.png)

Para completar la acción, tienes algunas opciones:

- Seleccione **Administrar** para ir a la pantalla de configuración y realizar el cambio. A continuación, obtendrás los puntos que vale la acción, visibles en el vuelo hacia fuera. Los puntos suelen tardar unas 24 horas en actualizarse.

- Seleccione **Compartir** para copiar el vínculo directo a la acción de mejora. También puede elegir la plataforma para compartir el vínculo, como correo electrónico, Microsoft Teams o Microsoft Planner.

Agrega **notas** para realizar un seguimiento del progreso o cualquier otra cosa en la que quieras comentar. Si agrega sus propias **etiquetas a** la acción de mejora, puede filtrar por dichas etiquetas.

### <a name="choose-an-improvement-action-status"></a>Elegir un estado de acción de mejora

Elija los estados y las notas de registro específicas de la acción de mejora.

- **To address:** you recognize that the improvement action is necessary and plan to address it at some point in the future. Este estado también se aplica a las acciones que se detectan como parcialmente, pero que no se completan completamente.
- **Planeado:** hay planes concretos para completar la acción de mejora.
- **Riesgo aceptado:** la seguridad siempre debe estar equilibrada con la facilidad de uso y no todas las recomendaciones funcionarán para su entorno. Cuando ese es el caso, puede optar por aceptar el riesgo, o el riesgo restante, y no aplicar la acción de mejora. No se le dará ningún punto, pero la acción ya no estará visible en la lista de acciones de mejora. Puede ver esta acción en el historial o deshacerla en cualquier momento.
- **Resuelto a través de** terceros y **Resuelto** mediante mitigación alternativa: la acción de mejora ya ha sido abordada por una aplicación o software de terceros, o una herramienta interna. Obtendrás los puntos que vale la acción, por lo que tu puntuación refleja mejor tu posición de seguridad general. Si una herramienta interna o de terceros ya no cubre el control, puede elegir otro estado. Tenga en cuenta que Microsoft no tendrá visibilidad sobre la integridad de la implementación si la acción de mejora se marca como uno de estos estados.

#### <a name="threat--vulnerability-management-improvement-actions"></a>Acciones de & administración de vulnerabilidades de amenazas

Para las acciones de mejora en la categoría "Dispositivo", no puedes elegir estados. En su lugar, se le dirigirá a la recomendación de Administración de amenazas y vulnerabilidades [de](/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) seguridad asociada [en el Centro de seguridad de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/use) para tomar medidas. La excepción que elija y la justificación que escriba será específica de ese portal. No estará presente en el portal de puntuación segura de Microsoft.

#### <a name="completed-improvement-actions"></a>Acciones de mejora completadas

Las acciones de mejora tienen un estado "completado" una vez que se han logrado todos los puntos posibles para la acción de mejora. Las acciones de mejora completadas se confirman a través de los datos de Microsoft y no se puede cambiar el estado.

### <a name="assess-information-and-review-user-impact"></a>Evaluar la información y revisar el impacto del usuario

La sección denominada **De un vistazo** te mostrará la categoría, los ataques contra los que puede proteger y el producto.

**El impacto** del usuario es lo que experimentarán los  usuarios si se aprueba la acción de mejora y los usuarios afectados son las personas que se verán afectadas.

### <a name="implement-the-improvement-action"></a>Implementar la acción de mejora

En **la sección** Implementación se muestran los requisitos previos, los pasos siguientes paso a paso para completar la acción de mejora, el estado actual de implementación de la acción de mejora y cualquier vínculo más información.

Entre los requisitos previos se incluyen las licencias necesarias o las acciones que se deben completar antes de abordar la acción de mejora. Asegúrese de que tiene suficientes puestos en la licencia para completar la acción de mejora y que dichas licencias se aplican a los usuarios necesarios.  

## <a name="we-want-to-hear-from-you"></a>Queremos escuchar sus comentarios

Si tiene algún problema, háganoslo saber publicando en la comunidad [seguridad, privacidad & cumplimiento.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) Estamos supervisando la comunidad y proporcionaremos ayuda.

## <a name="related-resources"></a>Recursos relacionados

- [Introducción a la puntuación segura de Microsoft](microsoft-secure-score.md)
- [Realizar un seguimiento del historial de puntuación segura de Microsoft y cumplir objetivos](microsoft-secure-score-history-metrics-trends.md)
- [Próximas novedades](microsoft-secure-score-whats-coming.md)
- [Novedades](microsoft-secure-score-whats-new.md)
