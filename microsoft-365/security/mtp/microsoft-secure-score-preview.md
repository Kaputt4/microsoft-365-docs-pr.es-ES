---
title: Puntuación segura de Microsoft (versión preliminar)
description: Describe la puntuación segura de Microsoft en el centro de seguridad 365 de Microsoft, cómo se calculan los detalles y qué administradores de seguridad pueden esperar si lo usan.
keywords: seguridad, malware, Microsoft 365, M365, calificación segura, centro de seguridad, acciones de mejora
ms.prod: w10
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
ms.openlocfilehash: 8319dcabe6032228e2124b68f9f7d8f237ff34de
ms.sourcegitcommit: d818828c66cf98b0b0037ba8b3cb790c940281b7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43583374"
---
# <a name="microsoft-secure-score-preview"></a>Puntuación segura de Microsoft (versión preliminar)

>[!IMPORTANT]
>Parte de la información se refiere a un producto prelanzamiento que puede modificarse de forma sustancial antes de su lanzamiento comercial. Microsoft makes no warranties, express or implied, with respect to the information provided here.

La calificación segura de Microsoft es una medida de la postura de seguridad de una organización, con un número más alto que indica que se han realizado más acciones de mejora. Seguir las recomendaciones de puntuación de seguridad puede proteger a su organización de las amenazas. Desde un panel centralizado en el centro de seguridad de Microsoft 365, las organizaciones pueden supervisar y trabajar en la seguridad de las identidades, los datos, las aplicaciones, los dispositivos y la infraestructura de Microsoft 365.

La puntuación segura ayuda a las organizaciones a:  

* Informe sobre el estado actual de la postura de seguridad de la organización.
* Mejorar su postura de seguridad proporcionando detección, visibilidad, orientación y control.  
* Comparar con benchmarks y establecer indicadores clave de rendimiento (KPI).

Las organizaciones obtienen acceso a las sólidas visualizaciones de métricas y tendencias, la integración con otros productos de Microsoft, la puntuación con organizaciones similares y mucho más. La puntuación también puede reflejar Cuándo las soluciones de terceros han tratado las acciones recomendadas.

