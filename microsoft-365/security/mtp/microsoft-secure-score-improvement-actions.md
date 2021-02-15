---
title: Evaluar la posición de seguridad a través de la puntuación de seguridad de Microsoft
description: Describe cómo tomar medidas para mejorar la puntuación de seguridad de Microsoft en el Centro de seguridad de Microsoft 365.
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
ms.openlocfilehash: 8cf416e773abc6cbe1fd891fcec9f02a5011c413
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930647"
---
# <a name="assess-your-security-posture-with-microsoft-secure-score"></a>Evaluar la posición de seguridad con la puntuación de seguridad de Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Puntuación de seguridad de Microsoft es una medida de la posición de seguridad de una organización, con un número mayor que indica más acciones de mejora tomadas. Puede encontrarse en el Centro de seguridad https://security.microsoft.com/securescore [de Microsoft 365.](overview-security-center.md)

Para ayudarle a obtener la información que necesita más rápidamente, las acciones de mejora de Microsoft se organizan en grupos:

* Identidad (cuentas de Azure Active Directory & roles)
* Dispositivo (Microsoft Defender para punto de conexión, conocido como Puntuación de [seguridad de Microsoft para dispositivos)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices)
* Aplicación (correo electrónico y aplicaciones en la nube, incluidos Office 365 y Microsoft Cloud App Security)

>[!NOTE]
>En la versión reciente de Puntuación de seguridad de Microsoft, se publicó un modelo de puntuación mejorado que hizo que la puntuación de seguridad de Microsoft fuera temporalmente incompatible con la puntuación de seguridad de identidad y la API de Graph. [Ver detalles](microsoft-secure-score-whats-new.md)

En la página de información general de puntuación de seguridad de Microsoft, vea cómo se dividen los puntos entre estos grupos y qué puntos están disponibles. También puede obtener una vista general de la puntuación total, la tendencia histórica de su puntuación segura con comparaciones de indicadores y acciones de mejora prioritarios que se pueden realizar para mejorar la puntuación.

![Página principal de puntuación segura](../../media/secure-score/secure-score-homepage-new.png)

## <a name="check-your-current-score"></a>Comprobar la puntuación actual

Para comprobar la puntuación actual, vaya a la página de información general de Puntuación de seguridad de Microsoft y busque el icono que indica **La puntuación segura.** La puntuación se mostrará como un porcentaje, junto con el número de puntos que has logrado del total de puntos posibles.

Además, si selecciona  el botón Incluir junto a la puntuación, puede elegir diferentes vistas de la puntuación. Estas distintas vistas de puntuación se mostrarán en el gráfico en el icono de puntuación y en el gráfico de desglose de puntos.

Las siguientes son puntuaciones que puede agregar a su vista de la puntuación general para darle una imagen más completa de la puntuación general:

- **Puntuación planeada:** mostrar la puntuación proyectada cuando se completan las acciones planeadas
- **Puntuación de licencia actual:** mostrar la puntuación que se puede lograr con la licencia actual de Microsoft
- **Puntuación alcanzable:** mostrar la puntuación que se puede lograr con las licencias de Microsoft y la aceptación del riesgo actual

Esta vista es el aspecto que tendrá si has incluido todas las vistas de puntuación posibles:

![La puntuación segura, incluida la puntuación planeada, la puntuación de licencia actual y la puntuación alcanzable](../../media/secure-score/your-secure-score.png)

## <a name="take-action-to-improve-your-score"></a>Tomar medidas para mejorar la puntuación

La **pestaña Acciones de** mejora enumera las recomendaciones de seguridad que abordan posibles superficies de ataque. También incluye su estado (para abordar, planear, aceptar el riesgo, resuelto a través de terceros, resuelto mediante mitigación alternativa y completado). Puede buscar, filtrar y agrupar todas las acciones de mejora.  

### <a name="ranking"></a>Clasificación

La clasificación se basa en el número de puntos que queda por lograr, la dificultad de implementación, el impacto del usuario y la complejidad. Las acciones de mejora con mayor clasificación tienen un gran número de puntos restantes con dificultad baja, impacto en el usuario y complejidad.

### <a name="view-improvement-action-details"></a>Ver los detalles de las acciones de mejora

Cuando seleccionas una acción de mejora específica, aparece un control desplegable de página completa.  

![Ejemplo de acción de mejora](../../media/secure-score/secure-score-improvement-action-details.png)

Para completar la acción, tienes algunas opciones:

- Selecciona **Administrar** para ir a la pantalla de configuración y realizar el cambio. A continuación, obtendrás los puntos que vale la acción, visibles en el control de salida. Los puntos suelen tardar unas 24 horas en actualizarse.

