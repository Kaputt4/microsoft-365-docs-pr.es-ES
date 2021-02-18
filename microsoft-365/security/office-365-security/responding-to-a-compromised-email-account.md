---
title: Responder a una cuenta de correo electrónico en peligro
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.collection:
- o365_security_incident_response
- M365-security-compliance
- m365solution-smb
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
localization_priority: Priority
search.appverid:
- MET150
description: Aprenda a reconocer y responder a una cuenta de correo electrónico comprometida utilizando las herramientas disponibles en Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1bbd607386b49b45ebd7444c4a91d05e4cee475b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288614"
---
# <a name="responding-to-a-compromised-email-account"></a>Responder a una cuenta de correo electrónico en peligro

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

**Resumen** Aprenda a reconocer y responder a una cuenta de correo electrónico en peligro en Microsoft 365.

## <a name="what-is-a-compromised-email-account-in-microsoft-365"></a>¿Qué es una cuenta de correo electrónico en peligro en Microsoft 365?

El acceso a los buzones, los datos y otros servicios de Microsoft 365 se controla mediante el uso de credenciales, como un nombre de usuario y contraseña o PIN. Cuando alguien que no sea el usuario roba estas credenciales, se considera que las credenciales robadas suponen un riesgo. Con ellas, el atacante puede iniciar sesión como el usuario original y realizar acciones ilícitas.
Con las credenciales robadas, el atacante puede obtener acceso a archivos en OneDrive del usuario, las carpetas de SharePoint o el buzón de Microsoft 365 del usuario. Una acción habitual es que el atacante envíe correos electrónicos como el usuario original a destinatarios tanto dentro como fuera de la organización. Cuando el atacante envía datos a destinatarios externos, se denomina "exfiltración" de datos.

## <a name="symptoms-of-a-compromised-microsoft-email-account"></a>Síntomas de una cuenta de correo electrónico de Microsoft en peligro

Los usuarios pueden observar e informar sobre actividad inusual en sus buzones de Microsoft 365. Estos son algunos síntomas comunes:

- Actividad sospechosa, como correos electrónicos eliminados o que faltan.

- Otros usuarios pueden recibir correos electrónicos de la cuenta en peligro sin que el correo electrónico correspondiente aparezca en la carpeta **Elementos enviados** del remitente.

- La presencia de reglas de bandeja de entrada que no se han creado por el usuario o el administrador. Estas reglas pueden reenviar automáticamente correos electrónicos a direcciones desconocidas o moverlos a las carpetas de **Notas**, **Correo no deseado** o **Suscripciones RSS**.

- El nombre para mostrar del usuario puede cambiarse en la lista Global de direcciones.

- El buzón del usuario está bloqueado para enviar correo electrónico.

- Las carpetas de Elementos enviados o Elementos eliminados en Microsoft Outlook o Outlook en la Web (anteriormente conocido como Outlook Web App) contienen mensajes comunes de cuentas robadas, como "Estoy atascado en Londres, envíame dinero".

- Se han realizado cambios inusuales en el perfil, como el nombre, el número de teléfono o el código postal.

- Cambios inusuales de credenciales, como múltiples cambios de contraseña requeridos.

- Se ha agregado recientemente el reenvío de correo.

- Se ha agregado recientemente una firma inusual, como una firma de entidad bancaria falsa o una firma de recetas de medicamentos.

Si un usuario informa de los síntomas anteriores, debería realizar una mayor investigación. El Centro de seguridad y cumplimiento de Microsoft 365 y el Portal de Azure ofrecen herramientas para ayudarle a investigar la actividad de una cuenta de usuario que crea que puede estar en riesgo.

- **Registros de auditoría unificados en el Centro de seguridad y cumplimiento**: revise todas las actividades de la cuenta sospechosa, filtre los resultados con un rango de fechas que abarque desde antes de que se produjese la actividad sospechosa hasta la fecha actual. No filtre las actividades durante la búsqueda.

- **Registros de auditoría de administrador en el EAC**: en Exchange Online, puede usar el Centro de administración de Exchange (EAC) para buscar y ver las entradas del registro de auditoría del administrador. El registro de auditoría del administrador registra acciones específicas, según los cmdlets de PowerShell de Exchange Online, realizadas por administradores y usuarios que tienen asignados privilegios de administrador. Las entradas en el registro de auditoría del administrador proporcionan información acerca del cmdlet que se ejecutó, los parámetros que se usaron, el usuario que ejecutó el cmdlet y los objetos que se vieron afectados.

- **Registros de inicio de sesión de Azure AD y otros informes de riesgos en el portal de Azure AD**: examine los valores de estas columnas:

  - Revise la dirección IP
  - ubicaciones de inicio de sesión
  - horas de inicio de sesión
  - inicios de sesión correctos y fallidos

## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-microsoft-365-account-and-mailbox"></a>Cómo proteger y restaurar la función de correo electrónico a un buzón o una cuenta de Microsoft 365 en peligro

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