Además, puede obtener acceso a sus recomendaciones y puntuaciones a través de la [API de Microsoft Graph](https://www.microsoft.com/security/partnerships/graph-security-api). Obtenga información sobre el [tipo de recurso de puntuación segura](https://go.microsoft.com/fwlink/?linkid=2092996).

## <a name="how-it-works"></a>Funcionamiento

Se le proporcionan puntos para configurar las características de seguridad recomendadas, realizar tareas relacionadas con la seguridad o resolver la acción de mejora con una aplicación o software de terceros. Algunas acciones de mejora solo proporcionan puntos cuando se completan completamente y otras proporcionan puntos parciales si se completan para algunos dispositivos o usuarios. Si no puede o no desea activar una de las acciones de mejora, puede optar por aceptar el riesgo o el riesgo restante.

Le mostramos el conjunto completo de posibles mejoras, independientemente de la licencia, para que pueda comprender los procedimientos recomendados de seguridad y mejorar su puntuación. La postura absoluta de seguridad se representa mediante calificación segura, que permanece igual independientemente de las licencias de producto que posea la organización. Tenga en cuenta que la seguridad debe sopesarse con facilidad de uso y no todas las recomendaciones pueden funcionar en su entorno.

La puntuación se actualiza en tiempo real para reflejar la información que se presenta en las páginas de acciones de visualización y de mejora. La puntuación segura también se sincroniza diariamente para recibir datos del sistema sobre los puntos alcanzados para cada acción.

### <a name="how-improvement-actions-are-scored"></a>Cómo se puntuan las acciones de mejora

Cada acción de mejora merece 10 puntos o menos. La mayoría se puntuan de una manera binaria: Si implementa la acción de mejora, como crear una nueva Directiva o activar una configuración específica, obtendrá un 100% de los puntos. Para otras acciones de mejora, los puntos se dan como un porcentaje de la configuración total. Por ejemplo, si los Estados de acción de mejora obtienen 30 puntos al proteger a todos los usuarios con la autenticación multifactor y solo tiene 5 de 100 usuarios totales protegidos, se le asignará una puntuación parcial de unos 2 puntos (5 protegidos/100 en total * 30 máx PTS = puntuación parcial de 2 PTO).

### <a name="products-included-in-secure-score"></a>Productos incluidos en la puntuación segura

Actualmente hay recomendaciones para Office 365 (como SharePoint Online, Exchange Online, OneDrive para la empresa, Microsoft Information Protection, etc.), Azure AD, ATP de Microsoft defender y Cloud App Security. Pronto estarán disponibles recomendaciones para otros productos de seguridad. Las recomendaciones no cubren todas las superficies de ataque asociadas con cada producto, pero son una buena línea de base. También puede marcar las acciones de mejora como cubiertas por un tercero.

## <a name="required-permissions"></a>Permisos necesarios

Para tener permiso de acceso a la puntuación segura de Microsoft, debe tener asignado uno de los siguientes roles en Azure Active Directory.

### <a name="read-and-write-roles"></a>Lectura y escritura de roles

Con acceso de lectura y escritura, puede realizar cambios e interactuar directamente con la calificación segura. También puede asignar acceso de solo lectura a otros usuarios.

* Administrador global
* Administrador de seguridad
* Administrador de Exchange
* Administrador de SharePoint

### <a name="read-only-roles"></a>Solo lectura roles

Con acceso de solo lectura, no es posible editar el estado ni las notas para una acción de mejora, editar zonas de puntuación ni editar comparaciones personalizadas.

* Administrador del servicio de asistencia
* Administrador de usuarios
* Administrador de servicios
* Lector de seguridad
* Operador de seguridad
* Lector global

### <a name="graph-api"></a>API de Graph

Para obtener acceso a la API de Graph, debe tener uno de los siguientes ámbitos además de un rol:

* Ámbito securityevents. Read. All (para roles de solo lectura)
* Ámbito securityevents. ReadWrite. All (para roles de lectura y escritura)

## <a name="gain-visibility-into-your-security-posture"></a>Obtener visibilidad de la postura de seguridad

Para ayudarle a la información que necesita con mayor rapidez, las acciones de mejora de Microsoft se organizan en grupos:

* Identity (cuentas de Azure AD & roles)
* Datos (Microsoft Information Protection)
* Dispositivo (no hay acciones de mejora por ahora)
* Aplicación (aplicaciones de correo electrónico y nube, incluidos Office 365 y Microsoft Cloud App Security)
* Infraestructura (no hay acciones de mejora por ahora)

En la página información general sobre la calificación segura de Microsoft, puede ver cómo se dividen los puntos entre estos grupos y qué puntos están disponibles. La página de información general también es la ubicación para obtener una vista completa de la puntuación total, la tendencia histórica de la puntuación segura con comparaciones de los bancos de pruebas y las acciones de mejora ordenadas por prioridad que se pueden realizar para mejorar la puntuación.

![Página Web de](../../media/secure-score/secure-score-homepage.png)
puntuación segura*figura 1: Página de introducción a la calificación segura de Microsoft*

## <a name="take-action-to-improve-your-score"></a>Tomar medidas para mejorar su puntuación

La ficha acciones de mejora muestra las recomendaciones de seguridad que abordan las posibles superficies de ataque, junto con su estado (completado, planeado, riesgo aceptado, tercero y dirección de la empresa). Puede buscar, filtrar y agrupar todas las acciones de mejora.  

### <a name="ranking"></a>Porcentaje

La clasificación se basa en el número de puntos restantes que quedan para lograr, la dificultad de implementación, el impacto del usuario y la complejidad. Las acciones de mejora con mayor jerarquía tienen un gran número de puntos que quedan con problemas, impacto en el usuario y complejidad.

### <a name="actions"></a>Acciones

Al seleccionar una acción de mejora específica, aparece un elemento flotante de página completa.  

![Ejemplo](../../media/secure-score/secure-score-improvement-action.png)
de control flotante de acción de mejora*figura 2: ejemplo de control flotante de acción de mejora*

Para completar la acción, tiene algunas opciones:

* Seleccione **administrar** para ir a la pantalla de configuración y realizar el cambio. A continuación, obtendrá los puntos que merece la acción, visible en el vuelo hacia fuera. Generalmente, los puntos tardan unas 24 horas en actualizarse.

* Seleccione **compartir** para copiar el vínculo directo a la acción de mejora o elija la plataforma para compartir el vínculo, por ejemplo, correo electrónico, Microsoft Teams, Microsoft Planner o ServiceNow. La selección de ServiceNow le permitirá crear un vale de cambio que será visible en ServiceNow y en la Página principal del centro de seguridad de Microsoft 365. Para obtener más información, consulte [Microsoft 365 Security Center and ServiceNow Integration](tickets.md).

* Seleccione **Editar estado y notas** para editar los Estados manuales o registrar las notas específicas para la acción de mejora. Puede filtrar o agrupar por los Estados en la pestaña acciones de mejora. Los statues que puede seleccionar son los siguientes

    * **Para solucionarlo** , debe reconocer que la acción de mejora es necesaria y planificar para solucionarla en algún momento posterior. Este estado también se aplica a las acciones que se detectan como parcialmente, pero que no se completan completamente.
    * **Planificado** : hay planes concretos en su ubicación para completar la acción de mejora.
    * **Riesgo aceptado** : la seguridad siempre debe sopesarse con la facilidad de uso y no todas las recomendaciones funcionarán para su entorno. En ese caso, puede optar por aceptar el riesgo, o el riesgo restante, y no activar la acción de mejora. No se le proporcionarán puntos, pero la acción ya no será visible en la lista de acciones de mejora. Puede ver esta acción en el historial o deshacerla en cualquier momento.
    * **Resolver a través de terceros** : la acción de mejora ya ha sido tratada por un software o una aplicación de terceros. Obtendrá los puntos que merece la acción, de modo que su puntuación refleje mejor su postura de seguridad general. Si un tercero ya no cubre el control, puede elegir otro Estado. Tenga en cuenta que Microsoft no tendrá visibilidad sobre la integridad de la implementación si la acción de mejora se ha marcado como resuelta a través de terceros

### <a name="prerequisites"></a>Requisitos previos

Requisitos previos en la sección implementación, enumerará las licencias que se deben obtener o las acciones que deben realizarse antes de que se solucione la acción de mejora. Asegúrese de que tiene suficientes plazas en la licencia para completar la acción de mejora y de que esas licencias se aplican a los usuarios necesarios.  

## <a name="track-your-score-history-and-meet-goals"></a>Realizar un seguimiento del historial de puntuación y cumplir los objetivos

Puede ver un gráfico de la puntuación de su organización con el tiempo en la ficha **historial** . debajo del gráfico hay una lista de todas las acciones realizadas en el intervalo de tiempo seleccionado y sus atributos, como puntos y categoría resultantes. Puede personalizar un intervalo de fechas y filtrar por categoría.

En la ficha **métricas & tendencias** , hay varios gráficos y gráficos para proporcionar más visibilidad sobre las tendencias y establecer los objetivos. Puede establecer el intervalo de fechas para toda la página de visualizaciones. Las visualizaciones incluyen:

* **La zona de puntuación segura** , personalizada en función de los objetivos de la organización y las definiciones de los intervalos de puntuación buenos, correctos y no válidos.
* **Tendencia de regresión** : escala de tiempo de puntos que se han regresivo debido a cambios en la configuración, el usuario o el dispositivo.  
* **Tendencia de comparación** : cómo se compara la puntuación segura de la organización con las otras personas a lo largo del tiempo. Esta vista puede incluir líneas que representan la media de puntuación de organizaciones con recuento de asientos similar y una vista de comparación personalizada que puede establecer.
* **Tendencia de aceptación de riesgos** : escala de tiempo de acciones mejoradas marcadas como "riesgo aceptado".
* **Cambios de puntuación** : número de puntos alcanzados, puntos de regresión o nuevas acciones agregados, junto con el cambio de puntuación subsiguiente en el intervalo de fechas especificado.

## <a name="risk-awareness"></a>Conocimiento de riesgos

La puntuación segura de Microsoft es un resumen numérico de su postura de seguridad en función de las configuraciones del sistema, el comportamiento del usuario y otras medidas relacionadas con la seguridad; no es una medida absoluta de la probabilidad de que se infrinja el sistema o sus datos. En su lugar, representa en qué medida ha adoptado controles de seguridad en su entorno de Microsoft, lo que puede ayudar a compensar el riesgo de infracciones. Ningún servicio en línea está completamente inmune a las infracciones de seguridad y la puntuación segura no se debe interpretar como una garantía contra la infracción de seguridad de ninguna manera.

## <a name="whats-new"></a>¿Hay alguna novedad? 

Para convertir la puntuación segura de Microsoft en un mejor representante de su postura de seguridad, hemos realizado algunos cambios. Para obtener información sobre los cambios planeados, consulte [¿qué viene con la puntuación segura de Microsoft?](microsoft-secure-score-whats-coming.md)

### <a name="updated-interface-and-functionality"></a>Interfaz y funciones actualizadas

* Todas las nuevas métricas y vistas de tendencias para CISO y discusiones de nivel de liderazgo
* Nuevas formas de realizar un seguimiento y evaluar su puntuación
* Mejor seguimiento y comprensión de las regresiones de puntuación
* Filtrar, etiquetar, buscar y agrupar las acciones de mejora
* Administrar hacia sus metas futuras mediante proyecciones de puntuación y acciones planeadas
* Y mucho más.

### <a name="removed-not-scored-and-review-improvement-actions"></a>Se quitaron las acciones de mejora "sin puntuar" y "revisión"

Uno de los principios de la puntuación segura es que la puntuación debe estar estandarizada y ser fácil de relacionar con. Las acciones de mejora que no se pueden medir o realizar acciones han causado confusión. Una calificación segura de Microsoft solo tiene sentido cuando cada recomendación puede tener un efecto claro en la puntuación. Las acciones de mejora no puntuadas no se pueden medir y las acciones de mejora de revisión no se miden en el mismo estándar que otras acciones de mejora.

Por estos motivos, todas las acciones de mejora que no se hayan puntuado o requerían una cadencia de revisión se han eliminado temporalmente. No es necesario realizar ninguna acción en su parte.

### <a name="simplification-of-the-point-system"></a>Simplificación del sistema de punto

Para estandarizar puntos en varias experiencias, se ha actualizado el total de puntos de acción de mejora de la puntuación segura para que merezca 10 puntos o menos. Es necesario ser más coherente en el respire ancho de los controles de seguridad que tenemos hoy y los que se van a agregar en el futuro. Si bien se trata de un cambio significativo y verá los totales de los puntos de colocación, no habrá cambios en su postura de seguridad.

## <a name="we-want-to-hear-from-you"></a>Queremos conocer su opinión

Si tiene algún problema, háganoslo saber mediante la publicación de la comunidad de [seguridad, privacidad & cumplimiento](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) . Estamos supervisando la comunidad y le proporcionaremos ayuda.
