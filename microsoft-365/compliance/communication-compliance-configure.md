---
title: Introducción al cumplimiento de las comunicaciones
description: Configure las directivas de cumplimiento de comunicaciones para configurar las comunicaciones del usuario para su revisión.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: a3c9aabd370117c085574144ff9450e74ae277c7
ms.sourcegitcommit: 4cbb4ec26f022f5f9d9481f55a8a6ee8406968d2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2020
ms.locfileid: "49527529"
---
# <a name="get-started-with-communication-compliance"></a>Introducción al cumplimiento de las comunicaciones

Use las directivas de cumplimiento de comunicaciones para identificar las comunicaciones de los usuarios con el fin de examinarlas por los revisores externos o internos. Para obtener más información sobre cómo las directivas de cumplimiento de comunicaciones pueden ayudarle a supervisar las comunicaciones en su organización, consulte [directivas de cumplimiento de comunicaciones en Microsoft 365](communication-compliance.md). Si desea revisar cómo contoso ha configurado rápidamente una directiva de cumplimiento de comunicaciones para supervisar el lenguaje ofensivo en Microsoft Teams, Exchange Online y Yammer Communications, consulte este [caso práctico](communication-compliance-case-study.md).

## <a name="subscriptions-and-licensing"></a>Suscripciones y licencias

Antes de empezar con el cumplimiento de la comunicación, debe confirmar la [suscripción de Microsoft 365](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) y los complementos. Para acceder y usar el cumplimiento de las comunicaciones, su organización debe tener una de las siguientes suscripciones o complementos:

- Suscripción a Microsoft 365 E5 (versión de pago o de prueba)
- Suscripción a Microsoft 365 E3 + complemento de cumplimiento de Microsoft 365 E5
- Suscripción a Microsoft 365 E3 + complemento Microsoft 365 E5 del servicio de administración de riesgos de Insider
- Suscripción a Microsoft 365 A5 (versión de pago o de prueba)
- Suscripción a Microsoft 365 a3 + complemento de cumplimiento A5 de Microsoft 365
- Suscripción a Microsoft 365 a3 + complemento de administración de riesgos de la A5 del Insider de Microsoft 365
- Suscripción a Microsoft 365 G5 (versión de pago o de prueba)
- Suscripción a Microsoft 365 G5 + complemento de cumplimiento de Microsoft 365 G5
- Suscripción a Microsoft 365 G5 + complemento de administración de riesgos de Insider de Microsoft 365 G5
- Suscripción a Office 365 Enterprise E5 (versión de pago o de prueba)
- Suscripción a Office 365 A5 (versión de pago o de prueba)
- Office 365 Enterprise E3 subscription + el complemento Office 365 Advanced Compliance (ya no está disponible para las nuevas suscripciones, vea note)

Los usuarios incluidos en las directivas de cumplimiento de comunicaciones deben tener asignada una de las licencias anteriores.

>[!IMPORTANT]
>Office 365 Advanced Compliance ya no se vende como una suscripción independiente. Cuando expiren las suscripciones actuales, los clientes deben pasar a una de las suscripciones anteriores, que contienen las mismas características de cumplimiento o más.

