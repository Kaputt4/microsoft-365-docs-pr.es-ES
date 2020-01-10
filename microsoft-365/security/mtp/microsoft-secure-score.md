---
title: Puntuación de seguridad de Microsoft
description: Describe la puntuación segura de Microsoft en el centro de seguridad 365 de Microsoft, cómo se calculan los detalles y qué administradores de seguridad pueden esperar.
keywords: seguridad, malware, Microsoft 365, M365, calificación segura, centro de seguridad, acciones de mejora
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
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
ms.openlocfilehash: 656b444da9b85028aa1d280a76ca038e2d3a3ac6
ms.sourcegitcommit: a2e9ab69f99f2069372ccfffd9ef2ffbd8568826
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/10/2020
ms.locfileid: "41012193"
---
# <a name="microsoft-secure-score"></a>Puntuación de seguridad de Microsoft

La calificación segura de Microsoft es una medida de la postura de seguridad de una organización, con un número más alto que indica que se han realizado más acciones de mejora. Seguir las recomendaciones de puntuación de seguridad puede proteger a su organización de las amenazas. Desde un panel centralizado en el centro de seguridad de Microsoft 365, las organizaciones pueden supervisar y trabajar en la seguridad de las identidades, los datos, las aplicaciones, los dispositivos y la infraestructura de Microsoft 365.

La puntuación segura ayuda a las organizaciones a:

* Informe sobre el estado actual de la postura de seguridad de la organización.
* Mejorar su postura de seguridad proporcionando detección, visibilidad, orientación y control.  
* Comparar con benchmarks y establecer indicadores clave de rendimiento (KPI).

Las organizaciones obtienen acceso a las sólidas visualizaciones de métricas y tendencias, la integración con otros productos de Microsoft, la puntuación con organizaciones similares y mucho más. La puntuación también puede reflejar Cuándo las soluciones de terceros han tratado las acciones recomendadas.

