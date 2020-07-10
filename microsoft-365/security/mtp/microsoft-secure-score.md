---
title: Puntuación de seguridad de Microsoft
description: Describe la puntuación segura de Microsoft en el centro de seguridad 365 de Microsoft, cómo mejorar su postura de seguridad y qué administradores de seguridad pueden esperar.
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
ms.openlocfilehash: 212cefebfa3b4954f30d114419f82a5862e98a4f
ms.sourcegitcommit: 09a500a44d8723f8f2be87d9ad4ce7e453c5192b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2020
ms.locfileid: "45094803"
---
# <a name="microsoft-secure-score"></a>Puntuación de seguridad de Microsoft

La calificación segura de Microsoft es una medida de la postura de seguridad de una organización, con un número más alto que indica que se han realizado más acciones de mejora. Puede encontrarse en https://security.microsoft.com/securescore el [centro de seguridad de Microsoft 365](overview-security-center.md).

Seguir las recomendaciones de puntuación segura puede proteger a su organización de las amenazas. Desde un panel centralizado en el centro de seguridad de Microsoft 365, las organizaciones pueden supervisar y trabajar en la seguridad de las identidades, los datos, las aplicaciones, los dispositivos y la infraestructura de Microsoft 365.

La puntuación segura ayuda a las organizaciones a:  

* Informe sobre el estado actual de la postura de seguridad de la organización.
* Mejorar su postura de seguridad proporcionando detección, visibilidad, orientación y control.  
* Comparar con benchmarks y establecer indicadores clave de rendimiento (KPI).

Las organizaciones obtienen acceso a las sólidas visualizaciones de métricas y tendencias, la integración con otros productos de Microsoft, la puntuación con organizaciones similares y mucho más. La puntuación también puede reflejar Cuándo las soluciones de terceros han tratado las acciones recomendadas.

