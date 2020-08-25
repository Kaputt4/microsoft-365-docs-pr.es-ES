---
title: Evaluar la postura de seguridad a través de la puntuación segura de Microsoft
description: Describe cómo realizar una acción para mejorar la puntuación segura de Microsoft en el centro de seguridad de Microsoft 365.
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
ms.openlocfilehash: ab75e7ddbf3ada01c3f1247e58d8dc9472ecae77
ms.sourcegitcommit: 787b198765565d54ee73972f664bdbd5023d666b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/24/2020
ms.locfileid: "46866980"
---
# <a name="assess-your-security-posture-with-microsoft-secure-score"></a>Evaluar la postura de seguridad con calificación segura de Microsoft

La calificación segura de Microsoft es una medida de la postura de seguridad de una organización, con un número más alto que indica que se han realizado más acciones de mejora. Puede encontrarse en https://security.microsoft.com/securescore el [centro de seguridad de Microsoft 365](overview-security-center.md).

Para ayudarle a la información que necesita con mayor rapidez, las acciones de mejora de Microsoft se organizan en grupos:

* Identity (cuentas de Azure Active Directory & roles)
* Datos (Microsoft Information Protection)
* Dispositivo (ATP de Microsoft defender, conocido como [puntuación de configuración](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configuration-score))
* Aplicación (aplicaciones de correo electrónico y nube, incluidos Office 365 y Microsoft Cloud App Security)
* Infraestructura (no hay acciones de mejora por ahora)

>[!NOTE]
>En la versión más reciente de la puntuación segura de Microsoft, se ha lanzado un modelo de resultados mejorado que ha hecho que la puntuación segura de Microsoft sea incompatible temporalmente con la puntuación segura de la identidad y la API de Graph. [Ver detalles](microsoft-secure-score-whats-new.md)

En la página información general sobre la calificación segura de Microsoft, vea cómo se dividen los puntos entre estos grupos y qué puntos están disponibles. También puede obtener una visión general de la puntuación total, la tendencia histórica de la puntuación segura con comparaciones de los bancos de pruebas y las acciones de mejora ordenadas por prioridad que se pueden realizar para mejorar su puntuación.

![Página principal de puntuación segura](../../media/secure-score/secure-score-homepage-new.png)

## <a name="check-your-current-score"></a>Comprobar el resultado actual

Para comprobar el resultado actual, vaya a la página información general sobre la calificación segura de Microsoft y busque el icono que indica **su puntuación segura**. La puntuación se mostrará como un porcentaje, junto con el número de puntos que ha obtenido de un total de puntos posibles.

Además, si selecciona el botón **incluir** junto a su puntuación, podrá elegir distintas vistas de la puntuación. Estas vistas de puntuación diferentes se mostrarán en el gráfico en el mosaico de puntuación y en el gráfico de desglose de puntos.

Los siguientes son los resultados que puede Agregar a su vista de la puntuación general para proporcionarle una imagen más completa de su puntuación general:

- **Puntuación planificada**: Mostrar calificación proyectada cuando se completen las acciones planeadas
- **Puntuación de la licencia actual**: Mostrar la puntuación que se puede lograr con su licencia actual de Microsoft
- **Puntuación viable**: Mostrar la puntuación que se puede lograr con las licencias de Microsoft y la aceptación de riesgos actual

Esta vista es el aspecto que tendrá si ha incluido todas las vistas de puntuación posibles:

![La puntuación segura, incluidos el resultado planificado, la puntuación de la licencia actual y la puntuación viable](../../media/secure-score/your-secure-score.png)

## <a name="take-action-to-improve-your-score"></a>Tomar medidas para mejorar su puntuación

La ficha **acciones de mejora** muestra las recomendaciones de seguridad que abordan las posibles superficies de ataque. También incluye su estado (para dirigir, planear, arriesgarse, resolverse a través de terceros, resolverse a través de una mitigación alternativa y completarse). Puede buscar, filtrar y agrupar todas las acciones de mejora.  

### <a name="ranking"></a>Porcentaje

La clasificación se basa en el número de puntos que quedan para lograr, la dificultad de implementación, el impacto del usuario y la complejidad. Las acciones de mejora con mayor jerarquía tienen un gran número de puntos que quedan con problemas, impacto en el usuario y complejidad.

### <a name="view-improvement-action-details"></a>Ver detalles de la acción de mejora

Al seleccionar una acción de mejora específica, aparece un elemento flotante de página completa.  

![Ejemplo de control flotante de acción de mejora ](../../media/secure-score/secure-score-improvement-action-details.png)
 *figura 2: ejemplo de control flotante de acción de mejora*

