---
title: Portal de Microsoft 365 Defender
description: El portal de Microsoft 365 Defender combina protección, detección, investigación y respuesta a amenazas de correo electrónico, colaboración, identidad, dispositivo y aplicación, en un lugar central.
keywords: introducción a MMicrosoft 365 Defender, ciberseguridad, amenazas persistentes avanzadas, seguridad empresarial, dispositivos, dispositivo, identidad, usuarios, datos, aplicaciones, incidentes, investigación y corrección automatizadas, búsqueda avanzada
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier1
ms.custom:
- admindeeplinkDEFENDER
- intro-overview
ms.topic: conceptual
adobe-target: true
ms.openlocfilehash: bc690e91ceb83d49814e869f40411da900faa719
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68051264"
---
# <a name="microsoft-365-defender-portal"></a>Portal de Microsoft 365 Defender

El [portal de Microsoft 365 Defender](https://sip.security.microsoft.com/homepage) combina protección, detección, investigación y respuesta a amenazas de correo electrónico, colaboración, identidad, dispositivo y aplicación en la nube, en un lugar central. El portal de Microsoft 365 Defender hace hincapié en el acceso rápido a la información, diseños más sencillos y reunir información relacionada para facilitar su uso. Incluye:

- **[Microsoft Defender para Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)** Microsoft Defender para Office 365 ayuda a las organizaciones a proteger su empresa con un conjunto de características de prevención, detección, investigación y búsqueda para proteger el correo electrónico y Office 365 recursos.
- **[Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection)** ofrece protección preventiva, detección posterior a la vulneración, investigación automatizada y respuesta para los dispositivos de la organización.
- **[Microsoft Defender for Identity](/defender-for-identity/what-is)** es una solución de seguridad basada en la nube que aprovecha las señales de Active Directory local para identificar, detectar e investigar amenazas avanzadas, identidades en peligro y acciones internas malintencionadas dirigidas a su organización.
- **[Microsoft Defender for Cloud Apps](/cloud-app-security/)** es una solución completa entre SaaS y PaaS que ofrece visibilidad profunda, controles de datos seguros y protección contra amenazas mejorada para las aplicaciones en la nube.

Vea este breve vídeo para obtener información sobre el portal de Microsoft 365 Defender.  
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWBKau]

## <a name="what-to-expect"></a>Qué esperar

El portal de Microsoft 365 Defender ayuda a los equipos de seguridad a investigar y responder a los ataques mediante la incorporación de señales de diferentes cargas de trabajo a un conjunto de experiencias unificadas para:

- Incidentes & alertas
- Búsqueda
- Acciones & envíos
- Análisis de amenazas
- Puntuación de seguridad
- Centro de aprendizaje
- Ensayos

Microsoft 365 Defender enfatiza la *unidad, la claridad y los objetivos comunes*. 

> [!NOTE]
> El portal de Microsoft 365 Defender es accesible sin necesidad de que los clientes realicen pasos de migración o compren una nueva licencia. Por ejemplo, este nuevo portal es accesible para los administradores con una suscripción A3, al igual que para los que tienen Microsoft Defender para Office 365 Plan 1 y Plan 2; sin embargo, Exchange Online Protection o Defender para Office 365  Los clientes del plan 1 solo ven las características de seguridad que admite su licencia de suscripción. El objetivo del portal es centralizar la seguridad.

## <a name="incident-and-alert-investigations"></a>Investigaciones de incidentes y alertas

La centralización de la información de seguridad crea un único lugar para investigar incidentes de seguridad en Microsoft 365. Un ejemplo principal es **Incidentes** en **Incidentes & alertas**.

:::image type="content" source="../../media/converged-incidents-2.png" alt-text="Página Incidentes del portal de Microsoft 365 Defender" lightbox="../../media/converged-incidents-2.png":::

Al seleccionar un nombre de incidente se muestra una página que muestra el valor de centralizar la información de seguridad, ya que tendrá una mejor información sobre la extensión completa de una amenaza, desde el correo electrónico hasta la identidad, hasta los puntos de conexión.

:::image type="content" source="../../media/converged-incident-info-3.png" alt-text="Página Resumen de un incidente en el portal de Microsoft 365 Defender" lightbox="../../media/converged-incident-info-3.png":::

Tómese el tiempo necesario para revisar los incidentes en su entorno, explorar en profundidad cada alerta y practicar la creación de conocimientos sobre cómo acceder a la información y determinar los pasos siguientes en el análisis.

