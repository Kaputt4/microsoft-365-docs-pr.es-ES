---
title: Crear una retención por juicio
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 07/20/2022
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid: MET150
ms.assetid: 39db1659-0b12-4243-a21c-2614512dcb44
description: Obtenga información sobre cómo colocar un buzón en suspensión por juicio, conservando todo el contenido del buzón durante una investigación.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
- admindeeplinkCOMPLIANCE
ms.openlocfilehash: 3210d85bfde39ac2d67d5f20a5170da950d25e91
ms.sourcegitcommit: 433f5b448a0149fcf462996bc5c9b45d17bd46c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2022
ms.locfileid: "67826168"
---
# <a name="create-a-litigation-hold"></a>Crear una retención por juicio

Puede colocar un buzón en suspensión por juicio para conservar todo el contenido del buzón, incluidos los elementos eliminados y las versiones originales de los elementos modificados. Al colocar un buzón de usuario en suspensión por juicio, también se conserva el contenido del buzón de archivo del usuario (si está habilitado). Al crear una suspensión, puede especificar una duración de suspensión (también denominada *suspensión basada en tiempo*) para que los elementos eliminados y modificados se conserven durante un período especificado y, a continuación, se eliminen permanentemente del buzón. O bien, puede conservar el contenido indefinidamente (denominada *suspensión infinita*) o hasta que se quite la suspensión por litigio. Si especifica un período de duración de retención, se calcula a partir de la fecha en que se recibe un mensaje o se crea un elemento de buzón.
  
Esto es lo que sucede al crear una suspensión por litigio.
  
- Los elementos eliminados permanentemente por el usuario se conservan en la carpeta Elementos recuperables del buzón del usuario mientras dure la suspensión.

- Los elementos purgados de la carpeta Elementos recuperables por el usuario se conservan mientras dure la suspensión.

- La cuota de almacenamiento para la carpeta Elementos recuperables aumenta de 30 GB a 110 GB.

- Los elementos de los buzones principal y de archivo del usuario se conservan

## <a name="assign-an-exchange-online-plan-2-license"></a>Asignación de una licencia del plan 2 de Exchange Online

Para colocar un buzón de Exchange Online en suspensión por litigio, se le debe asignar una licencia Exchange Online plan 2. Si a un buzón se le asigna una licencia de Exchange Online plan 1, tendría que asignarle una licencia de Archivado de Exchange Online independiente para ponerla en espera.