Si no tiene un plan de Office 365 Enterprise E5 existente y desea probar el cumplimiento de la comunicación, puede [Agregar Microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) a la suscripción existente o [registrarse para obtener una versión de prueba](https://www.microsoft.com/microsoft-365/enterprise) de Office 365 Enterprise E5.

## <a name="step-1-required-enable-permissions-for-communication-compliance"></a>Paso 1 (obligatorio): habilitar permisos para el cumplimiento de la comunicación

>[!Important]
>De forma predeterminada, los administradores globales no tienen acceso a las características de cumplimiento de comunicaciones. Los roles asignados en este paso son necesarios antes de que se pueda tener acceso a las características de cumplimiento de la comunicación. Después de configurar los grupos de roles, los permisos del grupo de roles pueden tardar hasta 30 minutos en aplicarse a los usuarios asignados en toda la organización.

Hay cinco grupos de roles usados para configurar los permisos para administrar las características de cumplimiento de comunicaciones. Para que el cumplimiento de la **comunicación** esté disponible como una opción de menú en el centro de cumplimiento de Microsoft 365 y para continuar con estos pasos de configuración, debe estar asignado a los grupos de roles de *cumplimiento normativo de comunicaciones* o *Administración cumplimiento de comunicaciones* . Para obtener acceso y administrar las características de cumplimiento de comunicaciones tras la configuración inicial, los usuarios deben pertenecer al menos a un grupo de roles de cumplimiento de la comunicación.

En función de cómo desee administrar las directivas y alertas de comunicación, deberá asignar usuarios a grupos de roles específicos. Tiene la opción de asignar usuarios con responsabilidades de cumplimiento diferentes a grupos de roles específicos para administrar diferentes áreas de características de cumplimiento de comunicaciones. O bien, puede decidir asignar todas las cuentas de usuario para administradores, analistas, investigadores y visores designados al grupo de funciones de *cumplimiento de comunicaciones* . Use un grupo de roles único o varios grupos de roles para ajustarse mejor a los requisitos de administración de cumplimiento.

Elija entre estas opciones de grupo de roles al configurar el cumplimiento de la comunicación:

| Role | Permisos de funciones |
|:-----|:-----|
| **Cumplimiento de la comunicación** | Use este grupo de roles para administrar el cumplimiento de la comunicación de su organización en un único grupo. Al agregar todas las cuentas de usuario para administradores, analistas, investigadores y visores designados, puede configurar los permisos de cumplimiento de comunicaciones en un único grupo. Este grupo de roles contiene todos los roles de permisos de cumplimiento de comunicaciones. Esta configuración es la forma más sencilla de empezar rápidamente con el cumplimiento de la comunicación y es una buena opción para las organizaciones que no necesitan permisos separados definidos para grupos de usuarios independientes. |
| **Administrador de cumplimiento de comunicaciones** | Use este grupo de roles para configurar inicialmente el cumplimiento de comunicaciones y posteriormente para separar los administradores de cumplimiento de comunicaciones en un grupo definido. Los usuarios asignados a este grupo de roles pueden crear, leer, actualizar y eliminar las directivas de cumplimiento de la comunicación, la configuración global y las asignaciones de grupos de roles. Los usuarios asignados a este grupo de roles no pueden ver los mensajes de alerta. |
| **Analista de cumplimiento de comunicaciones** | Use este grupo para asignar permisos a los usuarios que van a actuar como analistas de cumplimiento de comunicaciones. Los usuarios asignados a este grupo de roles pueden ver las directivas en las que se asignan como revisores, ver los metadatos de los mensajes (no el contenido del mensaje), remitir a otros revisores o enviar notificaciones a los usuarios. Los analistas no pueden resolver alertas pendientes. |
| **Investigador de cumplimiento de la comunicación** | Use este grupo para asignar permisos a los usuarios que actuarán como investigadores de cumplimiento de la comunicación. Los usuarios asignados a este grupo de roles pueden ver el contenido y los metadatos de los mensajes, escalar a revisores adicionales, escalar a un caso de eDiscovery avanzado, enviar notificaciones a los usuarios y resolver la alerta. |
| **Visor de cumplimiento de comunicaciones** | Use este grupo para asignar permisos a los usuarios que van a administrar los informes de comunicación. Los usuarios asignados a este grupo de roles pueden tener acceso a todos los widgets de informes en la página de inicio de cumplimiento de comunicaciones y pueden ver todos los informes de cumplimiento de comunicaciones. |

### <a name="option-1-assign-all-compliance-users-to-the-communication-compliance-role-group"></a>Opción 1: asignar todos los usuarios de cumplimiento al grupo de funciones de cumplimiento de comunicaciones

1. Inicie sesión [https://protection.office.com/permissions](https://protection.office.com/permissions) con las credenciales de una cuenta de administrador en la organización de Microsoft 365.

2. En el centro de seguridad &amp; y cumplimiento, vaya a **permisos**. Seleccione el vínculo para ver y administrar roles en Office 365.

3. Seleccione el grupo de funciones *cumplimiento de comunicaciones* y, después, seleccione **Editar Grupo de roles**.

4. Seleccione **elegir miembros** en el panel de navegación izquierdo y, a continuación, seleccione **Editar**.

5. Seleccione **Agregar** y, a continuación, marque la casilla para todos los usuarios que quiera agregar al grupo de funciones *cumplimiento de comunicaciones* .

6. Seleccione **Agregar** y haga clic en **listo**.

7. Seleccione **Guardar** para agregar los usuarios al grupo de roles. Seleccione **cerrar** para completar los pasos

### <a name="option-2-assign-users-to-specific-communication-compliance-role-groups"></a>Opción 2: asignar usuarios a grupos de roles de cumplimiento de comunicaciones específicos

Use esta opción para asignar usuarios a grupos de roles específicos para segmentar el acceso y las responsabilidades del cumplimiento de comunicaciones entre los distintos usuarios de la organización.

1. Inicie sesión [https://protection.office.com/permissions](https://protection.office.com/permissions) con las credenciales de una cuenta de administrador en la organización de Microsoft 365.

2. En el centro de seguridad &amp; y cumplimiento, vaya a **permisos**. Seleccione el vínculo para ver y administrar roles en Office 365.

3. Seleccione uno de los grupos de roles de cumplimiento de comunicaciones y, después, seleccione **Editar Grupo de roles**.

4. Seleccione **elegir miembros** en el panel de navegación izquierdo y, a continuación, seleccione **Editar**.

5. Seleccione **Agregar** y, a continuación, marque la casilla de verificación para todos los usuarios que desee agregar al grupo de roles.

6. Seleccione **Agregar** y haga clic en **listo**.

7. Seleccione **Guardar** para agregar los usuarios al grupo de roles.

8. Seleccione el siguiente grupo de funciones cumplimiento de comunicaciones y, a continuación, repita los pasos 4-7 para cada grupo de roles necesario.

9. Seleccione **cerrar** para completar los pasos.

Para obtener más información acerca de los grupos de roles y los permisos, consulte [Permissions in the Compliance Center](../security/office-365-security/protect-against-threats.md).

## <a name="step-2-required-enable-the-audit-log"></a>Paso 2 (obligatorio): habilitar el registro de auditoría

El cumplimiento de la comunicación requiere registros de auditoría para mostrar alertas y realizar un seguimiento de las acciones de corrección realizadas por los revisores. Los registros de auditoría son un resumen de todas las actividades asociadas con una directiva de organización definida o cada vez que cambia una directiva de cumplimiento de la comunicación.

Para obtener instrucciones paso a paso para activar la auditoría, vea [activar o desactivar la búsqueda de registros de auditoría](turn-audit-log-search-on-or-off.md). Después de activar la auditoría, se muestra un mensaje que indica que se está preparando el registro de auditoría y que puede ejecutar una búsqueda en un par de horas después de que se complete la preparación. Solo tiene que realizar esta acción una vez. Para obtener más información acerca del uso del registro de auditoría, vea [Buscar en el registro de auditoría](search-the-audit-log-in-security-and-compliance.md).

## <a name="step-3-optional-set-up-groups-for-communication-compliance"></a>Paso 3 (opcional): configurar grupos para el cumplimiento de la comunicación

 Al crear una directiva de cumplimiento de la comunicación, se define quién ha revisado sus comunicaciones y quién realiza las revisiones. En la Directiva, usará direcciones de correo electrónico para identificar personas o grupos de personas. Para simplificar la configuración, puede crear grupos para los usuarios que tengan su comunicación revisada y grupos para los usuarios que revisen dichas comunicaciones. Si está usando grupos, es posible que necesite varios. Por ejemplo, si desea supervisar las comunicaciones entre dos grupos de personas distintas o si desea especificar un grupo que no va a supervisarse.

Use el siguiente gráfico para ayudarle a configurar los grupos de su organización para las directivas de cumplimiento de comunicaciones:

| **Miembro de la Directiva** | **Grupos admitidos** | **Grupos no admitidos** |
|:-----|:-----|:-----|
|Usuarios supervisados <br> Usuarios no supervisados | Grupos de distribución <br> Grupos de Microsoft 365 | Grupos de distribución dinámicos <br> Grupos de distribución anidados <br> Grupos de seguridad habilitados para correo |
| Reviewers | Ninguno | Grupos de distribución <br> Grupos de distribución dinámicos <br> Grupos de distribución anidados <br> Grupos de seguridad habilitados para correo |
  
Cuando se asigna un grupo de distribución en la Directiva, la Directiva supervisa todos los correos electrónicos y chats de cada usuario en el grupo de distribución. Cuando se asigna un grupo de Microsoft 365 en la Directiva, la Directiva supervisa todos los correos electrónicos y los chats de equipo enviados a ese grupo, no los correos electrónicos y chats individuales recibidos por cada miembro del grupo.

Si es una organización con una implementación local de Exchange o un proveedor de correo electrónico externo y desea supervisar los chats de Microsoft Teams para los usuarios, debe crear un grupo de distribución para los usuarios con buzones locales o externos para supervisar. Más adelante en estos pasos, asignará este grupo de distribución como la selección de **usuarios y grupos supervisados** en el Asistente para directivas.

>[!IMPORTANT]
>Debe presentar una solicitud al Soporte técnico de Microsoft para que su organización pueda utilizar la interfaz gráfica de usuario en el Centro de seguridad y cumplimiento para buscar datos de chat de Teams de usuarios locales. Para obtener más información, vea [Buscar buzones de correo basados en la nube para usuarios locales](search-cloud-based-mailboxes-for-on-premises-users.md).

Para obtener más información acerca de la configuración de grupos, vea:

- [Crear y administrar grupos de distribución](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [Información general de los grupos de 365 de Microsoft](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups)

## <a name="step-4-optional-verify-your-yammer-tenant-is-in-native-mode"></a>Paso 4 (opcional): comprobar que el inquilino de Yammer está en modo nativo

En el modo nativo, todos los usuarios de Yammer están en Azure Active Directory (Azure AD), todos los grupos son grupos de Office 365 y todos los archivos se almacenan en SharePoint Online. El inquilino de Yammer debe estar en modo nativo para que las directivas de cumplimiento de comunicaciones analicen e identifiquen conversaciones peligrosas en mensajes privados y conversaciones de la comunidad en Yammer.

Para obtener más información acerca de la configuración de Yammer en modo nativo, consulte:

- [Información general sobre el modo nativo de Yammer en Microsoft 365](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode)
- [Configurar su red de Yammer para el Modo nativo para Microsoft 365](https://docs.microsoft.com/yammer/configure-your-yammer-network/native-mode)

## <a name="step-5-required-create-a-communication-compliance-policy"></a>Paso 5 (obligatorio): crear una directiva de cumplimiento de la comunicación
  
>[!Important]
>No se admite el uso de PowerShell para crear y administrar directivas de cumplimiento de comunicaciones. Para crear y administrar estas directivas, debe usar los controles de administración de directivas de la [solución Microsoft 365 Communication Compliance](https://compliance.microsoft.com/supervisoryreview).

1. Inicie sesión [https://compliance.microsoft.com](https://compliance.microsoft.com) con las credenciales de una cuenta de administrador en la organización de Microsoft 365.

2. En el centro de cumplimiento de Microsoft 365, seleccione **cumplimiento de comunicaciones**.
  
3. Seleccione la pestaña **directivas** .

4. Seleccione **crear Directiva** para crear y configurar una nueva Directiva a partir de una plantilla o para crear y configurar una directiva personalizada.

    Si elige una plantilla de directiva para crear una directiva, deberá:

    - Confirme o actualice el nombre de la Directiva. Los nombres de las directivas no se pueden cambiar una vez creada la Directiva.
    
    - Elija los usuarios o grupos que desea supervisar, incluida la elección de los usuarios o grupos que quiera excluir.
    
    - Elija los revisores para la Directiva. Los revisores son usuarios individuales y todos los revisores deben tener buzones hospedados en Exchange Online. Los revisores agregados aquí son los revisores que puede elegir al escalar una alerta en el flujo de trabajo de investigación y corrección. Cuando se agregan revisores a una directiva, reciben automáticamente un mensaje de correo electrónico que les notifica la asignación a la Directiva y proporciona vínculos a la información sobre el proceso de revisión.
    
    - Elija un campo de condición limitada, normalmente un tipo de información confidencial o un diccionario de palabras clave que se aplicará a la Directiva.

    Si decide usar el Asistente para directivas para crear una directiva personalizada, deberá:

    - Asigne un nombre y una descripción a la Directiva. Los nombres de las directivas no se pueden cambiar una vez creada la Directiva.
    
    - Elija los usuarios o grupos que desea supervisar, incluidos todos los usuarios de la organización, usuarios y grupos específicos, u otros usuarios y grupos que quiera excluir.
    
    - Elija los revisores para la Directiva. Los revisores son usuarios individuales y todos los revisores deben tener buzones hospedados en Exchange Online. Los revisores agregados aquí son los revisores que puede elegir al escalar una alerta en el flujo de trabajo de investigación y corrección. Cuando se agregan revisores a una directiva, reciben automáticamente un mensaje de correo electrónico que les notifica la asignación a la Directiva y proporciona vínculos a la información sobre el proceso de revisión.
    
    - Elija los canales de comunicación para analizar, incluidos Exchange, Microsoft Teams, Yammer o Skype empresarial. También elige analizar los orígenes de terceros si ha configurado un conector en Microsoft 365.
    
    - Elija la dirección de comunicación que se va a supervisar, incluidas las comunicaciones entrantes, salientes o internas.
    
    - Definir las [condiciones](communication-compliance-feature-reference.md#ConditionalSettings)de la Directiva de cumplimiento de comunicaciones. Puede elegir entre la dirección del mensaje, la palabra clave, los tipos de archivo y las condiciones de coincidencia de tamaño.
    
    - Elija si le gustaría incluir tipos de información confidencial. En este paso puede seleccionar los tipos de información confidencial predeterminada y personalizado. Elija entre los tipos de información confidencial existentes o los diccionarios de palabras clave personalizados en el Asistente para la Directiva de cumplimiento de comunicaciones. Puede crear estos elementos antes de ejecutar el asistente si es necesario. También puede crear nuevos tipos de información confidencial desde el Asistente para directivas de cumplimiento de comunicaciones.
    
    - Elija si le gustaría habilitar los clasificadores. Los clasificadores pueden detectar lenguaje e imágenes inapropiados que se envían o reciben en el cuerpo de los mensajes de correo electrónico u otros tipos de texto. Puede elegir los siguientes clasificadores integrados: *amenaza*, *blasfemia*, *acoso dirigido*, *imágenes para adultos*, imágenes de *racy* e imágenes de *Gory*.

      > [!CAUTION]
      > Estamos desaprobando el clasificador incorporado de **Lenguaje ofensivo** porque ha estado produciendo un alto número de falsos positivos. No lo use y, si actualmente lo está usando, debería mover sus procesos de negocio fuera de él. En su lugar, se recomienda usar en su lugar los clasificadores integrados **Threats**, **blasfemias** y los de **acoso específicos** .

    - Definir el porcentaje de comunicaciones que se van a revisar.
    
    - Revise las selecciones de la Directiva y cree la Directiva.

5. Seleccione **crear Directiva** al usar las plantillas o **Enviar** cuando se use el Asistente para directivas personalizadas.

6. La página se **ha creado la Directiva** se muestra con instrucciones sobre cuándo se activará la Directiva y qué comunicaciones se capturarán.

## <a name="step-6-optional-create-notice-templates-and-configure-user-anonymization"></a>Paso 6 (opcional): crear plantillas de aviso y configurar anonymization de usuario

Si desea tener la opción de responder a una alerta de Directiva mediante el envío de un aviso de aviso al usuario asociado, deberá crear al menos una plantilla de aviso en la organización. Los campos de plantilla de aviso son editables antes de que se envíen como parte del proceso de corrección de alertas y se recomienda crear una plantilla de notificación personalizada para cada directiva de cumplimiento de la comunicación.

También puede optar por habilitar anonymization para los nombres de usuario mostrados al investigar las coincidencias de directivas y realizar acciones en los mensajes.

1. Inicie sesión [https://compliance.microsoft.com](https://compliance.microsoft.com) con las credenciales de una cuenta de administrador en la organización de Microsoft 365.

2. En el centro de cumplimiento de Microsoft 365, vaya a **cumplimiento de comunicaciones**.

3. Para configurar anonymization para los nombres de usuario, seleccione la pestaña **privacidad** .

4. Para habilitar anonymization, seleccione **Mostrar anonimizan versiones de los nombres de usuario**.

5. Seleccione **Guardar**.

6. Vaya a la ficha **plantillas de notificación** y, a continuación, seleccione **Crear plantilla de notificación**.

7. En la página **modificar una plantilla de notificación** , complete los campos siguientes:

    - Nombre de plantilla (obligatorio)
    - Enviar desde (obligatorio)
    - CC y CCO (opcional)
    - Asunto (obligatorio)
    - Cuerpo del mensaje (obligatorio)

8. Seleccione **Guardar** para crear y guardar la plantilla de aviso.

## <a name="step-7-optional-test-your-communication-compliance-policy"></a>Paso 7 (opcional): probar la Directiva de cumplimiento de la comunicación

Después de crear una directiva de cumplimiento de comunicaciones, es una buena idea probarla para asegurarse de que la Directiva aplica correctamente las condiciones definidas. Es posible que también desee [probar sus directivas de prevención de pérdida de datos (DLP)](create-test-tune-dlp-policy.md) si las directivas de cumplimiento de comunicaciones incluyen tipos de información confidencial. Asegúrese de dar tiempo a las directivas de activación para que se capturen las comunicaciones que desea probar.

Siga estos pasos para probar la Directiva de cumplimiento de la comunicación:

1. Abra un cliente de correo electrónico, Microsoft Teams o Yammer mientras ha iniciado sesión como un usuario supervisado definido en la Directiva que desea probar.

2. Envíe un correo electrónico, un chat de Microsoft Teams o un mensaje de Yammer que cumpla los criterios que haya definido en la Directiva de cumplimiento de la comunicación. Esta prueba puede ser una palabra clave, el tamaño de los datos adjuntos, el dominio, etc. Asegúrese de determinar si la configuración condicional configurada en la Directiva es demasiado restrictiva o demasiado flexible.

    > [!NOTE]
    > Los mensajes de correo electrónico pueden tardar hasta 24 horas en procesarse por completo en una directiva. Las comunicaciones de Microsoft Teams, Yammer y las plataformas de terceros pueden tardar hasta 48 horas en procesarse completamente en una directiva.

3. Inicie sesión en Microsoft 365 como revisor designado en la Directiva de cumplimiento de la comunicación. Navegue a **Communication compliance**  >  **alertas** de cumplimiento de comunicaciones para ver las alertas de las directivas.

4. Corrija la alerta con los controles de corrección y compruebe que la alerta se haya resuelto correctamente.

## <a name="next-steps"></a>Pasos siguientes

Una vez que haya completado estos pasos para crear su primera Directiva de cumplimiento de comunicaciones, empezará a recibir alertas de los indicadores de actividad tras 24-48 horas. Configure directivas adicionales según sea necesario siguiendo las instrucciones del paso 5 de este artículo.

Para obtener más información sobre cómo investigar las alertas de cumplimiento de comunicaciones, consulte [investigar y corregir las alertas de cumplimiento de comunicaciones](communication-compliance-investigate-remediate.md).
