---
title: Configurar el cumplimiento de la comunicación para Microsoft 365 (versión preliminar)
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
description: Configure las directivas de cumplimiento de comunicaciones para configurar las comunicaciones de los empleados para revisión.
ms.openlocfilehash: 0a830914a22968119d836e2190a6f133d91fd305
ms.sourcegitcommit: 5f96fa472cbdca30c2cfe24d66c9c6fcaedb1a6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2019
ms.locfileid: "38755608"
---
# <a name="configure-communication-compliance-for-microsoft-365-preview"></a>Configurar el cumplimiento de la comunicación para Microsoft 365 (versión preliminar)

> [!IMPORTANT]
> Este tema se aplica a la configuración del cumplimiento de comunicaciones en una suscripción de Microsoft 365. Si desea configurar directivas de supervisión para una suscripción de Office 365, vea [Configure la supervisión para office 365](supervision-policies.md).

Use las directivas de cumplimiento de comunicaciones para capturar las comunicaciones de los empleados para que las examinen los revisores externos o internos. Para obtener más información sobre cómo las directivas de cumplimiento de comunicaciones pueden ayudarle a supervisar las comunicaciones en su organización, consulte [directivas de cumplimiento de comunicaciones en Microsoft 365](communication-compliance.md).

> [!NOTE]
> Los usuarios supervisados por directivas de cumplimiento de la comunicación deben tener una licencia de cumplimiento de Microsoft 365 E5, una licencia de Office 365 Enterprise E3 con el complemento de cumplimiento avanzado o incluirse en una suscripción a Office 365 Enterprise E5.
> Si no tiene un plan existente de Enterprise E5 y desea probar el cumplimiento de la comunicación, puede [registrarse para obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).
  
Siga estos pasos para configurar y usar el cumplimiento de la comunicación en su organización de Microsoft 365:
  