> [!NOTE]
> En el caso de las organizaciones Office 365 Educación, la suspensión por litigios se admite en las suscripciones de Office 365 A1, que incluyen una licencia Exchange Online plan 2 con características complementarias. Para obtener más información, consulte la sección "Características de Exchange Online" en la [descripción del servicio Office 365 Educación](/office365/servicedescriptions/office-365-platform-service-description/office-365-education#exchange-online-features).

## <a name="place-a-mailbox-on-litigation-hold"></a>Colocación de un buzón en suspensión por juicio

Estos son los pasos para colocar un buzón en suspensión por juicio mediante el Centro de administración de Microsoft 365.

1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Centro de administración de Microsoft 365</a> y, a continuación, haga clic en **Usuarios** > **usuarios activos**.

2. Seleccione el usuario que desea colocar en suspensión por juicio.

3. En la página de control flotante de propiedades, haga clic en la pestaña **Correo** y, a continuación, en **Más acciones**, haga clic en **Administrar suspensión por juicio**.

   ![Haga clic en Administrar suspensión por juicio en la pestaña Correo de la página desplegable propiedades de usuario.](../media/M365AdminCenterLitHold1.png)

4. En la página de control flotante **Administrar suspensión de litigios** , active la casilla **Activar suspensión por juicio** y escriba la siguiente información opcional:

    1. **Duración de suspensión (días):** use este cuadro para crear una suspensión basada en el tiempo y especificar cuánto tiempo se mantienen los elementos de buzón cuando el buzón se coloca en suspensión por juicio. La duración se calcula desde la fecha en que un elemento de buzón se recibe o se crea. Cuando expire la duración de retención de un elemento específico, ese elemento ya no se conservará. Si deja este cuadro en blanco, los elementos se conservan indefinidamente o hasta que se quita la suspensión. Use días para especificar la duración.

    2. **Nota visible para el usuario**: use este cuadro para informar al usuario de que su buzón está en suspensión por juicio. La nota aparecerá en la página Información de la cuenta en el buzón del usuario si usa Outlook 2010 o posterior. Para acceder a esta página, los usuarios pueden hacer clic en **Archivo** en Outlook.

    3. **Página web con más información para el usuario**: use este cuadro para dirigir al usuario a un sitio web para obtener más información sobre la suspensión por juicio. Esta dirección URL aparece en la página Información de la cuenta en el buzón del usuario si usa Outlook 2010 o posterior. Para acceder a esta página, los usuarios pueden hacer clic en **Archivo** en Outlook.

. Haga clic en **Guardar cambios** en la página flotante **Detención por juicio** para crear la suspensión.

   El sistema muestra un banner que indica que el cambio puede tardar hasta 240 minutos en surtir efecto.

### <a name="create-a-litigation-hold-using-powershell"></a>Creación de una suspensión por juicio mediante PowerShell

También puede crear una suspensión por litigio ejecutando el siguiente comando en [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $true
```

El comando anterior conserva los elementos indefinidamente porque no se especifica la duración de la suspensión. Para crear una suspensión basada en el tiempo, use el siguiente comando:

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $true -LitigationHoldDuration <number of days>
```

También puede ejecutar el siguiente comando para comprobar si el buzón está colocado en suspensión por juicio:

```powershell
Get-Mailbox <username> | FL LitigationHoldEnabled
```

Un valor de *True* indica que el buzón está en suspensión por juicio/

Para obtener más información, vea [Set-Mailbox](/powershell/module/exchange/set-mailbox).

## <a name="how-does-litigation-hold-work"></a>¿Cómo funciona la suspensión de litigios?

En el flujo de trabajo normal de eliminación de elementos, se mueve un elemento de buzón a la subcarpeta Eliminaciones en la carpeta Elementos recuperables cuando un usuario lo elimina de forma permanente (Mayús + Suprimir) o lo elimina de la carpeta Elementos eliminados. Una directiva de retención (que es una etiqueta de retención configurada con una acción de Eliminar retención) también mueve elementos de la subcarpeta Eliminaciones cuando expira el período de retención. Cuando un usuario purga un elemento en la carpeta Elementos recuperables, o bien si expira el período de retención de elementos eliminados de un elemento, este se mueve a la subcarpeta Depuraciones de la carpeta Elementos recuperables y se marca para su eliminación permanente. Se eliminará de Exchange la próxima vez que el Asistente para carpeta administrada (MFA) procese el buzón de correo.

Cuando se coloca un buzón en suspensión por juicio, los elementos de la subcarpeta Purgas se conservan durante la duración de retención especificada por la suspensión por juicio. La duración de la retención se calcula a partir de la fecha original en que se ha recibido o creado un elemento, y define el tiempo que se retienen los elementos en la subcarpeta Depuraciones. Cuando expira la duración de retención de un elemento en la subcarpeta Depuraciones, el elemento se marca para su eliminación permanente y se eliminará de Exchange la próxima vez que el MFA procese el buzón de correo. Si se retiene de forma indefinida un buzón de correo, los elementos nunca se eliminarán de la subcarpeta Depuraciones.

En la ilustración siguiente se muestran las subcarpetas en las carpetas Elementos recuperables y el proceso de flujo de trabajo de retención.

![Ciclo de vida de suspensión de litigios.](../media/LitigationHoldLifeCycle.png)

> [!NOTE]
> Si se coloca una suspensión asociada a un caso de exhibición de documentos electrónicos en un buzón, los elementos purgados se mueven de la subcarpeta Eliminaciones a la subcarpeta DiscoveryHolds y se conservan hasta que el buzón se libera de la suspensión de eDiscovery.
