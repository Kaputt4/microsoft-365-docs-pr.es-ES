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
- business_assist
search.appverid:
- BCS160
- MET150
- MOE150
description: Siga los pasos de esta solución para quitar un antiguo empleado Microsoft 365 proteger los datos de su organización.
ms.openlocfilehash: 17d66e3ff39e00861acdf90e2d5f155cb9225f2c
ms.sourcegitcommit: 6e90baef421ae06fd790b0453d3bdbf624b7f9c0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2022
ms.locfileid: "62765893"
---
# <a name="overview-remove-a-former-employee-and-secure-data"></a>Información general: Quitar un antiguo empleado y datos seguros

A question we often get is, "What should I do to secure data and protect access when an employee leaves my organization?" En esta serie de artículos se explica cómo bloquear el acceso a Microsoft 365 para que estos usuarios no puedan iniciar sesión en Microsoft 365, los pasos que debe seguir para proteger los datos de la organización y cómo permitir que otros empleados accedan al correo electrónico y OneDrive datos.

> [!TIP]
> Si necesita ayuda con los pasos de este tema, considere la posibilidad de [trabajar con un especialista en pequeñas empresas de Microsoft](https://go.microsoft.com/fwlink/?linkid=2186871). Con Business Assist, usted y sus empleados obtienen acceso diario a los especialistas de pequeñas empresas a medida que crece su negocio, desde la incorporación hasta el uso diario.

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

## <a name="watch-delete-a-user"></a>Watch: Delete a user

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR?autoplay=false]

Cuando un empleado deja la empresa, deberá quitarlos de Microsoft 365 para empresas. Antes de hacerlo, debe impedir que tengan acceso a los archivos de la empresa, conservar los documentos que crearon y realizar otras tareas de administrador asociadas con la eliminación de un usuario.

1. En el Centro de administración, seleccione **Usuarios** y elija **Usuarios activos**.
1. Seleccione el usuario que desea quitar y, a continuación, **seleccione Eliminar usuario**.
1. Active la casilla para quitar su licencia y active la casilla para quitar sus alias de correo electrónico.
1. Active la casilla para dar a otro usuario acceso al correo electrónico del antiguo empleado y elija **Seleccionar un usuario y establecer opciones de correo electrónico**.
1. Para quitar los alias de correo electrónico asociados, seleccione **X** junto a sus alias.
1. Revise la información del buzón compartido y seleccione **Finalizar**.
1. Confirme que las opciones están configuradas correctamente y elija **Asignar y convertir**.
1. Revise los resultados y seleccione **Cerrar**.

Después de quitar un usuario, tiene hasta 30 días para restaurar su cuenta.

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
