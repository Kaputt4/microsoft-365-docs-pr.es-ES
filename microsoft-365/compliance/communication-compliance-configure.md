---
title: Introducción al cumplimiento de las comunicaciones
description: Configurar directivas de cumplimiento de comunicaciones para configurar las comunicaciones de los usuarios para su revisión.
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
ms.openlocfilehash: 442f0dd13415c4ca435cdf69336d1fb07a9e045d
ms.sourcegitcommit: fa5659cb66d84dcfeebc03b47bd9d38017d8934d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2021
ms.locfileid: "50109929"
---
# <a name="get-started-with-communication-compliance"></a>Introducción al cumplimiento de las comunicaciones

Use directivas de cumplimiento de comunicaciones para identificar las comunicaciones de los usuarios para su examen por parte de revisores internos o externos. Para obtener más información acerca de cómo las directivas de cumplimiento de comunicaciones pueden ayudarle a supervisar las comunicaciones de su organización, vea directivas de cumplimiento de [comunicaciones en Microsoft 365.](communication-compliance.md) Si desea revisar cómo Contoso configuró rápidamente una directiva de cumplimiento de comunicaciones para supervisar el lenguaje ofensivo en las comunicaciones de Microsoft Teams, Exchange Online y Yammer, consulte este [caso](communication-compliance-case-study.md)práctico.

## <a name="subscriptions-and-licensing"></a>Suscripciones y licencias

Antes de empezar con el cumplimiento de las comunicaciones, debe confirmar su suscripción a [Microsoft 365](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) y cualquier complemento. Para acceder y usar el cumplimiento de las comunicaciones, la organización debe tener una de las siguientes suscripciones o complementos:

- Suscripción a Microsoft 365 E5 (versión de pago o de prueba)
- Suscripción a Microsoft 365 E3 + el complemento de cumplimiento de Microsoft 365 E5
- Suscripción a Microsoft 365 E3 + el complemento De administración de riesgos de Microsoft 365 E5 Insider
- Suscripción a Microsoft 365 A5 (versión de pago o de prueba)
- Suscripción a Microsoft 365 A3 + el complemento de cumplimiento de Microsoft 365 A5
- Suscripción a Microsoft 365 A3 + el complemento De administración de riesgos de Microsoft 365 A5 Insider
- Suscripción a Microsoft 365 G5 (versión de pago o de prueba)
- Suscripción a Microsoft 365 G5 + el complemento de cumplimiento de Microsoft 365 G5
- Suscripción a Microsoft 365 G5 + el complemento De administración de riesgos de Microsoft 365 G5 Insider
- Suscripción a Office 365 Enterprise E5 (versión de pago o de prueba)
- Suscripción a Office 365 A5 (versión de pago o de prueba)
- Suscripción a Office 365 Enterprise E3 + el complemento de cumplimiento avanzado de Office 365 (ya no está disponible para nuevas suscripciones, vea la nota)

Los usuarios incluidos en las directivas de cumplimiento de comunicaciones deben tener asignada una de las licencias anteriores.

>[!IMPORTANT]
>El cumplimiento avanzado de Office 365 ya no se vende como suscripción independiente. Cuando expiran las suscripciones actuales, los clientes deben realizar la transición a una de las suscripciones anteriores, que contienen las mismas características de cumplimiento o características adicionales.

