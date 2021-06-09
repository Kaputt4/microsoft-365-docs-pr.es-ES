---
title: Configurar características avanzadas en Microsoft Defender para endpoint
description: Activa las características avanzadas, como el archivo de bloqueo en Microsoft Defender para endpoint.
keywords: características avanzadas, configuración, archivo de bloqueo, investigación automatizada, resolución automática, skype, microsoft defender para la identidad, office 365, azure information protection, intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 7fd9ec25c21b2d70238bd5b0d6b58b60731088ea
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845479"
---
# <a name="configure-advanced-features-in-defender-for-endpoint"></a>Configurar características avanzadas en Defender para endpoint

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


> ¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedfeats-abovefoldlink)

Según los productos de seguridad de Microsoft que use, algunas características avanzadas podrían estar disponibles para integrar Defender for Endpoint con.

## <a name="enable-advanced-features"></a>Habilitar características avanzadas

1. En el panel de navegación, seleccione **Configuración de**  >  **preferencias Características avanzadas**.
2. Seleccione la característica avanzada que desea configurar y alternar la configuración entre **On** y **Off**.
3. Haga clic **en Guardar preferencias**.

Use las siguientes características avanzadas para protegerse mejor de los archivos potencialmente malintencionados y obtener una mejor información durante las investigaciones de seguridad.

## <a name="automated-investigation"></a>Investigación automatizada

Active esta característica para aprovechar las características automatizadas de investigación y corrección del servicio. Para obtener más información, vea [Investigación automatizada](automated-investigations.md).

## <a name="live-response"></a>Respuesta en directo

Active esta característica para que los usuarios con los permisos adecuados puedan iniciar una sesión de respuesta en directo en dispositivos.

Para obtener más información acerca de las asignaciones de roles, vea [Create and manage roles](user-roles.md).

## <a name="live-response-for-servers"></a>Respuesta en directo para servidores
Active esta característica para que los usuarios con los permisos adecuados puedan iniciar una sesión de respuesta en directo en los servidores.

Para obtener más información acerca de las asignaciones de roles, vea [Create and manage roles](user-roles.md).


## <a name="live-response-unsigned-script-execution"></a>Ejecución de script sin signo de respuesta en directo

Habilitar esta característica permite ejecutar scripts sin signo en una sesión de respuesta en directo.

## <a name="always-remediate-pua"></a>Corregir siempre la PUA
Las aplicaciones potencialmente no deseadas (PUA) son una categoría de software que puede hacer que el equipo se ejecute lentamente, muestre anuncios inesperados o, en el peor de los casos, instale otro software que pueda ser inesperado o no deseado. 

Active esta característica para que las aplicaciones potencialmente no deseadas (PUA) se corrija en todos los dispositivos del espacio empresarial, incluso si la protección pua no está configurada en los dispositivos. Esto ayudará a proteger a los usuarios de la instalación involuntaria de aplicaciones no deseadas en su dispositivo. Cuando está desactivada, la corrección depende de la configuración del dispositivo. 


## <a name="restrict-correlation-to-within-scoped-device-groups"></a>Restringir la correlación a grupos de dispositivos con ámbito
Esta configuración se puede usar para escenarios en los que las operaciones SOC locales quisieran limitar las correlaciones de alertas solo a los grupos de dispositivos a los que pueden tener acceso. Al activar esta configuración, un incidente compuesto por alertas que se cruzan entre grupos de dispositivos ya no se considerará un solo incidente. A continuación, el SOC local puede tomar medidas sobre el incidente porque tienen acceso a uno de los grupos de dispositivos implicados. Sin embargo, soc global verá varios incidentes diferentes por grupo de dispositivos en lugar de un incidente. No recomendamos activar esta configuración a menos que esto supere las ventajas de la correlación de incidentes en toda la organización
>[!NOTE]
>Cambiar esta configuración afecta solo a las correlaciones futuras de alertas.

## <a name="enable-edr-in-block-mode"></a>Habilitar EDR en modo de bloque
La detección y respuesta de puntos de conexión (EDR) en modo de bloqueo proporciona protección contra artefactos malintencionados, incluso cuando Antivirus de Microsoft Defender se ejecuta en modo pasivo. Cuando está activado, EDR en modo de bloqueo bloquea los artefactos o comportamientos malintencionados que se detectan en un dispositivo. EDR en modo de bloqueo funciona en segundo plano para corregir artefactos malintencionados detectados después de la infracción.


## <a name="autoresolve-remediated-alerts"></a>Alertas remediadas de Autoresolve

