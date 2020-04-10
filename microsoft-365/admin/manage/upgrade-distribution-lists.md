---
title: Actualizar listas de distribución a grupos de Office 365 en Outlook
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 787d7a75-e201-46f3-a242-f698162ff09f
description: Obtenga información sobre cómo actualizar una o varias listas de distribución a Office 365 grupos en Outlook y cómo usar PowerShell para actualizar simultáneamente varias listas de distribución.
ms.openlocfilehash: c3acf1d47a37d79d666b1b951bea704c273ccf09
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212286"
---
# <a name="upgrade-distribution-lists-to-office-365-groups-in-outlook"></a>Actualizar listas de distribución a grupos de Office 365 en Outlook

Puede actualizar las listas de distribución a Office 365 grupos con Outlook. Esta es una excelente forma de dar a las listas de distribución de la organización todas las características y funciones de los grupos de Office 365. [Por qué debería actualizar sus listas de distribución a los grupos de Outlook](https://support.office.com/article/7fb3d880-593b-4909-aafa-950dd50ce188.aspx)

Puede actualizar las listas de distribución de una en una o varias al mismo tiempo.

## <a name="upgrade-one-or-many-distribution-lists-to-office-365-groups-in-outlook"></a>Actualizar una o varias listas de distribución a Office 365 grupos en Outlook

Debe ser un administrador global de Office 365 o un administrador de Exchange para actualizar una lista de distribución. Para actualizar a los grupos de Office 365, un grupo de distribución debe tener un propietario con un buzón de correo. 

1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a>.

2. En el centro de administración de Exchange, vaya a **grupos**de **destinatarios** \> .<br/>Verá un aviso en el que se indica que tiene listas de distribución (también denominadas **grupos de distribución** ) que pueden actualizarse a grupos de Office 365.<br/> ![Seleccione el botón introducción](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)

3. Seleccione una o varias listas de distribución (también denominada **grupo de distribución** ) en la página **grupos** .<br/>![Seleccionar un grupo de distribución](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)

4. Seleccione el icono de actualización.<br/>![Icono de actualización a Office 365 grupos](../../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

5. En el cuadro de diálogo información, seleccione **sí** para confirmar la actualización. El proceso comienza inmediatamente. Según el tamaño y el número de DLs que esté actualizando, el proceso puede tardar minutos u horas.<br/>Si no se puede actualizar la lista de distribución, aparece un cuadro de diálogo que le indica. Vea [¿qué listas de distribución no se pueden actualizar?](#which-distribution-lists-cannot-be-upgraded).

6. Si está actualizando varias listas de distribución, use la lista desplegable para filtrar las listas de distribución que se han actualizado. Si la lista no está completa, espere un tiempo y, a continuación, seleccione **Actualizar** para ver lo que se ha actualizado correctamente.<br/>No hay ninguna notificación que le indique cuándo se ha completado el proceso de actualización para todas las listas de distribución que ha seleccionado. Puede averiguarlo buscando ver lo que se muestra en **disponible para actualizar** o actualizar listas de **distribución**.

7. Si seleccionó una DL para la actualización, pero sigue apareciendo en la página como disponible para la actualización, no se pudo actualizar. Consulte [Qué hacer si la actualización no funciona](#what-to-do-if-the-upgrade-doesnt-work).

> [!NOTE]
> Si obtiene los mensajes de correo electrónico de Resumen de los grupos, es posible que observe en la parte inferior que a veces le permitirá actualizar las listas de distribución válidas de las que es propietario. Consulte [tener una conversación grupal en Outlook](https://support.office.com/article/a0482e24-a769-4e39-a5ba-a7c56e828b22.aspx) para obtener más información sobre los mensajes de correo electrónico de texto implícita.


## <a name="what-to-do-if-the-upgrade-doesnt-work"></a>Qué hacer si la actualización no funciona

Las listas de distribución que no se actualizan permanecen sin cambios.

Si se produce un error al actualizar una o más listas de distribución **elegibles** , abra una [incidencia de soporte técnico](../contact-support-for-business-products.md). El problema tendrá que remitirse al equipo de ingeniería de grupos para que pueda resolver el problema.

Es posible que la lista de distribución no se actualice debido a una interrupción del servicio, pero bastante improbable. Si lo desea, espere un rato y, a continuación, intente actualizar la DL de nuevo.

## <a name="how-to-use-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a>Cómo usar PowerShell para actualizar varias listas de distribución al mismo tiempo

Si tiene experiencia en el uso de PowerShell, es posible que quiera ir a esta ruta en lugar de usar la interfaz de usuario. Tenemos un conjunto de cmdlets que le ayudarán a actualizar las listas de distribución. Véalo a continuación.

### <a name="upgrade-a-single-dl"></a>Actualizar una única DL

Para actualizar una única DL, ejecute el siguiente comando:

`Upgrade-DistributionGroup -DlIdentities \<Dl SMTP address\>`

Por ejemplo, si desea actualizar una DL con la dirección SMTP dl1@contoso.com, ejecute el siguiente comando:

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com`

> [!NOTE]
> También puede actualizar una única lista de distribución a un grupo de Office 365 mediante el cmdlet [de PowerShell New-UnifiedGroup](https://go.microsoft.com/fwlink/?LinkID=786379)

### <a name="upgrade-multiple-dls-in-a-batch"></a>Actualizar varias listas de distribución en un lote

También puede pasar varias listas de distribución como un lote y actualizarlas de forma conjunta:

```
Upgrade-DistributionGroup -DlIdentities \<DL SMTP address1\>, \< DL SMTP address2\>,

\< DL SMTP address3\>, \< DL SMTP address 4\>
```

Por ejemplo, si desea actualizar cinco DL con `dl1@contoso.com` la dirección SMTP y `dl2@contoso.com` `dl3@contoso.com`, `dl4@contoso.com` y `dl5@contoso.com`, ejecute el siguiente comando:

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com, dl2@contoso.com, dl3@contoso.com, dl4@contoso.com, dl5@contoso.com`

### <a name="upgrade-all-eligible-dls"></a>Actualizar todas las listas de distribución elegibles

Hay dos formas de actualizar todas las listas de distribución elegibles.

> [!NOTE]
> El cmdlet upgrade-DistributionGroup no recibe datos de la canalización; por este motivo, es necesario usar el operador "foreach{}-Object" para ejecutarse correctamente.

1. Obtenga las listas de distribución elegibles del espacio empresarial y actualícelas mediante el comando de actualización:

```
Get-EligibleDistributionGroupForMigration | Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

2. Obtenga la lista de todas las listas de distribución y actualice solo las listas de distribución elegibles:

```
Get-DistributionGroup| Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

## <a name="faq-about-upgrading-distribution-lists-to-office-365-groups-in-outlook"></a>Preguntas más frecuentes sobre la actualización de listas de distribución a Office 365 grupos en Outlook

### <a name="which-distribution-lists-cannot-be-upgraded"></a>¿Qué listas de distribución no se pueden actualizar?

Solo se pueden actualizar las listas de distribución simples, no anidadas y administradas en la nube. En la tabla siguiente se enumeran las listas de distribución que **no** se pueden actualizar.

|**Propiedad**|**Países?**|
|:-----|:-----|
|Lista de distribución administrada local.  <br/> |No  <br/> |
|Listas de distribución anidadas. La lista de distribución tiene grupos secundarios o pertenece a otro grupo.  <br/> |No  <br/> |
|Listas de distribución con **miembros RecipientTypeDetails** distintos de **UserMailbox**, **SharedMailbox**, **buzón**, **MailUser**  <br/> |No  <br/> |
|Lista de distribución que tiene más de 100 propietarios  <br/> |No  <br/> |
|Lista de distribución que solo tiene miembros pero no el propietario  <br/> |No  <br/> |
|Lista de distribución que tiene un alias que contiene caracteres especiales  <br/> |No  <br/> |
|Si la lista de distribución está configurada como una dirección de reenvío para el buzón compartido  <br/> |No  <br/> |
|Si la DL forma parte de la **restricción de remitentes** en otra DL.  <br/> |No  <br/> |
|Grupos de seguridad  <br/> |No  <br/> |
|Listas de distribución dinámicas  <br/> |No  <br/> |
|Listas de distribución convertidas en **RoomLists**  <br/> |No  <br/> |
|Listas de distribución donde **MemberJoinRestriction** o **MemberDepartRestriction** está **cerrada**  <br/> |No  <br/> |

### <a name="how-do-i-check-which-dls-are-eligible-for-upgrade"></a>¿Cómo puedo comprobar qué listas de distribución son aptas para la actualización?

Si desea comprobar si una DL es elegible o no, puede ejecutar el siguiente comando:

`Get-DistributionGroup \<DL SMTP address\> | Get-EligibleDistributionGroupForMigration`

Si desea comprobar qué listas de distribución son aptas para la actualización, ejecute el siguiente comando:

`Get-EligibleDistributionGroupForMigration`

### <a name="who-can-run-the-upgrade-scripts"></a>¿Quién puede ejecutar los scripts de actualización?

Personas con Office 365 derechos de administrador global o de administrador de Exchange.

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-a-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a>¿Por qué la tarjeta de contacto todavía muestra una lista de distribución? ¿Qué debo hacer para evitar que una lista de distribución actualizada se muestre en mi lista de sugerencias automáticas?

- Para Outlook: cuando un usuario intenta enviar un correo electrónico en Outlook escribiendo el nombre del grupo de Office 365 después de la migración, el destinatario se resolverá como la lista de distribución en lugar del grupo. La tarjeta de contacto del destinatario será la tarjeta de contacto de las listas de distribución. Esto se debe a la caché de destinatarios o la memoria sobrenombre de Outlook. El correo electrónico se enviará correctamente al grupo, pero podría causar confusión en el remitente.<br/>Puede realizar los pasos de este tema, [información sobre la lista autocompletar de Outlook](https://go.microsoft.com/fwlink/?LinkID=798736) para restablecer la caché, lo que corregirá este problema.

- Para Outlook en la web: en caso de Outlook en la web, el destinatario de la lista de distribución permanecerá en la memoria caché. Puede seguir los pasos de [quitar nombre sugerido o dirección de correo electrónico de la lista de autocompletar](https://support.office.com/article/9E1419D9-E88F-445B-B07F-F558B8A37C58.aspx) para actualizar la caché y ver la tarjeta de contacto del grupo.

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a>¿Los nuevos miembros del grupo obtienen un correo electrónico de bienvenida en su bandeja de entrada?

No. La configuración para habilitar los mensajes de bienvenida se establece en false de forma predeterminada. Esta configuración afecta a los miembros del grupo nuevos y existentes que pueden unirse una vez completada la migración. Si el propietario del grupo permite más adelante a los usuarios invitados, los invitados no recibirán un correo electrónico de bienvenida en su bandeja de entrada. Los miembros de invitado pueden seguir trabajando con el grupo.

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a>¿Qué ocurre si una o varias de las listas de distribución no se actualizan?

Hay algunos casos en los que, aunque la DL es elegible pero no se puede actualizar. La DL no se actualiza y permanece como una DL.

- Donde el administrador ha aplicado la **Directiva de direcciones de correo electrónico de grupo** para los grupos de una organización e intenta actualizar las listas de distribución que no cumplen los criterios, la DL no se actualiza.

- No se pudieron actualizar las listas de distribución con **MemberJoinRestriction** o **MemberDepartRestriction** establecidos en **cerrado**.

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a>¿Qué sucede con la DL si se produce un error en la actualización de EAC?

La actualización solo se producirá cuando se envíe la llamada al servidor. Si se produce un error en la actualización, las listas de distribución estarán intactas. Funcionarán del mismo modo que lo usan.


