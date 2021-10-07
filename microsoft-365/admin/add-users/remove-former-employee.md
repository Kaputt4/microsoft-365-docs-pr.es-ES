---
title: 'Quitar un antiguo empleado: información general'
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
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
- AdminTemplateSet
- m365solution-removeemployee
search.appverid:
- BCS160
- MET150
- MOE150
description: Siga los pasos de esta solución para quitar un antiguo empleado Microsoft 365 proteger los datos de su organización.
ms.openlocfilehash: 63a53ba8ae982fd49b033da62c27d4da3d72737d
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60161611"
---
# <a name="overview-remove-a-former-employee-and-secure-data"></a>Información general: Quitar un antiguo empleado y datos seguros

A question we often get is, "What should I do to secure data and protect access when an employee leaves my organization?" En esta serie de artículos se explica cómo bloquear el acceso a Microsoft 365 para que estos usuarios no puedan iniciar sesión en Microsoft 365, los pasos que debe seguir para proteger los datos de la organización y cómo permitir que otros empleados accedan al correo electrónico y OneDrive datos.

## <a name="before-you-begin"></a>Antes de empezar

Debe ser un administrador global para completar los pasos de esta solución.

Para completar los pasos de esta serie, use estas Microsoft 365 y características.

|Producto o componente|Funcionalidad o característica|
|---|---|
|Centro de administración de Microsoft 365|Convertir buzón, reenviar correo electrónico, revocar acceso, quitar usuario |
|Centro de administración de Exchange|Bloquear usuario, bloquear el acceso al correo electrónico, borrar dispositivo |
|OneDrive y SharePoint |Dar acceso a otros usuarios |
|Outlook|Importar archivos pst, agregar buzón |
|Active Directory|Quitar usuarios en entornos híbridos |

## <a name="solution-remove-a-former-employee"></a>Solución: quitar un antiguo empleado

> [!IMPORTANT]
> Aunque hemos numerado los pasos de esta solución y no tiene que completar la solución con el orden exacto, se recomienda realizar los pasos de esta manera.

:::image type="content" source="../../media/delete-user-account.png" alt-text="Screenshot: Steps for removing a former employee from your organization":::

<br>

****

|Paso|Por qué se debe realizar este procedimiento|
|---|---|
|[Paso 1: impedir que un antiguo empleado inicia sesión y bloquee el acceso a Microsoft 365 servicios](remove-former-employee-step-1.md)|Esto bloquea el inicio de sesión de su antiguo empleado Microsoft 365 e impide que la persona acceda a Microsoft 365 servicios.|
|[Paso 2: Guardar el contenido del buzón de un antiguo empleado](remove-former-employee-step-2.md)|Esto es útil para la persona que va a asumir el trabajo del empleado, o si hay litigio.|
|[Paso 3: Reenviar el correo electrónico de un antiguo empleado a otro empleado o convertirlo a un buzón compartido](remove-former-employee-step-3.md)|Esta opción permite mantener activa la dirección de correo electrónico de su antiguo empleado. Si tiene clientes o socios que siguen enviando correos electrónicos a la dirección del antiguo empleado, con esta opción el correo llegará a la persona que ahora se encarga del trabajo.|
|[Paso 4: Dar a otro empleado acceso a OneDrive y Outlook datos](remove-former-employee-step-4.md)|Si solo quita la licencia de un usuario, pero no elimina la cuenta, podrá obtener acceso al contenido de OneDrive del usuario incluso hasta 30 días después. <p> Antes de eliminar la cuenta, debe dar acceso a sus OneDrive y Outlook a otro usuario. Después de eliminar la cuenta de un empleado, el contenido de su OneDrive y Outlook se conserva durante **30** días. Sin embargo, durante esos 30 días, puede restaurar la cuenta del usuario y obtener acceso a su contenido. Si restaura la cuenta del usuario, el contenido OneDrive y Outlook seguirá siendo accesible para usted incluso después de 30 días.|
|[Paso 5: Borrar y bloquear el dispositivo móvil de un antiguo empleado](remove-former-employee-step-5.md)|Quita los datos profesionales del teléfono o de la tableta.|
|[Paso 6: Quitar y eliminar la Microsoft 365 de un antiguo empleado](remove-former-employee-step-6.md)|Cuando quita una licencia, puede asignarla a otra persona. O bien, puede eliminar la licencia para no pagar por ella hasta que contrate a otra persona.  <p> Al quitar o eliminar una licencia, el correo electrónico, los contactos y el calendario antiguos del usuario se conservan durante **30 días** y, después, se eliminan permanentemente. Si quita o elimina una licencia, pero no elimina la cuenta, podrá obtener acceso al contenido de OneDrive del usuario incluso hasta 30 días después.  |
|[Paso 7: Eliminar la cuenta de usuario de un antiguo empleado](remove-former-employee-step-7.md)|Esto quita la cuenta del centro de administración. Mantiene todo organizado.|
|

## <a name="related-content"></a>Contenido relacionado

[Restaurar un usuario](restore-user.md) (artículo)\
[Agregar un nuevo empleado a Microsoft 365](add-new-employee.md) (artículo)\
[Asignar licencias a los usuarios](../manage/assign-licenses-to-users.md) (artículo)\
[Unassign licenses from users](../manage/remove-licenses-from-users.md) (article)
