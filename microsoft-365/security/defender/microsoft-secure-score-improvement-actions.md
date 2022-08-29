---
title: Evaluación de la posición de seguridad mediante puntuación segura de Microsoft
description: Describe cómo realizar acciones para mejorar la puntuación de seguridad de Microsoft en el portal de Microsoft 365 Defender.
keywords: puntuación de seguridad de microsoft, puntuación de seguridad, puntuación de seguridad de office 365, puntuación de seguridad de Microsoft, Microsoft 365 Defender portal, acciones de mejora
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: d09c64d7986a85bbc90469d7cd8cc20bdf0d367e
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "67328571"
---
# <a name="assess-your-security-posture-with-microsoft-secure-score"></a>Evaluación de la posición de seguridad con puntuación segura de Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

La Puntuación de seguridad de Microsoft es una medida de la actitud de seguridad de una organización, donde un número más alto indica que se han tomado más acciones de mejora. Se puede encontrar en https://security.microsoft.com/securescore el [portal de Microsoft 365 Defender](microsoft-365-defender.md).

Para ayudarle a encontrar la información que necesita más rápidamente, las acciones de mejora de Microsoft se organizan en grupos:

- Identidad (cuentas de Azure Active Directory & roles)
- Dispositivo (Microsoft Defender para punto de conexión, conocido como [Puntuación segura de Microsoft para dispositivos](/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices))
- Aplicaciones (aplicaciones de correo electrónico y aplicaciones en la nube, incluidos Office 365 y Microsoft Defender for Cloud Apps)

>[!NOTE]
>En la versión reciente de Puntuación segura de Microsoft, se ha publicado un modelo de puntuación mejorado que hacía que La puntuación segura de Microsoft fuera temporalmente incompatible con la Puntuación de seguridad de identidad y la Graph API. [Ver detalles](microsoft-secure-score-whats-new.md)

En la página de información general de puntuación segura de Microsoft, vea cómo se dividen los puntos entre estos grupos y qué puntos están disponibles. También puede obtener una vista completa de la puntuación total, la tendencia histórica de la puntuación segura con comparaciones de pruebas comparativas y las acciones de mejora priorizada que se pueden realizar para mejorar la puntuación.

:::image type="content" source="../../media/secure-score/secure-score-home-page.png" alt-text="Página principal de puntuación segura en el portal de Microsoft 365 Defender" lightbox="../../media/secure-score/secure-score-home-page.png":::

## <a name="check-your-current-score"></a>Comprobación de la puntuación actual

Para comprobar la puntuación actual, vaya a la página de información general de puntuación segura de Microsoft y busque el icono que indica **Su puntuación de seguridad**. La puntuación se mostrará como un porcentaje, junto con el número de puntos que ha logrado del total de puntos posibles.

Además, si selecciona el botón **Incluir** situado junto a la puntuación, puede elegir distintas vistas de la puntuación. Estas distintas vistas de puntuación se mostrarán en el gráfico en el icono de puntuación y en el gráfico de desglose de puntos.

A continuación se muestran las puntuaciones que puede agregar a la vista de la puntuación general para proporcionarle una imagen más completa de la puntuación general:

- **Puntuación planeada**: mostrar la puntuación proyectada cuando se completan las acciones planeadas
- **Puntuación de licencia actual**: mostrar la puntuación que se puede lograr con la licencia actual de Microsoft
- **Puntuación alcanzable**: mostrar la puntuación que se puede lograr con las licencias de Microsoft y la aceptación del riesgo actual

Esta vista es el aspecto que tendrá si ha incluido todas las vistas de puntuación posibles:

:::image type="content" source="../../media/secure-score/secure-score-achievable.png" alt-text="La puntuación de seguridad, incluida la puntuación planeada, la puntuación de licencia actual y la puntuación alcanzable en el portal de Microsoft 365 Defender" lightbox="../../media/secure-score/secure-score-achievable.png":::

## <a name="take-action-to-improve-your-score"></a>Realizar acciones para mejorar la puntuación

En la pestaña **Acciones de mejora** se enumeran las recomendaciones de seguridad que abordan posibles superficies expuestas a ataques. También incluye su estado (para abordar, planear, aceptar riesgos, resolverse a través de terceros, resolverse mediante mitigación alternativa y completarse). Puede buscar, filtrar y agrupar todas las acciones de mejora.  

### <a name="ranking"></a>Ranking

La clasificación se basa en el número de puntos que quedan por lograr, la dificultad de implementación, el impacto del usuario y la complejidad. Las acciones de mejora clasificadas más altas tienen un gran número de puntos restantes con poca dificultad, impacto en el usuario y complejidad.

### <a name="view-improvement-action-details"></a>Visualización de los detalles de la acción de mejora

Al seleccionar una acción de mejora específica, aparece un control flotante de página completa.  