Para completar la acción, tiene algunas opciones:

* Seleccione **administrar** para ir a la pantalla de configuración y realizar el cambio. A continuación, obtendrá los puntos que merece la acción, visible en el vuelo hacia fuera. Generalmente, los puntos tardan unas 24 horas en actualizarse.

* Seleccione **compartir** para copiar el vínculo directo a la acción de mejora. También puede elegir la plataforma para compartir el vínculo, como correo electrónico, Microsoft Teams, Microsoft Planner o ServiceNow. La selección de ServiceNow le permitirá crear un vale de cambio que será visible en ServiceNow y en la Página principal del centro de seguridad de Microsoft 365. Para obtener más información, consulte [Microsoft 365 Security Center and ServiceNow Integration](tickets-security-center.md).

### <a name="choose-an-improvement-action-status"></a>Elegir un estado de acción de mejora

Elija los Estados y anote las notas específicas para la acción de mejora.

- **Para solucionarlo** , reconozca que la acción de mejora es necesaria y planee solucionarla en algún momento posterior. Este estado también se aplica a las acciones que se detectan como parcialmente, pero que no se completan completamente.
- **Planificado** : hay planes concretos en su ubicación para completar la acción de mejora.
- **Riesgo aceptado** : la seguridad debe estar siempre equilibrada con la facilidad de uso y no todas las recomendaciones funcionarán para su entorno. En ese caso, puede optar por aceptar el riesgo, o el riesgo restante, y no activar la acción de mejora. No recibirá puntos, pero la acción ya no estará visible en la lista de acciones de mejora. Puede ver esta acción en el historial o deshacerla en cualquier momento.
- **Resuelto a través de terceros** y **resuelto a través de mitigación alternativa** : la acción de mejora ya ha sido tratada por una aplicación o software de terceros o por una herramienta interna. Obtendrá los puntos que merece la acción, de modo que su puntuación refleje mejor su postura de seguridad general. Si un tercero o una herramienta interna ya no cubre el control, puede elegir otro Estado. Tenga en cuenta que Microsoft no tendrá visibilidad sobre la integridad de la implementación si la acción de mejora se marca como cualquiera de estos Estados.

#### <a name="threat--vulnerability-management-improvement-actions"></a>Acciones de mejora de la administración de amenazas & vulnerabilidad

Para las acciones de mejora en la categoría "dispositivo", no podrá elegir los Estados. En su lugar, se le dirigirá a la [recomendación de seguridad asociada & Vulnerability Management (TVM)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) en el [centro de seguridad de Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use) para tomar medidas. La excepción que elija y justifique que escriba será específica de ese portal. No estará presente en el portal de calificación segura de Microsoft.

#### <a name="completed-improvement-actions"></a>Acciones de mejora completadas

Las acciones de mejora tienen el estado "completado" una vez que se han logrado todos los puntos posibles para la acción de mejora. Las acciones de mejora completadas se confirman a través de datos de Microsoft y no podrá cambiar el estado.

### <a name="assess-information-and-review-user-impact"></a>Evaluar la información y revisar el impacto del usuario

La sección a la que se ha llamado **de un vistazo** le dirá la categoría, los ataques con los que puede protegerse y el producto.

El **impacto del usuario** muestra lo que los usuarios experimentarán si se le aplica la acción de mejora y **los usuarios afectados** muestran quién la experimentará.

### <a name="implement-the-improvement-action"></a>Implementar la acción de mejora

En la sección **implementación** se muestran los requisitos previos, paso a paso para completar la acción de mejora, el estado de implementación actual de la acción de mejora y cualquier otro vínculo más información.

Los requisitos previos incluyen las licencias que se deben obtener o las acciones que deben realizarse antes de que se solucione la acción de mejora. Asegúrese de que tiene suficientes plazas en la licencia para completar la acción de mejora y de que esas licencias se aplican a los usuarios necesarios.  

## <a name="we-want-to-hear-from-you"></a>Queremos conocer su opinión

Si tiene algún problema, háganoslo saber mediante la publicación de la comunidad de [seguridad, privacidad & cumplimiento](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) . Estamos supervisando la comunidad y le proporcionaremos ayuda.

## <a name="related-resources"></a>Recursos relacionados

- [Introducción a la puntuación segura de Microsoft](microsoft-secure-score.md)
- [Realizar un seguimiento del historial de puntuación segura de Microsoft y cumplir los objetivos](microsoft-secure-score-history-metrics-trends.md)
- [Próximas novedades](microsoft-secure-score-whats-coming.md)
- [Novedades](microsoft-secure-score-whats-new.md)