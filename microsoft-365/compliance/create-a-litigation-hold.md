---
title: Crear una retención por juicio
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 3/13/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MET150
ms.assetid: 39db1659-0b12-4243-a21c-2614512dcb44
description: Obtenga información sobre cómo poner un buzón en retención por juicio y conservar todo el contenido del buzón durante una investigación.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: 9c62dfcd9e4cf1e3cc75e029b250c7abe80de6df
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818049"
---
# <a name="create-a-litigation-hold"></a>Crear una retención por juicio

Puede poner un buzón en retención por juicio para retener todo el contenido del buzón, incluidos los elementos eliminados y las versiones originales de los elementos modificados. Cuando se pone un buzón de usuario en retención por juicio, también se conserva el contenido del buzón de archivo del usuario (si está habilitado). Al crear una suspensión, puede especificar una duración de retención (también denominada *retención basada en tiempo*) para que los elementos eliminados y modificados se conserven durante un período específico y, a continuación, se eliminen de forma permanente del buzón. O bien solo puede retener el contenido indefinidamente (denominado una *retención infinita*) o hasta que se quite la retención por juicio. Si especifica un período de duración de retención, se calcula a partir de la fecha en que se recibe un mensaje o se crea un elemento de buzón de correo. 
  
Esto es lo que sucede cuando se crea una retención por juicio.
  
- Los elementos eliminados de forma permanente por el usuario se conservan en la carpeta elementos recuperables del buzón del usuario durante toda la retención.
    
- Los elementos purgados de la carpeta elementos recuperables por el usuario se conservan durante toda la retención.
    
- La cuota de almacenamiento de la carpeta elementos recuperables se ha incrementado de 30 GB a 110 GB.
    
- Se conservan los elementos del buzón principal del usuario y los buzones de archivo.
    
## <a name="assign-an-exchange-online-plan-2-license"></a>Asignar una licencia de plan 2 de Exchange Online

- Para poner un buzón de correo de Exchange online en retención por juicio, se le debe asignar una licencia de Exchange Online (plan 2). Si un buzón tiene asignada una licencia de Exchange Online (plan 1), tendrá que asignarle una licencia de archivado de Exchange Online independiente para ponerla en espera.
    

## <a name="place-a-mailbox-on-litigation-hold"></a>Poner un buzón en retención por juicio

Estos son los pasos para poner un buzón en retención por juicio mediante el centro de administración de Exchange.

1. Vaya a [https://outlook.office.com/ecp](https://outlook.office.com/ecp) e inicie sesión con su cuenta de administrador global.

2. Haga clic en **destinatarios > buzones** en el panel de navegación izquierdo.

3. Seleccione el buzón que desea poner en retención por juicio y, a continuación, haga clic en **Editar**.

4. En la página de propiedades de buzones, haga clic en **Características de buzón**.
    
5. En **Retención por juicio: Deshabilitado**, haga clic en **Habilitar** para colocar el buzón en Retención por juicio.
    
6. En la página **retención por juicio** , escriba la siguiente información opcional: 
    
    - Duración de retención por **juicio (días)** : Use este cuadro para crear una retención basada en tiempo y especificar cuánto tiempo se conservarán los elementos del buzón cuando el buzón de correo se coloca en retención por juicio. La duración se calcula desde la fecha en que un elemento de buzón se recibe o se crea. Cuando expire la duración de retención de un elemento específico, dicho elemento ya no se conservará. Si deja este cuadro en blanco, los elementos se conservan indefinidamente o hasta que se quite la retención. Use días para especificar la duración.
    
    - **Nota** : Use este cuadro para informar al usuario de que su buzón de correo está en retención por juicio. La nota aparecerá en la página de información de cuenta del buzón de correo del usuario si usa Outlook 2010 o posterior. Para tener acceso a esta página, los usuarios pueden hacer clic en **archivo** en Outlook.
    
    - **URL** : Use este cuadro para dirigir al usuario a un sitio web para obtener más información sobre la retención por juicio. Esta dirección URL aparece en la página de información de cuenta del buzón del usuario si usa Outlook 2010 o posterior. Para tener acceso a esta página, los usuarios pueden hacer clic en **archivo** en Outlook..

7. Haga clic en **Guardar** en la página **retención por juicio** y, a continuación, haga clic en **Guardar** en la página de propiedades del buzón.

### <a name="create-a-litigation-hold-using-powershell"></a>Crear una retención por juicio con PowerShell

También puede crear una retención por juicio ejecutando el siguiente comando en [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell):

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $true
```

El comando anterior conserva los elementos indefinidamente porque no se especifica la duración de la retención. Para crear una retención basada en tiempo, use el siguiente comando:

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $true -LitigationHoldDuration <number of days>
```

Para obtener más información, vea [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox).

## <a name="how-does-litigation-hold-work"></a>¿Cómo funciona la retención por juicio?

En el flujo de trabajo normal de eliminación de elementos, se mueve un elemento de buzón a la subcarpeta Eliminaciones en la carpeta Elementos recuperables cuando un usuario lo elimina de forma permanente (Mayús + Suprimir) o lo elimina de la carpeta Elementos eliminados. Una directiva de retención (que es una etiqueta de retención configurada con una acción de Eliminar retención) también mueve elementos de la subcarpeta Eliminaciones cuando expira el período de retención. Cuando un usuario purga un elemento en la carpeta Elementos recuperables, o bien si expira el período de retención de elementos eliminados de un elemento, este se mueve a la subcarpeta Depuraciones de la carpeta Elementos recuperables y se marca para su eliminación permanente. Se eliminará de Exchange la próxima vez que el Asistente para carpeta administrada (MFA) procese el buzón de correo.

When a mailbox is placed on Litigation Hold, items in the Purges subfolder are preserved for the hold duration specified by the Litigation Hold. The hold duration is calculated from the original date an item was received or created, and defines how long items in the Purges subfolder are held. When the hold duration expires for an item in the Purges subfolder, the item is marked for permanent deletion and will be purged from Exchange the next time the mailbox is processed by the MFA. If an indefinite hold is placed on a mailbox, items will never be purged from the Purges subfolder.

En la ilustración siguiente se muestran las subcarpetas en las carpetas Elementos recuperables y el proceso de flujo de trabajo de retención.

![Ciclo de vida de retención por juicio](../media/LitigationHoldLifeCycle.png)

> [!NOTE]
> Si una retención asociada con un caso de exhibición de documentos electrónicos se coloca en un buzón, los elementos purgados se mueven de la subcarpeta eliminaciones a la subcarpeta retenciones y se conservan hasta que el buzón se libere de la suspensión de exhibición de documentos electrónicos.
  
