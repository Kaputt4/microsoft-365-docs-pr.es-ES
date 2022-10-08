---
title: Actualizar listas de distribución a Grupos de Microsoft 365 en Exchange Online
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkEXCHANGE
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 787d7a75-e201-46f3-a242-f698162ff09f
description: Obtenga información sobre cómo actualizar una o varias listas de distribución a Grupos de Microsoft 365 en Exchange Online y cómo usar PowerShell para actualizar varias listas de distribución simultáneamente.
ms.openlocfilehash: ba0555011cba2dcc3bd8285d577c61ef3c7ddded
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68203231"
---
# <a name="upgrade-distribution-lists-to-microsoft-365-groups-in-exchange-online"></a>Actualizar listas de distribución a Grupos de Microsoft 365 en Exchange Online

Actualizar una lista de distribución a un grupo de Microsoft 365 es una excelente manera de mejorar las características y funcionalidades de los grupos de su organización. Para obtener más información, vea [Por qué debe actualizar las listas de distribución a grupos en Outlook](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188).

Puede actualizar las listas de distribución de uno en uno o varias al mismo tiempo. Puede usar el Centro de administración de Exchange (EAC) o Exchange Online PowerShell.

## <a name="upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups"></a>Actualice uno o varios grupos de listas de distribución a Grupos de Microsoft 365

Debe ser administrador global o administrador de Exchange para actualizar una lista de distribución. Para actualizar a Grupos de Microsoft 365, la lista de distribución debe tener un propietario designado y ese propietario debe ser un buzón de correo.

### <a name="use-the-classic-eac-to-upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a>Uso del EAC clásico para actualizar uno o varios grupos de listas de distribución a Grupos de Microsoft 365 en Outlook

> [!NOTE]
> Los procedimientos de esta sección no están disponibles en el nuevo EAC.

1. Vaya al Centro de administración de Exchange > **Grupos de destinatarios**\>.<a href="https://go.microsoft.com/fwlink/?linkid=2183233" target="_blank"></a>

   Verá un aviso que indica que tiene listas de distribución (también denominadas **grupos de distribución**) que son aptas para actualizarse a Grupos de Microsoft 365.
   
   ![Seleccione el botón Introducción.](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)

1. Seleccione una o varias listas de distribución (también **denominadas grupos de distribución**) en la página **grupos** .

   ![Seleccione un grupo de distribución.](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)