- **Paso 1 (opcional)**: [configurar grupos para el cumplimiento de la comunicación](#step-1-set-up-groups-for-communication-compliance-optional) 

    Antes de empezar a usar el cumplimiento de la comunicación, determine quién necesita las comunicaciones revisadas y quién realiza las revisiones. Si quiere empezar solo con unos pocos usuarios para ver cómo funciona el cumplimiento de la comunicación, puede omitir la configuración de grupos por ahora.

- **Paso 2 (obligatorio)**: [hacer que el cumplimiento de la comunicación esté disponible en su organización](#step-2-make-communication-compliance-available-in-your-organization-required)

    Agregarse a sí mismo al rol de **Administrador de revisión de supervisión** para que pueda configurar directivas. También tendrá que crear un grupo con el administrador de **revisión de supervisión**, los roles de **Administración de casos** y **revisión** para personas o grupos que vayan a tomar medidas de investigación y corrección en mensajes con coincidencias de directivas. Cualquiera que tenga estos roles asignados puede tener acceso a la página cumplimiento en la **comunicación** en el centro de cumplimiento de Microsoft 365. Si el correo electrónico que se puede rever está hospedado en Exchange Online, cada revisor debe tener [acceso remoto de PowerShell a Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).

- **Paso 3 (obligatorio)**: [configurar una directiva de cumplimiento de la comunicación](#step-3-create-a-communication-compliance-policy-required)

    Puede crear directivas de cumplimiento de comunicaciones en el centro de cumplimiento de Microsoft 365. Estas directivas definen qué comunicaciones están sujetas a revisión en su organización y especifica quién realiza las revisiones. Las comunicaciones incluyen correo electrónico, Microsoft Teams, Skype empresarial y comunicaciones de plataforma de terceros (como Facebook, Twitter, etc.).

- **Paso 4 (opcional)**: [crear plantillas de avisos de empleados](#step-4-create-employee-notice-templates-optional)

    Cree plantillas de notificación personalizadas para enviar notificaciones de correo electrónico a los empleados como opción de corrección de las coincidencias de directivas.

- **Paso 5 (opcional)**: [probar la Directiva de cumplimiento de la comunicación](#step-5-test-your-communication-compliance-policy-optional)

    Pruebe la Directiva de cumplimiento de comunicaciones para asegurarse de que funciona según lo deseado. Es importante asegurarse de que la estrategia de cumplimiento cumple los estándares.

## <a name="step-1-set-up-groups-for-communication-compliance-optional"></a>Paso 1: configurar grupos para el cumplimiento de la comunicación (opcional)

 Al crear una directiva de cumplimiento de la comunicación, se define quién ha revisado sus comunicaciones y quién realiza las revisiones. En la Directiva, usará direcciones de correo electrónico para identificar personas o grupos de personas. Para simplificar la configuración, puede crear grupos para los usuarios que tengan su comunicación revisada y grupos para los usuarios que revisen dichas comunicaciones. Si está usando grupos, es posible que necesite varios. Por ejemplo, desea supervisar las comunicaciones entre dos grupos de personas distintas o si desea especificar un grupo que no se va a supervisar.

Use el siguiente gráfico para ayudarle a configurar los grupos de su organización para las directivas de cumplimiento de comunicaciones:

| **Miembro de la Directiva** | **Grupos admitidos** | **Grupos no admitidos** |
|:-----|:-----|:-----|
|Usuarios supervisados <br> Usuarios no supervisados | Grupos de distribución <br> Grupos de Office 365 | Grupos de distribución dinámicos |
| Reviewers | Grupos de seguridad habilitados para correo  | Grupos de distribución <br> Grupos de distribución dinámicos |
  
Cuando se selecciona un grupo de Office 365 para los usuarios supervisados, la Directiva supervisa el contenido del buzón de correo de Office 365 compartido y los canales de Microsoft Teams asociados con el grupo. Al seleccionar una lista de distribución, la Directiva supervisa los buzones de usuario individuales.

Para obtener más información acerca de la configuración de grupos, vea:

- [Crear y administrar grupos de distribución](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [Administrar grupos de seguridad habilitados para correo](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups)
- [Información general sobre los grupos de Office 365](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups?view=o365-worldwide)

## <a name="step-2-make-communication-compliance-available-in-your-organization-required"></a>Paso 2: hacer que el cumplimiento de la comunicación esté disponible en su organización (obligatorio)

Para que el cumplimiento de la **comunicación** esté disponible como una opción de menú en el centro de cumplimiento de Microsoft 365, debe tener asignado el rol de administrador de **revisión de supervisión** . Además, para investigar y corregir mensajes con coincidencias de directivas, debe crear un grupo para revisores con el **Administrador de revisión de supervisión**, los roles de **Administración de casos** y **revisión** .

### <a name="create-a-new-role-group"></a>Crear un nuevo grupo de roles

1. Inicie sesión [https://compliance.microsoft.com](https://compliance.microsoft.com) con las credenciales de una cuenta de administrador en la organización de Office 365.

2. En el centro de cumplimiento de Microsoft 365, vaya a **permisos**. Seleccione el vínculo para ver y administrar roles en Office 365.

3. Seleccione **Crear**.

4. En el campo **nombre** , asigne un nombre descriptivo al nuevo grupo de roles. Seleccione **Siguiente**.

5. Seleccione **elegir roles** y, después, haga clic en **Agregar**. Marque la casilla de **verificación administrador de revisión de supervisión**, administración de **casos**y **revisión**y, a continuación, seleccione **Agregar** y **listo**. Seleccione **Siguiente**.

6. Seleccione **elegir miembros** y, a continuación, seleccione **Agregar**. Marque la casilla de verificación para todos los usuarios y grupos que desee que creen directivas y administre los mensajes con coincidencias de directivas y, a continuación, seleccione **Agregar** y **listo**. Seleccione **Siguiente**.

7. Seleccione **Crear grupo de funciones** para finalizar.

Para obtener más información acerca de los grupos de roles y los permisos, consulte [Permissions in the Compliance Center](../security/office-365-security/protect-against-threats.md).

## <a name="step-3-create-a-communication-compliance-policy-required"></a>Paso 3: crear una directiva de cumplimiento de la comunicación (obligatorio)
  
1. Inicie sesión [https://compliance.microsoft.com](https://compliance.microsoft.com) con las credenciales de una cuenta de administrador en la organización de Microsoft 365.

2. En el centro de cumplimiento de Microsoft 365, seleccione **cumplimiento de comunicaciones**.
  
3. Seleccione la pestaña **directivas** .

4. Seleccione **crear Directiva** para crear y configurar una nueva Directiva a partir de una plantilla o para crear y configurar una directiva personalizada.

    Si elige una plantilla de directiva para crear una directiva, deberá:

    - Confirme o actualice el nombre de la Directiva. Los nombres de las directivas no se pueden cambiar una vez creada la Directiva.
    - Elija los usuarios o grupos que desea supervisar, incluida la elección de los usuarios o grupos que quiera excluir.
    - Elija los revisores para la Directiva. Los revisores pueden ser usuarios individuales o [grupos de seguridad habilitados para correo](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group). Todos los revisores deben tener buzones hospedados en Exchange Online.
    - Elija un campo de condición limitada, normalmente un tipo de información confidencial o un diccionario de palabras clave que se aplicará a la Directiva.

    Si decide usar el Asistente para directivas para crear una directiva personalizada, deberá:

    - Asigne un nombre y una descripción a la Directiva. Los nombres de las directivas no se pueden cambiar una vez creada la Directiva.
    - Elija los usuarios o grupos que desea supervisar, incluida la elección de todos los usuarios de la organización, usuarios y grupos específicos, u otros usuarios y grupos que quiera excluir. -
    - Elija los revisores para la Directiva. Los revisores pueden ser usuarios individuales o [grupos de seguridad habilitados para correo](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group). Todos los revisores deben tener buzones hospedados en Exchange Online.
    - Elija los canales de comunicación para analizar, incluidos Exchange, Microsoft Teams o Skype empresarial. También elige analizar los orígenes de terceros si ha configurado un conector en Microsoft 365.
    - Elija la dirección de comunicación que se va a supervisar, incluidas las comunicaciones entrantes, salientes o internas.
    - Definir las [condiciones](communication-compliance-feature-reference.md#ConditionalSettings)de la Directiva de cumplimiento de comunicaciones. Puede elegir entre la dirección del mensaje, la palabra clave, los tipos de archivo y las condiciones de coincidencia de tamaño.
    - Elija si le gustaría incluir tipos de información confidencial. Aquí puede seleccionar los tipos de información confidencial predeterminada y personalizado. Elegir entre los tipos de información confidencial personalizados existentes o los diccionarios de palabras clave personalizados en el Asistente para la Directiva de cumplimiento de comunicaciones, puede crear estos elementos antes de ejecutar el asistente si es necesario. Si lo desea, también puede crear nuevos tipos de información confidencial desde el Asistente para la Directiva de cumplimiento de comunicaciones.
    - Elija si quiere habilitar el modelo de lenguaje ofensivo. Esto detecta un idioma no apropiado enviado o recibido en el cuerpo de los mensajes de correo electrónico.
    - Definir el porcentaje de comunicaciones que se van a revisar.
    - Revise las selecciones de la Directiva y cree la Directiva.

5. Seleccione **crear Directiva** al usar las plantillas o **Enviar** cuando se use el Asistente para directivas personalizadas.

6. La página se **ha creado la Directiva** se muestra con instrucciones sobre cuándo se activará la Directiva y se capturarán las comunicaciones.

## <a name="step-4-create-employee-notice-templates-optional"></a>Paso 4: crear plantillas de aviso de empleado (opcional)

Si desea tener la opción de responder a una alerta de Directiva mediante el envío de una notificación de recordatorio al empleado asociado, deberá crear al menos una plantilla de aviso en la organización. Los campos de plantilla de aviso son editables antes de enviar como parte del proceso de corrección de alertas y se recomienda crear una plantilla de notificación personalizada para cada directiva de cumplimiento de la comunicación.

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

## <a name="step-5-test-your-communication-compliance-policy-optional"></a>Paso 5: probar la Directiva de cumplimiento de la comunicación (opcional)

Después de crear una directiva de cumplimiento de la comunicación, es aconsejable probarla para asegurarse de que la Directiva aplica correctamente las condiciones definidas. Es posible que también desee [probar sus directivas de prevención de pérdida de datos (DLP)](create-test-tune-dlp-policy.md) si las directivas de cumplimiento de comunicaciones incluyen tipos de información confidencial. Asegúrese de dar tiempo a las directivas de activación para que se capturen las comunicaciones que desea probar.

Siga estos pasos para probar la Directiva de cumplimiento de la comunicación:

1. Abra un cliente de correo electrónico o Microsoft teams que haya iniciado sesión como usuario supervisado definido en la Directiva que desea probar.
2. Envíe un correo electrónico o un chat de Microsoft teams que cumpla los criterios que haya definido en la Directiva de cumplimiento de la comunicación. Puede ser una palabra clave, el tamaño de los datos adjuntos, el dominio, etc. Asegúrese de determinar si la configuración condicional configurada en la Directiva es demasiado restrictiva o demasiado flexible.

    > [!NOTE]
    > Las comunicaciones en todos los canales de origen pueden tardar hasta 24 horas en procesarse completamente en una directiva.

3. Inicie sesión en Microsoft 365 como revisor designado en la Directiva de cumplimiento de la comunicación. Navegue a **** > **alertas** de cumplimiento de comunicaciones para ver las alertas de las directivas.

4. Corrija la alerta con los controles de corrección y compruebe que la alerta se haya resuelto correctamente.