Para los inquilinos creados en o después de Windows 10, versión 1809, la funcionalidad de investigación y corrección automatizada se configura de forma predeterminada para resolver alertas en las que el estado del resultado del análisis automatizado es "No se encontraron amenazas" o "Corregido".  Si no quieres que las alertas se resuelvan automáticamente, tendrás que desactivar manualmente la característica.

> [!TIP]
> Para los inquilinos creados antes de esa versión, deberá activar manualmente esta característica desde la [página Características avanzadas.](https://securitycenter.windows.com/preferences2/integration)

> [!NOTE]
>
> - El resultado de la acción de resolución automática puede influir en el cálculo del nivel de riesgo del dispositivo, que se basa en las alertas activas encontradas en un dispositivo.
> - Si un analista de operaciones de seguridad establece manualmente el estado de una alerta en "En curso" o "Resuelto", la funcionalidad de resolución automática no la sobrescribirá.

## <a name="allow-or-block-file"></a>Permitir o bloquear archivo

El bloqueo solo está disponible si su organización cumple estos requisitos:

- Usa Antivirus de Microsoft Defender como la solución antimalware activa y,
- La característica de protección basada en la nube está habilitada

Esta característica permite bloquear archivos potencialmente malintencionados en la red. El bloqueo de un archivo impedirá que se lea, se escriba o se ejecute en dispositivos de la organización.

Para activar **Permitir o bloquear** archivos:

1. En el panel de navegación, **seleccione Configuración**  >  **Características avanzadas** Permitir o bloquear  >  **archivo**.

1. Alterna la configuración entre **On** y **Off**.

    ![Imagen de la configuración avanzada para la característica de archivo de bloqueo](images/atp-preferences-setup.png)

1. Seleccione **Guardar preferencias** en la parte inferior de la página.

Después de activar esta característica, puede [bloquear archivos a través](respond-file-alerts.md#allow-or-block-file) de la pestaña Agregar **indicador** en la página de perfil de un archivo.

## <a name="custom-network-indicators"></a>Indicadores de red personalizados

Activar esta característica permite crear indicadores para direcciones IP, dominios o direcciones URL, que determinan si se permitirán o bloquearán en función de la lista de indicadores personalizada.

Para usar esta característica, los dispositivos deben ejecutarse Windows 10 versión 1709 o posterior. También deben tener protección de red en modo de bloqueo y versión 4.18.1906.3 o posterior de la plataforma antimalware, vea [KB 4052623](https://go.microsoft.com/fwlink/?linkid=2099834).

Para obtener más información, vea [Administrar indicadores](manage-indicators.md).

> [!NOTE]
> La protección de red aprovecha los servicios de reputación que procesan solicitudes en ubicaciones que podrían estar fuera de la ubicación seleccionada para los datos de Defender para endpoint.

## <a name="tamper-protection"></a>Protección contra alteraciones
Durante algunos tipos de ataques cibernéticos, los actores malos intentan deshabilitar las características de seguridad, como la protección antivirus, en las máquinas. A los actores malintencionados les gusta deshabilitar las características de seguridad para obtener un acceso más fácil a los datos, para instalar malware o para aprovechar sus datos, identidades y dispositivos.

La protección contra alteraciones bloquea Antivirus de Microsoft Defender y evita que se cambie la configuración de seguridad a través de aplicaciones y métodos.

Esta característica está disponible si su organización usa Antivirus de Microsoft Defender y la protección basada en la nube está habilitada. Para obtener más información, vea [Use next-generation technologies in Antivirus de Microsoft Defender through cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md).

Mantenga activada la protección contra alteraciones para evitar cambios no deseados en la solución de seguridad y sus características esenciales.


## <a name="show-user-details"></a>Mostrar detalles de usuario

Active esta característica para que pueda ver los detalles del usuario almacenados en Azure Active Directory. Los detalles incluyen la imagen, el nombre, el título y la información del departamento de un usuario al investigar entidades de cuenta de usuario. Puede encontrar información de cuenta de usuario en las siguientes vistas:

- Panel de operaciones de seguridad
- Cola de alertas
- Página de detalles del dispositivo

Para obtener más información, vea [Investigar una cuenta de usuario](investigate-user.md).


## <a name="skype-for-business-integration"></a>Skype Empresarial integración

La habilitación Skype Empresarial integración le permite comunicarse con los usuarios mediante Skype Empresarial, correo electrónico o teléfono. Esto puede ser útil cuando necesita comunicarse con el usuario y mitigar los riesgos.

> [!NOTE]
> Cuando un dispositivo se aísla de la red, hay una ventana emergente donde puedes elegir habilitar las comunicaciones Outlook y Skype que permite las comunicaciones al usuario mientras se desconectan de la red. Esta configuración se aplica a Skype y Outlook comunicación cuando los dispositivos están en modo aislado.

## <a name="microsoft-defender-for-identity-integration"></a>Integración de Microsoft Defender para identidades

La integración con Microsoft Defender for Identity te permite pivotar directamente en otro producto de seguridad de Microsoft Identity. Microsoft Defender for Identity aumenta una investigación con información adicional sobre una cuenta comprometida sospechosa y recursos relacionados. Al habilitar esta característica, enriquecerás la funcionalidad de investigación basada en dispositivos al girar por la red desde un punto de vista de identificación.

> [!NOTE]
> Tendrás que tener la licencia adecuada para habilitar esta característica.

## <a name="office-365-threat-intelligence-connection"></a>Office 365 Conexión de inteligencia de amenazas

Esta característica solo está disponible si tiene un Office 365 E5 o el complemento de inteligencia de amenazas. Para obtener más información, vea la Office 365 Enterprise de producto de E5.

Al activar esta característica, podrás incorporar datos de Microsoft Defender para Office 365 en Centro de seguridad de Microsoft Defender para llevar a cabo una investigación de seguridad completa en buzones de correo Office 365 y dispositivos Windows.

> [!NOTE]
> Tendrás que tener la licencia adecuada para habilitar esta característica.

Para recibir la integración contextual de dispositivos en Office 365 inteligencia de amenazas, deberás habilitar la configuración de Defender para endpoints en el panel Seguridad & cumplimiento. Para obtener más información, vea [Threat investigation and response](/microsoft-365/security/office-365-security/office-365-ti).

## <a name="microsoft-threat-experts---targeted-attack-notifications"></a>Expertos en amenazas de Microsoft: notificaciones de ataque dirigido

De los dos componentes de Microsoft Threat Expert, la notificación de ataques dirigidos está en disponibilidad general. La funcionalidad de expertos a petición aún está en versión preliminar. Solo puede usar la funcionalidad de expertos a petición si ha solicitado una vista previa y la aplicación se ha aprobado. Puedes recibir notificaciones de ataques dirigidos desde Expertos en amenazas de Microsoft a través del panel de alertas del portal de defender para puntos de conexión y por correo electrónico si lo configuras.

> [!NOTE]
> La Expertos en amenazas de Microsoft de Defender for Endpoint está disponible con una licencia de E5 para [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security).
## <a name="microsoft-cloud-app-security"></a>Microsoft Cloud App Security

Al habilitar esta configuración, Defender para las señales de punto de conexión Microsoft Cloud App Security para proporcionar una mayor visibilidad del uso de aplicaciones en la nube. Los datos reenviados se almacenan y procesan en la misma ubicación que los Cloud App Security datos.

> [!NOTE]
> Esta característica estará disponible con una licencia E5 para [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) en dispositivos que ejecuten Windows 10, versión 1709 (compilación del sistema operativo 16299.1085 con [KB4493441](https://support.microsoft.com/help/4493441)), Windows 10, versión 1803 (compilación del sistema operativo 17134.704 con [KB4493464](https://support.microsoft.com/help/4493464)), Windows 10, versión 1809 (compilación del sistema operativo 17763.379 con [KB4489899),](https://support.microsoft.com/help/4489899)o versiones Windows 10 posteriores.

## <a name="microsoft-secure-score"></a>Puntuación de seguridad de Microsoft

Reenvía las señales de Punto de conexión de Microsoft Defender a Puntuación segura de Microsoft en el centro Microsoft 365 seguridad. Al activar esta característica, Microsoft Secure Score ofrece visibilidad sobre la posición de seguridad del dispositivo. Los datos reenviados se almacenan y procesan en la misma ubicación que los datos de puntuación segura de Microsoft.


### <a name="enable-the-microsoft-defender-for-endpoint-integration-from-the-microsoft-defender-for-identity-portal"></a>Habilitar la integración de Microsoft Defender para endpoints desde el portal de Microsoft Defender para identidades

Para recibir la integración contextual de dispositivos en Microsoft Defender for Identity, también tendrás que habilitar la característica en el portal de Microsoft Defender para identidad.

1. Inicie sesión en el [portal de Microsoft Defender para identidad](https://portal.atp.azure.com/) con un rol administrador global o administrador de seguridad.

2. Haga **clic en Crear la instancia**.

3. Alterna la configuración de integración a **Activar** y haz clic **en Guardar**.

Después de completar los pasos de integración en ambos portales, podrás ver alertas relevantes en la página detalles del dispositivo o detalles del usuario.

## <a name="web-content-filtering"></a>Filtrado de contenido web
Bloquear el acceso a sitios web que contengan contenido no deseado y realizar un seguimiento de la actividad web en todos los dominios. Para especificar las categorías de contenido web que desea bloquear, cree una [directiva de filtrado de contenido web](https://security.microsoft.com/preferences2/web_content_filtering_policy). Asegúrese de que tiene protección de red en modo de bloqueo al implementar la línea base de seguridad de [Microsoft Defender para](https://devicemanagement.microsoft.com/#blade/Microsoft_Intune_Workflows/SecurityBaselineSummaryMenu/overview/templateType/2)endpoints .


## <a name="share-endpoint-alerts-with-microsoft-compliance-center"></a>Compartir alertas de extremo con el Centro de cumplimiento de Microsoft
Reenvía las alertas de seguridad de puntos de conexión y su estado de evaluación al Centro de cumplimiento de Microsoft, lo que le permite mejorar las directivas de administración de riesgos internos con alertas y corregir los riesgos internos antes de que causen daños. Los datos reenviados se procesan y almacenan en la misma ubicación que los Office 365 datos.

Después de configurar los indicadores de infracción de directivas de seguridad en la configuración de administración de riesgos de insider, las [alertas](/microsoft-365/compliance/insider-risk-management-settings#indicators) de Defender for Endpoint se compartirán con la administración de riesgos de insider para los usuarios aplicables.



## <a name="microsoft-intune-connection"></a>Microsoft Intune conexión

Defender for Endpoint se puede integrar con [Microsoft Intune](/intune/what-is-intune) para habilitar el acceso condicional basado en riesgos [del dispositivo.](/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune) Al activar [esta característica,](configure-conditional-access.md)podrás compartir información de dispositivo defender para endpoint con Intune, lo que mejora la aplicación de directivas.

> [!IMPORTANT]
> Tendrás que habilitar la integración en Intune y Defender for Endpoint para usar esta característica. Para obtener más información sobre pasos específicos, vea [Configure Conditional Access in Defender for Endpoint](configure-conditional-access.md).

Esta característica solo está disponible si tiene lo siguiente:

- Un inquilino con licencia para Enterprise Mobility + Security E3 y Windows E5 (o Microsoft 365 Enterprise E5)
- Un entorno Microsoft Intune activo, con dispositivos administrados por Intune Windows 10 [unidos a Azure AD.](/azure/active-directory/devices/concept-azure-ad-join/)


### <a name="conditional-access-policy"></a>Directiva de acceso condicional

Al habilitar la integración de Intune, Intune creará automáticamente una directiva clásica de acceso condicional (CA). Esta directiva de ca clásica es un requisito previo para configurar informes de estado en Intune. No se debe eliminar.

> [!NOTE]
> La directiva de CA clásica creada por Intune es distinta de las directivas modernas de acceso [condicional,](/azure/active-directory/conditional-access/overview/)que se usan para configurar puntos de conexión.


## <a name="device-discovery"></a>Detección de dispositivo
Le ayuda a encontrar dispositivos no administrados conectados a la red corporativa sin necesidad de dispositivos adicionales o cambios de proceso engorrosos. Con dispositivos incorporados, puede encontrar dispositivos no administrados en la red y evaluar vulnerabilidades y riesgos. Para obtener más información, consulta [Detección de dispositivos](device-discovery.md).

> [!NOTE]
> Siempre puedes aplicar filtros para excluir dispositivos no administrados de la lista de inventario de dispositivos. También puede usar la columna de estado de incorporación en las consultas API para filtrar los dispositivos no administrados. 

## <a name="preview-features"></a>Versión preliminar de las características

Obtenga información sobre las nuevas características en la versión preliminar de Defender for Endpoint. Pruebe las próximas características al activar la experiencia de vista previa.

Tendrás acceso a las próximas características, sobre las que puedes proporcionar comentarios para ayudar a mejorar la experiencia general antes de que las características estén disponibles en general.




## <a name="related-topics"></a>Temas relacionados

- [Actualizar la configuración de retención de datos](data-retention-settings.md)
- [Configurar notificaciones de alerta](configure-email-notifications.md)
