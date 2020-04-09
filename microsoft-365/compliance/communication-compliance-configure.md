---
title: Configurar el cumplimiento de la comunicación
description: Configure las directivas de cumplimiento de comunicaciones para configurar las comunicaciones de los empleados para revisión.
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
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: e9e13c4bb9a950326a5fc718be26f93d046776e7
ms.sourcegitcommit: 13f28aa762e467bab8ab1e95e1917b3ac28931da
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2020
ms.locfileid: "43193518"
---
# <a name="configure-communication-compliance-in-microsoft-365"></a>Configurar el cumplimiento de la comunicación en Microsoft 365

>[!IMPORTANT]
>Este tema se aplica a la configuración del cumplimiento de comunicaciones en una suscripción de Microsoft 365. Si desea configurar directivas de supervisión para una suscripción de Office 365, vea [Configure la supervisión para office 365](supervision-policies.md).

Use las directivas de cumplimiento de comunicaciones para capturar las comunicaciones de los empleados para que las examinen los revisores externos o internos. Para obtener más información sobre cómo las directivas de cumplimiento de comunicaciones pueden ayudarle a supervisar las comunicaciones en su organización, consulte [directivas de cumplimiento de comunicaciones en Microsoft 365](communication-compliance.md). Si desea revisar cómo contoso ha configurado rápidamente una directiva de cumplimiento de la comunicación para supervisar el lenguaje ofensivo en Microsoft Teams y en las comunicaciones de Exchange Online, consulte este [caso práctico](communication-compliance-case-study.md).

## <a name="before-you-begin"></a>Antes de empezar

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
- Office 365 Enterprise E3 subscription + el complemento Office 365 Advanced Compliance (ya no está disponible para las nuevas suscripciones, vea note)

Los usuarios incluidos en las directivas de cumplimiento de comunicaciones deben tener asignada una de las licencias anteriores.

>[!IMPORTANT]
>Office 365 Advanced Compliance ya no se vende como una suscripción independiente. Cuando expiren las suscripciones actuales, los clientes deben pasar a una de las suscripciones anteriores, que contienen las mismas características de cumplimiento o más.

