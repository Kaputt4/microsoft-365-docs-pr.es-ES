---
title: Actualizar listas de distribución a Grupos de Microsoft 365 en Outlook
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
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
description: Obtenga información sobre cómo actualizar una o varias listas de distribución a Grupos de Microsoft 365 en Outlook y cómo usar PowerShell para actualizar varias listas de distribución simultáneamente.
ms.openlocfilehash: 832d65854a6a18ad28e3d9fca6d1d11c17146c80
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/12/2022
ms.locfileid: "64782267"
---
# <a name="upgrade-distribution-lists-to-microsoft-365-groups-in-outlook"></a>Actualizar listas de distribución a Grupos de Microsoft 365 en Outlook

Puede actualizar las listas de distribución a Grupos de Microsoft 365 en Outlook. Esta es una excelente manera de proporcionar a las listas de distribución de su organización todas las características y funciones de Grupos de Microsoft 365. [Por qué debería actualizar sus listas de distribución a grupos de Outlook](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)

Puede actualizar las dll de uno en uno o varias al mismo tiempo.

## <a name="upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a>Actualice uno o varios grupos de listas de distribución a Grupos de Microsoft 365 en Outlook

Debe ser un administrador global o Exchange administrador para actualizar un grupo de listas de distribución. Para actualizar a Grupos de Microsoft 365, el grupo de lista de distribución debe tener un propietario con un buzón.

### <a name="use-the-new-eac-to-upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a>Use el nuevo EAC para actualizar uno o varios grupos de listas de distribución a Grupos de Microsoft 365 en Outlook

1. Vaya al nuevo centro de administración de Exchange > **Grupos de destinatarios**\>.<a href="https://go.microsoft.com/fwlink/?linkid=2183233" target="_blank"></a>

2. Seleccione el grupo de lista de distribución (también denominado **grupo de distribución**) que desea actualizar a Microsoft 365 grupo desde la página **Grupos**.

3. Seleccione el **grupo Actualizar distribución** en la barra de herramientas.

4. En el cuadro de diálogo **¿Listo para actualizar?**, haga clic en **Actualizar**. El proceso comienza inmediatamente. Según el tamaño y el número de grupos de lista de distribución que va a actualizar, el proceso puede tardar minutos o horas.

> [!NOTE]
> Un banner en la parte superior indica la actualización, por ejemplo, *los grupos de distribución se han actualizado. Los cambios tardarán 5 minutos en reflejarse. Filtre por Microsoft 365 grupos para ver los grupos de distribución actualizados*.

### <a name="use-the-classic-eac-to-upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a>Use el EAC clásico para actualizar uno o varios grupos de listas de distribución a Grupos de Microsoft 365 en Outlook

1. Vaya al centro de administración de Exchange > **grupos de destinatarios**\>.<a href="https://go.microsoft.com/fwlink/?linkid=2183233" target="_blank"></a><br/>Verá un aviso que indica que tiene listas de distribución (también denominadas **grupos de distribución**) que son aptas para actualizarse a Grupos de Microsoft 365.<br/> ![Seleccione el botón Comenzar.](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)

1. Seleccione una o varias listas de distribución (también **denominadas grupos de distribución**) en la página **grupos** .<br/>![Seleccione un grupo de distribución.](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)