Si no tiene un plan existente de Office 365 Enterprise E5 y quiere probar el cumplimiento de las comunicaciones, puede agregar [Microsoft 365](/office365/admin/try-or-buy-microsoft-365) [a](https://www.microsoft.com/microsoft-365/enterprise) su suscripción existente o registrarse para una prueba de Office 365 Enterprise E5.

## <a name="step-1-required-enable-permissions-for-communication-compliance"></a>Paso 1 (obligatorio): Habilitar permisos para el cumplimiento de las comunicaciones

>[!Important]
>De forma predeterminada, los administradores globales no tienen acceso a las características de cumplimiento de comunicaciones. Los roles asignados en este paso son necesarios antes de que se pueda acceder a las características de cumplimiento de comunicaciones. Después de configurar los grupos de roles, los permisos del grupo de roles pueden tardar hasta 30 minutos en aplicarse a los usuarios asignados en toda la organización.

Hay cinco grupos de roles que se usan para configurar permisos para administrar las características de cumplimiento de comunicaciones. Para que el cumplimiento de comunicaciones esté disponible como opción de menú en el Centro  de cumplimiento  de Microsoft 365 y para continuar con estos pasos de configuración, debe estar asignado a los grupos de roles Cumplimiento de comunicaciones o Administrador de cumplimiento de comunicaciones.  Para obtener acceso a las características de cumplimiento de comunicaciones y administrarlas después de la configuración inicial, los usuarios deben ser miembros de al menos un grupo de roles de cumplimiento de comunicaciones.

Dependiendo de cómo quiera administrar las directivas y alertas de comunicación, deberá asignar usuarios a grupos de roles específicos. Tiene la opción de asignar usuarios con diferentes responsabilidades de cumplimiento a grupos de roles específicos para administrar diferentes áreas de características de cumplimiento de comunicaciones. O puede decidir asignar todas las cuentas de usuario para administradores designados, analistas, investigadores y visores al grupo de roles *Cumplimiento de* comunicaciones. Use un único grupo de roles o varios grupos de roles para ajustarse mejor a sus requisitos de administración de cumplimiento.

Elija entre estas opciones de grupo de roles al configurar el cumplimiento de las comunicaciones:

| Role | Permisos de funciones |
|:-----|:-----|
| **Cumplimiento de comunicaciones** | Use este grupo de roles para administrar el cumplimiento de las comunicaciones de su organización en un solo grupo. Al agregar todas las cuentas de usuario para administradores, analistas, investigadores y visores designados, puede configurar los permisos de cumplimiento de comunicaciones en un solo grupo. Este grupo de roles contiene todas las funciones de permisos de cumplimiento de comunicaciones. Esta configuración es la forma más sencilla de empezar rápidamente con el cumplimiento de las comunicaciones y es una buena opción para las organizaciones que no necesitan permisos independientes definidos para grupos de usuarios independientes. |
| **Administrador de cumplimiento de comunicaciones** | Use este grupo de roles para configurar inicialmente el cumplimiento de las comunicaciones y, posteriormente, separar a los administradores de cumplimiento de comunicaciones en un grupo definido. Los usuarios asignados a este grupo de roles pueden crear, leer, actualizar y eliminar directivas de cumplimiento de comunicaciones, configuraciones globales y asignaciones de grupos de roles. Los usuarios asignados a este grupo de roles no pueden ver alertas de mensajes. |
| **Analista de cumplimiento de comunicaciones** | Use este grupo para asignar permisos a los usuarios que actuarán como analistas de cumplimiento de comunicaciones. Los usuarios asignados a este grupo de roles pueden ver directivas donde se asignan como revisores, ver metadatos de mensajes (no contenido del mensaje), escalar a revisores adicionales o enviar notificaciones a los usuarios. Los analistas no pueden resolver alertas pendientes. |
| **Investigador de cumplimiento de comunicaciones** | Use este grupo para asignar permisos a los usuarios que actuarán como investigadores de cumplimiento de comunicaciones. Los usuarios asignados a este grupo de roles pueden ver los metadatos y el contenido de los mensajes, escalar a revisores adicionales, escalar a un caso de eDiscovery avanzado, enviar notificaciones a los usuarios y resolver la alerta. |
| **Visor de cumplimiento de comunicaciones** | Use este grupo para asignar permisos a los usuarios que administrarán informes de comunicación. Los usuarios asignados a este grupo de roles pueden acceder a todos los widgets de informes en la página principal de cumplimiento de comunicaciones y ver todos los informes de cumplimiento de comunicaciones. |

### <a name="option-1-assign-all-compliance-users-to-the-communication-compliance-role-group"></a>Opción 1: Asignar todos los usuarios de cumplimiento al grupo de roles Cumplimiento de comunicaciones

1. Inicie sesión [https://protection.office.com/permissions](https://protection.office.com/permissions) con las credenciales de una cuenta de administrador de su organización de Microsoft 365.

2. En el Centro &amp; de cumplimiento de seguridad, vaya a **Permisos.** Seleccione el vínculo para ver y administrar roles en Office 365.

3. Seleccione el grupo *de roles Cumplimiento de* comunicaciones y, a continuación, seleccione Editar grupo de **roles.**

4. Seleccione **Elegir miembros** en el panel de navegación izquierdo y, a continuación, seleccione **Editar**.

5. Seleccione **Agregar** y, a continuación, active la casilla para todos los usuarios que desee agregar al grupo de roles *Cumplimiento de* comunicaciones.

6. Seleccione **Agregar** y, a continuación, **seleccione Listo.**

7. Seleccione **Guardar** para agregar los usuarios al grupo de roles. Seleccione **Cerrar** para completar los pasos

### <a name="option-2-assign-users-to-specific-communication-compliance-role-groups"></a>Opción 2: Asignar usuarios a grupos de roles de cumplimiento de comunicaciones específicos

Use esta opción para asignar usuarios a grupos de roles específicos para segmentar el acceso y las responsabilidades de cumplimiento de comunicaciones entre los distintos usuarios de la organización.

1. Inicie sesión [https://protection.office.com/permissions](https://protection.office.com/permissions) con las credenciales de una cuenta de administrador de su organización de Microsoft 365.

2. En el Centro &amp; de cumplimiento de seguridad, vaya a **Permisos.** Seleccione el vínculo para ver y administrar roles en Office 365.

3. Seleccione uno de los grupos de roles de cumplimiento de comunicaciones y, a continuación, **seleccione Editar grupo de roles.**

4. Seleccione **Elegir miembros** en el panel de navegación izquierdo y, a continuación, seleccione **Editar**.

5. Seleccione **Agregar** y, a continuación, active la casilla para todos los usuarios que desee agregar al grupo de roles.

6. Seleccione **Agregar** y, a continuación, **seleccione Listo.**

7. Seleccione **Guardar** para agregar los usuarios al grupo de roles.

8. Seleccione el siguiente grupo de roles de cumplimiento de comunicaciones y repita los pasos del 4 al 7 para cada grupo de roles necesario.

9. Seleccione **Cerrar** para completar los pasos.

Para obtener más información acerca de los grupos de roles y los permisos, vea [Permisos en el Centro de cumplimiento.](../security/office-365-security/protect-against-threats.md)

## <a name="step-2-required-enable-the-audit-log"></a>Paso 2 (obligatorio): Habilitar el registro de auditoría

El cumplimiento de las comunicaciones requiere registros de auditoría para mostrar alertas y realizar un seguimiento de las acciones de corrección realizadas por los revisores. Los registros de auditoría son un resumen de todas las actividades asociadas a una directiva organizativa definida o en cualquier momento en que cambie una directiva de cumplimiento de comunicaciones.

Para obtener instrucciones paso a paso para activar la auditoría, vea Activar o desactivar la búsqueda del registro [de auditoría.](turn-audit-log-search-on-or-off.md) Después de activar la auditoría, se muestra un mensaje que indica que el registro de auditoría se está preparando y que puede ejecutar una búsqueda en un par de horas después de que se complete la preparación. Solo tiene que realizar esta acción una vez. Para obtener más información acerca del uso del registro de auditoría, vea [Buscar en el registro de auditoría.](search-the-audit-log-in-security-and-compliance.md)

## <a name="step-3-optional-set-up-groups-for-communication-compliance"></a>Paso 3 (opcional): Configurar grupos para el cumplimiento de las comunicaciones

 Al crear una directiva de cumplimiento de comunicaciones, se define quién tiene sus comunicaciones revisadas y quién realiza revisiones. En la directiva, usará direcciones de correo electrónico para identificar a personas o grupos de personas. Para simplificar la configuración, puede crear grupos para las personas que tienen sus comunicaciones revisadas y grupos para las personas que revisan dichas comunicaciones. Si usa grupos, es posible que necesite varios. Por ejemplo, si desea supervisar las comunicaciones entre dos grupos distintos de personas o si desea especificar un grupo que no se va a supervisar.

Use el siguiente gráfico para configurar grupos en su organización para las directivas de cumplimiento de comunicaciones:

| **Miembro de directiva** | **Grupos admitidos** | **Grupos no admitidos** |
|:-----|:-----|:-----|
|Usuarios supervisados <br> Usuarios no supervisados | Grupos de distribución <br> Grupos de Microsoft 365 | Grupos de distribución dinámicos <br> Grupos de distribución anidados <br> Grupos de seguridad habilitados para correo |
| Reviewers | Ninguno | Grupos de distribución <br> Grupos de distribución dinámicos <br> Grupos de distribución anidados <br> Grupos de seguridad habilitados para correo |
  
Cuando asigna un grupo de distribución en la directiva, la directiva supervisa todos los correos electrónicos y chats de Teams de cada usuario del grupo de distribución. Cuando asigna un grupo de Microsoft 365 en la directiva, la directiva supervisa todos los correos electrónicos y chats de Teams enviados a ese grupo, no los correos electrónicos y chats individuales recibidos por cada miembro del grupo.

Si es una organización con una implementación local de Exchange o un proveedor de correo electrónico externo y desea supervisar los chats de Microsoft Teams para sus usuarios, debe crear un grupo de distribución para que los usuarios con buzones locales o externos supervisen. Más adelante en estos pasos, asignará  este grupo de distribución como la selección de usuarios y grupos supervisados en el asistente para directivas.

>[!IMPORTANT]
>Debe presentar una solicitud al Soporte técnico de Microsoft para que su organización pueda utilizar la interfaz gráfica de usuario en el Centro de seguridad y cumplimiento para buscar datos de chat de Teams de usuarios locales. Para obtener más información, consulte Buscar buzones [basados en la nube para usuarios locales.](search-cloud-based-mailboxes-for-on-premises-users.md)

Para administrar usuarios supervisados en grandes organizaciones empresariales, es posible que deba supervisar todos los usuarios en grupos grandes. Puede usar PowerShell para configurar un grupo de distribución para una directiva de cumplimiento de comunicaciones global para el grupo asignado. Esto le permite supervisar a miles de usuarios con una única directiva y mantener actualizada la directiva de cumplimiento de comunicaciones a medida que los nuevos empleados se unan a su organización.

1. Cree un grupo de [distribución](/powershell/module/exchange/new-distributiongroup) dedicado para la directiva de cumplimiento de comunicaciones global con las siguientes propiedades: asegúrese de que este grupo de distribución no se usa para otros fines u otros servicios de Office 365.

    - **MemberDepartRestriction = Closed**. Garantiza que los usuarios no se puedan quitar del grupo de distribución.
    - **MemberJoinRestriction = Closed**. Garantiza que los usuarios no puedan agregarse al grupo de distribución.
    - **ModerationEnabled = True**. Garantiza que todos los mensajes enviados a este grupo están sujetos a aprobación y que el grupo no se usa para comunicarse fuera de la configuración de directiva de cumplimiento de comunicaciones.

    ```PowerShell
    New-DistributionGroup -Name <your group name> -Alias <your group alias> -MemberDepartRestriction 'Closed' -MemberJoinRestriction 'Closed' -ModerationEnabled $true
    ```

2. Seleccione un atributo personalizado de [Exchange sin usar para](/Exchange/recipients/mailbox-custom-attributes) realizar un seguimiento de los usuarios agregados a la directiva de cumplimiento de comunicaciones de su organización.

3. Ejecute el siguiente script de PowerShell en una programación periódica para agregar usuarios a la directiva de cumplimiento de comunicaciones:

    ```PowerShell
    $Mbx = (Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited -Filter {CustomAttribute9 -eq $Null})
    $i = 0
    ForEach ($M in $Mbx) 
    {
      Write-Host "Adding" $M.DisplayName
      Add-DistributionGroupMember -Identity <your group name> -Member $M.DistinguishedName -ErrorAction SilentlyContinue
      Set-Mailbox -Identity $M.Alias -<your custom attribute name> SRAdded 
      $i++
    }
    Write-Host $i "Mailboxes added to supervisory review distribution group."
    ```

Para obtener más información acerca de la configuración de grupos, vea:

- [Crear y administrar grupos de distribución](/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [Introducción a los grupos de Microsoft 365](/office365/admin/create-groups/office-365-groups)

## <a name="step-4-optional-verify-your-yammer-tenant-is-in-native-mode"></a>Paso 4 (opcional): Comprobar que el inquilino de Yammer está en modo nativo

En el modo nativo, todos los usuarios de Yammer están en Azure Active Directory (Azure AD), todos los grupos son Grupos de Office 365 y todos los archivos se almacenan en SharePoint Online. Su espacio empresarial de Yammer debe estar en modo nativo para que las directivas de cumplimiento de comunicaciones analicen e identifiquen conversaciones de riesgo en mensajes privados y conversaciones de la comunidad en Yammer.

Para obtener más información acerca de la configuración de Yammer en modo nativo, vea:

- [Información general sobre el modo nativo de Yammer en Microsoft 365](/yammer/configure-your-yammer-network/overview-native-mode)
- [Configurar su red de Yammer para el Modo nativo para Microsoft 365](/yammer/configure-your-yammer-network/native-mode)

## <a name="step-5-required-create-a-communication-compliance-policy"></a>Paso 5 (obligatorio): Crear una directiva de cumplimiento de comunicaciones
  
>[!Important]
>No se admite el uso de PowerShell para crear y administrar directivas de cumplimiento de comunicaciones. Para crear y administrar estas directivas, debe usar los controles de administración de directivas en la solución de cumplimiento de comunicaciones [de Microsoft 365.](https://compliance.microsoft.com/supervisoryreview)

1. Inicie sesión [https://compliance.microsoft.com](https://compliance.microsoft.com) con las credenciales de una cuenta de administrador de su organización de Microsoft 365.

2. En el Centro de cumplimiento de Microsoft 365, seleccione **Cumplimiento de comunicaciones.**
  
3. Seleccione la **pestaña** Directivas.

4. Seleccione **Crear directiva** para crear y configurar una nueva directiva a partir de una plantilla o para crear y configurar una directiva personalizada.

    Si elige una plantilla de directiva para crear una directiva, hará lo siguiente:

    - Confirme o actualice el nombre de la directiva. Los nombres de directiva no se pueden cambiar una vez creada la directiva.
    
    - Elija los usuarios o grupos que desea supervisar, incluida la elección de usuarios o grupos que quiera excluir. Al usar la plantilla de conflicto de interés, seleccionará dos grupos o dos usuarios para supervisar las comunicaciones internas.
    
    - Elija los revisores de la directiva. Los revisores son usuarios individuales y todos los revisores deben tener buzones hospedados en Exchange Online. Los revisores agregados aquí son los revisores que puede elegir al escalar una alerta en el flujo de trabajo de investigación y corrección. Cuando se agregan revisores a una directiva, reciben automáticamente un mensaje de correo electrónico que les notifica la asignación a la directiva y proporciona vínculos a información sobre el proceso de revisión.
    
    - Elija un campo de condición limitado, normalmente un tipo de información confidencial o un diccionario de palabras clave para aplicar a la directiva.

    Si decide usar el Asistente para directivas para crear una directiva personalizada, hará lo siguiente:

    - Asigne un nombre y una descripción a la directiva. Los nombres de directiva no se pueden cambiar una vez que se crea la directiva.
    
    - Elija los usuarios o grupos que desea supervisar, incluidos todos los usuarios de su organización, usuarios y grupos específicos, u otros usuarios y grupos que quiera excluir.
    
    - Elija los revisores de la directiva. Los revisores son usuarios individuales y todos los revisores deben tener buzones hospedados en Exchange Online. Los revisores agregados aquí son los revisores que puede elegir al escalar una alerta en el flujo de trabajo de investigación y corrección. Cuando se agregan revisores a una directiva, reciben automáticamente un mensaje de correo electrónico que les notifica la asignación a la directiva y proporciona vínculos a información sobre el proceso de revisión.
    
    - Elija los canales de comunicación que desea analizar, incluidos Exchange, Microsoft Teams, Yammer o Skype Empresarial. También elegirá examinar orígenes de terceros si ha configurado un conector en Microsoft 365.
    
    - Elija la dirección de comunicación que desea supervisar, incluidas las comunicaciones entrantes, salientes o internas.
    
    - Definir las condiciones de la directiva de cumplimiento de [comunicaciones.](communication-compliance-feature-reference.md#ConditionalSettings) Puede elegir entre la dirección del mensaje, la palabra clave, los tipos de archivo y las condiciones de coincidencia de tamaño.
    
    - Elija si desea incluir tipos de información confidencial. Este paso es donde puede seleccionar tipos de información confidencial predeterminados y personalizados. Elija entre tipos de información confidencial personalizados existentes o diccionarios de palabras clave personalizadas en el Asistente para directivas de cumplimiento de comunicaciones. Puede crear estos elementos antes de ejecutar el asistente si es necesario. También puede crear nuevos tipos de información confidencial desde el Asistente para directivas de cumplimiento de comunicaciones.
    
    - Elige si quieres habilitar clasificadores. Los clasificadores pueden detectar el idioma inapropiado y las imágenes enviadas o recibidas en el cuerpo de los mensajes de correo electrónico u otros tipos de texto. Puede elegir los siguientes clasificadores *integrados:* Amenaza *,* blasfedad *,* acoso *dirigido,* imágenes para adultos, imágenes *racy* e *imágenes gory*.

      > [!CAUTION]
      > Estamos desaprobando el clasificador incorporado de **Lenguaje ofensivo** porque ha estado produciendo un alto número de falsos positivos. No lo use y, si actualmente lo está usando, debe quitar los procesos de negocio. Se recomienda usar en **su** lugar  **los** clasificadores integrados Amenaza, Blasfez y Hostigamiento dirigido.

    - Definir el porcentaje de comunicaciones que se revisarán.
    
    - Revisa las selecciones de directiva y crea la directiva.

5. Seleccione **Crear directiva** al usar las plantillas o **Enviar** al usar el Asistente para directivas personalizadas.

6. La **página Su directiva se creó** con instrucciones sobre cuándo se activará la directiva y qué comunicaciones se capturarán.

## <a name="step-6-optional-create-notice-templates-and-configure-user-anonymization"></a>Paso 6 (opcional): Crear plantillas de aviso y configurar el anonimización de usuarios

Si desea tener la opción de responder a una alerta de directiva enviando un aviso al usuario asociado, deberá crear al menos una plantilla de aviso en su organización. Los campos de plantilla de aviso son editables antes de que se envíen como parte del proceso de corrección de alertas y se recomienda crear una plantilla de aviso personalizada para cada directiva de cumplimiento de comunicaciones.

También puedes habilitar la anonimización para los nombres de usuario mostrados al investigar coincidencias de directivas y tomar medidas en los mensajes.

1. Inicie sesión [https://compliance.microsoft.com](https://compliance.microsoft.com) con las credenciales de una cuenta de administrador de su organización de Microsoft 365.

2. En el Centro de cumplimiento de Microsoft 365, vaya a **Cumplimiento de comunicaciones.**

3. Para configurar la anonimización de nombres de usuario, seleccione la **pestaña** Privacidad.

4. Para habilitar la anonimización, seleccione **Mostrar versiones anónimas de nombres de usuario.**

5. Haga clic en **Guardar**.

6. Vaya a la pestaña **Plantillas de** aviso y, a continuación, seleccione Crear plantilla **de aviso.**

7. En la **página Modificar una plantilla de aviso,** complete los siguientes campos:

    - Nombre de plantilla (obligatorio)
    - Enviar desde (obligatorio)
    - CC y CCO (opcional)
    - Asunto (obligatorio)
    - Cuerpo del mensaje (obligatorio)

8. Seleccione **Guardar para** crear y guardar la plantilla de aviso.

## <a name="step-7-optional-test-your-communication-compliance-policy"></a>Paso 7 (opcional): Probar la directiva de cumplimiento de comunicaciones

Después de crear una directiva de cumplimiento de comunicaciones, es una buena idea probarla para asegurarse de que la directiva aplica correctamente las condiciones definidas. También puede probar las directivas de prevención de pérdida de datos [(DLP)](create-test-tune-dlp-policy.md) si las directivas de cumplimiento de comunicaciones incluyen tipos de información confidencial. Asegúrese de dar tiempo a las directivas para que se activen de modo que se capturan las comunicaciones que desea probar.

Siga estos pasos para probar la directiva de cumplimiento de comunicaciones:

1. Abra un cliente de correo electrónico, Microsoft Teams o Yammer mientras ha iniciado sesión como un usuario supervisado definido en la directiva que desea probar.

2. Envíe un mensaje de correo electrónico, chat de Microsoft Teams o Yammer que cumpla con los criterios definidos en la directiva de cumplimiento de comunicaciones. Esta prueba puede ser una palabra clave, un tamaño de datos adjuntos, un dominio, etc. Asegúrese de determinar si la configuración condicional configurada en la directiva es demasiado restrictiva o demasiado lenienta.

    > [!NOTE]
    > Los mensajes de correo electrónico pueden tardar hasta 24 horas en procesarse completamente en una directiva. Las comunicaciones en plataformas de Microsoft Teams, Yammer y de terceros pueden tardar hasta 48 horas en procesarse completamente en una directiva.

3. Inicie sesión en Microsoft 365 como revisor designado en la directiva de cumplimiento de comunicaciones. Vaya a **Alertas de cumplimiento**  >  **de** comunicaciones para ver las alertas de las directivas.

4. Corrija la alerta con los controles de corrección y compruebe que la alerta se ha resuelto correctamente.

## <a name="next-steps"></a>Pasos siguientes

Después de completar estos pasos para crear la primera directiva de cumplimiento de comunicaciones, empezará a recibir alertas de indicadores de actividad después de 24-48 horas. Configure directivas adicionales según sea necesario con las instrucciones del paso 5 de este artículo.

Para obtener más información sobre cómo investigar alertas de cumplimiento de comunicaciones, vea Investigar y corregir alertas de cumplimiento [de comunicaciones.](communication-compliance-investigate-remediate.md)
