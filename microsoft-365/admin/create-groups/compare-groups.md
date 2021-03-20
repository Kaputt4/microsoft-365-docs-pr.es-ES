---
title: Comparar grupos
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 758759ad-63ee-4ea9-90a3-39f941897b7d
description: Obtenga más información sobre los tipos de grupos que puede usar.
ms.openlocfilehash: 8565b567706a70bb014fab42b23e9c55fb0efc45
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908751"
---
# <a name="compare-groups"></a>Comparar grupos

En la sección **Grupos** del Centro de administración de Microsoft 365, puede crear y administrar estos tipos de grupos: 

- **Los grupos de Microsoft 365** (anteriormente grupos de Office 365) se usan para la colaboración entre usuarios, tanto dentro como fuera de la empresa.
- **Los grupos de distribución** se usan para enviar notificaciones a un grupo de personas.
- **Los grupos de seguridad** se usan para conceder acceso a los recursos como SharePoint.
- **Los grupos de seguridad habilitados para correo** se usan para conceder acceso a recursos como SharePoint y enviar notificaciones por correo electrónico a estos usuarios.
- **Los buzones compartidos** se usan cuando varios usuarios necesitan tener acceso al mismo buzón, como la dirección de correo electrónico del soporte técnico e información de la empresa.

## <a name="microsoft-365-groups"></a>Grupos de Microsoft 365

Los grupos de Microsoft 365 se usan para la colaboración entre usuarios, tanto dentro como fuera de la compañía. Con cada grupo de Microsoft 365, los miembros obtienen un correo electrónico de grupo y un área de trabajo compartida para las conversaciones, los archivos y los eventos de calendario, Stream y un Planner.

Puede agregar personas externas a su empresa a un grupo siempre y cuando esta opción se haya [habilitado por parte del administrador](manage-guest-access-in-groups.md). También puede permitir que los remitentes externos puedan enviar correos electrónicos a la dirección de correo electrónico del grupo.

Los grupos de Microsoft 365 se pueden [configurar para la pertenencia dinámica en Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type), lo que permite que los miembros del grupo se agreguen o eliminen automáticamente en función de los atributos del usuario como el departamento, la ubicación, el puesto, etc.

Se puede tener acceso a los grupos de Microsoft 365 a través de aplicaciones móviles como Outlook para iOS y Outlook para Android.

Los miembros del grupo pueden enviar como o enviar en nombre de la dirección de correo electrónico del grupo si está opción ha sido [activada por el administrador](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md).

## <a name="distribution-groups"></a>Grupos de distribución

[Los grupos de distribución](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups) se usan para enviar notificaciones a un grupo de personas. Pueden recibir correo electrónico externo si lo habilita el administrador.

Los grupos de distribución son mejores para las situaciones en las que necesita transmitir información a un grupo definido de personas, como "Usuarios del edificio A" o "Todos los usuarios de Contoso".

Los grupos de distribución se pueden [actualizar a grupos de Microsoft 365](../manage/upgrade-distribution-lists.md).

## <a name="security-groups"></a>Grupos de seguridad

[Los grupos de seguridad](../email/create-edit-or-delete-a-security-group.md) se usan para conceder acceso a los recursos de Microsoft 365, como SharePoint. Pueden simplificar la administración, ya que solo necesita administrar el grupo, en lugar de agregar usuarios a cada recurso por separado.

Los grupos de seguridad pueden contener usuarios o dispositivos. Se puede usar la creación de un grupo de seguridad para dispositivos con servicios de administración de dispositivos móviles, como Intune.

Los grupos de seguridad se pueden [configuran para la pertenencia dinámica en Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type), lo que permite que los miembros del grupo o los dispositivos se agreguen o eliminen automáticamente en función de los atributos del usuario, como el departamento, la ubicación o el título; o los atributos del dispositivo, como la versión del sistema operativo.

## <a name="mail-enabled-security-groups"></a>Grupos de seguridad habilitados para correo

Los grupos de seguridad habilitados para correo funcionan de la misma manera que los grupos de seguridad normales, excepto que no se pueden administrar dinámicamente a través de Azure Active Directory y no pueden contener dispositivos.

Incluyen la capacidad para enviar correo a todos los miembros del grupo.

## <a name="shared-mailboxes"></a>Buzones compartidos

[Los buzones compartidos](../email/create-a-shared-mailbox.md) se usan cuando varios usuarios necesitan tener acceso al mismo buzón, como la dirección de correo electrónico del soporte técnico o información de la empresa, el escritorio de recepción u otra función que puedan compartir varios usuarios.

Los buzones compartidos pueden recibir mensajes externos si el administrador ha habilitado esta opción.

Los usuarios con permisos para el buzón del grupo pueden enviar como o enviar en nombre de la dirección de correo electrónico del buzón si el administrador le ha concedido permisos de usuario para hacerlo. Esto es especialmente útil para los buzones de ayuda y soporte técnico, ya que los usuarios pueden enviar mensajes de correo electrónico desde "Soporte técnico de Contoso" o "Escritorio de recepción del edificio A".

Actualmente, no es posible migrar un buzón compartido a un grupo de Microsoft 365. ¿Le gustaría que fuese posible? Infórmenos. **[Vote aquí](https://go.microsoft.com/fwlink/?linkid=871518)**.

## <a name="related-articles"></a>Artículos relacionados

[Obtener más información sobre los grupos de Microsoft 365](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Por qué debería actualizar sus listas de distribución a grupos de Outlook](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)