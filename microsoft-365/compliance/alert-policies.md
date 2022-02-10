---
title: Microsoft 365 de alertas
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.custom:
- seo-marvel-apr2020
- admindeeplinkCOMPLIANCE
- admindeeplinkDEFENDER
description: Cree directivas de alerta en el Centro de cumplimiento de Microsoft 365 o en el portal de Microsoft 365 Defender para supervisar posibles amenazas, pérdida de datos y problemas de permisos.
ms.openlocfilehash: 9137c74cd2c32539a339a9cabc2d9f66f6923636
ms.sourcegitcommit: cafca45069819a44c7cf8c67f6c1e105de1b3393
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/10/2022
ms.locfileid: "62520492"
---
# <a name="alert-policies-in-microsoft-365"></a>Directivas de alerta en Microsoft 365

Puede usar directivas de alerta y el panel de alertas en el portal de Centro de cumplimiento de Microsoft 365 o Microsoft 365 Defender para crear directivas de alerta y, a continuación, ver las alertas generadas cuando los usuarios realizan actividades que coinciden con las condiciones de una directiva de alerta. Hay varias directivas de alerta predeterminadas que le ayudan a supervisar actividades como asignar privilegios de administrador en Exchange Online, ataques de malware, campañas de suplantación de identidad (phishing) y niveles inusuales de eliminaciones de archivos y uso compartido externo.

