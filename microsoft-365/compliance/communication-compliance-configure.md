---
title: Introducción al cumplimiento de las comunicaciones
description: Configurar directivas de cumplimiento de comunicaciones para configurar las comunicaciones de usuario para su revisión.
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
ms.openlocfilehash: 3e84c3266dd802fb6cab12db0c20773838b4e2a9
ms.sourcegitcommit: b169f6ad3e44a7fcebf77f43be9eb5edd84ea5ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2021
ms.locfileid: "52077193"
---
# <a name="get-started-with-communication-compliance"></a>Introducción al cumplimiento de las comunicaciones

Use directivas de cumplimiento de comunicaciones para identificar las comunicaciones de los usuarios para su examen por revisores internos o externos. Para obtener más información acerca de cómo las directivas de cumplimiento de comunicaciones pueden ayudarle a supervisar las comunicaciones en su organización, vea directivas de cumplimiento de comunicaciones [en Microsoft 365](communication-compliance.md). Si desea revisar cómo Contoso configuró rápidamente una directiva de cumplimiento de comunicaciones para supervisar el lenguaje ofensivo en las comunicaciones de Microsoft Teams, Exchange Online y Yammer, consulte este caso práctico [.](communication-compliance-case-study.md)

## <a name="subscriptions-and-licensing"></a>Suscripciones y licencias

Antes de empezar con el cumplimiento de las comunicaciones, debe confirmar su [Microsoft 365 suscripción y](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) cualquier complemento. Para obtener acceso y usar el cumplimiento de la comunicación, la organización debe tener una de las siguientes suscripciones o complementos:

- Microsoft 365 E5 suscripción (versión de pago o de prueba)
- Microsoft 365 E3 suscripción + el Cumplimiento de Microsoft 365 E5 complemento
- Microsoft 365 E3 suscripción + el Microsoft 365 E5 de Administración de riesgos de Insider
- Microsoft 365 Suscripción A5 (versión de pago o de prueba)
- Microsoft 365 Suscripción A3 + el complemento Microsoft 365 cumplimiento de A5
- Microsoft 365 Suscripción A3 + el complemento Microsoft 365 A5 Insider Risk Management
- Microsoft 365 Suscripción de G5 (versión de pago o de prueba)
- Microsoft 365 Suscripción de G5 + el Microsoft 365 de cumplimiento de G5
- Microsoft 365 Suscripción de G5 + el complemento Microsoft 365 G5 Insider Risk Management
- Office 365 Enterprise Suscripción E5 (versión de pago o de prueba)
- Office 365 A5 suscripción (versión de pago o de prueba)
- Office 365 Enterprise Suscripción E3 + Cumplimiento avanzado de Office 365 complemento (ya no está disponible para las nuevas suscripciones, vea la nota)

Los usuarios incluidos en las directivas de cumplimiento de comunicaciones deben tener asignada una de las licencias anteriores.

>[!IMPORTANT]
>Cumplimiento avanzado de Office 365 ya no se vende como una suscripción independiente. Cuando expiran las suscripciones actuales, los clientes deben realizar la transición a una de las suscripciones anteriores, que contienen las mismas o adicionales características de cumplimiento.