Para obtener más información, consulte [incidentes en Microsoft 365 Defender](incidents-overview.md).

## <a name="hunting"></a>Búsqueda
Puede crear reglas de detección personalizadas y buscar amenazas específicas en su entorno. **La búsqueda** usa una herramienta de búsqueda de amenazas basada en consultas que le permite inspeccionar eventos de forma proactiva en su organización para buscar indicadores de amenazas y entidades. Estas reglas se ejecutan automáticamente para buscar y, a continuación, responder a la sospecha de actividad de infracción, máquinas mal configuradas y otros hallazgos.

Para obtener más información, consulte [Búsqueda proactiva de amenazas con la búsqueda avanzada en Microsoft 365 Defender](advanced-hunting-overview.md).

## <a name="improved-processes"></a>Procesos mejorados

Los controles y el contenido comunes aparecen en el mismo lugar o se condensan en una fuente de datos, lo que facilita la búsqueda. Por ejemplo, la configuración unificada.

### <a name="unified-settings"></a>Configuración unificada

:::image type="content" source="../../media/converged-add-role-9.png" alt-text="Página Configuración del portal de Microsoft 365 Defender" lightbox="../../media/converged-add-role-9.png":::

### <a name="permissions--roles"></a>Permisos & roles

:::image type="content" source="../../media/converged-roles-5.png" alt-text="Los roles de puntos de conexión & grupos que se muestran en la página Permisos & roles" lightbox="../../media/converged-roles-5.png":::

El acceso a Microsoft 365 Defender se configura con roles globales de Azure AD o mediante roles personalizados.

- Más información sobre cómo [administrar el acceso a Microsoft 365 Defender](m365d-permissions.md)
- Obtenga más información sobre cómo [crear roles personalizados](custom-roles.md) en Microsoft 365 Defender


### <a name="integrated-reports"></a>Informes integrados

Los informes también se unifican en Microsoft 365 Defender. Los administradores pueden empezar con un informe de seguridad general y bifurcarse en informes específicos sobre puntos de conexión, correo electrónico & colaboración. Los vínculos aquí se generan dinámicamente en función de la configuración de la carga de trabajo.

### <a name="quickly-view-your-microsoft-365-environment"></a>Visualización rápida del entorno de Microsoft 365

En la página **Inicio** se muestran muchas de las tarjetas comunes que necesitan los equipos de seguridad. La composición de tarjetas y datos depende del rol de usuario. Dado que Microsoft 365 Defender portal usa el control de acceso basado en rol, los distintos roles verán tarjetas más significativas para sus trabajos cotidianos.

Esta información de un vistazo le ayuda a mantenerse al día con las actividades más recientes de su organización. Microsoft 365 Defender reúne señales de diferentes orígenes para presentar una vista holística del entorno de Microsoft 365.

Puede agregar y quitar tarjetas diferentes en función de sus necesidades.

### <a name="search-across-entities-preview"></a>Búsqueda entre entidades (versión preliminar)

>[!IMPORTANT]
> Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.
La barra de búsqueda se encuentra en la parte superior de la página. A medida que escribe, se proporcionan sugerencias para que sea más fácil encontrar entidades. La página de resultados de búsqueda mejorada centraliza los resultados de todas las entidades.

Puede buscar en las siguientes entidades en Defender para punto de conexión y Defender for Identity: 

- **Dispositivos** : compatible con Defender para punto de conexión y Defender for Identity. Admite el uso de operadores de búsqueda. 
- **Usuarios** : compatible con Defender para punto de conexión, Defender for Identity y Defender for Cloud Apps. 
- **Archivos, direcciones IP y direcciones URL:** las mismas funcionalidades que en Defender para punto de conexión.

    >[!NOTE]
    >Las búsquedas de direcciones IP y URL coinciden exactamente y no aparecen en la página de resultados de búsqueda; conducen directamente a la página de entidad. 

- **MDVM** : las mismas funcionalidades que en Defender para punto de conexión (vulnerabilidades, software y recomendaciones). 

## <a name="threat-analytics"></a>Análisis de amenazas

Realice un seguimiento y responda a las amenazas emergentes con los siguientes Microsoft 365 Defender análisis de amenazas: Análisis de amenazas es la solución de inteligencia sobre amenazas Microsoft 365 Defender de expertos investigadores de seguridad de Microsoft. Está diseñado para ayudar a los equipos de seguridad a ser lo más eficientes posible a la vez que se enfrentan a amenazas emergentes, como:

