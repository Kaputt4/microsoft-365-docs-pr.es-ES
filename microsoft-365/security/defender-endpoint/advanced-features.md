---
title: Configuración de características avanzadas en Microsoft Defender para punto de conexión
description: Active características avanzadas, como el archivo de bloque en Microsoft Defender para punto de conexión.
keywords: características avanzadas, configuración, archivo de bloque, investigación automatizada, resolución automática, skype, microsoft defender for identity, office 365, azure information protection, intune
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
ms.openlocfilehash: 5d1aea5fe5d8d1baaae3f616137f23dd93714f95
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67679655"
---
# <a name="configure-advanced-features-in-defender-for-endpoint"></a>Configuración de características avanzadas en Defender para punto de conexión

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-advancedfeats-abovefoldlink)

En función de los productos de seguridad de Microsoft que use, es posible que haya algunas características avanzadas disponibles para integrar Defender para punto de conexión con .

## <a name="enable-advanced-features"></a>Habilitación de características avanzadas

1. En el panel de navegación, seleccione **Configuración** \> **Puntos de conexión** **Características avanzadas**\>.
2. Seleccione la característica avanzada que desea configurar y cambie la configuración entre **Activado** y **Desactivado**.
3. Haga clic en **Guardar preferencias**.

Use las siguientes características avanzadas para protegerse mejor frente a archivos potencialmente malintencionados y obtener una mejor información durante las investigaciones de seguridad.

## <a name="automated-investigation"></a>Investigación automatizada

Active esta característica para aprovechar las características automatizadas de investigación y corrección del servicio. Para obtener más información, consulte [Investigación automatizada](automated-investigations.md).

## <a name="live-response"></a>Respuesta inmediata

> [!NOTE]
> La respuesta dinámica requiere que la **investigación automatizada** esté activada para poder habilitarla en la sección configuración avanzada del portal de Microsoft Defender para punto de conexión.

Active esta característica para que los usuarios con los permisos adecuados puedan iniciar una sesión de respuesta en vivo en los dispositivos.

Para obtener más información sobre las asignaciones de roles, consulte [Creación y administración de roles](user-roles.md).

## <a name="live-response-for-servers"></a>Respuesta dinámica para servidores

Active esta característica para que los usuarios con los permisos adecuados puedan iniciar una sesión de respuesta activa en los servidores.

Para obtener más información sobre las asignaciones de roles, consulte [Creación y administración de roles](user-roles.md).

## <a name="live-response-unsigned-script-execution"></a>Ejecución de script sin signo de respuesta dinámica

La habilitación de esta característica le permite ejecutar scripts sin firmar en una sesión de respuesta en directo.

## <a name="always-remediate-pua"></a>Corrección siempre de PUA

Las aplicaciones potencialmente no deseadas (PUA) son una categoría de software que puede hacer que el equipo se ejecute lentamente, mostrar anuncios inesperados o, en el peor de los casos, instalar otro software, que podría ser inesperado o no deseado.

Active esta característica para que las aplicaciones potencialmente no deseadas (PUA) se corrijan en todos los dispositivos del inquilino, incluso si la protección pua no está configurada en los dispositivos. Esta activación de la característica ayuda a proteger a los usuarios de la instalación involuntaria de aplicaciones no deseadas en su dispositivo. Cuando se desactiva, la corrección depende de la configuración del dispositivo.

## <a name="restrict-correlation-to-within-scoped-device-groups"></a>Restricción de la correlación a dentro de grupos de dispositivos con ámbito

Esta configuración se puede usar para escenarios en los que las operaciones soc locales desean limitar las correlaciones de alertas solo a los grupos de dispositivos a los que pueden acceder. Al activar esta configuración, un incidente compuesto por alertas de que los grupos entre dispositivos ya no se considerarán un único incidente. A continuación, el SOC local puede tomar medidas sobre el incidente porque tienen acceso a uno de los grupos de dispositivos implicados. Sin embargo, soc global verá varios incidentes diferentes por grupo de dispositivos en lugar de un incidente. No se recomienda activar esta configuración a menos que hacerlo supere las ventajas de la correlación de incidentes en toda la organización.

> [!NOTE]
> Cambiar esta configuración afecta solo a las correlaciones de alertas futuras.

## <a name="enable-edr-in-block-mode"></a>Habilitación de EDR en modo de bloque

La detección y respuesta de puntos de conexión (EDR) en modo de bloque proporciona protección contra artefactos malintencionados, incluso cuando el Antivirus de Microsoft Defender se ejecuta en modo pasivo. Cuando está activado, EDR en modo de bloque bloquea los artefactos malintencionados o los comportamientos detectados en un dispositivo. EDR en modo de bloque funciona en segundo plano para corregir artefactos malintencionados que se detectan después de la infracción.

