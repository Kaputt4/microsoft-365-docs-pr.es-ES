---
title: 'Eliminación de un empleado anterior: información general'
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
- adminvideo
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
description: Bloquee el acceso a Microsoft 365 para que un antiguo empleado no pueda iniciar sesión, proteger los datos de la organización y permitir que otros empleados accedan a su correo electrónico y a los datos de OneDrive.
ms.openlocfilehash: 163cb427ce66f9c1f583681895f18fc67d0745dc
ms.sourcegitcommit: ecc04b5b8f84b34255a2d5e90b5ab596af0d16c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67496601"
---
# <a name="overview-remove-a-former-employee-and-secure-data"></a>Información general: Eliminación de un empleado anterior y protección de datos

Consulte [ayuda de Microsoft 365 para pequeñas empresas](https://go.microsoft.com/fwlink/?linkid=2197659) en YouTube.

Una pregunta que a menudo obtenemos es: "¿Qué debo hacer para proteger los datos y proteger el acceso cuando un empleado deja mi organización?" En esta serie de artículos se explica cómo bloquear el acceso a Microsoft 365 para que estos usuarios no puedan iniciar sesión en Microsoft 365, los pasos que debe seguir para proteger los datos de la organización y cómo permitir que otros empleados accedan al correo electrónico y a los datos de OneDrive.

> [!TIP]
> Si necesita ayuda con los pasos que se describen en este tema, considere la posibilidad de [trabajar con un especialista en pequeñas empresas de Microsoft](https://go.microsoft.com/fwlink/?linkid=2186871). Con Business Assist, usted y sus empleados obtienen acceso de forma ininterrumpida a especialistas de pequeñas empresas a medida que hace crecer su negocio, desde la incorporación hasta el uso diario.

## <a name="before-you-begin"></a>Antes de empezar

Debe ser administrador global para completar los pasos de esta solución.

Para completar los pasos de esta serie, use estas funcionalidades y características de Microsoft 365.

|Producto o componente|Funcionalidad o característica|
|---|---|
|Centro de administración de Microsoft 365|Convertir buzón de correo, reenviar correo electrónico, revocar el acceso, quitar usuario |
|Centro de administración de Exchange|Bloquear el usuario, bloquear el acceso al correo electrónico, borrar el dispositivo |
|OneDrive y SharePoint |Dar acceso a otros usuarios |
|Outlook|Importar archivos pst, agregar buzón |
|Active Directory|Eliminación de usuarios en entornos híbridos |


## <a name="solution-remove-a-former-employee"></a>Solución: Quitar un empleado anterior

> [!IMPORTANT]
> Aunque hemos numerado los pasos de esta solución y no es necesario completar la solución con el orden exacto, se recomienda realizar los pasos de esta manera.

:::image type="content" source="../../media/delete-user-account.png" alt-text="Captura de pantalla: Pasos para quitar un empleado anterior de la organización":::

<br>

****

|Paso|Por qué se debe realizar este procedimiento|
|---|---|
|[Paso 1: Impedir que un antiguo empleado inicie sesión y bloquee el acceso a los servicios de Microsoft 365](remove-former-employee-step-1.md)|Esto impide que el antiguo empleado inicie sesión en Microsoft 365 e impide que la persona acceda a los servicios de Microsoft 365.|
|[Paso 2: Guardar el contenido del buzón de un empleado anterior](remove-former-employee-step-2.md)|Esto es útil para la persona que va a asumir el trabajo del empleado, o si hay litigios.|
|[Paso 3: Borrar y bloquear el dispositivo móvil de un antiguo empleado](remove-former-employee-step-3.md)|Quita los datos profesionales del teléfono o de la tableta.|
|[Paso 4: Reenviar el correo electrónico de un antiguo empleado a otro empleado o convertirlo en un buzón compartido](remove-former-employee-step-4.md)|Esta opción permite mantener activa la dirección de correo electrónico de su antiguo empleado. Si tiene clientes o socios que siguen enviando correos electrónicos a la dirección del antiguo empleado, con esta opción el correo llegará a la persona que ahora se encarga del trabajo.|
|[Paso 5: Dar a otro empleado acceso a los datos de OneDrive y Outlook](remove-former-employee-step-5.md)|Si solo quita la licencia de un usuario, pero no elimina la cuenta, podrá obtener acceso al contenido de OneDrive del usuario incluso hasta 30 días después. <p> Antes de eliminar la cuenta, debe conceder acceso de OneDrive y Outlook a otro usuario. Después de eliminar la cuenta de un empleado, el contenido de Su OneDrive y Outlook se conserva durante **30** días. Sin embargo, durante esos 30 días, puede restaurar la cuenta del usuario y obtener acceso a su contenido. Si restaura la cuenta del usuario, el contenido de OneDrive y Outlook seguirá siendo accesible incluso después de 30 días.| 
|[Paso 6: Eliminación y eliminación de la licencia de Microsoft 365 de un empleado anterior](remove-former-employee-step-6.md)|Cuando quita una licencia, puede asignarla a otra persona. O bien, puede eliminar la licencia para no pagar por ella hasta que contrate a otra persona.  <p> Al quitar o eliminar una licencia, el correo electrónico, los contactos y el calendario antiguos del usuario se conservan durante **30 días** y, después, se eliminan permanentemente. Si quita o elimina una licencia, pero no elimina la cuenta, podrá obtener acceso al contenido de OneDrive del usuario incluso hasta 30 días después.  |
|[Paso 7: Eliminación de la cuenta de usuario de un antiguo empleado](remove-former-employee-step-7.md)|Esto quita la cuenta del centro de administración. Mantiene todo organizado.|

## <a name="watch-delete-a-user"></a>Inspección: Eliminación de un usuario

Consulte este vídeo y otros en nuestro [canal de YouTube](https://go.microsoft.com/fwlink/?linkid=2198203).

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR?autoplay=false]

Cuando un empleado deja la empresa, tendrá que quitarlos de Microsoft 365 para empresas. Antes de hacerlo, debe impedir que accedan a los archivos de la empresa, conservar los documentos que crearon y realizar otras tareas de administración asociadas a la eliminación de un usuario.

1. En el centro de administración, seleccione **Usuarios** y elija **Usuarios activos**.
1. Seleccione el usuario que desea quitar y, a continuación, seleccione **Eliminar usuario**.
1. Active la casilla para quitar su licencia y active la casilla para quitar sus alias de correo electrónico.
1. Active la casilla para conceder a otro usuario acceso al correo electrónico del empleado anterior y elija **Seleccionar un usuario y establecer opciones de correo electrónico**.
1. Para quitar los alias de correo electrónico asociados, seleccione **X** junto a sus alias.
1. Revise la información del buzón compartido y seleccione **Finalizar**.
1. Confirme que las opciones están establecidas correctamente y elija **Asignar y convertir**.
1. Revise los resultados y seleccione **Cerrar**.

Después de quitar un usuario, tiene hasta 30 días para restaurar su cuenta.
## <a name="related-content"></a>Contenido relacionado

[Restauración de un usuario](restore-user.md) (artículo)\
[Agregar un nuevo empleado a Microsoft 365](add-new-employee.md) (artículo)\
[Asignar licencias a los usuarios](../manage/assign-licenses-to-users.md) (artículo)\
[Remove-CalendarEvents](/powershell/module/exchange/remove-calendarevents)\
[Anulación de la asignación de licencias de usuarios](../manage/remove-licenses-from-users.md) (artículo)
