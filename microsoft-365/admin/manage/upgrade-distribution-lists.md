---
title: Actualizar listas de distribución a Grupos de Microsoft 365 en Outlook
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 787d7a75-e201-46f3-a242-f698162ff09f
description: Obtenga información sobre cómo actualizar una o varias listas de distribución a Grupos de Microsoft 365 en Outlook y cómo usar PowerShell para actualizar varias listas de distribución simultáneamente.
ms.openlocfilehash: 95f887b4386b349dc9d8bb471deab19b5425f6f5
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080532"
---
# <a name="upgrade-distribution-lists-to-microsoft-365-groups-in-outlook"></a>Actualizar listas de distribución a Grupos de Microsoft 365 en Outlook

Puede actualizar listas de distribución a Grupos de Microsoft 365 con Outlook. Esta es una excelente manera de proporcionar a las listas de distribución de su organización todas las características y funcionalidades de grupos de Microsoft 365. [Por qué debería actualizar sus listas de distribución a grupos de Outlook](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)

Puede actualizar las DLs de una en una, o varias al mismo tiempo.

## <a name="upgrade-one-or-many-distribution-lists-to-microsoft-365-groups-in-outlook"></a>Actualizar una o varias listas de distribución a Grupos de Microsoft 365 en Outlook

Debe ser administrador global o administrador de Exchange para actualizar una lista de distribución. Para actualizar a Grupos de Microsoft 365, un grupo de distribución debe tener un propietario con un buzón.

1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a>.

2. En el Centro de administración de Exchange, vaya **a Grupos de** \> **destinatarios.**<br/>Verá un aviso que indica que tiene listas de distribución (también denominadas grupos de **distribución)** que pueden actualizarse a Grupos de Microsoft 365.<br/> ![Seleccionar el botón Introducción](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)

3. Seleccione una o más listas de distribución (también denominadas grupos **de distribución)** en la **página de** grupos.<br/>![Seleccionar un grupo de distribución](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)

