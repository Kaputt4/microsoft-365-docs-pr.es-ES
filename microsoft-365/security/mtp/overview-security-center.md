---
title: Vista general del Centro de seguridad de Microsoft 365
description: Ventajas del Centro de seguridad de Microsoft 365, que combina Microsoft Defender para Office 365 (MDO) y Microsoft Defender para Endpoint (MDE), con Microsoft Defender para identidad (MDI) y Microsoft Cloud App Security (MCAS). En este artículo se describen los avances del Centro de seguridad de Microsoft 365 para los administradores.
keywords: seguridad, malware, Microsoft 365, M365, centro de seguridad, monitor, informe, identidades, datos, dispositivos, aplicaciones
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.date: 02/02/2021
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 89e72d703bd70647d6c2b00732315b8e5f015cc7
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167219"
---
# <a name="the-unified-microsoft-365-security-center-overview"></a>Información general del Centro de seguridad unificado de Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**Se aplica a:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft Defender para Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)

> ¿Desea experimentar Microsoft 365 Defender? Puede [evaluarlo en un entorno de laboratorio o](https://aka.ms/mtp-trial-lab) ejecutar el proyecto piloto en [producción.](https://aka.ms/m365d-pilotplaybook)

El centro de seguridad mejorado de **Microsoft 365** ( ) combina protección, detección, investigación y respuesta a las amenazas de correo electrónico, colaboración, identidad y dispositivo, en un [https://security.microsoft.com](https://security.microsoft.com) portal central.    

El Centro de seguridad de Microsoft 365 reúne la funcionalidad de los portales de seguridad de Microsoft existentes, como el Centro de seguridad de Microsoft Defender y el Centro de seguridad & cumplimiento de Office 365. El centro de seguridad enfatiza el acceso rápido a la información, diseños más sencillos y la colaboración de la información relacionada para facilitar su uso. Este centro incluye:

- **[Microsoft Defender para Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)** Microsoft Defender para Office 365 ayuda a las organizaciones a proteger su empresa con un conjunto de características de prevención, detección, investigación y búsqueda para proteger el correo electrónico y los recursos de Office 365.
- **[Microsoft Defender para endpoint ofrece](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)** protección preventiva, detección posterior a la infracción, investigación automatizada y respuesta para los dispositivos de su organización.
- **[Microsoft 365 Defender](microsoft-threat-protection.md)** forma parte de la solución de detección y respuesta extendida (XDR) de Microsoft que aprovecha la cartera de seguridad de Microsoft 365 para analizar automáticamente los datos de amenazas entre dominios y crear una imagen de un ataque en un solo panel. 

Si necesita información sobre lo que ha cambiado desde el Centro de seguridad y cumplimiento de Office 365 & o el Centro de seguridad de Microsoft Defender, vea:

- [Defender para Office 365 en el Centro de seguridad de Microsoft 365.](microsoft-365-security-center-mdo.md)
- [Defender para punto de conexión en el Centro de seguridad de Microsoft 365.](microsoft-365-security-center-mde.md)

## <a name="what-to-expect"></a>Qué esperar

Todo el contenido de seguridad que use en el Centro de seguridad y cumplimiento de Office 365 (protection.office.com) y el Centro de seguridad de Microsoft Defender (securitycenter.microsoft.com) ahora puede encontrarse en el Centro de seguridad de *Microsoft 365.*

El Centro de seguridad de Microsoft 365 ayuda a los equipos de seguridad a investigar y responder a los ataques a través de señales de diferentes cargas de trabajo en una única experiencia unificada:

- Incidentes y & alertas
- Búsqueda
- Centro de actividades
- Análisis de amenazas

El Centro de seguridad de Microsoft 365 enfatiza la *unidad,* la claridad y los objetivos comunes a medida que combina Microsoft Defender para Office 365 y Microsoft Defender para endpoint. La combinación se basaba en las prioridades que se enumeran a continuación y se realizaba sin sacrificar las capacidades que cada conjunto de seguridad traía a la combinación:

- bloques de creación comunes
- terminología común
- entidades comunes
- paridad de características con otras cargas de trabajo

## <a name="unified-investigations"></a>Investigaciones unificadas

La racionalización de los centros de seguridad crea un único panel para investigar cualquier incidente en una organización de Microsoft 365. Un ejemplo principal es el **nodo Incidentes** en el inicio rápido del Centro de seguridad de Microsoft 365.

:::image type="content" source="../../media/converged-incidents-2.png.png" alt-text="La página Incidentes en MDO.":::

Por ejemplo, hacer doble clic en  un nombre de incidente con gravedad alta le lleva a una página que muestra la ventaja de los centros de convergencia.

![Incidente de varias fases que implica la escalación de privilegios en varios puntos de conexión, que muestra 16 dispositivos afectados y 9 usuarios afectados.](../../media/converged-incident-info-3.png)

> [!TIP]
> La pestaña **Usuarios** convergentes es un buen lugar para comenzar las consultas. Esta única página muestra información para los usuarios de cargas de trabajo convergentes (Microsoft Defender para Endpoint, Microsoft Defender para Identidad y MCAS, si la aprovecha) y una variedad de orígenes como Active Directory local, Azure Active Directory, usuarios sincronizados, locales y de terceros. Obtenga más información sobre [la nueva experiencia de usuarios.](investigate-users.md)

La información del incidente muestra los datos específicos de usuario/identidad y los dispositivos de riesgo, junto a los buzones afectados. También relaciona cualquier información **de investigación y** **evidencias recopiladas.** Esto hace que sea más fácil para los administradores y los equipos de operaciones de seguridad pivotar desde una alerta de alto riesgo a los usuarios y buzones afectados. Si se **observan las pestañas** Incidentes en la parte superior de esta página, hay otras tablas dinámicas de seguridad clave disponibles desde esta única ubicación.

> [!IMPORTANT]
> En la parte superior de cualquier página de un incidente específico, verá las pestañas **Resumen,** Alertas, Dispositivos,  **Usuarios,** **Buzones** de **correo,** Investigaciones **y** Evidencias.

La selección **de investigaciones** abre una página que incluye un gráfico del análisis que se está llevando a cabo y muestra un estado (como la aprobación **pendiente)** para la corrección. Tómese el tiempo para seleccionar incidentes específicos en su entorno, explore en profundidad estas pestañas y práctica la creación de un perfil para distintos tipos de amenazas. La familiaridad se beneficiará de las investigaciones de presión posteriores.

## <a name="improved-processes"></a>Procesos mejorados

Los controles y el contenido comunes aparecen en el mismo lugar o se condensan en una fuente de datos, lo que facilita su búsqueda. Por ejemplo, configuración unificada.

### <a name="unified-settings"></a>Configuración unificada

![Haga clic en "Roles" y abra la página Configuración, que incluye configuración general, permisos, API y reglas. Abra Permisos y, a continuación, Roles. Muestra todos los roles](../../media/converged-add-role-9.png)

### <a name="permissions--roles"></a>Permisos y & roles

![Permisos & página Roles que muestra roles de puntos de conexión & grupos, roles y grupos de dispositivos.](../../media/converged-roles-5.png)

 Access the Microsoft 365 security center is configured with Azure Active Directory global roles or by using custom roles. Para Defender para endpoint, vea [Asignar acceso de usuario al Centro de seguridad de Microsoft Defender.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/assign-portal-access) Para Defender para Office 365, vea Permisos en el Centro de cumplimiento de Microsoft 365 y el Centro de seguridad [de Microsoft 365.](../office-365-security/permissions-microsoft-365-compliance-security.md)

- Obtenga más información sobre cómo [administrar el acceso a Microsoft 365 Defender](mtp-permissions.md)
- Obtenga más información sobre cómo [crear roles personalizados en](custom-roles.md) el Centro de seguridad de Microsoft 365

### <a name="integrated-reports"></a>Informes integrados

Los informes también se unificados en el Centro de seguridad de Microsoft 365. Los administradores pueden empezar con un informe de seguridad general y crear informes específicos sobre los puntos de conexión, el correo electrónico & colaboración. Los vínculos aquí se generan dinámicamente en función de la configuración de la carga de trabajo.

### <a name="quickly-view-your-microsoft-365-environment"></a>Ver rápidamente el entorno de Microsoft 365

La **página** principal muestra muchas de las tarjetas comunes que necesitan los equipos de seguridad. La composición de tarjetas y datos depende del rol de usuario. Dado que el Centro de seguridad de Microsoft 365 usa el control de acceso basado en roles, los distintos roles verán tarjetas que son más significativas para sus trabajos diarios.  

Esta información de un vistazo le ayuda a mantenerse al día con las actividades más recientes de su organización. El Centro de seguridad de Microsoft 365 reúne señales de diferentes orígenes para presentar una vista holística de su entorno de Microsoft 365.

Las tarjetas entran en estas categorías:

- **Identidades:** supervise las identidades de su organización y realice un seguimiento de los comportamientos sospechosos o de riesgo. [Obtenga más información sobre la protección de identidades.](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)
- **Datos:** ayude a realizar un seguimiento de la actividad del usuario que podría dar lugar a la divulgación de datos no autorizados.
- **Dispositivos:** obtenga información actualizada sobre alertas, actividad de infracciones y otras amenazas en sus dispositivos.
- **Aplicaciones:** obtenga información sobre cómo se usan las aplicaciones en la nube en su organización. [Obtenga más información sobre las aplicaciones detectadas de Cloud App Security.](https://docs.microsoft.com/cloud-app-security/discovered-apps)

## <a name="threat-analytics-with-better-data-coverage"></a>Análisis de amenazas con mejor cobertura de datos
Realice un seguimiento y responda a las amenazas emergentes con la siguiente experiencia integrada de análisis de amenazas de Microsoft 365 Defender:

- Mejor cobertura de datos entre Microsoft Defender para Endpoint y Microsoft Defender para Office 365, lo que permite la administración de incidentes combinada, la investigación automática, la corrección y la búsqueda proactiva o reactiva de amenazas en todo el dominio. 
- Detecciones y mitigaciones relacionadas con el correo electrónico de Microsoft Defender para Office 365, además de los datos del punto de conexión ya disponibles en Microsoft Defender para Endpoint.
- Una vista de incidentes relacionados con amenazas que agregan alertas en casos de ataques de un extremo a otro en Microsoft Defender para Endpoint y Microsoft Defender para Office 365 para reducir la cola de trabajo, así como simplificar y acelerar la investigación.
- Intentos de ataque detectados y bloqueados por soluciones de Microsoft 365 Defender. También hay datos que puedes usar para impulsar acciones preventivas que mitigan el riesgo de una mayor exposición y aumentan la resistencia. 
- Diseño mejorado que coloca la información que requiere acción en el punto de mira para ayudarle a identificar rápidamente los datos para centrarse, investigar y aprovechar de forma urgente los informes.

## <a name="a-centralized-learning-hub"></a>Un centro de aprendizaje centralizado

El Centro de seguridad de Microsoft 365 incluye un centro de aprendizaje que ofrece instrucciones oficiales de recursos como el blog de seguridad de Microsoft, la comunidad de seguridad de Microsoft en YouTube y la documentación oficial en docs.microsoft.com.

Dentro del centro de aprendizaje, las instrucciones de colaboración de & de correo electrónico (Microsoft Defender para Office 365 o MDO) están en paralelo con Endpoint (Microsoft Defender para Endpoint o MDE) y los recursos de aprendizaje de Microsoft 365 Defender.

El centro de aprendizaje se abre con rutas de aprendizaje organizadas en torno a temas como "¿Cómo investigar usando Microsoft 365 Defender?". y "Procedimientos recomendados de Microsoft Defender para Office 365". Actualmente, esta sección está a cargo del grupo de productos de seguridad de Microsoft. Cada ruta de aprendizaje refleja un tiempo proyectado que se tarda en pasar por los conceptos. For example 'Steps to take when a Microsoft Defender for Office 365 user account is compromised' is projected to take 8 minutes, and is valuable learning on the fly.

Después de hacer clic en el contenido, puede resultar útil marcar este sitio y organizar los marcadores en una carpeta "Seguridad" o "Crítica". Para ver todas las rutas de aprendizaje, haga clic en el vínculo Mostrar todo en el panel principal.

> [!NOTE]
> Hay filtros  útiles en la parte superior del centro de aprendizaje del Centro de seguridad de Microsoft 365 que le permitirán elegir entre productos (actualmente Microsoft 365 Defender, Microsoft Defender para Endpoint y Microsoft Defender para Office 365). Observe que se muestra el número de recursos de aprendizaje para cada sección, lo que puede ayudar a los alumnos a realizar un seguimiento de cuántos recursos tienen a mano para el aprendizaje y el aprendizaje.
>
> Junto con el filtro producto, se enumeran los temas actuales, los tipos de recursos (desde vídeos a seminarios web), los niveles de familiaridad o experiencia con las áreas de seguridad, los roles de seguridad y las características del producto.

## <a name="send-us-your-feedback"></a>Envíenos sus comentarios

Necesitamos sus comentarios. We're always looking to improve, so if there's something you'd like to see, [send us your Microsoft 365 Defender feedback](https://www.microsoft.com/videoplayer/embed/RE4K5Ci).

También puede dejar comentarios de este artículo. En la sección "Comentarios" al final de "Enviar y ver comentarios para", las opciones son *Este* producto o *Esta página.*

Usa el **botón Este producto para** obtener información sobre *el* producto:

1. Seleccione *este producto* en la parte inferior del artículo.
    1. Haga clic con el botón secundario en el botón y "Abrir en una pestaña nueva" si desea seguir leyendo estas instrucciones.
2. Esto navegará al foro **de UserVoice.**
3. Tiene 2 opciones:
    1. Desplácese hacia abajo hasta el cuadro de texto ¿Cómo podemos mejorar el cumplimiento o proteger mejor a los usuarios en *Office 365?* y pegue en el Centro de seguridad de *Microsoft 365.* Puede buscar en los resultados una idea como la suya y votarla o usar el botón para publicar **una nueva idea.**
    1. Si estás seguro de que este problema ya está notificado y quieres elevar  su perfil con un voto (o votos), usa el cuadro Enviar comentarios a la derecha de UserVoice. Busque el *Centro de seguridad de Microsoft 365,* busque el problema y use el botón de **voto** para aumentar su estado.

Use *esta página para* obtener comentarios sobre el propio artículo. Gracias por sus comentarios. Su voz nos ayuda a mejorar los productos.

### <a name="explore-what-the-security-center-has-to-offer"></a>Explorar lo que el centro de seguridad tiene que ofrecer

Siga explorando las características y capacidades del Centro de seguridad de Microsoft 365:

- [Administrar incidentes y alertas](manage-incidents.md)
- [Realizar un seguimiento y responder a las amenazas emergentes con análisis de amenazas](threat-analytics.md)
- [El centro de actividades](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [Búsqueda de amenazas en dispositivos, correos electrónicos, aplicaciones e identidades](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-query-emails-devices)
- [Reglas de detección personalizadas](https://docs.microsoft.com/microsoft-365/security/mtp/custom-detection-rules)
- [Alertas de colaboración & correo electrónico](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies)
- [Crear una simulación de ataques de suplantación de identidad (phishing)](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulation-training) y [crear una carga útil para formar a los equipos](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulation-training-payloads)
 
### <a name="related-information"></a>Información relacionada
- [Centro de seguridad de Microsoft 365](overview-security-center.md)
- [Microsoft Defender para Office 365 en el Centro de seguridad de Microsoft 365](microsoft-365-security-center-mdo.md)
- [Microsoft Defender para puntos de conexión en el Centro de seguridad de Microsoft 365](microsoft-365-security-center-mde.md)
- [Redirigir cuentas de Microsoft Defender para Endpoint al Centro de seguridad de Microsoft 365](microsoft-365-security-mde-redirection.md)