Si no tiene un plan de Office 365 Enterprise E5 existente y desea probar el cumplimiento de las comunicaciones, puede agregar [Microsoft 365](/office365/admin/try-or-buy-microsoft-365) [a](https://www.microsoft.com/microsoft-365/enterprise) la suscripción existente o registrarse para una prueba de Office 365 Enterprise E5.

## <a name="step-1-required-enable-permissions-for-communication-compliance"></a>Paso 1 (obligatorio): Habilitar permisos para el cumplimiento de comunicaciones

>[!Important]
>De forma predeterminada, los administradores globales no tienen acceso a las características de cumplimiento de la comunicación. Los roles asignados en este paso son necesarios antes de que se pueda acceder a las características de cumplimiento de comunicaciones. Después de configurar los grupos de roles, los permisos del grupo de roles pueden tardar hasta 30 minutos en aplicarse a los usuarios asignados en toda la organización.

Hay cinco grupos de roles que se usan para configurar permisos para administrar las características de cumplimiento de comunicaciones. Para que **el** cumplimiento de la comunicación esté disponible como una opción de menú en  el Centro de cumplimiento de Microsoft 365 y para continuar con estos pasos de configuración, debe asignarse a los grupos de roles Cumplimiento de comunicaciones o Administración de cumplimiento *de* comunicaciones. Para obtener acceso y administrar las características de cumplimiento de comunicaciones después de la configuración inicial, los usuarios deben ser miembros de al menos un grupo de roles de cumplimiento de comunicaciones.

Dependiendo de cómo desee administrar las directivas de comunicación y las alertas, deberá asignar usuarios a grupos de roles específicos. Tiene la opción de asignar usuarios con diferentes responsabilidades de cumplimiento a grupos de roles específicos para administrar diferentes áreas de características de cumplimiento de comunicación. O puede decidir asignar todas las cuentas de usuario para administradores, analistas, investigadores y visores designados al grupo de roles *Cumplimiento* de comunicaciones. Use un único grupo de roles o varios grupos de roles para ajustarse mejor a sus requisitos de administración de cumplimiento.

Elija entre estas opciones de grupo de roles al configurar el cumplimiento de la comunicación:

| Role | Permisos de funciones |
|:-----|:-----|
| **Cumplimiento de comunicaciones** | Use este grupo de roles para administrar el cumplimiento de comunicaciones de su organización en un solo grupo. Al agregar todas las cuentas de usuario para administradores designados, analistas, investigadores y visores, puede configurar los permisos de cumplimiento de comunicaciones en un solo grupo. Este grupo de funciones contiene todos los roles de permisos de cumplimiento de comunicación. Esta configuración es la forma más sencilla de empezar rápidamente con el cumplimiento de las comunicaciones y es una buena opción para las organizaciones que no necesitan permisos independientes definidos para grupos independientes de usuarios. |
| **Administrador de cumplimiento de comunicaciones** | Use este grupo de roles para configurar inicialmente el cumplimiento de las comunicaciones y posteriormente para segregar a los administradores de cumplimiento de comunicaciones en un grupo definido. Los usuarios asignados a este grupo de roles pueden crear, leer, actualizar y eliminar directivas de cumplimiento de comunicación, configuración global y asignaciones de grupos de roles. Los usuarios asignados a este grupo de roles no pueden ver alertas de mensajes. |
| **Analista de cumplimiento de comunicaciones** | Use este grupo para asignar permisos a los usuarios que actuarán como analistas de cumplimiento de comunicaciones. Los usuarios asignados a este grupo de roles pueden ver directivas en las que se les asigna como revisores, ver metadatos de mensajes (no contenido del mensaje), escalar a revisores adicionales o enviar notificaciones a los usuarios. Los analistas no pueden resolver alertas pendientes. |
| **Investigador de cumplimiento de comunicaciones** | Use este grupo para asignar permisos a los usuarios que actuarán como investigadores de cumplimiento de comunicaciones. Los usuarios asignados a este grupo de roles pueden ver los metadatos y el contenido de los mensajes, escalar a revisores adicionales, escalar a un caso Advanced eDiscovery, enviar notificaciones a los usuarios y resolver la alerta. |
| **Visor de cumplimiento de comunicaciones** | Use este grupo para asignar permisos a los usuarios que administrarán informes de comunicación. Los usuarios asignados a este grupo de roles pueden tener acceso a todos los widgets de informes de la página principal de cumplimiento de comunicaciones y pueden ver todos los informes de cumplimiento de comunicaciones. |

### <a name="option-1-assign-all-compliance-users-to-the-communication-compliance-role-group"></a>Opción 1: Asignar todos los usuarios de cumplimiento al grupo de roles Cumplimiento de comunicaciones

1. Inicie sesión [https://protection.office.com/permissions](https://protection.office.com/permissions) con las credenciales de una cuenta de administrador en su Microsoft 365 organización.

2. En el Centro &amp; de cumplimiento de seguridad, vaya a **Permisos**. Seleccione el vínculo para ver y administrar roles en Office 365.

3. Seleccione el grupo *de roles Cumplimiento* de comunicaciones y, a continuación, **edite el grupo de roles**.

4. Seleccione **Elegir miembros** en el panel de navegación izquierdo y, a continuación, seleccione **Editar**.

5. Seleccione **Agregar** y, a continuación, active la casilla para todos los usuarios que desee agregar al grupo de roles *Cumplimiento* de comunicaciones.

6. Seleccione **Agregar** y, después, **Listo**.

7. Seleccione **Guardar** para agregar los usuarios al grupo de roles. Seleccione **Cerrar** para completar los pasos

### <a name="option-2-assign-users-to-specific-communication-compliance-role-groups"></a>Opción 2: Asignar usuarios a grupos de roles de cumplimiento de comunicaciones específicos

Use esta opción para asignar usuarios a grupos de roles específicos para segmentar el acceso y las responsabilidades de cumplimiento de comunicaciones entre diferentes usuarios de la organización.

1. Inicie sesión [https://protection.office.com/permissions](https://protection.office.com/permissions) con las credenciales de una cuenta de administrador en su Microsoft 365 organización.

2. En el Centro &amp; de cumplimiento de seguridad, vaya a **Permisos**. Seleccione el vínculo para ver y administrar roles en Office 365.

3. Seleccione uno de los grupos de roles de cumplimiento de comunicación y, a continuación, **seleccione Editar grupo de funciones**.

4. Seleccione **Elegir miembros** en el panel de navegación izquierdo y, a continuación, seleccione **Editar**.

5. Seleccione **Agregar** y, a continuación, active la casilla para todos los usuarios que desee agregar al grupo de roles.

6. Seleccione **Agregar** y, después, **Listo**.

7. Seleccione **Guardar** para agregar los usuarios al grupo de roles.

8. Seleccione el siguiente grupo de roles de cumplimiento de comunicaciones y, a continuación, repita los pasos 4-7 para cada grupo de roles requerido.

9. Seleccione **Cerrar** para completar los pasos.

Para obtener más información acerca de los grupos de roles y los permisos, vea [Permisos en el Centro de cumplimiento](../security/office-365-security/protect-against-threats.md).

## <a name="step-2-required-enable-the-audit-log"></a>Paso 2 (obligatorio): Habilitar el registro de auditoría

El cumplimiento de la comunicación requiere registros de auditoría para mostrar alertas y realizar un seguimiento de las acciones de corrección realizadas por los revisores. Los registros de auditoría son un resumen de todas las actividades asociadas con una directiva organizativa definida o en cualquier momento en que cambie una directiva de cumplimiento de comunicación.

Para obtener instrucciones paso a paso para activar la auditoría, vea Activar o desactivar la búsqueda del [registro de auditoría.](turn-audit-log-search-on-or-off.md) Después de activar la auditoría, se muestra un mensaje que dice que el registro de auditoría se está preparando y que puede ejecutar una búsqueda en un par de horas después de que se complete la preparación. Solo tienes que hacer esta acción una vez. Para obtener más información acerca del uso del registro de auditoría, vea [Buscar en el registro de auditoría](search-the-audit-log-in-security-and-compliance.md).

## <a name="step-3-optional-set-up-groups-for-communication-compliance"></a>Paso 3 (opcional): Configurar grupos para el cumplimiento de las comunicaciones

 Al crear una directiva de cumplimiento de comunicaciones, se define quién tiene sus comunicaciones revisadas y quién realiza las revisiones. En la directiva, usarás direcciones de correo electrónico para identificar personas o grupos de personas. Para simplificar la configuración, puede crear grupos para personas que tienen sus comunicaciones revisadas y grupos para personas que revisan dichas comunicaciones. Si usa grupos, es posible que necesite varios. Por ejemplo, si desea supervisar las comunicaciones entre dos grupos distintos de personas o si desea especificar un grupo que no se va a supervisar.

Use el siguiente gráfico para ayudarle a configurar grupos en su organización para las directivas de cumplimiento de comunicaciones:

| **Miembro de la directiva** | **Grupos admitidos** | **Grupos no admitidos** |
|:-----|:-----|:-----|
|Usuarios supervisados <br> Usuarios no supervisados | Grupos de distribución <br> Grupos de Microsoft 365 | Grupos de distribución dinámicos <br> Grupos de distribución anidados <br> Grupos de seguridad habilitados para correo <br> Microsoft 365 grupos con pertenencia dinámica |
| Reviewers | Ninguno | Grupos de distribución <br> Grupos de distribución dinámicos <br> Grupos de distribución anidados <br> Grupos de seguridad habilitados para correo |
  
Al asignar un grupo de distribución en la directiva, la directiva supervisa todos los mensajes de correo electrónico y Teams chats de cada usuario del grupo de distribución. Al asignar un grupo de Microsoft 365 en la directiva, la directiva supervisa todos los mensajes de correo electrónico y los chats Teams enviados a ese grupo, no los correos electrónicos individuales y los chats recibidos por cada miembro del grupo.

Si es una organización con una implementación local de Exchange o un proveedor de correo electrónico externo y desea supervisar los chats de Microsoft Teams para los usuarios, debe crear un grupo de distribución para que los usuarios con buzones locales o externos supervisen. Más adelante en estos pasos, asignará  este grupo de distribución como la selección de usuarios y grupos supervisados en el asistente para directivas.

Para administrar usuarios supervisados en organizaciones empresariales grandes, es posible que deba supervisar todos los usuarios en grupos grandes. Puede usar PowerShell para configurar un grupo de distribución para una directiva de cumplimiento de comunicaciones global para el grupo asignado. Esto le permite supervisar a miles de usuarios con una única directiva y mantener actualizada la directiva de cumplimiento de comunicaciones a medida que los nuevos empleados se unan a su organización.

1. Cree un grupo [de distribución](/powershell/module/exchange/new-distributiongroup) dedicado para la directiva de cumplimiento de comunicaciones global con las siguientes propiedades: asegúrese de que este grupo de distribución no se usa para otros fines u otros servicios Office 365 de distribución.

    - **MemberDepartRestriction = Closed**. Garantiza que los usuarios no puedan quitarse del grupo de distribución.
    - **MemberJoinRestriction = Closed**. Garantiza que los usuarios no pueden agregarse al grupo de distribución.
    - **ModerationEnabled = True**. Garantiza que todos los mensajes enviados a este grupo estén sujetos a aprobación y que el grupo no se esté utilizando para comunicarse fuera de la configuración de directiva de cumplimiento de comunicaciones.

    ```PowerShell
    New-DistributionGroup -Name <your group name> -Alias <your group alias> -MemberDepartRestriction 'Closed' -MemberJoinRestriction 'Closed' -ModerationEnabled $true
    ```

2. Seleccione un atributo Exchange personalizado sin usar [para](/Exchange/recipients/mailbox-custom-attributes) realizar un seguimiento de los usuarios agregados a la directiva de cumplimiento de comunicaciones de su organización.

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
- [Información general sobre Microsoft 365 grupos](/office365/admin/create-groups/office-365-groups)

## <a name="step-4-optional-verify-your-yammer-tenant-is-in-native-mode"></a>Paso 4 (opcional): Comprobar que el espacio empresarial Yammer está en modo nativo

En el modo nativo, todos los Yammer están en Azure Active Directory (Azure AD), todos los grupos son grupos Office 365 y todos los archivos se almacenan en SharePoint Online. Su Yammer inquilino debe estar en modo nativo para que las directivas de cumplimiento de comunicación analicen e identifiquen conversaciones de riesgo en mensajes privados y conversaciones de la comunidad en Yammer.

Para obtener más información sobre cómo configurar Yammer en modo nativo, vea:

- [Información general Yammer modo nativo en Microsoft 365](/yammer/configure-your-yammer-network/overview-native-mode)
- [Configurar su red de Yammer para el Modo nativo para Microsoft 365](/yammer/configure-your-yammer-network/native-mode)

## <a name="step-5-required-create-a-communication-compliance-policy"></a>Paso 5 (obligatorio): crear una directiva de cumplimiento de comunicaciones
  
>[!Important]
>No se admite el uso de PowerShell para crear y administrar directivas de cumplimiento de comunicaciones. Para crear y administrar estas directivas, debe usar los controles de administración de directivas en la [Microsoft 365 de cumplimiento de comunicaciones](https://compliance.microsoft.com/supervisoryreview).

1. Inicie sesión [https://compliance.microsoft.com](https://compliance.microsoft.com) con las credenciales de una cuenta de administrador en su Microsoft 365 organización.

2. En el centro Microsoft 365 cumplimiento, seleccione **Cumplimiento de comunicaciones**.
  
3. Seleccione la **pestaña** Directivas.

4. Seleccione **Crear directiva** para crear y configurar una nueva directiva desde una plantilla o para crear y configurar una directiva personalizada.

    Si elige una plantilla de directiva para crear una directiva, hará lo siguiente:

    - Confirme o actualice el nombre de la directiva. Los nombres de directiva no se pueden cambiar una vez creada la directiva.

    - Elija los usuarios o grupos que desea supervisar, incluida la elección de usuarios o grupos que desea excluir. Al usar la plantilla de conflicto de intereses, seleccionará dos grupos o dos usuarios para supervisar las comunicaciones internas.

    - Elija los revisores de la directiva. Los revisores son usuarios individuales y todos los revisores deben tener buzones hospedados en Exchange Online. Los revisores agregados aquí son los revisores que puede elegir al escalar una alerta en el flujo de trabajo de investigación y corrección. Cuando se agregan revisores a una directiva, reciben automáticamente un mensaje de correo electrónico que les notifica la asignación a la directiva y proporciona vínculos a información sobre el proceso de revisión.

    - Elija un campo de condición limitado, normalmente un tipo de información confidencial o un diccionario de palabras clave para aplicar a la directiva.

    >[!NOTE]
    >Si desea habilitar el reconocimiento óptico de caracteres [(OCR)](communication-compliance-feature-reference.md#optical-character-recognition-ocr-preview) para examinar imágenes incrustadas o adjuntas en mensajes de texto impreso o escrito a mano que coincidan con las condiciones de directiva, seleccione **Personalizar** las condiciones y el porcentaje de directiva y habilite Extraer texto impreso o escrito a mano de las imágenes para su  >   evaluación.

    Si elige usar el Asistente para directivas para crear una directiva personalizada, hará lo siguiente:

    - Asigne a la directiva un nombre y una descripción. Los nombres de directivas no se pueden cambiar una vez creada la directiva.

    - Elija los usuarios o grupos que desea supervisar, incluidos todos los usuarios de la organización, usuarios y grupos específicos, u otros usuarios y grupos que quiera excluir.

    - Elija los revisores de la directiva. Los revisores son usuarios individuales y todos los revisores deben tener buzones hospedados en Exchange Online. Los revisores agregados aquí son los revisores que puede elegir al escalar una alerta en el flujo de trabajo de investigación y corrección. Cuando se agregan revisores a una directiva, reciben automáticamente un mensaje de correo electrónico que les notifica la asignación a la directiva y proporciona vínculos a información sobre el proceso de revisión.

    - Elija los canales de comunicación que desea examinar, incluidos Exchange, Microsoft Teams, Yammer o Skype Empresarial. También elegirá examinar orígenes de terceros si ha configurado un conector en Microsoft 365.

    - Elija la dirección de comunicación que desea supervisar, incluidas las comunicaciones entrantes, salientes o internas.

    - Definir las condiciones de la directiva de cumplimiento de [comunicaciones](communication-compliance-feature-reference.md#ConditionalSettings). Puede elegir entre la dirección del mensaje, la palabra clave, los tipos de archivo y las condiciones de coincidencia de tamaño.

    - Elija si desea incluir tipos de información confidencial. Este paso es donde puede seleccionar tipos de información confidencial predeterminados y personalizados. Elija entre tipos de información confidencial personalizados existentes o diccionarios de palabras clave personalizadas en el Asistente para directivas de cumplimiento de comunicaciones. Puede crear estos elementos antes de ejecutar el asistente si es necesario. También puede crear nuevos tipos de información confidencial desde el Asistente para directivas de cumplimiento de comunicaciones.

    - Elija si desea habilitar clasificadores. Los clasificadores pueden detectar el idioma inapropiado y las imágenes enviadas o recibidas en el cuerpo de los mensajes de correo electrónico u otros tipos de texto. Puede elegir los siguientes clasificadores integrados: *Threat*, *Profanity*, *Targeted harassment*, *Adult images*, *Racy images* y *Gory images*.

    - Habilite el reconocimiento óptico de caracteres [(OCR)](communication-compliance-feature-reference.md#optical-character-recognition-ocr-preview) para examinar imágenes incrustadas o adjuntas en mensajes en busca de texto impreso o escrito a mano que coincida con las condiciones de la directiva. Para las directivas personalizadas, una o más configuraciones condicionales asociadas con texto, palabras clave, clasificadores o tipos de información confidencial deben configurarse en la directiva para habilitar la selección del examen óptico de reconocimiento de caracteres.

    - Definir el porcentaje de comunicaciones que se revisarán.

    - Revise las selecciones de directiva y cree la directiva.

5. Seleccione **Crear directiva** al usar las plantillas o **Enviar** al usar el asistente para directivas personalizadas.

6. La **página Su directiva se creó** se muestra con instrucciones sobre cuándo se activará la directiva y qué comunicaciones se capturarán.

## <a name="step-6-optional-create-notice-templates-and-configure-user-anonymization"></a>Paso 6 (opcional): crear plantillas de aviso y configurar el anonimización de usuarios

Si desea tener la opción de responder a una alerta de directiva mediante el envío de un aviso al usuario asociado, deberá crear al menos una plantilla de aviso en su organización. Los campos de plantilla de aviso son editables antes de que se envíen como parte del proceso de corrección de alertas y se recomienda crear una plantilla de aviso personalizada para cada directiva de cumplimiento de comunicaciones.

También puede habilitar la anonimización para los nombres de usuario mostrados al investigar coincidencias de directivas y realizar acciones en los mensajes.

1. Inicie sesión [https://compliance.microsoft.com](https://compliance.microsoft.com) con las credenciales de una cuenta de administrador en su Microsoft 365 organización.

2. En el centro Microsoft 365 cumplimiento, vaya a **Cumplimiento de comunicaciones.**

3. Para configurar la anonimización de nombres de usuario, seleccione la **pestaña** Privacidad.

4. Para habilitar la anonimización, seleccione **Mostrar versiones anónimas de nombres de usuario**.

5. Seleccione **Guardar**.

6. Vaya a la pestaña **Plantillas de** aviso y, a continuación, seleccione Crear plantilla **de aviso.**

7. En la **página Modificar una plantilla de aviso,** complete los siguientes campos:

    - Nombre de plantilla (obligatorio)
    - Enviar desde (obligatorio)
    - Cc y CCO (opcional)
    - Asunto (obligatorio)
    - Cuerpo del mensaje (obligatorio)

8. Seleccione **Guardar** para crear y guardar la plantilla de aviso.

## <a name="step-7-optional-test-your-communication-compliance-policy"></a>Paso 7 (opcional): probar la directiva de cumplimiento de comunicaciones

Después de crear una directiva de cumplimiento de comunicaciones, es una buena idea probarla para asegurarse de que la directiva aplique correctamente las condiciones definidas. También puede probar las directivas de prevención de pérdida de datos [(DLP)](create-test-tune-dlp-policy.md) si las directivas de cumplimiento de comunicación incluyen tipos de información confidencial. Asegúrese de dar tiempo a las directivas para que se activen de modo que se capturan las comunicaciones que desea probar.

Siga estos pasos para probar la directiva de cumplimiento de comunicaciones:

1. Abra un cliente de correo electrónico, Microsoft Teams o Yammer cuando haya iniciado sesión como un usuario supervisado definido en la directiva que desea probar.

2. Envíe un correo electrónico, Microsoft Teams chat o Yammer que cumpla los criterios que ha definido en la directiva de cumplimiento de comunicaciones. Esta prueba puede ser una palabra clave, tamaño de datos adjuntos, dominio, etc. Asegúrese de determinar si la configuración condicional configurada en la directiva es demasiado restrictiva o demasiado indulgente.

    > [!NOTE]
    > Los mensajes de correo electrónico pueden tardar hasta 24 horas en procesarse completamente en una directiva. Las comunicaciones Microsoft Teams, Yammer y plataformas de terceros pueden tardar hasta 48 horas en procesarse completamente en una directiva.

3. Inicie sesión en Microsoft 365 como revisor designado en la directiva de cumplimiento de comunicaciones. Vaya a **Alertas de cumplimiento**  >  **de** comunicación para ver las alertas de las directivas.

4. Corrija la alerta con los controles de corrección y compruebe que la alerta está correctamente resuelta.

## <a name="next-steps"></a>Pasos siguientes

Después de completar estos pasos para crear la primera directiva de cumplimiento de comunicaciones, empezará a recibir alertas de indicadores de actividad después de 24-48 horas. Configure directivas adicionales según sea necesario con las instrucciones del paso 5 de este artículo.

Para obtener más información sobre cómo investigar alertas de cumplimiento de comunicaciones, vea [Investigar y corregir alertas de cumplimiento de comunicaciones.](communication-compliance-investigate-remediate.md)