Si no tiene un plan de Microsoft 365 Enterprise E5 existente y desea probar la administración de riesgos de Insider, puede [Agregar microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) a su suscripción existente de Office 365 o [registrarse para obtener una versión de prueba](https://www.microsoft.com/microsoft-365/enterprise) de Microsoft 365 Enterprise E5.

## <a name="step-1-required-enable-permissions-for-communication-compliance"></a>Paso 1 (obligatorio): habilitar permisos para el cumplimiento de la comunicación

>[!Important]
>De forma predeterminada, los administradores globales no tienen acceso a las características de cumplimiento de comunicaciones. Los roles asignados en este paso son necesarios antes de que se pueda tener acceso a las características de cumplimiento de la comunicación.

Para que el cumplimiento de la **comunicación** esté disponible como una opción de menú en el centro de cumplimiento de Microsoft 365, debe tener asignado el rol de administrador de **revisión de supervisión** . Debe crear un nuevo grupo de roles para revisores con el **Administrador de revisión de supervisión**, la **Administración de casos**, el **Administrador de cumplimiento**y la **revisión** de roles para investigar y corregir mensajes con coincidencias de directivas.

### <a name="create-a-new-role-group"></a>Crear un nuevo grupo de roles

1. Inicie sesión [https://protection.office.com/permissions](https://protection.office.com/permissions) con las credenciales de una cuenta de administrador en la organización de Microsoft 365.

2. En el centro de seguridad y cumplimiento de Microsoft Office 365, vaya a **permisos**. Seleccione el vínculo para ver y administrar roles en Office 365.

3. Seleccione **Crear**.

4. En el campo **nombre** , asigne un nombre descriptivo al nuevo grupo de roles. Seleccione **Siguiente**.

5. Seleccione **elegir roles** y, después, haga clic en **Agregar**. Marque la casilla de **verificación administrador de revisión de supervisión**, administración de **casos**, **Administrador de cumplimiento**y **revisión**y, a continuación, seleccione **Agregar** y **listo**. Seleccione **Siguiente**.

    ![Grupos de roles obligatorios de cumplimiento de comunicación](../media/communication-compliance-role-groups-1.png)

6. Seleccione **elegir miembros** y, a continuación, seleccione **Agregar**. Marque la casilla de verificación para todos los usuarios y grupos que desee que creen directivas y administre los mensajes con coincidencias de directivas y, a continuación, seleccione **Agregar** y **listo**. Seleccione **Siguiente**.

7. Seleccione **Crear grupo de funciones** para finalizar.

Para obtener más información acerca de los grupos de roles y los permisos, consulte [Permissions in the Compliance Center](../security/office-365-security/protect-against-threats.md).

## <a name="step-2-required-enable-the-office-365-audit-log"></a>Paso 2 (obligatorio): habilitar el registro de auditoría de Office 365

El cumplimiento de la comunicación requiere registros de auditoría para mostrar alertas y realizar un seguimiento de las acciones de corrección realizadas por los revisores. Los registros de auditoría son un resumen de todas las actividades asociadas con una directiva de organización definida o cada vez que cambia una directiva de cumplimiento de la comunicación.

Para obtener instrucciones paso a paso para activar la auditoría, consulte [activar o desactivar la búsqueda de registros de auditoría de Office 365](turn-audit-log-search-on-or-off.md). Después de activar la auditoría, se muestra un mensaje que indica que se está preparando el registro de auditoría y que puede ejecutar una búsqueda en un par de horas después de que se complete la preparación. Solo tiene que realizar esta acción una vez. Para obtener más información acerca del uso del registro de auditoría, vea [Buscar en el registro de auditoría](search-the-audit-log-in-security-and-compliance.md).

## <a name="step-3-optional-set-up-groups-for-communication-compliance"></a>Paso 3 (opcional): configurar grupos para el cumplimiento de la comunicación

 Al crear una directiva de cumplimiento de la comunicación, se define quién ha revisado sus comunicaciones y quién realiza las revisiones. En la Directiva, usará direcciones de correo electrónico para identificar personas o grupos de personas. Para simplificar la configuración, puede crear grupos para los usuarios que tengan su comunicación revisada y grupos para los usuarios que revisen dichas comunicaciones. Si está usando grupos, es posible que necesite varios. Por ejemplo, si desea supervisar las comunicaciones entre dos grupos de personas distintas o si desea especificar un grupo que no va a supervisarse.

Use el siguiente gráfico para ayudarle a configurar los grupos de su organización para las directivas de cumplimiento de comunicaciones:

| **Miembro de la Directiva** | **Grupos admitidos** | **Grupos no admitidos** |
|:-----|:-----|:-----|
|Usuarios supervisados <br> Usuarios no supervisados | Grupos de distribución <br> Grupos de Office 365 | Grupos de distribución dinámicos |
| Reviewers | Ninguno | Grupos de distribución <br> Grupos de distribución dinámicos <br> Grupos de seguridad habilitados para correo |
  
Cuando se selecciona un grupo de Office 365 para los usuarios supervisados, la Directiva supervisa el contenido del buzón de correo de Office 365 compartido y los canales de Microsoft Teams asociados con el grupo. Al seleccionar una lista de distribución, la Directiva supervisa los buzones de usuario individuales.

Para obtener más información acerca de la configuración de grupos, vea:

- [Crear y administrar grupos de distribución](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [Información general sobre los grupos de Office 365](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups?view=o365-worldwide)

## <a name="step-4-required-create-a-communication-compliance-policy"></a>Paso 4 (obligatorio): crear una directiva de cumplimiento de la comunicación
  
>[!Important]
>No se admite el uso de PowerShell para crear y administrar directivas de cumplimiento de comunicaciones. Para crear y administrar estas directivas, debe usar los controles de administración de directivas de la [solución Microsoft 365 Communication Compliance](https://compliance.microsoft.com/supervisoryreview).

1. Inicie sesión [https://compliance.microsoft.com](https://compliance.microsoft.com) con las credenciales de una cuenta de administrador en la organización de Microsoft 365.

2. En el centro de cumplimiento de Microsoft 365, seleccione **cumplimiento de comunicaciones**.
  
3. Seleccione la pestaña **directivas** .

4. Seleccione **crear Directiva** para crear y configurar una nueva Directiva a partir de una plantilla o para crear y configurar una directiva personalizada.

    Si elige una plantilla de directiva integrada para crear una directiva, deberá:

    - Confirme o actualice el nombre de la Directiva. Los nombres de las directivas no se pueden cambiar una vez creada la Directiva.
    - Elija los usuarios o grupos que desea supervisar, incluida la elección de los usuarios o grupos que quiera excluir.
    - Elija los revisores para la Directiva. Los revisores son usuarios individuales y todos los revisores deben tener buzones hospedados en Exchange Online. Los revisores agregados aquí son los revisores que puede elegir al escalar una alerta en el flujo de trabajo de investigación y corrección.
    - Elija un campo de condición limitada, normalmente un tipo de información confidencial o un diccionario de palabras clave que se aplicará a la Directiva.

    Si decide usar el Asistente para directivas para crear una directiva personalizada, deberá:

    - Asigne un nombre y una descripción a la Directiva. Los nombres de las directivas no se pueden cambiar una vez creada la Directiva.
    - Elija los usuarios o grupos que desea supervisar, incluidos todos los usuarios de la organización, usuarios y grupos específicos, u otros usuarios y grupos que quiera excluir.
    - Elija los revisores para la Directiva. Los revisores son usuarios individuales y todos los revisores deben tener buzones hospedados en Exchange Online.
    - Elija los canales de comunicación para analizar, incluidos Exchange, Microsoft Teams o Skype empresarial. También elige analizar los orígenes de terceros si ha configurado un conector en Microsoft 365.
    - Elija la dirección de comunicación que se va a supervisar, incluidas las comunicaciones entrantes, salientes o internas.
    - Definir las [condiciones](communication-compliance-feature-reference.md#ConditionalSettings)de la Directiva de cumplimiento de comunicaciones. Puede elegir entre la dirección del mensaje, la palabra clave, los tipos de archivo y las condiciones de coincidencia de tamaño.
    - Elija si le gustaría incluir tipos de información confidencial. En este paso puede seleccionar los tipos de información confidencial predeterminada y personalizado. Elija entre los tipos de información confidencial existentes o los diccionarios de palabras clave personalizados en el Asistente para la Directiva de cumplimiento de comunicaciones. Puede crear estos elementos antes de ejecutar el asistente si es necesario. También puede crear nuevos tipos de información confidencial desde el Asistente para directivas de cumplimiento de comunicaciones.
    - Elija si le gustaría habilitar los clasificadores. Los clasificadores pueden detectar idiomas inapropiados enviados o recibidos en el cuerpo de los mensajes de correo electrónico u otros tipos de texto.

    >[!CAUTION]
    >Estamos descartando el clasificador integrado de **lenguaje ofensivo** porque ha generado un gran número de falsos positivos. No lo use y, si actualmente lo está usando, debería mover sus procesos de negocio fuera de él. En su lugar, se recomienda usar los clasificadores de **amenaza**, **blasfemia**y **acoso** integrados.

    - Definir el porcentaje de comunicaciones que se van a revisar.
    - Revise las selecciones de la Directiva y cree la Directiva.

5. Seleccione **crear Directiva** al usar las plantillas o **Enviar** cuando se use el Asistente para directivas personalizadas.

6. La página se **ha creado la Directiva** se muestra con instrucciones sobre cuándo se activará la Directiva y qué comunicaciones se capturarán.

## <a name="step-5-optional-create-employee-notice-templates"></a>Paso 5 (opcional): crear plantillas de avisos de empleados

Si desea tener la opción de responder a una alerta de Directiva mediante el envío de una notificación de recordatorio al empleado asociado, deberá crear al menos una plantilla de aviso en la organización. Los campos de plantilla de aviso son editables antes de que se envíen como parte del proceso de corrección de alertas y se recomienda crear una plantilla de notificación personalizada para cada directiva de cumplimiento de la comunicación.

1. Inicie sesión [https://compliance.microsoft.com](https://compliance.microsoft.com) con las credenciales de una cuenta de administrador en la organización de Microsoft 365.

2. En el centro de cumplimiento de Microsoft 365, vaya a **cumplimiento de comunicaciones**.

3. Seleccione la ficha **plantillas de notificación** y, a continuación, seleccione **Crear plantilla de notificación**.

4. En la página **modificar una plantilla de notificación** , complete los campos siguientes:

    - Nombre de plantilla de aviso (obligatorio)
    - Enviar desde (obligatorio)
    - CC y CCO (opcional)
    - Asunto (obligatorio)
    - Cuerpo del mensaje (obligatorio)

5. Seleccione **Guardar** para crear y guardar la plantilla de aviso.

## <a name="step-6-optional-test-your-communication-compliance-policy"></a>Paso 6 (opcional): probar la Directiva de cumplimiento de la comunicación

Después de crear una directiva de cumplimiento de comunicaciones, es una buena idea probarla para asegurarse de que la Directiva aplica correctamente las condiciones definidas. Es posible que también desee [probar sus directivas de prevención de pérdida de datos (DLP)](create-test-tune-dlp-policy.md) si las directivas de cumplimiento de comunicaciones incluyen tipos de información confidencial. Asegúrese de dar tiempo a las directivas de activación para que se capturen las comunicaciones que desea probar.

Siga estos pasos para probar la Directiva de cumplimiento de la comunicación:

1. Abra un cliente de correo electrónico o Microsoft Teams con una sesión iniciada como usuario supervisado definido en la Directiva que desea probar.
2. Envíe un correo electrónico o un chat de Microsoft teams que cumpla los criterios que haya definido en la Directiva de cumplimiento de la comunicación. Esta prueba puede ser una palabra clave, el tamaño de los datos adjuntos, el dominio, etc. Asegúrese de determinar si la configuración condicional configurada en la Directiva es demasiado restrictiva o demasiado flexible.

    > [!NOTE]
    > Las comunicaciones en todos los canales de origen pueden tardar hasta 24 horas en procesarse completamente en una directiva.

3. Inicie sesión en Microsoft 365 como revisor designado en la Directiva de cumplimiento de la comunicación. Navegue a **Communication compliance** > **alertas** de cumplimiento de comunicaciones para ver las alertas de las directivas.

4. Corrija la alerta con los controles de corrección y compruebe que la alerta se haya resuelto correctamente.
