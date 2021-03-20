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
description: Obtenga información sobre cómo colocar un buzón en retención por juicio, conservando todo el contenido del buzón durante una investigación.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: 046ee6fdc7c42026b1a69805883175982e3100b7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908404"
---
# <a name="create-a-litigation-hold"></a>Crear una retención por juicio

Puede colocar un buzón en retención por juicio para conservar todo el contenido del buzón, incluidos los elementos eliminados y las versiones originales de los elementos modificados. Al colocar un buzón de usuario en retención por juicio, también se conserva el contenido del buzón de archivo del usuario (si está habilitado). Al crear una retención, puede especificar una duración de retención (también denominada retención basada en *tiempo)* para que los elementos eliminados y modificados se conserven durante un período especificado y, a continuación, se eliminen permanentemente del buzón. O puede conservar el contenido de forma indefinida (denominada suspensión *infinita)* o hasta que se quite la retención por juicio. Si especifica un período de duración de retención, se calcula a partir de la fecha en que se recibe un mensaje o se crea un elemento de buzón. 
  
Esto es lo que sucede al crear una retención por juicio.
  
- Los elementos eliminados permanentemente por el usuario se conservan en la carpeta Elementos recuperables del buzón del usuario durante la conservación.
    
- Los elementos que el usuario purga de la carpeta Elementos recuperables se conservan durante la conservación.
    
- La cuota de almacenamiento de la carpeta Elementos recuperables aumenta de 30 GB a 110 GB.
    
- Los elementos de los buzones de correo principal y de archivo del usuario se conservan
    
## <a name="assign-an-exchange-online-plan-2-license"></a>Asignar una licencia de Exchange Online Plan 2

- Para colocar un buzón de Exchange Online en retención por juicio, debe tener asignada una licencia de Exchange Online Plan 2. Si a un buzón se le asigna una licencia del Plan 1 de Exchange Online, tendría que asignarle una licencia de Archivado de Exchange Online independiente para ponerla en espera.
    

## <a name="place-a-mailbox-on-litigation-hold"></a>Poner un buzón en retención por juicio

Estos son los pasos para colocar un buzón en retención por juicio mediante el Centro de administración de Exchange.

1. Vaya a [https://outlook.office.com/ecp](https://outlook.office.com/ecp) e inicie sesión con su cuenta de administrador global.

2. Haga **clic en Destinatarios > buzones en** el panel de navegación izquierdo.

3. Seleccione el buzón que desea colocar en retención por juicio y, a continuación, haga clic **en Editar**.

4. En la página de propiedades de buzones, haga clic en **Características de buzón**.
    
5. En **Retención por juicio: Deshabilitado**, haga clic en **Habilitar** para colocar el buzón en Retención por juicio.
    
6. En la **página Retención por** juicio, escriba la siguiente información opcional: 
    
    - **Duración de retención por juicio (días):** use este cuadro para crear una retención basada en tiempo y especificar cuánto tiempo se mantienen los elementos de buzón cuando el buzón se coloca en retención por juicio. La duración se calcula desde la fecha en que un elemento de buzón se recibe o se crea. Cuando la duración de retención expire para un elemento específico, ese elemento ya no se conservará. Si deja este cuadro en blanco, los elementos se conservan indefinidamente o hasta que se quita la retención. Use días para especificar la duración.
    
    - **Nota:** use este cuadro para informar al usuario de que su buzón está en retención por juicio. La nota aparecerá en la página Información de la cuenta en el buzón del usuario si está usando Outlook 2010 o posterior. Para obtener acceso a esta página, los usuarios pueden hacer clic **en Archivo** en Outlook.
    
    - **DIRECCIÓN URL:** use este cuadro para dirigir al usuario a un sitio web para obtener más información acerca de la retención por juicio. Esta dirección URL aparece en la página Información de la cuenta en el buzón del usuario si usa Outlook 2010 o posterior. Para obtener acceso a esta página, los usuarios pueden hacer clic **en Archivo** en Outlook.

7. Haga **clic en Guardar** en la página **Retención** por juicio y, a continuación, haga clic en **Guardar** en la página de propiedades del buzón.

### <a name="create-a-litigation-hold-using-powershell"></a>Crear una retención por juicio con PowerShell

También puede crear una retención por juicio ejecutando el siguiente comando en [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $true
```

El comando anterior conserva los elementos indefinidamente porque no se especifica la duración de la retención. Para crear una retención basada en tiempo, use el siguiente comando:

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $true -LitigationHoldDuration <number of days>
```

Para obtener más información, vea [Set-Mailbox](/powershell/module/exchange/set-mailbox).

## <a name="how-does-litigation-hold-work"></a>¿Cómo funciona la retención por juicio?

En el flujo de trabajo normal de eliminación de elementos, se mueve un elemento de buzón a la subcarpeta Eliminaciones en la carpeta Elementos recuperables cuando un usuario lo elimina de forma permanente (Mayús + Suprimir) o lo elimina de la carpeta Elementos eliminados. Una directiva de retención (que es una etiqueta de retención configurada con una acción de Eliminar retención) también mueve elementos de la subcarpeta Eliminaciones cuando expira el período de retención. Cuando un usuario purga un elemento en la carpeta Elementos recuperables, o bien si expira el período de retención de elementos eliminados de un elemento, este se mueve a la subcarpeta Depuraciones de la carpeta Elementos recuperables y se marca para su eliminación permanente. Se eliminará de Exchange la próxima vez que el Asistente para carpeta administrada (MFA) procese el buzón de correo.

Cuando un buzón se coloca en una retención por juicio, los elementos de la subcarpeta Depuraciones se conservan durante la duración de retención especificada en la retención por juicio. La duración de la retención se calcula a partir de la fecha original en que se ha recibido o creado un elemento, y define el tiempo que se retienen los elementos en la subcarpeta Depuraciones. Cuando expira la duración de retención de un elemento en la subcarpeta Depuraciones, el elemento se marca para su eliminación permanente y se eliminará de Exchange la próxima vez que el MFA procese el buzón de correo. Si se retiene de forma indefinida un buzón de correo, los elementos nunca se eliminarán de la subcarpeta Depuraciones.

En la ilustración siguiente se muestran las subcarpetas en las carpetas Elementos recuperables y el proceso de flujo de trabajo de retención.

![Ciclo de vida de retención por juicio](../media/LitigationHoldLifeCycle.png)

> [!NOTE]
> Si se coloca una retención asociada a un caso de exhibición de documentos electrónicos en un buzón, los elementos purgados se mueven de la subcarpeta Eliminaciones a la subcarpeta DiscoveryHolds y se conservan hasta que el buzón se libera de la retención de exhibición de documentos electrónicos.