- Seleccione **Compartir** para copiar el vínculo directo a la acción de mejora. También puede elegir la plataforma para compartir el vínculo, como correo electrónico, Microsoft Teams, Microsoft Planner o ServiceNow. Si selecciona ServiceNow, podrá crear un vale de cambio que estará visible en ServiceNow y en la página principal del Centro de seguridad de Microsoft 365. Para obtener más información, vea el Centro [de seguridad de Microsoft 365 y la integración de ServiceNow](tickets-security-center.md).

Agregue **notas** para realizar un seguimiento del progreso o cualquier otra cosa sobre la que desee comentar. Si agrega sus propias **etiquetas a** la acción de mejora, puede filtrar por esas etiquetas.

### <a name="choose-an-improvement-action-status"></a>Elegir un estado de acción de mejora

Elija los estados y registre las notas específicas de la acción de mejora.

- **Para solucionarlo,** debe reconocer que la acción de mejora es necesaria y tiene previsto abordarla en algún momento en el futuro. Este estado también se aplica a las acciones que se detectan como parcialmente, pero que no se completan completamente.
- **Planeado:** hay planes concretos para completar la acción de mejora.
- **Riesgo aceptado:** la seguridad siempre debe estar equilibrada con la facilidad de uso y no todas las recomendaciones funcionarán para su entorno. Cuando ese sea el caso, puede elegir aceptar el riesgo o el riesgo restante, y no aplicar la acción de mejora. No se le dará ningún punto, pero la acción ya no estará visible en la lista de acciones de mejora. Puede ver esta acción en el historial o deshacerla en cualquier momento.
- **Resuelto a través de** terceros y resuelto mediante mitigación **alternativa:** la acción de mejora ya ha sido abordada por una aplicación o software de terceros, o una herramienta interna. Obtendrás los puntos que vale la acción, por lo que tu puntuación refleja mejor tu posición de seguridad general. Si una herramienta interna o de terceros ya no cubre el control, puede elegir otro estado. Tenga en cuenta que Microsoft no tendrá visibilidad sobre la integridad de la implementación si la acción de mejora está marcada como cualquiera de estos estados.

#### <a name="threat--vulnerability-management-improvement-actions"></a>Acciones de & de administración de vulnerabilidades de amenazas

Para las acciones de mejora en la categoría "Dispositivo", no puedes elegir estados. En su lugar, se le [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) dirigirá a la recomendación de seguridad de administración de amenazas y vulnerabilidades asociada en el Centro de seguridad de [Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use) para tomar medidas. La excepción que elija y la justificación que escriba será específica de ese portal. No estará presente en el portal de puntuación de seguridad de Microsoft.

#### <a name="completed-improvement-actions"></a>Acciones de mejora completadas

Las acciones de mejora tienen un estado "completado" una vez que se han logrado todos los puntos posibles para la acción de mejora. Las acciones de mejora completadas se confirman a través de los datos de Microsoft y no se puede cambiar el estado.

### <a name="assess-information-and-review-user-impact"></a>Evaluar la información y revisar el impacto del usuario

La sección denominada **De un vistazo** te mostrará la categoría, los ataques contra los que puede proteger y el producto.

**El impacto en** el usuario es lo que experimentarán  los usuarios si se aprueba la acción de mejora y los usuarios afectados son las personas que se verán afectadas.

### <a name="implement-the-improvement-action"></a>Implementar la acción de mejora

En **la sección** Implementación se muestran los requisitos previos, los pasos siguientes paso a paso para completar la acción de mejora, el estado de implementación actual de la acción de mejora y cualquier vínculo más información.

Entre los requisitos previos se incluyen las licencias necesarias o las acciones que deben completarse antes de abordar la acción de mejora. Asegúrese de que tiene suficientes puestos en la licencia para completar la acción de mejora y que dichas licencias se aplican a los usuarios necesarios.  

## <a name="we-want-to-hear-from-you"></a>Queremos escuchar sus comentarios

Si tiene algún problema, háganoslo saber publicando en la comunidad [seguridad, privacidad & cumplimiento.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) Estamos supervisando la comunidad y le proporcionaremos ayuda.

## <a name="related-resources"></a>Recursos relacionados

- [Información general sobre puntuación de seguridad de Microsoft](microsoft-secure-score.md)
- [Realizar un seguimiento del historial de puntuaciones de seguridad de Microsoft y cumplir los objetivos](microsoft-secure-score-history-metrics-trends.md)
- [Próximas novedades](microsoft-secure-score-whats-coming.md)
- [Novedades](microsoft-secure-score-whats-new.md)