Incluso después de haber recuperado el acceso a su cuenta, el atacante puede haber agregado entradas traseras que permiten le permiten reanudar el control de la cuenta.

Debe realizar todos los pasos siguientes para volver a tener acceso a su cuenta lo antes posible para asegurarse de que el atacante no reanude el control de su cuenta. Estos pasos le ayudan a quitar las entradas traseras que puede haber agregado el atacante a su cuenta. Después de completar estos pasos, se recomienda que ejecute una detección de virus para asegurarse de que su equipo no está en peligro.

### <a name="step-1-reset-the-users-password"></a>Paso 1 Restablecer la contraseña del usuario

Siga los procedimientos que se describen en [Restablecer una contraseña de empresa para un usuario](../../admin/add-users/reset-passwords.md#reset-my-admin-password).

> [!IMPORTANT]
>
> - No envíe la nueva contraseña al usuario en cuestión por correo electrónico, ya que el atacante todavía tiene acceso al buzón en este momento.
>
> - Asegúrese de que la contraseña es segura y que contiene al menos un carácter especial, al menos un número y letras mayúsculas y minúsculas.
>
> - No vuelva a usar ninguna de las últimas cinco contraseñas. Aunque el requisito de historial de contraseña le permite volver a usar una contraseña más reciente, debería seleccionar algo que el atacante no pueda adivinar.
>
> - Si la identidad local se federa con Microsoft 365, debe cambiar la contraseña en el entorno local y, a continuación, debe notificar el peligro a su administrador.
>
> - Asegúrese de actualizar las contraseñas de aplicación. Las contraseñas de aplicación no se revocan automáticamente cuando se restablece la contraseña de una cuenta de usuario. El usuario debe eliminar las contraseñas de aplicación existentes y crear otras nuevas. Para obtener instrucciones, consulte [Crear y eliminar contraseñas de aplicación de la página de Comprobación de seguridad adicional](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-app-passwords#create-and-delete-app-passwords-from-the-additional-security-verification-page).
>
> - Se recomienda que habilite la autenticación multifactor (MFA) para evitar los robos de cuenta, especialmente para las cuentas con privilegios de administrador. Para obtener más información sobre MFA, vaya a [Configurar la autenticación multifactor](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a>Paso 2 Eliminar direcciones de reenvío de correo electrónico sospechosas

1. Abra el Centro de administración de Microsoft 365 en <https://admin.microsoft.com>

2. Vaya a **Usuarios** \> **Usuarios activos**. Busque la cuenta de usuario en cuestión y seleccione el usuario (fila) sin seleccionar la casilla.

3. En el menú desplegable de detalles que aparece, seleccione la pestaña **Correo**.

4. Si el valor en la sección **Reenvío de correo electrónico** es **Aplicado**, haga clic en **Administrar reenvío de correo electrónico**. En el menú flotante **Administrar reenvío de correo electrónico** que aparece, desactive **Reenviar todos los correos electrónicos enviados a este buzón** y luego haga clic en **Guardar cambios**.

### <a name="step-3-disable-any-suspicious-inbox-rules"></a>Paso 3 Deshabilitar las reglas de bandeja de entrada sospechosas

1. Inicie sesión en el buzón del usuario con Outlook en la Web.

2. Haga clic en el icono del engranaje y en **Correo**.

3. Haga clic en **Reglas de bandeja de entrada y barrido** y revise las reglas.

4. Deshabilite o elimine las reglas sospechosas.

### <a name="step-4-unblock-the-user-from-sending-mail"></a>Paso 4 Desbloquear el usuario para que pueda enviar correo

Si el buzón en peligro se usó de forma ilícita para enviar correo no deseado, es probable que el buzón se haya bloqueado para impedir el envío de correo.

Para desbloquear el envío de correo de un buzón, siga los procedimientos descritos en [Quitar un usuario, un dominio o una dirección IP de una lista de bloqueados después de enviar correo no deseado](removing-user-from-restricted-users-portal-after-spam.md).

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a>Paso 5 opcional: Bloquear la cuenta de usuario para impedir el inicio de sesión

> [!IMPORTANT]
> Puede bloquear la cuenta en peligro e impedir que inicie hasta que crea que es seguro volver a habilitar el acceso.

1. En el Centro de administración de Microsoft 365, vaya a **Usuarios** \> **Usuarios activos**.

2. Busque y seleccione la cuenta de usuario, haga clic en el ![icono Más](../../media/ITPro-EAC-MoreOptionsIcon.png) y luego seleccione **Editar estado de inicio de sesión**.

3. En el panel **Bloquear inicio de sesión** que aparece, seleccione **Bloquear el inicio de sesión de este usuario** y luego haga clic en **Guardar cambios**.

4. Abra el Centro de administración de Exchange (EAC) en <admin.protection.outlook.com/ecp/> y vaya a **Destinatarios > Buzones**.

5. Busque y seleccione el usuario. En el panel de detalles, siga estos pasos:

   - En la sección **Características de teléfono y voz**, siga estos pasos:

     - Seleccione **Deshabilitar Exchange ActiveSync** y, después, haga clic en **Sí** en la advertencia que aparece.
     - Seleccione **Deshabilitar OWA para dispositivos** y después haga clic en **Sí** en la advertencia que aparece.

   - En la sección **Conectividad de correo electrónico** para Outlook en la Web, haga clic en **Deshabilitar** y después haga clic en **Sí** en la advertencia que aparece.

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a>Paso 6 opcional: Quitar la cuenta en peligro de todos los grupos de roles administrativos

> [!NOTE]
> La pertenencia a grupos de roles administrativos puede restaurarse después de haber asegurado la cuenta.

1. Inicie sesión con una cuenta de administrador global:

2. En el Centro de administración de Microsoft 365, siga estos pasos:

   1. Vaya a **Usuarios** \> **Usuarios activos**.
   2. Busque y seleccione la cuenta de usuario, haga clic en el ![icono Más](../../media/ITPro-EAC-MoreOptionsIcon.png) y después seleccione **Administrar roles**.
   3. Quite todos los roles administrativos que están asignados a la cuenta. Cuando haya terminado, haga clic en **Guardar cambios**.

3. En el Centro de seguridad y cumplimiento en <https://protection.office.com>, siga estos pasos:

   Seleccione **Permisos**, seleccione cada grupo de roles de la lista y busque la cuenta de usuario en la sección **Miembros** del menú flotante de detalles que aparece. Si el grupo de roles contiene la cuenta de usuario, siga estos pasos:

   a. Haga clic en **Editar** junto a **Miembros**.
   b. En el control flotante **Editar Elegir miembros** que aparece, haga clic en **Editar**.
   c. En el control flotante **Elegir miembros** que aparece, seleccione la cuenta de usuario y haga clic en **Quitar**. Cuando haya terminado, haga clic en **Listo**, **Guardar** y después en **Cerrar**.

4. En el EAC, en <admin.protection.outlook.com/ecp/>, siga estos pasos:

   Seleccione **Permisos**, seleccione manualmente cada grupo de roles y, en el panel de detalles, compruebe las cuentas de usuario en la sección **Miembros**.  Si el grupo de roles contiene la cuenta de usuario, siga estos pasos:

   a. Seleccione el grupo de roles y haga clic en **Editar** ![icono Editar](../../media/ITPro-EAC-EditIcon.png).
   b. En la sección **Miembro**, seleccione la cuenta de usuario y después haga clic en **Quitar** ![icono Quitar](../../media/ITPro-EAC-RemoveIcon.gif). Cuando haya terminado, haga clic en **Guardar**.

### <a name="step-7-optional-additional-precautionary-steps"></a>Paso 7 opcional: Pasos de precauciones adicionales

1. Asegúrese de comprobar los elementos enviados. Puede que tenga que informar a los usuarios de la lista de contactos de que su cuenta está comprometida. El atacante puede haberles pedido dinero fingiendo, por ejemplo, que estaba perdido en un país distinto y necesitaba dinero, o el atacante puede enviarles un virus para obtener acceso también a sus equipos.

2. Cualquier otro servicio que use esta cuenta de Exchange como cuenta de correo electrónico alternativa puede haberse comprometido también. En primer lugar, siga estos pasos para la suscripción de Microsoft 365 y, a continuación, siga estos pasos para sus otras cuentas.

3. Asegúrese de que la información de contacto, como los números de teléfono y direcciones, es correcta.

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>Proteger Microsoft 365 como un profesional de la ciberseguridad

Su suscripción a Microsoft 365 incluye un potente conjunto de capacidades de seguridad que puede usar para proteger sus datos y los usuarios.  Use el [Plan de seguridad de Microsoft 365: principales prioridades para los primeros 30 días, 90 días y en adelante](security-roadmap.md) para implementar las prácticas recomendadas de Microsoft para proteger su espacio empresarial de Microsoft 365.

- Tareas a realizar en los primeros 30 días.  Estas tienen un efecto inmediato y de bajo impacto para los usuarios.

- Tareas para llevar a cabo en 90 días. Estas tareas necesitan un poco más de tiempo para planearlas e implementarlas, pero mejoran considerablemente el nivel de seguridad.

- Más de 90 días. Estas mejoras se crean en el trabajo de los 90 primeros días.

## <a name="see-also"></a>Vea también

- [Detectar y corregir las reglas de Outlook y ataques de inserciones de formularios personalizados en Microsoft 365](detect-and-remediate-outlook-rules-forms-attack.md)

- [Centro de Quejas de Crímenes por Internet](https://www.ic3.gov/preventiontips.aspx)

- [Bolsas de valores de EE. UU.: Fraude de suplantación de identidad](https://www.sec.gov/investor/pubs/phishing.htm)

- Para informar directamente a Microsoft y su administrador sobre el correo no deseado [Use el complemento Informar sobre el mensaje](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)