- Actores de amenazas activos y sus campañas
- Técnicas de ataque populares y nuevas
- Vulnerabilidades críticas
- Superficies de ataque comunes
- Malware frecuentes

## <a name="learning-hub"></a>Centro de aprendizaje

<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portal</a> incluye un centro de aprendizaje que proporciona instrucciones de recursos como el blog de seguridad de Microsoft, la comunidad de seguridad de Microsoft en YouTube y la documentación oficial.

> [!NOTE]
> Hay **filtros** útiles en la parte superior de Microsoft 365 Defender centro de aprendizaje que le permitirán elegir entre productos (actualmente Microsoft 365 Defender, Microsoft Defender para punto de conexión y Microsoft Defender para Office 365). Observe que se muestra el número de recursos de aprendizaje para cada sección, lo que puede ayudar a los alumnos a realizar un seguimiento de cuántos recursos tienen a mano para el aprendizaje y el aprendizaje.
>
> Junto con el filtro Producto, se enumeran temas actuales, tipos de recursos (desde vídeos hasta seminarios web), niveles de familiaridad o experiencia con áreas de seguridad, roles de seguridad y características de producto.

> [!TIP]
> Hay muchas otras oportunidades de aprendizaje en [Microsoft Learn](/training/). Encontrará formación de certificación como [Course MS-500T02-A: Implementing Microsoft 365 Threat Protection](/training/certifications/courses/ms-500t02).

## <a name="send-us-your-feedback"></a>Envíenos sus comentarios

Necesitamos sus comentarios. Siempre estamos buscando mejorar, así que si hay algo que le gustaría ver, [vea este vídeo para averiguar cómo puede confiar en nosotros para leer sus comentarios](https://www.microsoft.com/videoplayer/embed/RE4K5Ci).

## <a name="explore-what-the-microsoft-365-defender-portal-has-to-offer"></a>Explorar lo que ofrece el portal de Microsoft 365 Defender

Siga explorando las características y funcionalidades de Microsoft 365 Defender:

- [Administrar incidentes y alertas](manage-incidents.md)
- [Hacer seguimiento y responder a amenazas emergentes con el análisis de amenazas](threat-analytics.md)
- [El centro de actividades](m365d-action-center.md)
- [Buscar amenazas entre dispositivos, correos electrónicos, aplicaciones e identidades](./advanced-hunting-query-emails-devices.md)
- [Reglas de detección personalizada](./custom-detection-rules.md)
- [Alertas de colaboración y correos electrónicos](../../compliance/alert-policies.md#default-alert-policies)
- [Crear una simulación de ataque de suplantación de identidad (phishing)](../office-365-security/attack-simulation-training.md) y [crear una carga útil para entrenar a los equipos](/microsoft-365/security/office-365-security/attack-simulation-training-payloads)

## <a name="training-for-security-analysts"></a>Aprendizaje para analistas de seguridad

Con esta ruta de aprendizaje de Microsoft Learn, puede comprender Microsoft 365 Defender y cómo puede ayudar a identificar, controlar y corregir amenazas de seguridad.

|Aprendizaje:|Detectar y responder a ataques cibernéticos con Microsoft 365 Defender|
|---|---|
|![Icono de aprendizaje de Microsoft 365 Defender.](../../media/microsoft-365-defender/m365-defender-secure-organization.svg)|Microsoft 365 Defender unifica las señales de amenazas entre puntos de conexión, identidades, correo electrónico y aplicaciones para proporcionar una protección integrada frente ataques cibernéticos sofisticados. Microsoft 365 Defender es una experiencia central desde la cual investigar y responder a incidentes y buscar proactivamente actividades de ciberseguridad malintencionadas en curso.<p> 1 h 38 min - Ruta de aprendizaje - 5 módulos|

> [!div class="nextstepaction"]
> [Iniciar >](/training/paths/defender-detect-respond/)


## <a name="see-also"></a>Vea también

- [Novedades de Microsoft 365 Defender](whats-new.md)
- [Microsoft Defender para Office 365 en Microsoft 365 Defender](microsoft-365-security-center-mdo.md)
- [Microsoft Defender para punto de conexión en Microsoft 365 Defender](microsoft-365-security-center-mde.md)