4. Seleccione el icono de actualización.<br/>![Actualizar al icono grupos de Microsoft 365](../../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

5. En el cuadro de diálogo de información, **seleccione Sí** para confirmar la actualización. El proceso comienza inmediatamente. Según el tamaño y el número de DLs que actualice, el proceso puede tardar minutos u horas.<br/>Si la lista de distribución no se puede actualizar, aparece un cuadro de diálogo que lo dice. Vea [¿Qué listas de distribución no se pueden actualizar?](#which-distribution-lists-cant-be-upgraded).

6. Si va a actualizar varias listas de distribución, use la lista desplegable para filtrar qué listas de distribución se han actualizado. Si la lista no está completa, espere  un poco más y, a continuación, seleccione Actualizar para ver qué se ha actualizado correctamente.<br/>No hay ningún aviso que le indique cuándo se ha completado el proceso de actualización para todas las direcciones URL que seleccionó. Puede averiguarlo si quiere ver lo que aparece en Disponible para la **actualización** o las **DLL actualizadas.**

7. Si seleccionó una DL para la actualización, pero aún aparece en la página como Disponible para actualizar, no se pudo actualizar. Vea [Qué hacer si la actualización no funciona.](#what-to-do-if-the-upgrade-doesnt-work)

> [!NOTE]
> If you're getting the groups digest emails you may notice at the bottom that it will sometimes offer to let you upgrade any eligible distribution lists that you're the owner of. Vea [Tener una conversación de grupo en Outlook](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22) para obtener más información acerca de los correos electrónicos de resumen.

## <a name="what-to-do-if-the-upgrade-doesnt-work"></a>Qué hacer si la actualización no funciona

Las listas de distribución que no se pueden actualizar permanecen sin cambios.

Si una o más listas **de** distribución aptas no se pueden actualizar, abra un vale [de soporte técnico.](../contact-support-for-business-products.md) El problema deberá escalarse al equipo de ingeniería de grupos para que puedan averiguar el problema.

Es posible que la lista de distribución no se haya actualizado debido a una interrupción del servicio, pero es bastante poco probable. Si lo desea, espere un tiempo y vuelva a intentar actualizar la DL.

## <a name="how-to-use-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a>Cómo usar PowerShell para actualizar varias listas de distribución al mismo tiempo

Si tienes experiencia en el uso de PowerShell, es posible que quieras ir a esta ruta en lugar de usar la interfaz de usuario. Tenemos un conjunto de cmdlets que le ayudarán a actualizar las listas de distribución. Véalo a continuación.

### <a name="upgrade-a-single-dl"></a>Actualizar una sola DL

Para actualizar una sola DL, ejecute el siguiente comando:

```PowerShell
Upgrade-DistributionGroup -DlIdentities \<Dl SMTP address\>`
```

Por ejemplo, si desea actualizar una DLs con una dirección SMTP dl1@contoso.com, ejecute el siguiente comando:

```PowerShell
Upgrade-DistributionGroup -DlIdentities dl1@contoso.com`
```

> [!NOTE]
> También puede actualizar una única lista de distribución a un grupo de Microsoft 365 con el cmdlet de PowerShell [New-UnifiedGroup](https://go.microsoft.com/fwlink/?LinkID=786379)

### <a name="upgrade-multiple-dls-in-a-batch"></a>Actualizar varias DLs en un lote

También puede pasar varias DL como un lote y actualizarlas juntas:

```PowerShell
Upgrade-DistributionGroup -DlIdentities \<DL SMTP address1\>, \< DL SMTP address2\>,
\< DL SMTP address3\>, \< DL SMTP address 4\>
```

Por ejemplo, si desea actualizar cinco DLs con dirección SMTP y `dl1@contoso.com` , y , ejecute el siguiente `dl2@contoso.com` `dl3@contoso.com` `dl4@contoso.com` `dl5@contoso.com` comando:

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com, dl2@contoso.com, dl3@contoso.com, dl4@contoso.com, dl5@contoso.com`

### <a name="upgrade-all-eligible-dls"></a>Actualizar todas las DLs aptas

Hay dos formas de actualizar todas las DLs aptas.

> [!NOTE]
> El Upgrade-DistributionGroup cmdlet no recibe datos de la canalización, por este motivo es necesario usar el operador "foreach-object" para {} ejecutarse correctamente.

1. Obtenga las DLs aptas en el inquilino y actualícórlas con el comando de actualización:

```PowerShell
Get-EligibleDistributionGroupForMigration | Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

2. Obtenga la lista de todas las DL y actualice solo las DLs aptas:

```PowerShell
Get-DistributionGroup| Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

## <a name="faq-about-upgrading-distribution-lists-to-microsoft-365-groups-in-outlook"></a>Preguntas más frecuentes sobre cómo actualizar listas de distribución a Grupos de Microsoft 365 en Outlook

### <a name="which-distribution-lists-cant-be-upgraded"></a>¿Qué listas de distribución no se pueden actualizar?

Solo puede actualizar listas de distribución sencillas y no anidadas administradas en la nube. En la tabla siguiente se enumeran las listas de distribución **que no** se pueden actualizar.

|**Propiedad**|**¿Elegible?**|
|:-----|:-----|
|Lista de distribución administrada local.  <br/> |No  <br/> |
|Listas de distribución anidadas. La lista de distribución tiene grupos secundarios o es miembro de otro grupo.  <br/> |No  <br/> |
|Listas de distribución con **recipientTypeDetails miembro** distinto de **UserMailbox**, **SharedMailbox**, **TeamMailbox**, **MailUser**  <br/> |No  <br/> |
|Lista de distribución con más de 100 propietarios  <br/> |No  <br/> |
|Lista de distribución que solo tiene miembros pero ningún propietario  <br/> |No  <br/> |
|Lista de distribución que tiene alias que contiene caracteres especiales  <br/> |No  <br/> |
|Si la lista de distribución está configurada para ser una dirección de reenvío para el buzón compartido  <br/> |No  <br/> |
|Si la DL forma parte de **la restricción del remitente** en otra DL.  <br/> |No  <br/> |
|Grupos de seguridad  <br/> |No  <br/> |
|Listas de distribución dinámica  <br/> |No  <br/> |
|Listas de distribución que se han convertido a **RoomLists**  <br/> |No  <br/> |
|Listas de distribución **donde MemberJoinRestriction** o **MemberDepartRestriction** está **cerrado**  <br/> |No  <br/> |

### <a name="check-which-dls-are-eligible-for-upgrade"></a>Comprobar qué DLs son aptas para la actualización

Si desea comprobar si una DL es apta o no, puede ejecutar el siguiente comando:

`Get-DistributionGroup \<DL SMTP address\> | Get-EligibleDistributionGroupForMigration`

Si desea comprobar qué DLs son aptas para la actualización, ejecute el siguiente comando:

`Get-EligibleDistributionGroupForMigration`

### <a name="who-can-run-the-upgrade-scripts"></a>¿Quién puede ejecutar los scripts de actualización?

Personas con derechos de administrador global o administrador de Exchange.

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-a-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a>¿Por qué la tarjeta de contacto sigue mostrando una lista de distribución? ¿Qué debo hacer para evitar que una lista de distribución actualizada se muestre en mi lista de sugerencias automáticas?

- Para Outlook: cuando alguien intenta enviar un correo electrónico en Outlook escribiendo el nombre del grupo de Microsoft 365 después de la migración, el destinatario se resolverá como la lista de distribución en lugar del grupo. La tarjeta de contacto del destinatario será la tarjeta de contacto de listas de distribución. Esto se debe a la caché de destinatarios o a la caché de nombres de alias en Outlook. El correo electrónico se enviará correctamente al grupo, pero puede causar confusión al remitente.<br/>Puede realizar los pasos de este tema, Información sobre la lista [Autocompletar](https://go.microsoft.com/fwlink/?LinkID=798736) de Outlook para restablecer la memoria caché, lo que solucionará este problema.

- Para Outlook en la Web: en el caso de Outlook en la Web, el destinatario de la lista de distribución seguirá estando en la memoria caché. Puede seguir los [](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58) pasos descritos en Quitar el nombre o la dirección de correo electrónico sugeridos de la lista autocompletar para actualizar la memoria caché y ver la tarjeta de contacto del grupo.

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a>¿Los nuevos miembros del grupo reciben un correo electrónico de bienvenida en su bandeja de entrada?

No. La configuración para habilitar los mensajes de bienvenida se establece en false de forma predeterminada. Esta configuración afecta tanto a los miembros del grupo existentes como a los nuevos que pueden unirse una vez completada la migración. Si el propietario del grupo permite más adelante a los usuarios invitados, los usuarios invitados no recibirán un correo electrónico de bienvenida en su bandeja de entrada. Los miembros invitados pueden seguir trabajando con el grupo.

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a>¿Qué ocurre si una o algunas de las DL no se actualizan?

Hay algunos casos en los que dl es apto pero no se puede actualizar. La DL no se actualiza y permanece como una DL.

- Donde el administrador **ha** aplicado la directiva de direcciones de correo electrónico de grupo para los grupos de una organización e intenta actualizar las DLs que no cumplen los criterios, la DL no se actualiza

- Las DLs **con MemberJoinRestriction** o **MemberDepartRestriction** establecidos en **Closed**, no se pudieron actualizar

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a>¿Qué sucede con la DL si se produce un error en la actualización desde el EAC?

La actualización solo se realizará cuando se envía la llamada al servidor. Si se produce un error en la actualización, las DL estarán intactas. Funcionarán como antes.
