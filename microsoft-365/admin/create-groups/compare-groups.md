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
ms.localizationpriority: high
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
- admindeeplinkMAC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 758759ad-63ee-4ea9-90a3-39f941897b7d
description: Los miembros del Grupo de Microsoft 365 obtienen un correo electrónico de grupo y un área de trabajo compartida para las conversaciones, los archivos y los eventos de calendario, así como Stream y Planner.
ms.openlocfilehash: 72da8af8acd0725a5d7509b84f08e4220f7772d4
ms.sourcegitcommit: 33bc25167812b31c51cf096c728e3a5854e94f1c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2022
ms.locfileid: "64594717"
---
# <a name="compare-groups"></a>Comparar grupos

En la sección <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">**Grupos**</a> del Centro de administración de Microsoft 365, puede crear y administrar estos tipos de grupos: 

- Los **Grupos de Microsoft 365** se usan para la colaboración entre usuarios, tanto dentro como fuera de la compañía. Incluyen servicios de colaboración como SharePoint y Planner.
- **Los grupos de distribución** se usan para enviar notificaciones de correo electrónico a un grupo de personas.
- **Los grupos de seguridad** se usan para conceder acceso a los recursos como SharePoint.
- **Los grupos de seguridad habilitados para correo** se usan para conceder acceso a recursos como SharePoint y enviar notificaciones por correo electrónico a estos usuarios.
- **Los buzones compartidos** se usan cuando varios usuarios necesitan tener acceso al mismo buzón, como la dirección de correo electrónico del soporte técnico e información de la empresa.
- Los **grupos de distribución dinámicos** se crean para acelerar el envío masivo de mensajes de correo electrónico y demás información dentro de una organización.

Algunos grupos permiten la pertenencia dinámica o el correo electrónico.

||Grupos de Microsoft 365|Grupos de distribución|Grupos de seguridad|Grupos de seguridad habilitados para correo|Buzones compartidos|Grupos de distribución dinámicos|
|:----|:----|:----|:----|:----|:----|:----|
|**Habilitado para correo**|Sí|Sí|No|Sí|Sí|Sí|
|**Pertenencia dinámica en Azure AD**|Sí|No|Sí|No|No|No|

Todos estos tipos de grupo se pueden usar con Power Automate.

## <a name="microsoft-365-groups"></a>Grupos de Microsoft 365

Los Grupos de Microsoft 365 se usan para la colaboración entre usuarios, tanto dentro como fuera de la compañía. Con cada Grupo de Microsoft 365, los miembros obtienen un correo electrónico de grupo y un área de trabajo compartida para las conversaciones, los archivos y los eventos de calendario, así como Stream y Planner.

Puede agregar personas externas a su empresa a un grupo siempre y cuando esta opción se haya [habilitado por parte del administrador](manage-guest-access-in-groups.md). También puede permitir que los remitentes externos puedan enviar correos electrónicos a la dirección de correo electrónico del grupo.

Los Grupos de Microsoft 365 se pueden [configurar para la pertenencia dinámica en Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type), lo que permite agregar o eliminar a los miembros del grupo automáticamente en función de los atributos del usuario como el departamento, la ubicación, el cargo, etc.

Se puede tener acceso a los Grupos de Microsoft 365 a través de aplicaciones móviles como Outlook para iOS y Outlook para Android.

Los miembros del grupo pueden enviar como o enviar en nombre de la dirección de correo electrónico del grupo si está opción ha sido [activada por el administrador](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md).

Los Grupos de Microsoft 365 no admiten anidamiento con otros Grupos de Microsoft 365 o con grupos de distribución o de seguridad.

Los Grupos de Microsoft 365 se pueden agregar a uno de los tres grupos de SharePoint (Propietarios, Miembros o Visitantes) para conceder permisos a los usuarios al sitio.

## <a name="distribution-groups"></a>Grupos de distribución

[Los grupos de distribución](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups) se usan para enviar notificaciones a un grupo de personas. Pueden recibir correo electrónico externo si lo habilita el administrador.