## <a name="autoresolve-remediated-alerts"></a>Alertas corregidas de Autoresolve

En el caso de los inquilinos creados en o después de Windows 10, versión 1809, la funcionalidad de investigación y corrección automatizada se configura de forma predeterminada para resolver alertas en las que el estado del resultado del análisis automatizado es "No se encontraron amenazas" o "Corregidos". Si no desea que las alertas se resuelvan automáticamente, deberá desactivar manualmente la característica.

> [!TIP]
> En el caso de los inquilinos creados antes de esa versión, deberá activar manualmente esta característica desde la página [Características avanzadas](https://security.microsoft.com//preferences2/integration) .

> [!NOTE]
>
> - El resultado de la acción de resolución automática puede influir en el cálculo del nivel de riesgo del dispositivo, que se basa en las alertas activas que se encuentran en un dispositivo.
> - Si un analista de operaciones de seguridad establece manualmente el estado de una alerta en "En curso" o "Resuelto", la funcionalidad de resolución automática no la sobrescribirá.

## <a name="allow-or-block-file"></a>Permitir o bloquear el archivo

El bloqueo solo está disponible si su organización cumple estos requisitos:

- Usa antivirus de Microsoft Defender como solución antimalware activa y,
- La característica de protección basada en la nube está habilitada

Esta característica le permite bloquear archivos potencialmente malintencionados en la red. El bloqueo de un archivo impedirá que se lea, escriba o ejecute en dispositivos de la organización.

Para activar **Permitir o bloquear** archivos:

1. En el panel de navegación, seleccione **Configuración** \> **Puntos de conexión** **Características** \> avanzadas \> **generales** \> **Permitir o bloquear el archivo**.

1. Cambie la configuración entre **Activado** y **Desactivado**.
 
    :::image type="content" source="../../media/alloworblockfile.png" alt-text="Pantalla Puntos de conexión" lightbox="../../media/alloworblockfile.png":::

1. Seleccione **Guardar preferencias** en la parte inferior de la página.

Después de activar esta característica, puede [bloquear archivos](respond-file-alerts.md#allow-or-block-file) a través de la pestaña **Agregar indicador** de la página de perfil de un archivo.

## <a name="custom-network-indicators"></a>Indicadores de red personalizados

Activar esta característica le permite crear indicadores para direcciones IP, dominios o direcciones URL, que determinan si se permitirán o bloquearán en función de la lista de indicadores personalizados.

Para usar esta característica, los dispositivos deben ejecutar Windows 10 versión 1709 o posterior, o Windows 11. También deben tener protección de red en modo de bloque y versión 4.18.1906.3 o posterior de la plataforma antimalware [, consulte KB 4052623](https://go.microsoft.com/fwlink/?linkid=2099834).

Para obtener más información, vea [Administrar indicadores](manage-indicators.md).

> [!NOTE]
> La protección de red aprovecha los servicios de reputación que procesan solicitudes en ubicaciones que podrían estar fuera de la ubicación que ha seleccionado para los datos de Defender para punto de conexión.

## <a name="tamper-protection"></a>Protección contra alteraciones
Durante algunos tipos de ciberataques, los actores malintencionados intentan deshabilitar las características de seguridad, como la protección antivirus, en las máquinas. A los actores incorrectos les gusta deshabilitar las características de seguridad para obtener un acceso más fácil a los datos, para instalar malware o para aprovechar los datos, la identidad y los dispositivos.

La protección contra alteraciones básicamente bloquea el Antivirus de Microsoft Defender e impide que la configuración de seguridad se cambie a través de aplicaciones y métodos.

Esta característica está disponible si su organización usa el Antivirus de Microsoft Defender y la protección basada en la nube está habilitada. Para obtener más información, consulte [Uso de tecnologías de última generación en antivirus de Microsoft Defender mediante la protección proporcionada en la nube](cloud-protection-microsoft-defender-antivirus.md).

Mantenga activada la protección contra alteraciones para evitar cambios no deseados en la solución de seguridad y sus características esenciales.

## <a name="show-user-details"></a>Mostrar los detalles del usuario

Active esta característica para que pueda ver los detalles del usuario almacenados en Azure Active Directory. Los detalles incluyen la información de imagen, nombre, título y departamento de un usuario al investigar entidades de cuenta de usuario. Puede encontrar información de la cuenta de usuario en las vistas siguientes:

- Panel de operaciones de seguridad
- Cola de alertas
- Página de detalles del dispositivo

Para obtener más información, vea [Investigar una cuenta de usuario](investigate-user.md).

## <a name="skype-for-business-integration"></a>integración Skype Empresarial

La habilitación de la integración Skype Empresarial le permite comunicarse con los usuarios mediante Skype Empresarial, correo electrónico o teléfono. Esta activación puede ser útil cuando necesite comunicarse con el usuario y mitigar los riesgos.

> [!NOTE]
> Cuando un dispositivo se aísla de la red, hay un elemento emergente en el que puede optar por habilitar las comunicaciones de Outlook y Skype que permiten las comunicaciones con el usuario mientras están desconectados de la red. Esta configuración se aplica a la comunicación de Skype y Outlook cuando los dispositivos están en modo de aislamiento.

## <a name="microsoft-defender-for-identity-integration"></a>integración Microsoft Defender for Identity

La integración con Microsoft Defender for Identity permite dinamizar directamente en otro producto de seguridad de Microsoft Identity. Microsoft Defender for Identity aumenta una investigación con más información sobre una cuenta en peligro sospechosa y recursos relacionados. Al habilitar esta característica, enriquecerá la funcionalidad de investigación basada en dispositivos mediante la dinamización a través de la red desde un punto de vista de identificación.

> [!NOTE]
> Tendrá que tener la licencia adecuada para habilitar esta característica.

## <a name="office-365-threat-intelligence-connection"></a>Office 365 conexión de Inteligencia sobre amenazas

Esta característica solo está disponible si tiene un Office 365 E5 activo o el complemento Threat Intelligence. Para obtener más información, consulte la página del producto Office 365 Enterprise E5.

Al activar esta característica, podrá incorporar datos de Microsoft Defender para Office 365 en Microsoft 365 Defender para llevar a cabo una investigación de seguridad completa en los buzones de Office 365 y dispositivos Windows.

> [!NOTE]
> Tendrá que tener la licencia adecuada para habilitar esta característica.

Para recibir la integración contextual de dispositivos en Office 365 Threat Intelligence, deberá habilitar la configuración de Defender para punto de conexión en el panel Seguridad & cumplimiento. Para obtener más información, consulte [Investigación y respuesta de amenazas](/microsoft-365/security/office-365-security/office-365-ti).

## <a name="microsoft-threat-experts---targeted-attack-notifications"></a>Expertos en amenazas de Microsoft: notificaciones de ataque dirigidas

De los dos componentes de Microsoft Threat Expert, la notificación de ataque dirigida está en disponibilidad general. La funcionalidad expertos a petición todavía está en versión preliminar. Solo puede usar la funcionalidad expertos a petición si ha solicitado la versión preliminar y la aplicación se ha aprobado. Puede recibir notificaciones de ataque dirigidas desde Expertos en amenazas de Microsoft a través del panel de alertas del portal de Defender para punto de conexión y por correo electrónico si lo configura.

> [!NOTE]
> La funcionalidad Expertos en amenazas de Microsoft de Defender para punto de conexión está disponible con una licencia E5 para [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security).

## <a name="microsoft-defender-for-cloud-apps"></a>Microsoft Defender for Cloud Apps

Al habilitar esta configuración se reenvía las señales de Defender para punto de conexión a Microsoft Defender for Cloud Apps para proporcionar una visibilidad más profunda del uso de aplicaciones en la nube. Los datos reenviados se almacenan y procesan en la misma ubicación que los datos de Defender for Cloud Apps.

> [!NOTE]
> Esta característica estará disponible con una licencia E5 para [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) en dispositivos que ejecutan Windows 10, versión 1709 (compilación del sistema operativo 16299.1085 con [KB4493441](https://support.microsoft.com/help/4493441)), Windows 10, versión 1803 (compilación del sistema operativo 17134.704 con [KB4493464](https://support.microsoft.com/help/4493464)), Windows 10, versión 1809  (Compilación del sistema operativo 17763.379 con [KB4489899](https://support.microsoft.com/help/4489899)), versiones posteriores Windows 10 o Windows 11.

### <a name="enable-the-microsoft-defender-for-endpoint-integration-from-the-microsoft-defender-for-identity-portal"></a>Habilitación de la integración de Microsoft Defender para punto de conexión desde el portal de Microsoft Defender for Identity

Para recibir la integración contextual de dispositivos en Microsoft Defender for Identity, también deberá habilitar la característica en el portal de Microsoft Defender for Identity.

1. Inicie sesión en el [portal de Microsoft Defender for Identity](https://portal.atp.azure.com/) con un rol administrador global o administrador de seguridad.

2. Haga clic en **Crear instancia**.

3. Cambie la configuración de integración a **Activado** y haga clic en **Guardar**.

Después de completar los pasos de integración en ambos portales, podrá ver las alertas pertinentes en la página de detalles del dispositivo o de los detalles del usuario.

## <a name="web-content-filtering"></a>Filtrado de contenido web

Bloquear el acceso a sitios web que contienen contenido no deseado y realizar un seguimiento de la actividad web en todos los dominios. Para especificar las categorías de contenido web que desea bloquear, cree una [directiva de filtrado de contenido web](https://security.microsoft.com/preferences2/web_content_filtering_policy). Asegúrese de que tiene protección de red en modo de bloque al implementar la [línea base de seguridad Microsoft Defender para punto de conexión](https://devicemanagement.microsoft.com/#blade/Microsoft_Intune_Workflows/SecurityBaselineSummaryMenu/overview/templateType/2).

## <a name="share-endpoint-alerts-with-microsoft-purview-compliance-portal"></a>Compartir alertas de punto de conexión con portal de cumplimiento Microsoft Purview

Reenvía las alertas de seguridad del punto de conexión y su estado de evaluación de prioridades a portal de cumplimiento Microsoft Purview, lo que le permite mejorar las directivas de administración de riesgos internos con alertas y corregir los riesgos internos antes de que causen daños. Los datos reenviados se procesan y almacenan en la misma ubicación que los datos de Office 365.

Después de configurar los [indicadores de infracción de directivas de seguridad](/microsoft-365/compliance/insider-risk-management-settings#indicators) en la configuración de administración de riesgos internos, las alertas de Defender para punto de conexión se compartirán con la administración de riesgos internos para los usuarios aplicables.

## <a name="authenticated-telemetry"></a>Telemetría autenticada

Puede **activar la** telemetría autenticada para evitar la suplantación de telemetría en el panel.

## <a name="microsoft-intune-connection"></a>conexión Microsoft Intune

Defender for Endpoint se puede integrar con [Microsoft Intune](/intune/what-is-intune) para habilitar el [acceso condicional basado en riesgos del dispositivo](/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune). Al [activar esta característica](configure-conditional-access.md), podrá compartir la información del dispositivo de Defender para punto de conexión con Intune, lo que mejorará la aplicación de directivas.

> [!IMPORTANT]
> Tendrá que habilitar la integración en Intune y Defender para punto de conexión para usar esta característica. Para obtener más información sobre pasos específicos, vea [Configurar el acceso condicional en Defender para punto de conexión](configure-conditional-access.md).

Esta característica solo está disponible si tiene los siguientes requisitos previos:

- Un inquilino con licencia para Enterprise Mobility + Security E3 y Windows E5 (o Microsoft 365 Enterprise E5)
- Un entorno de Microsoft Intune activo, con dispositivos Windows administrados por Intune [unidos a Azure AD](/azure/active-directory/devices/concept-azure-ad-join/).

### <a name="conditional-access-policy"></a>Directiva de acceso condicional

Al habilitar Intune integración, Intune creará automáticamente una directiva de acceso condicional (CA) clásica. Esta directiva de CA clásica es un requisito previo para configurar informes de estado para Intune. No se debe eliminar.

> [!NOTE]
> La directiva de CA clásica creada por Intune es distinta de [las directivas](/azure/active-directory/conditional-access/overview/) modernas de acceso condicional, que se usan para configurar puntos de conexión.

## <a name="device-discovery"></a>Detección de dispositivo

Ayuda a encontrar dispositivos no administrados conectados a la red corporativa sin necesidad de dispositivos adicionales ni cambios en los procesos engorrosos. Con los dispositivos incorporados, puede encontrar dispositivos no administrados en la red y evaluar vulnerabilidades y riesgos. Para obtener más información, consulte [Detección de dispositivos](device-discovery.md).

> [!NOTE]
> Siempre puede aplicar filtros para excluir dispositivos no administrados de la lista de inventario de dispositivos. También puede usar la columna de estado de incorporación en consultas de API para filtrar dispositivos no administrados.

## <a name="preview-features"></a>Vista previa de las características

Obtenga información sobre las nuevas características en la versión preliminar de Defender para punto de conexión. Pruebe las próximas características activando la experiencia de vista previa.

Tendrá acceso a las próximas características, en las que puede proporcionar comentarios para ayudar a mejorar la experiencia general antes de que las características estén disponibles con carácter general.

## <a name="download-quarantined-files"></a>Descarga de archivos en cuarentena

Haga una copia de seguridad de los archivos en cuarentena en una ubicación segura y compatible para que se puedan descargar directamente desde la cuarentena. El botón **Descargar archivo** siempre estará disponible en la página de archivos. Esta configuración está activada de forma predeterminada. [Más información sobre los requisitos](respond-file-alerts.md#download-quarantined-files)

## <a name="related-topics"></a>Temas relacionados

- [Actualización de la configuración de retención de datos](data-retention-settings.md)
- [Configurar notificaciones de alerta](configure-email-notifications.md)
