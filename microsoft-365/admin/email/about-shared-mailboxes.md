---
title: Acerca de los buzones compartidos
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Los buzones compartidos se usan cuando varias personas necesitan tener acceso al mismo buzón. Obtenga información sobre lo que necesita saber antes de crear un buzón de correo compartido.
ms.openlocfilehash: f6feae1662093ffea2537a62c5e8fdf28c622166
ms.sourcegitcommit: 96b4593becc9450af136c528844e858c6e88b5a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2020
ms.locfileid: "48269354"
---
# <a name="about-shared-mailboxes"></a>Acerca de los buzones compartidos

Los buzones compartidos se usan cuando varios usuarios necesitan tener acceso al mismo buzón, como la dirección de correo electrónico del soporte técnico o información de la empresa, el escritorio de recepción u otra función que puedan compartir varios usuarios.

Los usuarios con permisos para el buzón del grupo pueden enviar como o enviar en nombre de la dirección de correo electrónico del buzón si el administrador le ha concedido permisos de usuario para hacerlo. Esto es especialmente útil para los buzones de ayuda y soporte técnico, ya que los usuarios pueden enviar mensajes de correo electrónico desde "Soporte técnico de Contoso" o "Escritorio de recepción del edificio A".

Antes [de crear un buzón compartido](create-a-shared-mailbox.md), aquí le indicamos algunas cosas que debe saber:

- **Licencias:** El buzón compartido puede almacenar hasta 50 GB de datos sin tener que asignar una licencia a él. Una vez superado ese límite, tendrá que asignar una licencia al buzón para almacenar más datos. Para obtener más información sobre las licencias de buzones compartidos, consulte [límites de Exchange Online](https://technet.microsoft.com/library/exchange-online-limits.aspx#StorageLimits). Cuando un buzón compartido alcanza el límite de almacenamiento, podrá recibir correo electrónico durante un tiempo, pero no podrá enviarlo. Después, dejará de recibir correo electrónico. Los remitentes del buzón recibirán un aviso de no entrega.

- **Permisos de usuario:** Debe conceder a los usuarios permisos (pertenencia) para usar el buzón compartido. Solo las personas de dentro de su organización pueden usar un buzón compartido.

- **Usuarios externos:** No puede conceder acceso a su buzón compartido a personas ajenas a la empresa (como personas con una cuenta de Gmail). Si quiere hacerlo, le recomendamos que cree un grupo para Outlook. Para obtener más información, vea [Create a Microsoft 365 Group in the admin Center](../create-groups/create-groups.md).

-  **Usar con Outlook:** Además de usar Outlook en la web desde el explorador para acceder a los buzones de correo compartidos, también puede usar la aplicación Outlook para iOS o la aplicación Outlook para Android. Para obtener más información, consulte <a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Agregar un buzón compartido a Outlook Mobile</a>. Otra opción es crear un grupo para el buzón compartido. Para obtener más información, vea [Comparar grupos](../create-groups/compare-groups.md).  

- **Cifrado:** No se puede cifrar el correo electrónico enviado desde un buzón compartido. Esto se debe a que un buzón compartido no tiene su propio contexto de seguridad (nombre de usuario/contraseña), por lo que no se le puede asignar una clave. Si más de una persona es miembro de y envían o reciben mensajes de correo electrónico cifrados con sus propias claves, es posible que otros miembros puedan leer el correo electrónico y otros no, en función de la clave pública con la que se cifró el correo electrónico.

- **Conversión de buzón:** Puede convertir los buzones de usuario en buzones compartidos. Vea [Convertir un buzón de usuario en un buzón compartido](convert-user-mailbox-to-shared-mailbox.md).

- **Roles de administrador:** Los usuarios con roles de administrador global o de administrador de Exchange pueden crear buzones compartidos.

- **Requisitos de suscripción:** Para crear un buzón compartido, necesita suscribirse a un plan de 365 para la empresa de Microsoft que incluya correo electrónico (el servicio de Exchange Online). La suscripción a Microsoft 365 apps for Business no incluye correo electrónico. Microsoft 365 Business Standard incluye correo electrónico.

- **Iniciar sesión:** Un buzón compartido no está diseñado para el inicio de sesión directo por parte de su cuenta de usuario asociada. Siempre debe bloquear el inicio de sesión para la cuenta de buzón de correo compartido y mantenerla bloqueada.

- **Demasiados usuarios:** Cuando hay demasiados usuarios designados que tienen acceso simultáneo a un buzón compartido, es posible que no se conecten de forma intermitente a este buzón. En este caso, puede considerar la posibilidad de reducir el número de usuarios o usar una carga de trabajo distinta, como un grupo de Microsoft 365 o una carpeta pública de Microsoft.

- **Eliminación de mensajes:** Por desgracia, no se puede impedir que los usuarios eliminen mensajes en un buzón compartido. La única forma de evitar esto es crear un grupo de 365 de Microsoft en lugar de un buzón compartido. Un grupo de Outlook es como un buzón compartido. Para ver una comparación de los dos, vea [Compare Groups](../create-groups/compare-groups.md). Para obtener más información acerca de los grupos, vea más [información acerca de los grupos](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2).

## <a name="related-articles"></a>Artículos relacionados

[Crear un buzón compartido](create-a-shared-mailbox.md)

[Configurar un buzón compartido](configure-a-shared-mailbox.md)

[Convertir un buzón de usuario en un buzón compartido](convert-user-mailbox-to-shared-mailbox.md)

[Quitar la licencia de un buzón compartido](remove-license-from-shared-mailbox.md)

[Resolver problemas con los buzones compartidos](resolve-issues-with-shared-mailboxes.md)