Además, puede obtener acceso a sus recomendaciones y puntuaciones a través de la [API de Microsoft Graph](https://www.microsoft.com/security/partnerships/graph-security-api). Obtenga información sobre el [tipo de recurso de puntuación segura](https://go.microsoft.com/fwlink/?linkid=2092996).

## <a name="how-it-works"></a>Cómo funciona

Se le proporcionan puntos para configurar las características de seguridad recomendadas, realizar tareas relacionadas con la seguridad (como ver informes) o solucionar la acción de mejora con una aplicación o un software de terceros. Algunas acciones de mejora solo proporcionan puntos cuando se completan completamente y otras proporcionan puntos parciales si se completan para algunos dispositivos o usuarios.

Le mostramos el conjunto completo de posibles mejoras, independientemente de la licencia, para que pueda comprender los procedimientos recomendados de seguridad y mejorar su puntuación. La postura absoluta de seguridad se representa mediante calificación segura, que permanece igual independientemente de las licencias de producto que posea la organización. Tenga en cuenta que la seguridad debe sopesarse con facilidad de uso y no todas las recomendaciones pueden funcionar en su entorno.

La puntuación se actualiza en tiempo real para reflejar la información que se presenta en las páginas de acciones de visualización y de mejora. La puntuación segura también se sincroniza diariamente para recibir datos del sistema sobre los puntos alcanzados para cada acción.

### <a name="how-improvement-actions-are-scored"></a>Cómo se puntuan las acciones de mejora

La mayoría se puntuan de una manera binaria: Si implementa la acción de mejora, como crear una nueva Directiva o activar una configuración específica, obtendrá un 100% de los puntos. Para otras acciones de mejora, los puntos se dan como un porcentaje de la configuración total. Por ejemplo, si los Estados de acción de mejora obtienen 30 puntos al proteger a todos los usuarios con la autenticación multifactor y solo tiene 5 de 100 usuarios totales protegidos, se le asignará una puntuación parcial de unos 2 puntos (5 protegidos/100 en total * 30 máx PTS = puntuación parcial de 2 PTO).

### <a name="products-included-in-secure-score"></a>Productos incluidos en la puntuación segura

Actualmente hay recomendaciones para Office 365 (como SharePoint Online, Exchange Online, OneDrive para la empresa, Microsoft Information Protection, etc.), Azure AD, Intune y Cloud App Security. Pronto estarán disponibles recomendaciones para otros productos de seguridad, como ATP de Azure y ATP de Microsoft defender. Las recomendaciones no cubren todas las superficies de ataque asociadas con cada producto, pero son una buena línea de base. También puede marcar las acciones de mejora como cubiertas por un tercero.

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

* Ámbito securityevents. Read. All (para rol de solo lectura)
* Ámbito securityevents. ReadWrite. All (para funciones de lectura y escritura)

## <a name="gain-visibility-into-your-security-posture"></a>Obtener visibilidad de la postura de seguridad

Para ayudarle a la información que necesita con mayor rapidez, las acciones de mejora de Microsoft se organizan en grupos:

* Identity (cuentas de Azure AD & roles con Azure ATP disponible próximamente)
* Datos (Microsoft Information Protection)
* Dispositivo (dispositivos ATP de Microsoft defender, próximamente)
* Aplicación (aplicaciones de correo electrónico y nube, incluidos Office 365 y Microsoft Cloud App Security)
* Infraestructura (recursos de Azure)

En la página información general sobre la calificación segura de Microsoft, puede ver cómo se dividen los puntos entre estos grupos y qué puntos están disponibles. La página de información general también es la ubicación para obtener una vista completa de la puntuación total, la tendencia histórica de la puntuación segura con comparaciones de los bancos de pruebas y las acciones de mejora ordenadas por prioridad que se pueden realizar para mejorar la puntuación.

![Página Web de](../media/secure-score/homepage-original.png)
puntuación segura*figura 1: Página de introducción a la calificación segura de Microsoft*

## <a name="take-action-to-improve-your-score"></a>Tomar medidas para mejorar su puntuación

La ficha acciones de mejora enumera las recomendaciones de seguridad que se redirigen a posibles superficies de ataque, junto con su estado (completado, no completado, resuelto a través de terceros y omitidos). Puede buscar, filtrar y agrupar todas las acciones de mejora.

### <a name="ranking"></a>Porcentaje

La clasificación se basa en el número de puntos restantes que quedan para lograr, la dificultad de implementación, el impacto del usuario y la complejidad. Las acciones de mejora con mayor jerarquía tienen un gran número de puntos que quedan con problemas, impacto en el usuario y complejidad.

### <a name="actions"></a>Acciones

La puntuación segura de Microsoft no realiza un seguimiento de las acciones etiquetadas como [no puntuadas]. Puede seguir realizando acciones pero su finalización no afectará a su calificación. Si una acción hace un seguimiento de la puntuación segura de Microsoft en el futuro y ya la ha completado, la puntuación segura reflejará automáticamente el cambio.

Cuando se selecciona una acción de mejora específica, aparece una volar hacia fuera. Para completar la acción, tiene algunas opciones:

1. Seleccione **Ver configuración** para ir a la pantalla de configuración y realizar el cambio. A continuación, puede obtener los puntos que merece la acción, visible en la parte superior de la volando. Los puntos pueden tardar hasta 24 horas en actualizarse.

2. Seleccione **resolver a través de terceros** porque la acción de mejora ya ha sido tratada por una aplicación o software de terceros. Usted obtiene los puntos que merece la acción, de modo que la puntuación segura refleje mejor su postura de seguridad general. Si un tercero ya no cubre el control, puede marcar la acción de mejora como no completada. Tenga en cuenta que Microsoft no tiene ninguna visibilidad sobre si se han cumplido los requisitos de puntuación si la acción de mejora se ha marcado como resuelta a través de terceros.

3. Seleccione **omitir** porque decidió aceptar el riesgo y no pasar la acción de mejora. Una vez que ignore una acción de mejora, se reducirá el número total de puntos de calificación seguros que puede lograr. Puede ver esta acción en el historial o deshacerla en cualquier momento.

4. Seleccione **revisar** porque la acción de mejora requiere que Revise regularmente una parte del entorno para obtener y conservar puntos. Por ejemplo, las reglas de reenvío de buzones deben revisarse cada semana para asegurarse de que los datos no se están exfiltrando desde la red. No es necesario realizar ningún cambio, pero se debe realizar una acción. Si revisa las reglas con regularidad, recibirá los puntos. Si no es así, se reduce el resultado.

![Ejemplo de acción de mejora de puntuación segura](../media/secure-score/secure-score1x450.png) ![Ejemplo de acción para mejorar la revisión de calificaciones seguras](../media/secure-score/secure-score2x450.png)

*Figuras 2 & 3: controles flotantes de acciones de mejora*

## <a name="monitor-improvements-over-time"></a>Supervisar las mejoras a lo largo del tiempo

Puede ver un gráfico de la puntuación de su organización con el tiempo en la ficha **historial** . debajo del gráfico hay una lista de todas las acciones realizadas en el intervalo de tiempo seleccionado y sus atributos, como puntos y categoría resultantes. Puede personalizar un intervalo de fechas y filtrar por categoría.

## <a name="risk-awareness"></a>Conocimiento de riesgos

La puntuación segura de Microsoft es un resumen numérico de la postura de seguridad en función de las configuraciones del sistema, el comportamiento del usuario y otras medidas relacionadas con la seguridad; no es una medida absoluta de la probabilidad de que se infrinja el sistema o sus datos. En su lugar, representa en qué medida ha adoptado controles de seguridad en su entorno de Microsoft, lo que puede ayudar a compensar el riesgo de infracciones. Ningún servicio en línea está completamente inmune a las infracciones de seguridad y la puntuación segura no se debe interpretar como una garantía contra la infracción de seguridad de ninguna manera.

## <a name="whats-coming"></a>¿Qué llega?

Para hacer que la puntuación segura de Microsoft sea un mejor representante de su postura de seguridad y mejorar el uso, estamos realizando algunos cambios en un futuro próximo. Se cambiará la puntuación y la puntuación máxima posible. Sin embargo, esto no implica un cambio en su postura de seguridad.

### <a name="mfa-improvement-action-updates"></a>Actualizaciones de acciones de mejora de MFA

Para reflejar la necesidad de las empresas de garantizar la máxima seguridad al aplicar las directivas que funcionan con su negocio, la calificación segura de Microsoft es quitar tres acciones de mejora centradas alrededor de la autenticación multifactor y agregando dos.

Los tres que se quitarán:
- Registrar todos los usuarios para la autenticación multifactor
- Requerir MFA para todos los usuarios
- Requerir MFA para los roles privilegiados de Azure AD

Nuevas acciones de mejora:
- Asegurarse de que todos los usuarios puedan completar la autenticación multifactor para el acceso seguro
- Requerir MFA para roles administrativos

 Estas nuevas acciones de mejora requerirán el registro de los usuarios o administradores para la autenticación multifactor (MFA) en el directorio y el establecimiento del conjunto adecuado de directivas que se adapten a las necesidades de la organización. El objetivo principal es tener flexibilidad a la vez que se asegura de que todos los usuarios y administradores puedan autenticarse con varios factores o solicitudes de verificación de identidad basadas en riesgos. Esto puede adoptar la forma de establecer los valores predeterminados de seguridad que permiten a Microsoft decidir cuándo desafiar a los usuarios para MFA o tener varias directivas que apliquen decisiones con ámbito.

### <a name="removing-not-scored-and-review-improvement-actions"></a>Eliminación de acciones de mejora "sin puntuar" y "revisión"

Uno de los principios de la puntuación segura es que la puntuación debe estar estandarizada y ser fácil de relacionar con. Las acciones de mejora que no se pueden medir o realizar acciones han causado confusión. Una calificación segura de Microsoft solo tiene sentido cuando cada recomendación puede tener un efecto claro en la puntuación. Las acciones de mejora no puntuadas no se pueden medir y las acciones de mejora de revisión no se miden en el mismo estándar que otras acciones de mejora.  

Por estos motivos, todas las acciones de mejora que no se hayan puntuado o que requerían una cadencia de revisión se eliminarán temporalmente. No es necesario realizar ninguna acción en su parte.

### <a name="simplification-of-the-point-system"></a>Simplificación del sistema de punto

Para estandarizar puntos en varias experiencias, se actualizará el total del punto de acción mejora de la puntuación segura para que merezca 10 puntos o menos. Es necesario ser más coherente en el respire ancho de los controles de seguridad que tenemos hoy y los que se van a agregar en el futuro. Si bien se trata de un cambio significativo y verá los totales de los puntos de colocación, no habrá cambios en su postura de seguridad.  

### <a name="preview-features"></a>Versión preliminar de las características

Las siguientes características se incluirán en la versión preliminar:

* Todas las nuevas métricas y vistas de tendencias para CISO y discusiones de nivel de liderazgo
* Nuevas formas de realizar un seguimiento y evaluar su puntuación
* Mejor seguimiento y supervisión de regresiones de puntuación
* Filtrar, etiquetar, buscar y agrupar las acciones de mejora
* Administrar hacia sus metas futuras mediante proyecciones de puntuación y acciones planeadas
* Y mucho más.

## <a name="we-want-to-hear-from-you"></a>Queremos conocer su opinión

Si tiene algún problema, háganoslo saber mediante la publicación de la comunidad de [seguridad, privacidad & cumplimiento](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) . Estamos supervisando la comunidad y le proporcionaremos ayuda.