![Página principal de puntuación segura](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a>Cómo funciona

Se le proporcionan puntos para configurar las características de seguridad recomendadas, realizar tareas relacionadas con la seguridad o resolver la acción de mejora con una aplicación o software de terceros, o una mitigación alternativa. Algunas acciones de mejora solo proporcionan puntos cuando se completan completamente y otras proporcionan puntos parciales si se completan para algunos dispositivos o usuarios. Si no puede o no desea activar una de las acciones de mejora, puede optar por aceptar el riesgo o el riesgo restante.

Le mostramos el conjunto completo de posibles mejoras, independientemente de la licencia, para que pueda comprender los procedimientos recomendados de seguridad y mejorar su puntuación. La postura absoluta de seguridad se representa mediante calificación segura, que permanece igual independientemente de las licencias de producto que posea la organización. Tenga en cuenta que la seguridad debe sopesarse con facilidad de uso y no todas las recomendaciones pueden funcionar en su entorno.

La puntuación se actualiza en tiempo real para reflejar la información que se presenta en las páginas de acciones de visualización y de mejora. La puntuación segura también se sincroniza diariamente para recibir datos del sistema sobre los puntos alcanzados para cada acción.

### <a name="key-scenarios"></a>Escenarios clave

- [Comprobar el resultado actual](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [Comparar su calificación con organizaciones como la suya](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [Ver acciones de mejora y decidir un plan de acción](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [Iniciar flujos de trabajo para investigar o implementar](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)
    - [Microsoft 365 Security Center and ServiceNow Integration](tickets-security-center.md)

### <a name="how-improvement-actions-are-scored"></a>Cómo se puntuan las acciones de mejora

Cada acción de mejora merece 10 puntos o menos. La mayoría se puntuan de una manera binaria: Si implementa la acción de mejora, como crear una nueva Directiva o activar una configuración específica, obtendrá un 100% de los puntos. Para otras acciones de mejora, los puntos se dan como un porcentaje de la configuración total. Por ejemplo, si los Estados de acción de mejora obtienen 10 puntos al proteger a todos los usuarios con la autenticación multifactor y solo tiene un 50 de 100 total de usuarios protegidos, se le asignará una puntuación parcial de 5 puntos (50 protegido/100 total * 10 máx PTS = 5 PTS de puntuación parcial).

### <a name="products-included-in-secure-score"></a>Productos incluidos en la puntuación segura

Actualmente hay recomendaciones para Microsoft 365 (incluido Exchange Online), Azure AD, ATP de Microsoft, ATP de Azure y seguridad de aplicaciones en la nube. Pronto estarán disponibles recomendaciones para otros productos de seguridad. Las recomendaciones no cubren todas las superficies de ataque asociadas con cada producto, pero son una buena línea de base. También puede marcar las acciones de mejora como cubiertas por un tercero o una mitigación alternativa.

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

Con acceso de solo lectura, no es posible editar el estado ni las notas para una acción de mejora, editar zonas de puntuación ni editar comparaciones personalizadas.

* Administrador del servicio de asistencia
* Administrador de usuarios
* Administrador de servicios
* Lector de seguridad
* Operador de seguridad
* Lector global

## <a name="risk-awareness"></a>Conocimiento de riesgos

La puntuación segura de Microsoft es un resumen numérico de su postura de seguridad en función de las configuraciones del sistema, el comportamiento del usuario y otras medidas relacionadas con la seguridad; no es una medida absoluta de la probabilidad de que se infrinja el sistema o sus datos. En su lugar, representa en qué medida ha adoptado controles de seguridad en su entorno de Microsoft, lo que puede ayudar a compensar el riesgo de infracciones. Ningún servicio en línea está completamente inmune a las infracciones de seguridad y la puntuación segura no se debe interpretar como una garantía contra la infracción de seguridad de ninguna manera.

## <a name="whats-new"></a>Novedades 

Para convertir la puntuación segura de Microsoft en un mejor representante de su postura de seguridad, hemos realizado algunos cambios. Para obtener información sobre los cambios planeados, consulte [¿qué viene con la puntuación segura de Microsoft?](microsoft-secure-score-whats-coming.md).

### <a name="incompatibility-with-identity-secure-score-and-graph-api"></a>Incompatibilidad con la puntuación segura de la identidad y la API de Graph

En la versión más reciente de la puntuación segura de Microsoft, se ha lanzado un modelo de resultados mejorado. Estos cambios permiten una vista más flexible y precisa de la postura de seguridad. Sin embargo, estas actualizaciones han hecho que la puntuación segura de Microsoft sea incompatible temporalmente con la puntuación segura de identidad y la API de Graph.

En el tiempo, la calificación de identidad segura y la API de Graph adoptarán el nuevo modelo de calificación. Hasta entonces, los clientes verán las diferencias en los resultados indicados por la puntuación segura de Microsoft, la puntuación segura de identidad y la API de Graph. Lamentamos las molestias y los motivos para garantizar que estas experiencias sean más compatibles en el futuro.

### <a name="updated-improvement-actions"></a>Acciones de mejora actualizadas

- Se agregaron acciones de mejora de Azure Active Directory
- Se agregaron acciones de mejora de protección contra amenazas avanzada de Azure
- Compatibilidad con las recomendaciones de seguridad de la [vulnerabilidad ATP & vulnerabilidad](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) de Microsoft defender
    - Todas las recomendaciones de seguridad emitidas suministradas por TVM ya están disponibles

### <a name="updated-interface-and-functionality"></a>Interfaz y funciones actualizadas

* Todas las nuevas métricas y vistas de tendencias para CISO y discusiones de nivel de liderazgo
* Nuevas formas de realizar un seguimiento y evaluar su puntuación
* Mejor seguimiento y comprensión de las regresiones de puntuación
* Filtrar, etiquetar, buscar y agrupar las acciones de mejora
* Administrar hacia sus metas futuras mediante proyecciones de puntuación y acciones planeadas
* Y mucho más.

### <a name="june-2020"></a>Junio de 2020

#### <a name="removed-improvement-action-for-microsoft-defender-advanced-threat-protection"></a>Se quitó la acción de mejora para la protección contra amenazas avanzada de Microsoft defender

* Activar las reglas de reducción de la superficie de ataque

#### <a name="added-improvement-actions-for-microsoft-defender-advanced-threat-protection"></a>Acciones de mejora agregadas para la protección contra amenazas avanzada de Microsoft defender

* Impedir que Adobe Reader cree procesos secundarios
* Usar protección avanzada contra ransomware
* Bloquear todas las aplicaciones de Office para crear procesos secundarios
* Impedir que las aplicaciones de Office creen contenido ejecutable
* Impedir que JavaScript o VBScript inicien contenido ejecutable descargado
* Bloquear la ejecución de scripts potencialmente ofuscados
* Bloquear contenido ejecutable del cliente de correo electrónico y Webmail
* Impedir que la aplicación de comunicación de Office cree procesos secundarios
* Bloquear procesos no habilitados y no firmados que se ejecutan desde USB
* Bloquear la persistencia a través de la suscripción de eventos WMI
* Impedir que las aplicaciones de Office inserten código en otros procesos
* Bloquear la ejecución de los archivos ejecutables a menos que cumplan un criterio de predominio, edad o lista de confianza
* Bloquear creaciones de procesos procedentes de PSExec y comandos WMI
* Bloquear credenciales de robo desde el subsistema de la autoridad de seguridad local de Windows (lsass.exe)
* Bloquear llamadas a la API Win32 desde macros de Office

## <a name="we-want-to-hear-from-you"></a>Queremos conocer su opinión

Si tiene algún problema, háganoslo saber mediante la publicación de la comunidad de [seguridad, privacidad & cumplimiento](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) . Estamos supervisando la comunidad y le proporcionaremos ayuda.

## <a name="related-resources"></a>Recursos relacionados

- [Obtener visibilidad de la postura de seguridad](microsoft-secure-score-improvement-actions.md)
- [Realizar un seguimiento del historial de puntuación segura de Microsoft y cumplir los objetivos](microsoft-secure-score-history-metrics-trends.md)
- [Próximas novedades](microsoft-secure-score-whats-coming.md)