:::image type="content" source="../../media/secure-score/secure-score-improvement-action-details.png" alt-text="Control flotante de una acción de mejora en el portal de Microsoft 365 Defender" lightbox="../../media/secure-score/secure-score-improvement-action-details.png":::

Para completar la acción, tiene algunas opciones:

- Seleccione **Administrar en Microsoft 365 Defender** para ir a la pantalla de configuración y realizar el cambio. A continuación, obtendrá los puntos que vale la pena, visibles en el control flotante. Por lo general, los puntos tardan aproximadamente 24 horas en actualizarse.

- Seleccione **Compartir** para copiar el vínculo directo a la acción de mejora. También puede elegir la plataforma para compartir el vínculo, como correo electrónico, Microsoft Teams o Microsoft Planner.

Agregue **Notas** para realizar un seguimiento del progreso o cualquier otra cosa sobre la que desee comentar. Si agrega sus **propias etiquetas** a la acción de mejora, puede filtrar por esas etiquetas.

### <a name="choose-an-improvement-action-status"></a>Elegir un estado de acción de mejora

Elija los estados y las notas de registro específicas de la acción de mejora.

- **Para solucionarlo** : reconoce que la acción de mejora es necesaria y planea abordarla en algún momento en el futuro. Este estado también se aplica a las acciones que se detectan como parcialmente, pero no completadas por completo.
- **Planeado** : hay planes concretos para completar la acción de mejora.
- **Riesgo aceptado** : la seguridad siempre debe equilibrarse con la facilidad de uso y no todas las recomendaciones funcionarán para su entorno. En ese caso, puede optar por aceptar el riesgo o el riesgo restante y no aplicar la acción de mejora. No se le proporcionará ningún punto, pero la acción ya no estará visible en la lista de acciones de mejora. Puede ver esta acción en el historial o deshacerla en cualquier momento.
- **Resuelto a través de terceros** y **resuelto mediante mitigación alternativa** : la acción de mejora ya la ha abordado una aplicación o software de terceros, o una herramienta interna. Obtendrá los puntos que vale la pena para que la puntuación refleje mejor su posición de seguridad general. Si una herramienta interna o de terceros ya no cubre el control, puede elegir otro estado. Tenga en cuenta que Microsoft no tendrá visibilidad sobre la integridad de la implementación si la acción de mejora está marcada como cualquiera de estos estados.

#### <a name="microsoft-defender-vulnerability-management-improvement-actions"></a>Administración de vulnerabilidades de Microsoft Defender acciones de mejora

Para las acciones de mejora en la categoría "Dispositivo", no puede elegir los estados. En su lugar, se le dirigirá a la [recomendación de seguridad de Administración de vulnerabilidades de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) asociada en el Microsoft 365 Defender para realizar acciones. La excepción que elija y la justificación que escriba serán específicas de ese portal. No estará presente en el portal puntuación segura de Microsoft.

#### <a name="completed-improvement-actions"></a>Acciones de mejora completadas

Las acciones de mejora tienen un estado "completado" una vez que se han alcanzado todos los puntos posibles para la acción de mejora. Las acciones de mejora completadas se confirman a través de los datos de Microsoft y no se puede cambiar el estado.

### <a name="assess-information-and-review-user-impact"></a>Evaluación de información y revisión del impacto del usuario

La sección denominada **De un vistazo** le indicará la categoría, los ataques contra los que puede proteger y el producto.

**El impacto del usuario** es lo que experimentarán los usuarios si se ha implementado la acción de mejora y los **usuarios afectados** son las personas que se verán afectadas.

### <a name="implement-the-improvement-action"></a>Implementación de la acción de mejora

En **la sección Implementación** se muestran los requisitos previos, los pasos siguientes paso a paso para completar la acción de mejora, el estado de implementación actual de la acción de mejora y cualquier vínculo de más información.

Entre los requisitos previos se incluyen las licencias necesarias o las acciones que se deben completar antes de que se aborde la acción de mejora. Asegúrese de que tiene suficientes puestos en su licencia para completar la acción de mejora y de que esas licencias se aplican a los usuarios necesarios.  

## <a name="we-want-to-hear-from-you"></a>Queremos escuchar sus comentarios

Si tiene algún problema, háganoslo saber publicando en la comunidad [seguridad, privacidad & cumplimiento](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) . Estamos supervisando la comunidad y proporcionaremos ayuda.

## <a name="related-resources"></a>Recursos relacionados

- [Introducción a la puntuación segura de Microsoft](microsoft-secure-score.md)
- [Seguimiento del historial de puntuación segura de Microsoft y cumplimiento de objetivos](microsoft-secure-score-history-metrics-trends.md)
- [Próximas novedades](microsoft-secure-score-whats-coming.md)
- [Novedades](microsoft-secure-score-whats-new.md)