> [!TIP]
> Vaya a la [sección Directivas de alerta predeterminadas](#default-alert-policies) de este artículo para obtener una lista y una descripción de las directivas de alerta disponibles.

Las directivas de alerta le permiten clasificar las alertas que desencadena una directiva, aplicar la directiva a todos los usuarios de la organización, establecer un nivel de umbral para cuando se desencadena una alerta y decidir si se van a recibir notificaciones por correo electrónico cuando se desencadenan alertas. También hay una página De alertas en la que puede ver y filtrar alertas, establecer un estado de alerta para **ayudarle a administrar** alertas y, a continuación, descartar alertas después de haber resuelto o resuelto el incidente subyacente.

> [!NOTE]
> Las directivas de alerta están disponibles para organizaciones con una suscripción Microsoft 365 Enterprise, Office 365 Enterprise o Office 365 US Government E1/F1/G1, E3/F3/G3 o E5/G5. La funcionalidad avanzada solo está disponible para organizaciones con una suscripción A5/G5, o para organizaciones que tienen una suscripción E1/F1/G1 o E3/F3/G3 y Microsoft Defender para Office 365 P2 o Cumplimiento de Microsoft 365 E5 o una suscripción de complemento E5 eDiscovery and Audit. La funcionalidad que requiere una suscripción de E5/G5 o complemento se resalta en este tema. Tenga en cuenta también que las directivas de alerta están disponibles en Office 365 GCC, GCC entornos gubernamentales de Estados Unidos de Alta y DoD.

## <a name="how-alert-policies-work"></a>Cómo funcionan las directivas de alertas

Este es un resumen rápido de cómo funcionan las directivas de alertas y las alertas que se desencadenan cuando la actividad de usuario o administrador coincide con las condiciones de una directiva de alerta.

![Información general sobre cómo funcionan las directivas de alertas.](../media/M365ComplianceDefender-AlertPolicies-Overview.png)

1. Un administrador de la organización crea, configura y activa una directiva de alerta mediante la página Directivas de  alerta del portal de Centro de cumplimiento de Microsoft 365 o Microsoft 365 Defender alerta. También puede crear directivas de alerta mediante el cmdlet [New-ProtectionAlert en PowerShell](/powershell/module/exchange/new-protectionalert) del Centro de & seguridad.

   Para crear directivas de alerta, debe tener asignado el rol Administrar alertas o el rol Configuración de la organización en el Centro de cumplimiento de Microsoft 365 o el portal de Defender.

   > [!NOTE]
   > La directiva tarda hasta 24 horas después de crear o actualizar una directiva de alertas. Esto se debe a que la directiva debe sincronizarse con el motor de detección de alertas.

2. Un usuario realiza una actividad que coincide con las condiciones de una directiva de alerta. En el caso de ataques de malware, los mensajes de correo electrónico infectados enviados a los usuarios de la organización desencadenan una alerta.

3. Microsoft 365 genera una alerta que se muestra en la página Alertas de Centro de cumplimiento de Microsoft 365 portal  de Defender. Además, si las notificaciones por correo electrónico están habilitadas para la directiva de alerta, Microsoft envía una notificación a una lista de destinatarios. Las alertas que un administrador u otros usuarios pueden ver en la página Alertas están determinadas por los roles asignados al usuario. Para obtener más información, vea [RBAC permissions required to view alerts](#rbac-permissions-required-to-view-alerts).

4. Un administrador administra alertas en el centro de cumplimiento. La administración de alertas consiste en asignar un estado de alerta para ayudar a realizar un seguimiento y administrar cualquier investigación.

## <a name="alert-policy-settings"></a>Configuración de directiva de alerta

Una directiva de alerta consta de un conjunto de reglas y condiciones que definen la actividad de usuario o administrador que genera una alerta, una lista de usuarios que desencadenan la alerta si realizan la actividad y un umbral que define cuántas veces debe producirse la actividad antes de que se desencadene una alerta. También categoriza la directiva y le asigna un nivel de gravedad. Estas dos configuraciones le ayudan a administrar las directivas de alerta (y las alertas que se desencadenan cuando se cumplen las condiciones de la directiva) porque puede filtrar esta configuración al administrar directivas y ver alertas en el centro de cumplimiento. Por ejemplo, puede ver alertas que coincidan con las condiciones de la misma categoría o ver alertas con el mismo nivel de gravedad.

Para ver y crear directivas de alerta:

### <a name="microsoft-365-compliance-center"></a>Centro de cumplimiento de Microsoft 365

Vaya a la <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Centro de cumplimiento de Microsoft 365</a> y, a continuación, seleccione **DirectivasAlertAlert** >  >  **directivas**.

![En el Centro de cumplimiento, seleccione Directivas y, en Alerta, seleccione Directivas de alerta para ver y crear directivas de alerta.](../media/LaunchAlertPoliciesMCC.png)

### <a name="microsoft-365-defender-portal"></a>Portal de Microsoft 365 Defender

Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender y</a>, en **Correo & la** colaboración, seleccione **Directivas &** **rulesAlert** >  directiva. Como alternativa, puede ir directamente a <https://security.microsoft.com/alertpolicies>.

![En el portal de Defender, seleccione Directivas & reglas en Correo & colaboración y, a continuación, seleccione Directiva de alerta para ver y crear directivas de alerta.](../media/LaunchAlertPoliciesDefenderPortal.png)

> [!NOTE]
> Debe tener asignado el rol administrar View-Only alertas para ver las directivas de alerta en el centro de cumplimiento o el portal de Defender. Debe tener asignado el rol Administrar alertas para crear y editar directivas de alertas. Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).

Una directiva de alertas consta de las siguientes opciones de configuración y condiciones.

- **Actividad que la alerta está rastreando**. Se crea una directiva para realizar un seguimiento de una actividad o, en algunos casos, algunas actividades relacionadas, como compartir un archivo con un usuario externo al compartirlo, asignar permisos de acceso o crear un vínculo anónimo. Cuando un usuario realiza la actividad definida por la directiva, se desencadena una alerta en función de la configuración del umbral de alerta.

    > [!NOTE]
    > Las actividades que se pueden realizar dependen del plan de administración Office 365 Enterprise organización o Office 365 del Gobierno de Estados Unidos. En general, las actividades relacionadas con campañas de malware y ataques de suplantación de identidad requieren una suscripción E5/G5 o una suscripción E1/F1/G1 o E3/F3/G3 con una suscripción de complemento de [Defender for Office 365](../security/office-365-security/defender-for-office-365.md) Plan 2.

- **Condiciones de actividad**. Para la mayoría de las actividades, puede definir condiciones adicionales que deben cumplirse para desencadenar una alerta. Entre las condiciones comunes se incluyen las direcciones IP (de modo que se desencadena una alerta cuando el usuario realiza la actividad en un equipo con una dirección IP específica o dentro de un intervalo de direcciones IP), si se desencadena una alerta si un usuario o usuarios específicos realizan esa actividad y si la actividad se realiza en un nombre de archivo o dirección URL específicos. También puede configurar una condición que desencadena una alerta cuando cualquier usuario de la organización realiza la actividad. Las condiciones disponibles dependen de la actividad seleccionada.

También puede definir etiquetas de usuario como condición de una directiva de alerta. Esto da como resultado las alertas desencadenadas por la directiva para incluir el contexto del usuario afectado. Puede usar etiquetas de usuario del sistema o etiquetas de usuario personalizadas. Para obtener más información, consulta [Etiquetas de usuario en Microsoft Defender para obtener Office 365](/microsoft-365/security/office-365-security/user-tags).

- **Cuando se desencadena la alerta**. Puede configurar una configuración que defina la frecuencia con la que puede producirse una actividad antes de que se desencadene una alerta. Esto le permite configurar una directiva para generar una alerta cada vez que una actividad coincide con las condiciones de la directiva, cuando se supera un umbral determinado o cuando la aparición de la actividad que la alerta está rastreando se vuelve inusual para su organización.

    ![Configure cómo se desencadenan las alertas, en función del momento en que se produzca la actividad, un umbral o una actividad inusual para su organización.](../media/howalertsaretriggered.png)

    Si selecciona la configuración en función de la actividad inusual, Microsoft establece un valor de línea base que define la frecuencia normal de la actividad seleccionada. Se tarda hasta siete días en establecer esta línea base, durante la cual no se generarán alertas. Una vez establecida la línea base, se desencadena una alerta cuando la frecuencia de la actividad rastreada por la directiva de alerta supera en gran parte el valor de línea base. Para las actividades relacionadas con la auditoría (como las actividades de archivos y carpetas), puede establecer una línea base basada en un único usuario o en función de todos los usuarios de la organización; para actividades relacionadas con malware, puede establecer una línea base basada en una única familia de malware, un solo destinatario o todos los mensajes de la organización.

    > [!NOTE]
    > La capacidad de configurar directivas de alerta basadas en un umbral o en una actividad inusual requiere una suscripción E5/G5 o una suscripción E1/F1/G1 o E3/F3/G3 con Microsoft Defender para Office 365 P2, Cumplimiento de Microsoft 365 E5 o una suscripción de complemento de exhibición de documentos electrónicos y auditoría Microsoft 365. Las organizaciones con una suscripción A1/F1/G1 y E3/F3/G3 solo pueden crear directivas de alerta donde se desencadene una alerta cada vez que se produzca una actividad.

- **Categoría de alerta**. Para ayudar con el seguimiento y la administración de las alertas generadas por una directiva, puede asignar una de las siguientes categorías a una directiva.

  - Prevención de pérdida de datos

  - Información de gobierno

  - Flujo del correo

  - Permisos

  - Administración de amenazas

  - Otros

  Cuando se produce una actividad que coincide con las condiciones de la directiva de alerta, la alerta generada se etiqueta con la categoría definida en esta configuración. Esto le permite realizar un seguimiento y administrar alertas que tienen la misma configuración de  categoría en la página Alertas del centro de cumplimiento, ya que puede ordenar y filtrar alertas según la categoría.

- **Gravedad de alerta**. De forma similar a la categoría de alerta, se asigna un atributo de gravedad (**Low**, **Medium**, **High** o **Informational**) a las directivas de alerta. Al igual que la categoría de alerta, cuando se produce una actividad que coincide con las condiciones de la directiva de alerta, la alerta generada se etiqueta con el mismo nivel de gravedad que se establece para la directiva de alerta. De nuevo, esto le permite realizar un seguimiento y administrar alertas que tienen la misma configuración de gravedad en la página **Alertas** . Por ejemplo, puede filtrar la lista de alertas para que solo se muestren alertas con una gravedad alta.

    > [!TIP]
    > Al configurar una directiva de alerta, considere la posibilidad de asignar una mayor gravedad a actividades que puedan tener consecuencias muy negativas, como la detección de malware después de la entrega a los usuarios, la visualización de datos confidenciales o clasificados, el uso compartido de datos con usuarios externos u otras actividades que puedan provocar pérdida de datos o amenazas de seguridad. Esto puede ayudarle a priorizar las alertas y las acciones que lleve a cabo para investigar y resolver las causas subyacentes.

- **Investigaciones automatizadas**. Algunas alertas desencadenarán investigaciones automatizadas para identificar posibles amenazas y riesgos que necesitan corrección o mitigación.  En la mayoría de los casos, estas alertas se desencadenan mediante la detección de correos electrónicos o actividades malintencionadas, pero en algunos casos las alertas se desencadenan mediante acciones de administrador en el portal de seguridad.  Para obtener más información acerca de las investigaciones automatizadas, vea [Automated investigation and response (AIR) in Microsoft Defender for Office 365](../security/office-365-security/office-365-air.md).

- **Notificaciones por correo electrónico**. Puede configurar la directiva para que las notificaciones de correo electrónico se envíen (o no se envíen) a una lista de usuarios cuando se desencadene una alerta. También puede establecer un límite de notificación diario para que, una vez alcanzado el número máximo de notificaciones, no se envíen más notificaciones para la alerta durante ese día. Además de las notificaciones por correo electrónico, usted u otros administradores pueden ver las alertas que desencadena una directiva en la página **Alertas** . Considere la posibilidad de habilitar las notificaciones de correo electrónico para directivas de alerta de una categoría específica o que tengan una configuración de gravedad mayor.

## <a name="default-alert-policies"></a>Directivas de alerta predeterminadas

Microsoft proporciona directivas de alerta integradas que ayudan a identificar Exchange de permisos de administrador, actividad de malware, posibles amenazas externas e internas y riesgos de gobierno de la información. En la **página Directivas de** alerta, los nombres de estas directivas integradas están en negrita y el tipo de directiva se define como **System**. Estas directivas están activadas de forma predeterminada. Puedes desactivar estas directivas (o volver a activar), configurar una lista de destinatarios a los que enviar notificaciones por correo electrónico y establecer un límite de notificación diario. La otra configuración de estas directivas no se puede editar.

En la tabla siguiente se enumeran y describen las directivas de alerta predeterminadas disponibles y la categoría a la que se asigna cada directiva. La categoría se usa para determinar qué alertas puede ver un usuario en la página Alertas. Para obtener más información, vea [RBAC permissions required to view alerts](#rbac-permissions-required-to-view-alerts).

En la tabla también se indica Office 365 Enterprise y Office 365 plan del Gobierno de Estados Unidos necesario para cada uno de ellos. Algunas directivas de alerta predeterminadas están disponibles si su organización tiene la suscripción de complemento adecuada además de una suscripción E1/F1/G1 o E3/F3/G3.
 
| Directiva de alerta predeterminada | Descripción | Categoría | Investigación automatizada | Enterprise suscripción |
|:-----|:-----|:-----|:-----|:-----|
|**Se detectó un clic de dirección URL potencialmente malintencionado**|Genera una alerta cuando un usuario protegido por [Caja fuerte vínculos de](../security/office-365-security/safe-links.md) la organización hace clic en un vínculo malintencionado. Este evento se desencadena cuando Microsoft Defender identifica los cambios de veredicto de url para Office 365 o cuando los usuarios invalidan las páginas de vínculos de Caja fuerte (según la directiva de vínculos de Microsoft 365 para empresas de Caja fuerte de la organización). Esta directiva de alerta tiene **una configuración de** gravedad alta. Para los clientes de Defender Office 365 P2, E5, G5, esta alerta desencadena automáticamente la investigación automatizada y la respuesta [en Office 365](../security/office-365-security/office-365-air.md). Para obtener más información sobre los eventos que desencadenan esta alerta, vea [Configurar Caja fuerte de vínculos](../security/office-365-security/set-up-safe-links-policies.md).|Administración de amenazas|Sí|E5/G5 o Defender para una Office 365 de complemento P2|
|**Resultado de envío de administrador completado**|Genera una alerta cuando un [envío de](../security/office-365-security/admin-submission.md) administrador completa el nuevo análisis de la entidad enviada. Se activará una alerta cada vez que se represente un resultado de nuevo análisis desde un envío de administrador. Estas alertas están diseñadas para recordarle que revise los [resultados de envíos](https://compliance.microsoft.com/reportsubmission) anteriores, envíe mensajes notificados por el usuario para obtener los últimos veredictos de comprobación de directivas y volver a examinar, y le ayudarán a determinar si las directivas de filtrado de su organización están teniendo el impacto previsto. Esta directiva tiene una **configuración de gravedad informativo** .|Administración de amenazas|No|E1/F1, E3/F3 o E5|
|**Investigación manual de correo electrónico desencadenada por el administrador**|Genera una alerta cuando un administrador desencadena la investigación manual de un correo electrónico desde el Explorador de amenazas. Para obtener más información, vea [Ejemplo: un administrador de seguridad desencadena una investigación desde el Explorador de amenazas](../security/office-365-security/automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer). Esta alerta notifica a la organización que se inició la investigación. La alerta proporciona información sobre quién la desencadenó e incluye un vínculo a la investigación. Esta directiva tiene una **configuración de gravedad informativo** .|Administración de amenazas|Sí|E5/G5 o Microsoft Defender para una Office 365 de complemento P2|
|**Investigación de compromiso de usuario desencadenada por el administrador**|Genera una alerta cuando un administrador desencadena la investigación manual de compromiso del usuario de un remitente o destinatario de correo electrónico desde el Explorador de amenazas. Para obtener más información, vea [Ejemplo:](../security/office-365-security/automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) un administrador de seguridad desencadena una investigación desde el Explorador de amenazas, que muestra el desencadenamiento manual relacionado de una investigación en un correo electrónico. Esta alerta notifica a su organización que se inició la investigación de compromiso del usuario. La alerta proporciona información sobre quién la desencadenó e incluye un vínculo a la investigación. Esta directiva tiene una **configuración de** gravedad media.|Administración de amenazas|Sí|E5/G5 o Microsoft Defender para una Office 365 de complemento P2|
|**Creación de una regla de reenvío o redirección**|Genera una alerta cuando alguien de la organización crea una regla de bandeja de entrada para su buzón que reenvía o redirige mensajes a otra cuenta de correo electrónico. Esta directiva solo realiza un seguimiento de las reglas de bandeja de entrada que se crean Outlook en la Web (anteriormente conocidas como Outlook Web App) o Exchange Online PowerShell. Esta directiva tiene una **configuración de gravedad informativo** . Para obtener más información acerca del uso de reglas de bandeja de entrada para reenviar y redirigir el correo electrónico en Outlook en la Web, vea Usar reglas en Outlook en la Web para reenviar automáticamente mensajes [a otra cuenta](https://support.office.com/article/1433e3a0-7fb0-4999-b536-50e05cb67fed).|Administración de amenazas|No|E1/F1/G1, E3/F3/G3 o E5/G5|
|**Búsqueda de eDiscovery iniciada o exportada**|Genera una alerta cuando alguien usa la herramienta de búsqueda de contenido en el Centro de seguridad y cumplimiento. Cuando se realizan las siguientes actividades de búsqueda de contenido, se desencadena una alerta: <br><br> <li> Se inicia una búsqueda de contenido <li> Los resultados de una búsqueda de contenido se exportan <li> Se exporta un informe de búsqueda de contenido <br><br> Las alertas también se desencadenan cuando las actividades de búsqueda de contenido anteriores se realizan en asociación con un caso de exhibición de documentos electrónicos. Esta directiva tiene una **configuración de gravedad informativo** . Para obtener más información acerca de las actividades de búsqueda de contenido, vea [Buscar actividades de exhibición de documentos electrónicos en el registro de auditoría](search-for-ediscovery-activities-in-the-audit-log.md#ediscovery-activities).|Administración de amenazas|No|E1/F1/G1, E3/F3/G3 o E5/G5|
|**Elevación de Exchange privilegio de administrador**|Genera una alerta cuando alguien tiene asignados permisos administrativos en su Exchange Online organización. Por ejemplo, cuando se agrega un usuario al grupo de roles Administración de la organización en Exchange Online. Esta directiva tiene una **configuración de** gravedad baja.|Permisos|No|E1/F1/G1, E3/F3/G3 o E5/G5|
|**Mensajes de correo electrónico que contienen archivos malintencionados quitados después de la entrega**|Genera una alerta cuando los mensajes que contienen un archivo malintencionado se entregan a los buzones de la organización. Si se produce este evento, Microsoft quita los mensajes infectados de Exchange Online buzones de correo mediante purga automática [de hora cero](../security/office-365-security/zero-hour-auto-purge.md). Esta directiva tiene una **configuración de gravedad informativo** y desencadena automáticamente la investigación y respuesta [automatizadas en Office 365](../security/office-365-security/office-365-air.md). Para obtener más información sobre esta nueva directiva, consulta [Nuevas directivas de alerta en Microsoft Defender para Office 365](new-defender-alert-policies.md).|Administración de amenazas|Sí|E5/G5 o Microsoft Defender para una Office 365 de complemento P2|
|**Mensajes de correo electrónico que contienen direcciones URL malintencionadas quitados después de la entrega**|Genera una alerta cuando los mensajes que contienen una dirección URL malintencionada se entregan a los buzones de la organización. Si se produce este evento, Microsoft quita los mensajes infectados de Exchange Online buzones de correo mediante purga automática [de hora cero](../security/office-365-security/zero-hour-auto-purge.md). Esta directiva tiene una **configuración de gravedad informativo** y desencadena automáticamente la investigación y respuesta [automatizadas en Office 365](../security/office-365-security/office-365-air.md). Para obtener más información sobre esta nueva directiva, consulta [Nuevas directivas de alerta en Microsoft Defender para Office 365](new-defender-alert-policies.md).|Administración de amenazas|Sí|E5/G5 o Defender para una Office 365 de complemento P2|
|**Mensajes de correo electrónico de una campaña quitados después de la entrega**|Genera una alerta cuando los mensajes asociados a una [campaña](../security/office-365-security/campaigns.md) se entregan a los buzones de la organización. Si se produce este evento, Microsoft quita los mensajes infectados de Exchange Online buzones de correo mediante purga automática [de hora cero](../security/office-365-security/zero-hour-auto-purge.md). Esta directiva tiene una **configuración de gravedad informativo** y desencadena automáticamente la investigación y respuesta [automatizadas en Office 365](../security/office-365-security/office-365-air.md). Para obtener más información sobre esta nueva directiva, consulta [Nuevas directivas de alerta en Microsoft Defender para Office 365](new-defender-alert-policies.md).|Administración de amenazas|Sí|E5/G5 o Defender para una Office 365 de complemento P2|
|**Mensajes de correo electrónico quitados después de la entrega**|Genera una alerta cuando los mensajes malintencionados que no contienen una entidad malintencionada (DIRECCIÓN URL o Archivo) o asociados con una campaña, se entregan a buzones de correo de la organización. Si se produce este evento, Microsoft quita los mensajes infectados de Exchange Online buzones de correo mediante purga automática [de hora cero](../security/office-365-security/zero-hour-auto-purge.md). Esta directiva tiene una **configuración de gravedad informativo** y desencadena automáticamente la investigación y respuesta [automatizadas en Office 365](../security/office-365-security/office-365-air.md). Para obtener más información sobre esta nueva directiva, consulta [Nuevas directivas de alerta en Microsoft Defender para Office 365](new-defender-alert-policies.md).|Administración de amenazas|Sí|E5/G5 o Defender para una Office 365 de complemento P2|
|**Correo electrónico notificado por el usuario como malware o cebo**|Genera una alerta cuando los usuarios de la organización informan de mensajes como correo electrónico de suplantación de identidad mediante el complemento Mensaje de informe. Esta directiva tiene una **configuración de** gravedad baja. Para obtener más información acerca de este complemento, vea [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2). Para los clientes de Defender Office 365 P2, E5, G5, esta alerta desencadena automáticamente la investigación automatizada y la respuesta [en Office 365](../security/office-365-security/office-365-air.md).|Administración de amenazas|Sí|E1/F1/G1, E3/F3/G3 o E5/G5|
|**Límite de envío de correo electrónico superado**|Genera una alerta cuando alguien de la organización ha enviado más correo del permitido por la directiva de correo no deseado saliente. Esto suele indicar que el usuario envía demasiado correo electrónico o que la cuenta puede estar en peligro. Esta directiva tiene una **configuración de** gravedad media. Si obtiene una alerta generada por esta directiva de alerta, es buena idea comprobar si la cuenta [de usuario está en peligro](../security/office-365-security/responding-to-a-compromised-email-account.md).|Administración de amenazas|No|E1/F1/G1, E3/F3/G3 o E5/G5|
|**Formulario bloqueado debido a un posible intento de suplantación de identidad (phishing)**|Genera una alerta cuando se ha restringido a alguien de la organización el uso compartido de formularios y la recopilación de respuestas mediante Microsoft Forms debido al comportamiento de intento de suplantación de identidad (phishing) repetido detectado. Esta directiva tiene una **configuración de gravedad alta** .|Administración de amenazas|No|E1, E3/F3 o E5|
|**Formulario marcado y confirmado como suplantación de identidad (phishing)**|Genera una alerta cuando microsoft ha identificado un formulario creado en Microsoft Forms desde dentro de su organización como posible suplantación de identidad mediante el uso indebido de informes y confirmado como suplantación de identidad por Parte de Microsoft. Esta directiva tiene una **configuración de** gravedad alta.|Administración de amenazas|No|E1, E3/F3 o E5|
|**Los mensajes se han retrasado**|Genera una alerta cuando Microsoft no puede entregar mensajes de correo electrónico a su organización local o a un servidor asociado mediante un conector. Cuando esto sucede, el mensaje se pone en cola en Office 365. Esta alerta se desencadena cuando hay 2.000 mensajes o más que se han puesto en cola durante más de una hora. Esta directiva tiene una **configuración de** gravedad alta.|Flujo del correo|No|E1/F1/G1, E3/F3/G3 o E5/G5|
|**Campaña de malware detectada después de la entrega**|Genera una alerta cuando un número inusualmente grande de mensajes que contienen malware se entregan a los buzones de la organización. Si se produce este evento, Microsoft quita los mensajes infectados de Exchange Online buzones de correo. Esta directiva tiene una **configuración de** gravedad alta.|Administración de amenazas|No|E5/G5 o Microsoft Defender para una Office 365 de complemento P2|
|**Campaña de malware detectada y bloqueada**|Genera una alerta cuando alguien ha intentado enviar un número inusualmente grande de mensajes de correo electrónico que contienen un determinado tipo de malware a los usuarios de la organización. Si se produce este evento, Microsoft bloquea los mensajes infectados y no se entregan a los buzones. Esta directiva tiene una **configuración de** gravedad baja.|Administración de amenazas|No|E5/G5 o Defender para una Office 365 de complemento P2|
|**Campaña de malware detectada en SharePoint y OneDrive**|Genera una alerta cuando se detecta un volumen inusualmente alto de malware o virus en archivos ubicados en SharePoint sitios o OneDrive cuentas de la organización. Esta directiva tiene una **configuración de** gravedad alta.|Administración de amenazas|No|E5/G5 o Defender para una Office 365 de complemento P2|
|**Malware no zapped porque ZAP está deshabilitado**| Genera una alerta cuando Microsoft detecta la entrega de un mensaje de malware a un buzón porque Zero-Hour la purga automática de mensajes de suplantación de identidad está deshabilitada. Esta directiva tiene una **configuración de gravedad informativo** . |Administración de amenazas|No|E5/G5 o Defender para una Office 365 de complemento P2|
|**Phish delivered because a user's Junk Mail folder is disabled**|Genera una alerta cuando Microsoft detecta que la carpeta correo no deseado de un usuario está deshabilitada, lo que permite la entrega de un mensaje de suplantación de identidad de elevada confianza en un buzón. Esta directiva tiene una **configuración de gravedad informativo** .|Administración de amenazas|No|E1/F1/G1, E3/F3/G3 o E5/G5|
|**Phish delivered due to an ETR override**|Genera una alerta cuando Microsoft detecta una regla de Exchange de transporte (ETR) que permitía la entrega de un mensaje de suplantación de identidad de elevada confianza en un buzón. Esta directiva tiene una **configuración de gravedad informativo** . Para obtener más información sobre Exchange de transporte (reglas de flujo de correo), vea Reglas de flujo de correo (reglas de [transporte) en Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).|Administración de amenazas|No|E1/F1/G1, E3/F3/G3 o E5/G5|
|**Phish delivered due to an IP allow policy**|Genera una alerta cuando Microsoft detecta una directiva de direcciones IP permitidas que permitía la entrega de un mensaje de suplantación de identidad de elevada confianza a un buzón. Esta directiva tiene una **configuración de gravedad informativo** . Para obtener más información acerca de la directiva de ip allow (filtrado de conexiones), vea [Configure the default connection filter policy - Office 365](../security/office-365-security/configure-the-connection-filter-policy.md).|Administración de amenazas|No|E1/F1/G1, E3/F3/G3 o E5/G5|
|**Phish no zapped porque ZAP está deshabilitado**| Genera una alerta cuando Microsoft detecta la entrega de un mensaje de suplantación de identidad de elevada confianza a un buzón porque Zero-Hour la purga automática de mensajes de suplantación de identidad está deshabilitada. Esta directiva tiene una **configuración de gravedad informativo** .|Administración de amenazas|No|E5/G5 o Defender para una Office 365 de complemento P2|
|**Phish delivered due to tenant or user override1**<sup></sup>|Genera una alerta cuando Microsoft detecta un administrador o una invalidación de usuario que permite la entrega de un mensaje de suplantación de identidad a un buzón. Algunos ejemplos de invalidaciones incluyen una regla de flujo de correo o bandeja de entrada que permite mensajes de un remitente o dominio específico, o una directiva contra correo no deseado que permite mensajes de remitentes o dominios específicos. Esta directiva tiene una **configuración de** gravedad alta.|Administración de amenazas|No|E5/G5 o Defender para una Office 365 de complemento P2|
|**Actividad de reenvío de correo electrónico sospechoso**|Genera una alerta cuando alguien de la organización ha enviado automáticamente correo electrónico a una cuenta externa sospechosa. Se trata de una advertencia anticipada para el comportamiento que puede indicar que la cuenta está en peligro, pero no lo suficientemente grave como para restringir al usuario. Esta directiva tiene una **configuración de** gravedad alta. Aunque es poco común, una alerta generada por esta directiva puede ser una anomalía. Es una buena idea comprobar si [la cuenta de usuario está en peligro](../security/office-365-security/responding-to-a-compromised-email-account.md).|Administración de amenazas|No|E1/F1/G1, E3/F3/G3 o E5/G5|
|**Patrones de envío de correo electrónico sospechosos detectados**|Genera una alerta cuando alguien de la organización ha enviado correo electrónico sospechoso y corre el riesgo de que se le restringa el envío de correo electrónico. Se trata de una advertencia anticipada para el comportamiento que puede indicar que la cuenta está en peligro, pero no lo suficientemente grave como para restringir al usuario. Esta directiva tiene una **configuración de** gravedad media. Aunque es poco común, una alerta generada por esta directiva puede ser una anomalía. Sin embargo, es una buena idea comprobar [si la cuenta de usuario está en peligro](../security/office-365-security/responding-to-a-compromised-email-account.md).|Administración de amenazas|Sí|E1/F1/G1, E3/F3/G3 o E5/G5  |
|**La entrada permitir/bloquear lista de inquilinos está a punto de expirar**|Genera una alerta cuando se va a quitar una entrada de lista de inquilinos permitidos o bloqueados. Este evento se desencadena tres días antes de la fecha de expiración, que se basa cuando se creó la entrada o se actualizó por última vez. Esta directiva de alerta tiene una **configuración de gravedad informativo** . Esto es para informar a los administradores de los próximos cambios en los filtros, ya que la opción permitir o bloquear podría desaparecer. En el caso de los bloques, puede ampliar la fecha de expiración para mantener el bloque en su lugar. For allows, you need to resubmit the item so that our analysts can take another look. Sin embargo, si la allow ya se ha calificado como un falso positivo, la entrada solo expirará cuando los filtros del sistema se hayan actualizado para permitir la entrada de forma natural. Para obtener más información sobre los eventos que desencadenan esta alerta, vea [Manage the Tenant Allow/Block list](../security/office-365-security/tenant-allow-block-list.md).|Administración de amenazas|No|E5/G5 o Defender para una Office 365 de complemento P2|
|**Inquilino restringido para enviar correo electrónico**|Genera una alerta cuando la mayor parte del tráfico de correo electrónico de su organización se ha detectado como sospechoso y Microsoft ha restringido a su organización el envío de correo electrónico. Investigue las cuentas de usuario y administrador potencialmente comprometidas, los nuevos conectores o las retransmisiones abiertas y, a continuación, póngase en contacto con el Soporte técnico de Microsoft para desbloquear su organización. Esta directiva tiene una **configuración de** gravedad alta. Para obtener más información sobre por qué se bloquean las organizaciones, vea Corregir problemas de entrega de correo electrónico para [el código de error 5.7.7xx en Exchange Online](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-7-700-through-5-7-750).|Administración de amenazas|No|E1/F1/G1, E3/F3/G3 o E5/G5|
|**Inquilino restringido para enviar correo electrónico no previsto**|Genera una alerta cuando se envía demasiado correo electrónico desde dominios no registrados (también conocidos como *dominios no previstos* ). Office 365 permite una cantidad razonable de correo electrónico de dominios no registrados, pero debe configurar todos los dominios que use para enviar correo electrónico como un dominio aceptado. Esta alerta indica que todos los usuarios de la organización ya no pueden enviar correo electrónico. Esta directiva tiene una **configuración de** gravedad alta. Para obtener más información sobre por qué se bloquean las organizaciones, vea Corregir problemas de entrega de correo electrónico para [el código de error 5.7.7xx en Exchange Online](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-7-700-through-5-7-750).|Administración de amenazas|No|E1/F1/G1, E3/F3/G3 o E5/G5|
|**Actividad de archivo de usuario externo inusual**|Genera una alerta cuando se realiza un número inusualmente grande de actividades en archivos de SharePoint o OneDrive usuarios externos a la organización. Esto incluye actividades como el acceso a archivos, la descarga de archivos y la eliminación de archivos. Esta directiva tiene una **configuración de** gravedad alta.|Información de gobierno|No|E5/G5, Microsoft Defender para Office 365 P2 o Microsoft 365 E5 de complemento|
|**Volumen inusual de uso compartido de archivos externos**|Genera una alerta cuando un número inusualmente grande de archivos SharePoint o OneDrive se comparten con usuarios externos a la organización. Esta directiva tiene una **configuración de** gravedad media.|Información de gobierno|No|E5/G5, Defender para Office 365 P2 o Microsoft 365 E5 de complemento|
|**Volumen inusual de eliminación de archivos**|Genera una alerta cuando se elimina un número inusualmente grande de archivos SharePoint o OneDrive en un período de tiempo corto. Esta directiva tiene una **configuración de** gravedad media.|Información de gobierno|No|E5/G5, Defender para Office 365 P2 o Microsoft 365 E5 de complemento|
|**Aumento inusual en el correo electrónico notificado como cebo**|Genera una alerta cuando hay un aumento significativo en el número de personas de la organización que usan el complemento Mensaje de informe Outlook para notificar mensajes como correo de suplantación de identidad. Esta directiva tiene una **configuración de** gravedad media. Para obtener más información acerca de este complemento, vea [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).|Administración de amenazas|No|E5/G5 o Defender para una Office 365 de complemento P2|
|**Suplantación de identidad de usuario entregada a la bandeja de entrada/**<sup>carpeta1,2</sup><sup></sup>|Genera una alerta cuando Microsoft detecta que un administrador o un reemplazo de usuario ha permitido la entrega de un mensaje de suplantación de identidad de usuario en la bandeja de entrada (u otra carpeta accesible para el usuario) de un buzón. Algunos ejemplos de invalidaciones incluyen una regla de flujo de correo o bandeja de entrada que permite mensajes de un remitente o dominio específico, o una directiva contra correo no deseado que permite mensajes de remitentes o dominios específicos. Esta directiva tiene una **configuración de** gravedad media.|Administración de amenazas|No|E5/G5 o Defender para una Office 365 de complemento P2|
|**Usuario solicitado para liberar un mensaje en cuarentena**|Genera una alerta cuando un usuario solicita la publicación de un mensaje en cuarentena. Para solicitar la publicación de mensajes en cuarentena, el permiso Permitir **que** los destinatarios soliciten que un mensaje se libere de la cuarentena (_PermissionToRequestRelease_) es necesario en la directiva de cuarentena (por ejemplo, desde el grupo Permisos preestablecidos de acceso limitado). Para obtener más información, vea [Allow recipients to request a message to be released from quarantine permission](../security/office-365-security/quarantine-policies.md#allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission). Esta directiva tiene una **configuración de gravedad informativo** .|Administración de amenazas|No|E1/F1/G1, E3/F3/G3 o E5/G5|
|**El usuario no puede enviar correo electrónico**|Genera una alerta cuando alguien de la organización está restringido a enviar correo saliente. Esto normalmente se produce cuando una cuenta está en peligro y el usuario aparece en la página  Usuarios restringidos de la Centro de cumplimiento de Microsoft 365. (Para obtener acceso a esta página, vaya a **Administración de amenazas > Revisar > usuarios restringidos**). Esta directiva tiene una **configuración de** gravedad alta. Para obtener más información acerca de los usuarios restringidos, consulte [Removing a user, domain, or IP address from a block list after sending spam email](/office365/securitycompliance/removing-user-from-restricted-users-portal-after-spam).|Administración de amenazas|Sí|E1/F1/G1, E3/F3/G3 o E5/G5|
|**El usuario no puede compartir formularios ni recopilar respuestas**|Genera una alerta cuando se ha restringido a alguien de la organización el uso compartido de formularios y la recopilación de respuestas mediante Microsoft Forms debido al comportamiento de intento de suplantación de identidad (phishing) repetido detectado. Esta directiva tiene una **configuración de** gravedad alta.|Administración de amenazas|No|E1, E3/F3 o E5|

> [!NOTE]
> <sup>1</sup> Hemos quitado temporalmente esta directiva de alerta predeterminada en función de los comentarios de los clientes. Estamos trabajando para mejorarlo y lo reemplazaremos por una nueva versión en un futuro próximo. Hasta entonces, puede crear una directiva de alerta personalizada para reemplazar esta funcionalidad mediante la siguiente configuración: <ul><li>La actividad es el correo electrónico de suplantación de identidad detectado en el momento de la entrega</li> <li>El correo no es ZAP'd</li> <li>La dirección del correo es Entrante</li> <li>El estado de entrega de correo es Entregado</li> <li>La tecnología de detección es retención de url malintencionada, detonación de url, filtro de phish avanzado, filtro de phishing general, suplantación de dominio, suplantación de usuario y suplantación de marca</li></ul> Para obtener más información acerca de la protección contra la suplantación de identidad en Office 365, vea [Configurar directivas contra suplantación de identidad (phishing) y contra suplantación de identidad (phishing).](../security/office-365-security/set-up-anti-phishing-policies.md)<br/><br/><sup>2</sup> Para volver a crear esta directiva de alerta, siga las instrucciones de la nota al pie anterior, pero elija Suplantación de usuario como la única tecnología de detección.

La actividad inusual supervisada por algunas de las directivas integradas se basa en el mismo proceso que la configuración del umbral de alerta que se describió anteriormente. Microsoft establece un valor de línea base que define la frecuencia normal de la actividad "habitual". A continuación, las alertas se desencadenan cuando la frecuencia de las actividades seguidas por la directiva de alerta integrada supera en gran parte el valor de línea base.

<a name="viewing-alerts"></a>

## <a name="view-alerts"></a>Ver alertas

Cuando una actividad realizada por los usuarios de la organización coincide con la configuración de una directiva de alerta, se genera una alerta y se  muestra en la página Alertas en el centro de cumplimiento o en el portal de Defender. Según la configuración de una directiva de alerta, también se envía una notificación por correo electrónico a una lista de usuarios especificados cuando se desencadena una alerta. Para cada alerta, el panel de la  página Alertas muestra el nombre de la directiva de alerta correspondiente, la gravedad y la categoría de la alerta (definida en la directiva de alerta) y el número de veces que se ha producido una actividad que ha generado la alerta. Este valor se basa en la configuración de umbral de la directiva de alerta. El panel también muestra el estado de cada alerta. Para obtener más información acerca del uso de la propiedad status para administrar alertas, vea [Managing alerts](#manage-alerts).

Para ver alertas:

### <a name="microsoft-365-compliance-center"></a>Centro de cumplimiento de Microsoft 365

 Vaya a <https://compliance.microsoft.com> y, a continuación, seleccione **Alertas**. Como alternativa, puede ir directamente a <https://compliance.microsoft.com/compliancealerts>.

![En el Centro de cumplimiento de Microsoft 365, seleccione Alertas.](../media/ViewAlertsMCC.png)

### <a name="microsoft-365-defender-portal"></a>Portal de Microsoft 365 Defender

Vaya a <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portal y</a>, a continuación, seleccione **Incidentes &** **alertsAlerts** > . Como alternativa, puede ir directamente a <https://security.microsoft.com/alerts>.

![En el portal Microsoft 365 Defender, seleccione Incidentes & alertas y, a continuación, seleccione Alertas.](../media/ViewAlertsDefenderPortal.png)

Puede usar los siguientes filtros para ver un subconjunto de todas las alertas en la página **Alertas** .

- **Estado.** Use este filtro para mostrar las alertas que tienen asignado un estado determinado. El estado predeterminado es **Active**. Usted u otros administradores pueden cambiar el valor de estado.

- **Directiva.** Use este filtro para mostrar alertas que coincidan con la configuración de una o más directivas de alerta. O puede mostrar todas las alertas de todas las directivas de alerta.

- **Intervalo de tiempo.** Use este filtro para mostrar las alertas que se generaron dentro de un intervalo de fecha y hora específico.

- **Gravedad.** Use este filtro para mostrar alertas que tienen asignada una gravedad específica.

- **Categoría.** Use este filtro para mostrar alertas de una o más categorías de alertas.

- **Etiquetas.** Use este filtro para mostrar alertas de una o varias etiquetas de usuario. Las etiquetas se reflejan en función de buzones etiquetados o usuarios que aparecen en las alertas. Consulta [Etiquetas de usuario en Office ATP 356](../security/office-365-security/user-tags.md) para obtener más información.

- **Source.** Use este filtro para mostrar las alertas desencadenadas por directivas de alerta en el centro de cumplimiento o alertas desencadenadas por Office 365 Cloud App Security directivas o ambas. Para obtener más información acerca Office 365 Cloud App Security alertas, consulta [Visualización de alertas de Defender para aplicaciones en la nube](#viewing-cloud-app-security-alerts).

> [!IMPORTANT]
> El filtrado y ordenación por etiquetas de usuario se encuentra actualmente en versión preliminar pública.
> Puede modificarse considerablemente antes de su lanzamiento comercial. Microsoft no ofrece garantías, explícitas o implícitas, con respecto a la información proporcionada al respecto.

## <a name="alert-aggregation"></a>Agregación de alertas

Cuando se producen varios eventos que coinciden con las condiciones de una directiva de alertas con un breve período de tiempo, se agregan a una alerta existente mediante un proceso denominado agregación *de alertas*. Cuando un evento desencadena una alerta, la alerta se genera y se muestra **en la página** Alertas y se envía una notificación. Si se produce el mismo evento dentro del intervalo de agregación, Microsoft 365 agrega detalles sobre el nuevo evento a la alerta existente en lugar de desencadenar una nueva alerta. El objetivo de la agregación de alertas es ayudar a reducir la "fatiga" de alertas y permitir que te enfoques y tomes medidas en menos alertas para el mismo evento.

La longitud del intervalo de agregación depende de la Office 365 o Microsoft 365 suscripción.

|Suscripción |Intervalo de agregación|
|:---------|:---------:|
|Office 365 o Microsoft 365 E5/G5|1 minuto|
|Defender para Office 365 Plan 2 |1 minuto|
|Complemento de cumplimiento E5 o complemento de detección y auditoría de E5|1 minuto|
|Office 365 o Microsoft 365 E1/F1/G1 o E3/F3/G3|15 minutos|
|Defender para Office 365 plan 1 o Exchange Online Protection|15 minutos|

Cuando se producen eventos que coinciden con la misma directiva de alerta en el intervalo de agregación, se agregan detalles sobre el evento posterior a la alerta original. Para todos los eventos, la información sobre los eventos agregados se muestra en el campo de detalles y el número de veces que se produjo un evento con el intervalo de agregación se muestra en el campo de recuento de actividad o éxito. Puede ver más información sobre todas las instancias de eventos agregados mediante la visualización de la lista de actividades.

La siguiente captura de pantalla muestra una alerta con cuatro eventos agregados. La lista de actividades contiene información sobre los cuatro mensajes de correo electrónico relevantes para la alerta.

![Ejemplo de agregación de alertas.](../media/AggregatedAlertExample.png)

Tenga en cuenta lo siguiente acerca de la agregación de alertas:

- Las alertas desencadenadas por **el clic en Una dirección URL potencialmente** [](#default-alert-policies) malintencionada se detectaron no se agregan a la directiva de alerta predeterminada. Esto se debe a que las alertas desencadenadas por esta directiva son únicas para cada usuario y mensaje de correo electrónico.

- En este momento, la **propiedad de** alerta Recuento de accesos no indica el número de eventos agregados para todas las directivas de alerta. Para las alertas desencadenadas por estas directivas de alerta, puede ver los eventos agregados haciendo clic en **Ver** lista de mensajes o **Ver actividad** en la alerta. Estamos trabajando para que el número de eventos agregados enumerados en la propiedad **de** alerta Recuento de impactos esté disponible para todas las directivas de alerta.

## <a name="rbac-permissions-required-to-view-alerts"></a>Permisos RBAC necesarios para ver alertas

Los permisos de control de acceso basado en roles (RBAC) asignados a los usuarios de la organización determinan qué alertas puede ver un usuario en la **página Alertas** . ¿Cómo se logra esto? Los roles de administración asignados a los usuarios (en función de su pertenencia a grupos de roles en el portal de Centro de cumplimiento de Microsoft 365 o Microsoft 365 Defender) determinan qué categorías de alerta puede ver un usuario en la **página Alertas**. Estos son algunos ejemplos:

- Los miembros del grupo de roles Administración de registros solo pueden ver las alertas generadas por las directivas de alerta a las que se asigna la **categoría Gobierno de** información.

- Los miembros del grupo de roles Administrador de cumplimiento no pueden ver las alertas generadas por las directivas de alerta a las que se asigna la **categoría Administración de** amenazas.

- Los miembros del grupo de roles administrador de exhibición de documentos electrónicos no pueden ver ninguna alerta porque ninguno de los roles asignados proporciona permiso para ver alertas de cualquier categoría de alerta.

Este diseño (basado en permisos RBAC) le permite determinar qué alertas pueden ver (y administrar) los usuarios en roles de trabajo específicos de la organización.

En la tabla siguiente se enumeran los roles necesarios para ver alertas de las seis categorías de alertas diferentes. La primera columna de las tablas enumera todos los roles del Centro de cumplimiento de Microsoft 365 o del portal Microsoft 365 Defender tabla.  Una marca de verificación indica que un usuario que tiene asignado ese rol puede ver alertas de la categoría de alerta correspondiente que aparece en la fila superior.

Para ver a qué categoría está asignada una directiva de alerta predeterminada, vea la tabla [en Directivas de alerta predeterminadas](#default-alert-policies).

|Rol|Información de gobierno|Prevención de pérdida de datos|Flujo del correo|Permisos|Administración de amenazas|Otros|
|:---------|:---------:|:---------:|:---------:|:---------:|:---------:|:---------:|
|Registros de auditoría|||||||
|Administración de casos|||||||
|Administrador de cumplimiento|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación.](../media/checkmark.png)||![Marca de verificación.](../media/checkmark.png)||![Marca de verificación.](../media/checkmark.png)|
|Búsqueda de cumplimiento|||||||
|Administración de dispositivos|||||||
|Administración de disposición|||||||
|Administración de cumplimiento de DLP||![Marca de verificación.](../media/checkmark.png)|||||
|Export|||||||
|Hold|||||||
|Analista de Information Protection||![Marca de verificación.](../media/checkmark.png)|||||
|Investigador de protección de información||![Marca de verificación.](../media/checkmark.png)|||||
|Administrar alertas||||||![Marca de verificación.](../media/checkmark.png)|
|Configuración de la organización||||||![Marca de verificación.](../media/checkmark.png)|
|Preview|||||||
|Administración de registros|![Marca de verificación.](../media/checkmark.png)||||||
|Administración de retención|![Marca de verificación.](../media/checkmark.png)||||||
|Revisar|||||||
|Descifrado de RMS|||||||
|Administración de roles||||![Marca de verificación.](../media/checkmark.png)|||
|Buscar y purgar|||||||
|Administrador de seguridad||![Marca de verificación.](../media/checkmark.png)||![Marca de verificación.](../media/checkmark.png)|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación.](../media/checkmark.png)|
|Lector de seguridad||![Marca de verificación.](../media/checkmark.png)||![Marca de verificación.](../media/checkmark.png)|![Marca de verificación.](../media/checkmark.png)|![Marca de verificación.](../media/checkmark.png)
|Vista Service Assurance|||||||
|Administrador de revisión de supervisión|||||||
|Registros de auditoría de solo vista|||||||
|View-Only administración de dispositivos|||||||
|View-Only de cumplimiento dlp||![Marca de verificación.](../media/checkmark.png)|||||
|View-Only administrar alertas||||||![Marca de verificación](../media/checkmark.png)|
|Destinatarios con permiso de vista|||![Marca de verificación](../media/checkmark.png)||||
|View-Only administración de registros|![Marca de verificación](../media/checkmark.png)||||||
|View-Only administración de retención|![Marca de verificación](../media/checkmark.png)||||||

> [!TIP]
> Para ver los roles asignados a cada uno de los grupos de roles predeterminados, ejecute los siguientes comandos en PowerShell del Centro de seguridad & cumplimiento:
>
> ```powershell
> $RoleGroups = Get-RoleGroup
> ```
>
> ```powershell
> $RoleGroups | foreach {Write-Output -InputObject `r`n,$_.Name,"-----------------------"; Get-RoleGroup $_.Identity | Select-Object -ExpandProperty Roles}
> ```
>
> También puede ver los roles asignados a un grupo de roles en el Centro de cumplimiento de Microsoft 365 o en el portal Microsoft 365 Defender funciones. Vaya a la **página Permisos** y seleccione un grupo de roles. Los roles asignados se enumeran en la página desplegable.

<a name="manage-alerts"></a>

## <a name="manage-alerts"></a>Administrar alertas

Una vez generadas y mostradas las alertas  en la página Alertas del centro de cumplimiento, puede realizar una triaje, investigar y resolverlas. Los mismos [permisos RBAC que](#rbac-permissions-required-to-view-alerts) dan a los usuarios acceso a alertas también les permiten administrar alertas.

Estas son algunas tareas que puede realizar para administrar alertas.

- **Asignar un estado a las alertas.** Puede asignar uno de los siguientes estados a las alertas: **Active** (el valor predeterminado), **Investigating**, **Resolved** o **Dismissed**. A continuación, puede filtrar esta configuración para mostrar alertas con la misma configuración de estado. Esta configuración de estado puede ayudar a realizar un seguimiento del proceso de administración de alertas.

- **Ver detalles de alerta.** Puede seleccionar una alerta para mostrar una página desplegable con detalles sobre la alerta. La información detallada depende de la directiva de alerta correspondiente, pero normalmente incluye lo siguiente:

  - Nombre de la operación real que desencadenó la alerta, como un cmdlet o una operación de registro de auditoría.

  - Descripción de la actividad que desencadenó la alerta.

  - El usuario (o lista de usuarios) que desencadenó la alerta. Esto se incluye solo para las directivas de alerta configuradas para realizar un seguimiento de un único usuario o una sola actividad.

  - El número de veces que se realizó el seguimiento de la actividad por parte de la alerta. Es posible que este número no coincida con el número real de alertas relacionadas enumeradas en la página Alertas porque es posible que se hayan desencadenado más alertas.

  - Un vínculo a una lista de actividades que incluye un elemento para cada actividad que se realizó que desencadenó la alerta. Cada entrada de esta lista identifica cuándo se produjo la actividad, el nombre de la operación real (como "FileDeleted"), el usuario que realizó la actividad, el objeto (como un archivo, un caso de exhibición de documentos electrónicos o un buzón) en el que se realizó la actividad y la dirección IP del equipo del usuario. Para las alertas relacionadas con malware, esto se vincula a una lista de mensajes.

  - Nombre (y vínculo) de la directiva de alerta correspondiente.

- **Suprimir notificaciones de correo electrónico.** Puedes desactivar (o suprimir) las notificaciones de correo electrónico de la página desplegable de una alerta. Al suprimir las notificaciones de correo electrónico, Microsoft no enviará notificaciones cuando se produzcan actividades o eventos que coincidan con las condiciones de la directiva de alertas. Pero las alertas se desencadenarán cuando las actividades realizadas por los usuarios coincidan con las condiciones de la directiva de alerta. También puede desactivar las notificaciones de correo electrónico editando la directiva de alertas.

- **Resolver alertas.** Puede marcar una alerta como resuelta en la página desplegable de una alerta (que establece el estado de la alerta en **Resuelto**). A menos que cambie el filtro, las alertas resueltas no se muestran en la página **Alertas** .

<a name="viewing-cloud-app-security-alerts"></a>

## <a name="view-defender-for-cloud-apps-alerts"></a>Ver alertas de Defender para aplicaciones en la nube

Las alertas que se desencadenan Office 365 Cloud App Security directivas se muestran ahora en la página **Alertas** del centro de cumplimiento. Esto incluye alertas desencadenadas por directivas de actividad y alertas desencadenadas por directivas de detección de anomalías en Office 365 Cloud App Security. Esto significa que puede ver todas las alertas en el centro de cumplimiento. Office 365 Cloud App Security solo está disponible para organizaciones con una suscripción Office 365 Enterprise E5 o Office 365 us Government G5. Para obtener más información, consulta [Overview of Defender for Cloud Apps](/cloud-app-security/what-is-cloud-app-security).

Las organizaciones que tienen Microsoft Defender para Aplicaciones en la nube como parte de una suscripción Enterprise Mobility + Security E5 o como un servicio independiente también pueden ver alertas de Defender para Aplicaciones en la nube relacionadas con Microsoft 365 aplicaciones y servicios en el Centro de cumplimiento de Microsoft 365 o el Microsoft 365 Defender web.

Para mostrar solo alertas de Defender para Aplicaciones en la nube en el centro de cumplimiento o en  el portal de Defender, usa el filtro Origen y selecciona **Defender para aplicaciones en la nube**.

![Usa el filtro Origen para mostrar solo alertas de Defender para Aplicaciones en la nube.](../media/FilterCASAlerts.png)

De forma similar a una alerta desencadenada por una directiva de alerta en el centro de cumplimiento, puedes seleccionar una alerta de Defender para aplicaciones en la nube para mostrar una página desplegable con detalles sobre la alerta. La alerta incluye un vínculo para ver los detalles y administrar la alerta en el portal de Defender for Cloud Apps y un vínculo a la directiva de Defender for Cloud Apps correspondiente que desencadenó la alerta. Consulta [Supervisar alertas en Defender para aplicaciones en la nube](/cloud-app-security/monitor-alerts).

![Los detalles de alerta contienen vínculos al portal de Defender for Cloud Apps.](../media/CASAlertDetail.png)

> [!IMPORTANT]
> Cambiar el estado de una alerta de Defender para Aplicaciones en la nube en el centro de cumplimiento no actualizará el estado de resolución de la misma alerta en el portal de Defender para aplicaciones en la nube. Por ejemplo, si marca el estado de la alerta como Resuelto  en el centro de cumplimiento, el estado de la alerta en el portal de Defender for Cloud Apps no cambiará. Para resolver o descartar una alerta de Defender for Cloud Apps, administra la alerta en el portal de Defender for Cloud Apps.