1. Seleccione el icono de actualización.

   ![Actualice al icono de Grupos de Microsoft 365.](../../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

1. En el cuadro de diálogo de información, seleccione **Sí** para confirmar la actualización. El proceso comienza inmediatamente. Según el tamaño y el número de iluminaciones de distribución que esté actualizando, el proceso puede tardar minutos o horas.

   Si no se puede actualizar la lista de distribución, aparece un cuadro de diálogo que lo indica. Consulte [¿Qué listas de distribución no se pueden actualizar?](#which-distribution-lists-cant-be-upgraded).

1. Si va a actualizar varias listas de distribución, use la lista desplegable para filtrar qué listas de distribución se han actualizado. Si la lista no está completa, espere un tiempo más y, a continuación, seleccione **Actualizar** para ver lo que se ha actualizado correctamente.

**Notas**:

- No recibirá una notificación cuando se completen las actualizaciones. En su lugar, consulte lo que aparece en **Disponible para** **las dll actualizadas o actualizadas**.

- Si seleccionó una lista de distribución para la actualización, pero sigue apareciendo en la página como **Disponible para actualizar**, no se pudo actualizar. Consulte [Qué hacer si la actualización no funciona](#what-to-do-if-the-upgrade-doesnt-work).

- Es posible que el correo electrónico de resumen de un grupo le permita actualizar las listas de distribución aptas de las que sea propietario. Para obtener más información sobre el correo electrónico de resumen, vea [Tener una conversación de grupo en Outlook](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22).

## <a name="what-to-do-if-the-upgrade-doesnt-work"></a>Qué hacer si la actualización no funciona

Las listas de distribución que no se pueden actualizar permanecen sin cambios.

Si no se pueden actualizar una o varias listas de distribución **aptas** , siga estos pasos:

1. Use [este script](https://aka.ms/DLToM365Group) para buscar posibles problemas. Corrija los problemas notificados por el script e intente actualizar la lista de distribución una vez más. 

2. Si el script no ayuda, abra una [incidencia de soporte técnico](../../business-video/get-help-support.md). El problema tendrá que escalarse al equipo de ingeniería de grupos.

## <a name="how-to-use-exchange-online-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a>Cómo usar Exchange Online PowerShell para actualizar varias listas de distribución al mismo tiempo

Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

### <a name="upgrade-a-single-distribution-list"></a>Actualización de una lista de distribución única

Para actualizar una lista de distribución única, use la sintaxis siguiente:

```PowerShell
Upgrade-DistributionGroup -DLIdentities <EmailAddress>
```

En este ejemplo se actualiza la lista de distribución marketing@contoso.com:

```PowerShell
Upgrade-DistributionGroup -DLIdentities marketing@contoso.com
```

Para obtener información detallada sobre la sintaxis y los parámetros, vea [Upgrade-DistributionGroup](/powershell/module/exchange/upgrade-distributiongroup).

> [!NOTE]
> También puede actualizar una lista de distribución única a un grupo de Microsoft 365 mediante el cmdlet [New-UnifiedGroup](/powershell/module/exchange/new-unifiedgroup) .

### <a name="upgrade-multiple-distribution-lists-at-the-same-time"></a>Actualizar varias listas de distribución al mismo tiempo

Para actualizar varias listas de distribución al mismo tiempo, use la sintaxis siguiente:

```PowerShell
Upgrade-DistributionGroup -DLIdentities <EmailAddress1>,<EmailAddress2>,...
```

En este ejemplo se actualizan las listas de distribución especificadas a Grupos de Microsoft 365.

```powershell
Upgrade-DistributionGroup -DLIdentities marketing@contoso.com,finanace@contoso.com,hr@contoso.com
```

Para obtener información detallada sobre la sintaxis y los parámetros, vea [Upgrade-DistributionGroup](/powershell/module/exchange/upgrade-distributiongroup).

### <a name="upgrade-all-eligible-distribution-lists"></a>Actualización de todas las listas de distribución aptas

Use cualquiera de los métodos siguientes para actualizar todas las listas de distribución aptas a Grupos de Microsoft 365:

- Actualice todas las listas de distribución aptas:

   ```PowerShell
   $All = Get-EligibleDistributionGroupForMigration -ResultSize unlimited
   $All | Foreach-Object {Upgrade-DistributionGroup -DLIdentities $_.PrimarySMTPAddress}
   ```

- Intente actualizar todas las listas de distribución tanto si son aptas como si no:

   ```PowerShell
   $All Get-DistributionGroup -RecipientTypeDetails MailUniversalDistributionGroup -ResultSize unlimited
   $All | Foreach-Object {Upgrade-DistributionGroup -DLIdentities $_.PrimarySMTPAddress}
   ```

## <a name="faq-about-upgrading-distribution-lists-to-microsoft-365-groups-in-outlook"></a>Preguntas más frecuentes sobre la actualización de listas de distribución a Grupos de Microsoft 365 en Outlook

### <a name="which-distribution-lists-cant-be-upgraded"></a>¿Qué listas de distribución no se pueden actualizar?

Solo puede actualizar listas de distribución administradas en la nube, sencillas y no anidadas. En la tabla siguiente se enumeran las listas de distribución que **no se pueden** actualizar.

|Propiedad|¿Apta?|
|---|:---:|
|Lista de distribución administrada de forma local.|No|
|Listas de distribución anidadas. La lista de distribución tiene grupos secundarios o es miembro de otro grupo.|No|
|Listas de distribución en las que uno o varios miembros son algo distinto de un buzón de usuario, un buzón compartido, un buzón de equipo o un usuario de correo. En otras palabras, el valor **RecipientTypeDetails** de cualquier miembro de la lista de distribución no es **UserMailbox**, **SharedMailbox**, **TeamMailbox** o **MailUser**.|No|
|Lista de distribución que tiene más de 100 propietarios.|No|
|Lista de distribución que solo tiene miembros pero ningún propietario.|No|
|Lista de distribución que tiene alias que contienen caracteres especiales.|No|
|La lista de distribución está configurada para ser una dirección de reenvío para un buzón compartido.|No|
|La lista de distribución forma parte de **La restricción del remitente** en otra lista de distribución.|No|
|Grupos de seguridad habilitados para correo.|No|
|Grupos de distribución dinámicos.|No|
|Listas de distribución convertidas en **RoomLists**.|No|

### <a name="check-which-distribution-lists-are-eligible-for-upgrade"></a>Comprobación de qué listas de distribución son aptas para la actualización

Para comprobar si una lista de distribución específica es apta para la actualización, ejecute el siguiente comando:

```PowerShell
Get-DistributionGroup <EmailAddress> | Get-EligibleDistributionGroupForMigration
```

Para ver todos los grupos de distribución aptos para la actualización, ejecute el siguiente comando:

```PowerShell
Get-EligibleDistributionGroupForMigration
```

### <a name="who-can-run-the-upgrade-scripts"></a>¿Quién puede ejecutar los scripts de actualización?

Personas con derechos de administrador global o administrador de Exchange.

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-an-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a>¿Por qué la tarjeta de contacto sigue mostrando una lista de distribución? ¿Qué debo hacer para evitar que una lista de distribución actualizada aparezca en mi lista de sugerencias automáticas?

- **Outlook**: después de actualizar una lista de ditribución a un grupo de Microsoft 365, la caché de destinatarios local del usuario (también conocida como caché de nombres nick) no conoce el cambio. Siga los pasos descritos en el artículo siguiente para restablecer la caché de destinatarios local del usuario: [Información sobre la lista autocompletar de Outlook](/outlook/troubleshoot/contacts/information-about-the-outlook-autocomplete-list). 

  Si no actualiza la caché de destinatarios, cualquier correo electrónico enviado al grupo de Microsoft 365 se entregará correctamente, pero los siguientes problemas permanecerán:
  
  - El destinatario del grupo se resolverá como la lista de distribución en lugar del grupo de Microsoft 365.
  - La tarjeta de contacto será el contacto de la lista de distribución en lugar del grupo de Microsoft 365.

- **Outlook en la Web**: al igual que Outlook, la lista de distribución permanecerá en la caché de destinatarios. Siga los pasos de este artículo para actualizar la memoria caché para ver la tarjeta de contacto del grupo: [Quitar el nombre sugerido o la dirección de correo electrónico de la lista de autocompletar](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58).

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a>¿Los nuevos miembros del grupo reciben un correo electrónico de bienvenida en su bandeja de entrada?

No. La configuración para habilitar los mensajes de bienvenida se establece en false de forma predeterminada. Esta configuración afecta tanto a los miembros del grupo existentes como a los nuevos que pueden unirse una vez completada la migración. Si más adelante el propietario del grupo permite a los usuarios invitados, los usuarios invitados no recibirán un correo electrónico de bienvenida en su Bandeja de entrada. Los miembros invitados pueden seguir trabajando con el grupo.

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a>¿Qué ocurre si una o algunas de las DLs no se actualizan?

Hay algunos casos en los que las listas de distribución aptas no se pueden actualizar. Por ejemplo:

- Un administrador ha aplicado una directiva de **dirección de Email** grupo y la lista de distribución no cumple los requisitos de la directiva.

- Una lista de distribución tiene **los valores MemberJoinRestriction** o **MemberDepartRestriction** establecidos en el valor **Closed**.

- La creación de grupos de Microsoft 365 está limitada como se describe en este artículo: [este artículo](/microsoft-365/solutions/manage-creation-of-groups).

  Use una de las siguientes soluciones alternativas para este problema específico:

  - Asegúrese de que todos los propietarios de la lista de distribución pueden crear Grupos de Microsoft 365 (es decir, los propietarios son miembros del grupo de seguridad al que se permite crear Grupos de Microsoft 365).

  - Reemplace temporalmente el propietario de la lista de distribución por un usuario que tenga permiso para crear Grupos de Microsoft 365.

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a>¿Qué ocurre con la dll si se produce un error en la actualización desde EAC?

La actualización solo se realizará cuando se envíe la llamada al servidor. Si se produce un error en la actualización, las listas de distribución permanecerán y funcionarán como antes.

### <a name="what-happens-to-message-approval-moderation-settings-on-distribution-groups-after-upgrading"></a>¿Qué ocurre con la configuración de aprobación de mensajes (moderación) en los grupos de distribución después de la actualización?

La configuración de aprobación de mensajes (moderación) se conserva y sigue funcionando bien después de actualizar el grupo de distribución a un grupo de Microsoft 365.

## <a name="related-content"></a>Contenido relacionado

[Comparar grupos](../create-groups/compare-groups.md) (artículo)\
[Explicación de Grupos de Microsoft 365 a los usuarios](../create-groups/explain-groups-knowledge-worker.md) (artículo)\
[Agregar o quitar miembros de grupos de Microsoft 365 mediante el Centro de administración](../create-groups/add-or-remove-members-from-groups.md)