Los grupos de distribución son mejores para las situaciones en las que necesita transmitir información a un grupo definido de personas, como "Usuarios del edificio A" o "Todos los usuarios de Contoso".

Los grupos de distribución se pueden [actualizar a Grupos de Microsoft 365](../manage/upgrade-distribution-lists.md).

Los grupos de distribución se pueden agregar a un equipo en Microsoft Teams, aunque solo se agregan los miembros y no el propio grupo.

Los Grupos de Microsoft 365 no pueden ser miembros de ningún grupo de distribución.

## <a name="dynamic-distribution-groups"></a>Grupos de distribución dinámicos 

Los [grupos de distribución dinámicos](/exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) son grupos habilitados para correo que se usan para enviar correos a personas con atributos específicos, como departamento o ubicación. Estos atributos se definen en el Centro de administración de Exchange en lugar de en Azure AD.

A diferencia de los grupos de distribución regular, que contienen un conjunto definido de miembros, la lista de miembros para grupos de distribución dinámica se calcula cada vez que se envía un mensaje al grupo, en base a los filtros y condiciones definidos. Cuando se envía un mensaje de correo electrónico a un grupo de distribución dinámico, éste se entrega a todos los destinatarios de la organización que coincidan con los criterios definidos para ese grupo.

## <a name="security-groups"></a>Grupos de seguridad

[Los grupos de seguridad](../email/create-edit-or-delete-a-security-group.md) se usan para conceder acceso a los recursos de Microsoft 365, como SharePoint. Pueden simplificar la administración, ya que solo necesita administrar el grupo, en lugar de agregar usuarios a cada recurso por separado.

Los grupos de seguridad pueden contener usuarios o dispositivos. La creación de un grupo de seguridad para dispositivos se puede usar con los servicios de administración de dispositivos móviles, como Intune.

Los grupos de seguridad se pueden [configuran para la pertenencia dinámica en Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type), lo que permite que los miembros del grupo o los dispositivos se agreguen o eliminen automáticamente en función de los atributos del usuario, como el departamento, la ubicación o el título; o los atributos del dispositivo, como la versión del sistema operativo.

Se pueden agregar grupos de seguridad a un equipo.

Los Grupos de Microsoft 365 no pueden ser miembros de ningún grupo de seguridad.

## <a name="mail-enabled-security-groups"></a>Grupos de seguridad habilitados para correo

Los grupos de seguridad habilitados para correo funcionan de la misma manera que los grupos de seguridad normales, excepto que no se pueden administrar dinámicamente a través de Azure Active Directory y no pueden contener dispositivos.

Incluyen la capacidad para enviar correo a todos los miembros del grupo.

Se pueden agregar grupos de seguridad habilitados para correo a un equipo.

## <a name="shared-mailboxes"></a>Buzones compartidos

[Los buzones compartidos](../email/create-a-shared-mailbox.md) se usan cuando varios usuarios necesitan tener acceso al mismo buzón, como la dirección de correo electrónico del soporte técnico o información de la empresa, el escritorio de recepción u otra función que puedan compartir varios usuarios.

Los buzones compartidos pueden recibir mensajes externos si el administrador ha habilitado esta opción.

Los buzones compartidos incluyen un calendario que se puede usar para la colaboración.

Los usuarios con permisos para el buzón del grupo pueden enviar como o enviar en nombre de la dirección de correo electrónico del buzón si el administrador le ha concedido permisos de usuario para hacerlo. Esto es útil en particular para los buzones de ayuda y soporte técnico, ya que los usuarios pueden enviar mensajes de correo electrónico desde "Soporte técnico de Contoso" o "Escritorio de recepción del edificio A".

No es posible migrar un buzón compartido a un Grupo de Microsoft 365.

## <a name="related-content"></a>Contenido relacionado

[Obtener información sobre los Grupos de Microsoft 365](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Actualizar listas de distribución a Grupos de Microsoft 365 en Outlook](/microsoft-365/admin/manage/upgrade-distribution-lists)

[Por qué debería actualizar sus listas de distribución a grupos de Outlook](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)