1. Seleccione el icono de actualización.<br/>![Actualice al icono de Grupos de Microsoft 365.](../../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

1. En el cuadro de diálogo de información, seleccione **Sí** para confirmar la actualización. El proceso comienza inmediatamente. Según el tamaño y el número de DLs que esté actualizando, el proceso puede tardar minutos o horas.<br/>Si no se puede actualizar la lista de distribución, aparece un cuadro de diálogo que lo indica. Consulte [¿Qué listas de distribución no se pueden actualizar?](#which-distribution-lists-cant-be-upgraded).

1. Si va a actualizar varias listas de distribución, use la lista desplegable para filtrar qué listas de distribución se han actualizado. Si la lista no está completa, espere un tiempo más y, a continuación, seleccione **Actualizar** para ver lo que se ha actualizado correctamente.<br/>No hay ningún aviso que le indique cuándo se ha completado el proceso de actualización para todas las DLs que seleccionó. Para averiguarlo, busque lo que aparece en **Disponible para actualizaciones** o **DLs actualizadas**.

1. Si seleccionó un archivo DL para la actualización, pero sigue apareciendo en la página como Disponible para actualizar, no se pudo actualizar. Consulte [Qué hacer si la actualización no funciona](#what-to-do-if-the-upgrade-doesnt-work).

> [!NOTE]
> Si recibe los mensajes de correo electrónico de resumen de grupos, es posible que observe en la parte inferior que a veces le ofrecerá que le permita actualizar las listas de distribución aptas de las que es propietario. Consulte [Tener una conversación grupal en Outlook](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22) para obtener más información sobre los correos electrónicos de resumen.

## <a name="what-to-do-if-the-upgrade-doesnt-work"></a>Qué hacer si la actualización no funciona

Las listas de distribución que no se pueden actualizar permanecen sin cambios.

Si una o varias listas de distribución **aptas** no se pueden actualizar, 

1. Use [este script](https://aka.ms/DLToM365Group) para buscar posibles problemas que puedan impedir la actualización de la lista de distribución a Microsoft 365 grupo, corregir los problemas notificados por el script e intentar actualizar la lista de distribución una vez más. 

2. Si el script anterior no ayuda o si el problema persiste, abra una [incidencia de soporte](../../business-video/get-help-support.md) técnico. El problema tendrá que escalarse al equipo de ingeniería de grupos para que puedan averiguar el problema.

## <a name="how-to-use-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a>Cómo usar PowerShell para actualizar varias listas de distribución al mismo tiempo

Si tiene experiencia en el uso de PowerShell, es posible que desee realizar esta ruta en lugar de usar la interfaz de usuario. Tenemos un conjunto de cmdlets que le ayudarán a actualizar las listas de distribución. Véalo a continuación.

### <a name="upgrade-a-single-dl"></a>Actualización de un único archivo DL

Para actualizar un único archivo DL, ejecute el siguiente comando:

```PowerShell
Upgrade-DistributionGroup -DlIdentities <Dl SMTP address>
```

Por ejemplo, si desea actualizar un archivo DL con la dirección SMTP dl1@contoso.com, ejecute el siguiente comando:

```PowerShell
Upgrade-DistributionGroup -DlIdentities dl1@contoso.com
```

> [!NOTE]
> También puede actualizar una lista de distribución única a un grupo de Microsoft 365 mediante el cmdlet de PowerShell [New-UnifiedGroup](/powershell/module/exchange/new-unifiedgroup).

### <a name="upgrade-multiple-dls-in-a-batch"></a>Actualización de varias direcciones URL en un lote

También puede pasar varias direcciones URL como un lote y actualizarlas juntas:

```PowerShell
Upgrade-DistributionGroup -DlIdentities <DL SMTP address1>, <DL SMTP address2>,
<DL SMTP address3>, <DL SMTP address4>
```

Por ejemplo, si desea actualizar cinco direcciones URL con la dirección `dl1@contoso.com` SMTP y `dl2@contoso.com`, `dl3@contoso.com``dl4@contoso.com` y `dl5@contoso.com`, ejecute el siguiente comando:

```powershell
Upgrade-DistributionGroup -DlIdentities dl1@contoso.com, dl2@contoso.com, dl3@contoso.com, dl4@contoso.com, dl5@contoso.com
```

### <a name="upgrade-all-eligible-dls"></a>Actualizar todas las listas de distribución válidas

Hay dos maneras de actualizar todas las listas de distribución válidas.

> [!NOTE]
> El cmdlet Upgrade-DistributionGroup no recibe datos de la canalización, por este motivo es necesario usar el operador "foreach-object{}" para ejecutarse correctamente.

1. Obtenga las listas de distribución válidas en el inquilino y actualícelas con el comando de actualización:

   ```PowerShell
   Get-EligibleDistributionGroupForMigration | Foreach-Object{
       Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
   }
   ```

2. Obtenga la lista de todas las direcciones URL y actualice solo las direcciones URL aptas:

   ```PowerShell
   Get-DistributionGroup| Foreach-Object{
       Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
   }
   ```

## <a name="faq-about-upgrading-distribution-lists-to-microsoft-365-groups-in-outlook"></a>Preguntas más frecuentes sobre la actualización de listas de distribución a Grupos de Microsoft 365 en Outlook

### <a name="which-distribution-lists-cant-be-upgraded"></a>¿Qué listas de distribución no se pueden actualizar?

Solo puede actualizar listas de distribución administradas en la nube, sencillas y no anidadas. En la tabla siguiente se enumeran las listas de distribución que **no se pueden** actualizar.

|Propiedad|¿Apta?|
|---|---|
|Lista de distribución administrada de forma local.|No|
|Listas de distribución anidadas. La lista de distribución tiene grupos secundarios o es miembro de otro grupo.|No|
|Listas de distribución con **miembros RecipientTypeDetails** distintos de **UserMailbox**, **SharedMailbox**, **TeamMailbox**, **MailUser**|No|
|Lista de distribución que tiene más de 100 propietarios|No|
|Lista de distribución que solo tiene miembros, pero sin propietario|No|
|Lista de distribución que tiene alias que contiene caracteres especiales|No|
|Si la lista de distribución está configurada para ser una dirección de reenvío para el buzón compartido|No|
|Si la lista de distribución forma parte de la **Restricción del remitente** en otra lista.|No|
|Grupos de seguridad|No|
|Listas de distribución dinámica|No|
|Listas de distribución que se han convertido en **RoomLists**|No|

### <a name="check-which-dls-are-eligible-for-upgrade"></a>Compruebe qué DL son aptas para la actualización.

Si desea comprobar si un archivo DL es apto o no, puede ejecutar el siguiente comando:

```PowerShell
Get-DistributionGroup <DL SMTP address> | Get-EligibleDistributionGroupForMigration
```

Si desea comprobar qué direcciones URL son aptas para la actualización, ejecute el siguiente comando:

```PowerShell
Get-EligibleDistributionGroupForMigration
```

### <a name="who-can-run-the-upgrade-scripts"></a>Quién puede ejecutar los scripts de actualización?

Personas con derechos de administrador global o Exchange administrador.

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-an-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a>¿Por qué la tarjeta de contacto sigue mostrando una lista de distribución? ¿Qué debo hacer para evitar que una lista de distribución actualizada aparezca en mi lista de sugerencias automáticas?

- Por Outlook: cuando alguien intenta enviar un correo electrónico en Outlook escribiendo el nombre del grupo Microsoft 365 después de la migración, el destinatario se resolverá como la lista de distribución en lugar del grupo. La tarjeta de contacto del destinatario será la tarjeta de contacto de las listas de distribución. Esto se debe a la caché de destinatarios o a la caché de nombres de nick en Outlook. El correo electrónico se enviará correctamente al grupo, pero podría causar confusión al remitente.<br/>Puede realizar los pasos de este artículo, [Información sobre la lista de autocompletar de Outlook](/outlook/troubleshoot/contacts/information-about-the-outlook-autocomplete-list) para restablecer la memoria caché, lo que solucionará este problema.

- Para Outlook en la Web: en caso de Outlook en la Web, el destinatario de la lista de distribución seguirá en la memoria caché. Puede seguir los pasos descritos en [Quitar el nombre sugerido o la dirección de correo electrónico de la lista de autocompletar](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58) para actualizar la memoria caché para ver la tarjeta de contacto del grupo.

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a>¿Los nuevos miembros del grupo reciben un correo electrónico de bienvenida en su bandeja de entrada?

No. La configuración para habilitar los mensajes de bienvenida se establece en false de forma predeterminada. Esta configuración afecta tanto a los miembros del grupo existentes como a los nuevos que pueden unirse una vez completada la migración. Si más adelante el propietario del grupo permite a los usuarios invitados, los usuarios invitados no recibirán un correo electrónico de bienvenida en su bandeja de entrada. Los miembros invitados pueden seguir trabajando con el grupo.

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a>¿Qué ocurre si una o algunas de las DLs no se actualizan?

Hay algunos casos en los que aunque DL es apto pero no se pudo actualizar. El archivo DL no se actualiza y permanece como un archivo DL.

- Cuando el administrador ha aplicado la **directiva de dirección de correo electrónico de grupo** para los grupos de una organización e intenta actualizar las direcciones URL que no cumplen los criterios, la dll no se actualiza.

- No se pudieron actualizar las dll con **MemberJoinRestriction** o **MemberDepartRestriction** establecidas en **Closed**.

- La creación de grupos de Microsoft 365 solo se permite a pocos usuarios, siguiendo los pasos de [este artículo](/microsoft-365/solutions/manage-creation-of-groups). En este escenario, si el propietario de la lista de distribución no puede crear Microsoft 365 grupo, la lista de distribución no se actualizará a Microsoft 365 grupo.
Solución alternativa: use una de las siguientes soluciones alternativas para el escenario anterior:

1. Asegúrese de que todos los usuarios mencionados como propietarios de la dll pueden crear el grupo M365, es decir, son miembros del grupo de seguridad que tiene permiso para el grupo M365.

   OR

2. Reemplace temporalmente el propietario de la dll que no tiene permiso para crear el grupo de M365 por un usuario que tenga permiso para crear el grupo M365.

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a>¿Qué ocurre con la dll si se produce un error en la actualización desde EAC?

La actualización solo se realizará cuando se envíe la llamada al servidor. Si se produce un error en la actualización, las dll estarán intactas. Funcionarán como antes.

### <a name="what-happens-to-message-approval-moderation-settings-on-distribution-groups-after-upgrading"></a>¿Qué ocurre con la configuración de aprobación de mensajes (moderación) en los grupos de distribución después de la actualización?

La configuración de aprobación de mensajes (moderación) se conserva y sigue funcionando correctamente después de actualizar el grupo de distribución a un grupo de Microsoft 365.

## <a name="related-content"></a>Contenido relacionado

[Comparar grupos](../create-groups/compare-groups.md) (artículo)\
[Explicación de Grupos de Microsoft 365 a los usuarios](../create-groups/explain-groups-knowledge-worker.md) (artículo)\
[Agregar o quitar miembros de grupos de Microsoft 365 mediante el Centro de administración](../create-groups/add-or-remove-members-from-groups.md)
