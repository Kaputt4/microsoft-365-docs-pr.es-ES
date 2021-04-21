---
title: Acerca de los buzones compartidos
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
description: Los buzones compartidos se usan cuando varias personas necesitan acceder al mismo buzón. Obtenga información sobre lo que debe saber antes de crear un buzón compartido.
ms.openlocfilehash: 83e779d59a8e763b3d0c0482966e75604d5f1574
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903219"
---
# <a name="about-shared-mailboxes"></a>Acerca de los buzones compartidos

Los buzones compartidos se usan cuando varios usuarios necesitan tener acceso al mismo buzón, como la dirección de correo electrónico del soporte técnico o información de la empresa, el escritorio de recepción u otra función que puedan compartir varios usuarios.

Los usuarios con permisos para el buzón del grupo pueden enviar como o enviar en nombre de la dirección de correo electrónico del buzón si el administrador le ha concedido permisos de usuario para hacerlo. Esto es especialmente útil para los buzones de ayuda y soporte técnico, ya que los usuarios pueden enviar mensajes de correo electrónico desde "Soporte técnico de Contoso" o "Escritorio de recepción del edificio A".

Antes de [crear un buzón compartido](create-a-shared-mailbox.md), estas son algunas cosas que debe saber:

- **Licencias:** El buzón compartido puede almacenar hasta 50 GB de datos sin que usted tenga que asignarle una licencia. Una vez superado ese límite, necesitará asignar una licencia al buzón para poder almacenar más datos. Para obtener más información sobre las licencias de los buzones compartidos, consulte [Límites de Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#StorageLimits). Cuando un buzón compartido alcanza el límite de almacenamiento, podrá recibir correo electrónico durante un tiempo, pero no podrá enviarlo. Después, dejará de recibir correo electrónico. Los remitentes del buzón recibirán un aviso de no entrega.

- **Permisos de usuario:** Debe dar a los usuarios permisos (suscripciones) para usar el buzón compartido. Solo las personas de su organización pueden usar los buzones de correo compartidos.

- **Usuarios externos:** No puede proporcionarle acceso a su buzón compartido a los usuarios ajenos a su negocio (como gente con una cuenta de Gmail). Si quiere hacerlo, le recomendamos crear más bien un grupo para Outlook. Para obtener más información, consulte [Crear un grupo de Microsoft 365 en el centro de administración](../create-groups/create-groups.md).

- **Usar con Outlook:** Además de usar Outlook en la Web desde el explorador para acceder a los buzones compartidos, también puede usar la aplicación Outlook para iOS o la aplicación Outlook para Android. Para obtener más información, consulte [Agregar un buzón compartido para Outlook Móvil](https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f). Otra opción es crear un grupo para el buzón compartido. Para obtener más información, vea [Comparar Grupos](../create-groups/compare-groups.md).

- **Cifrado:** No puede cifrar mensajes enviados desde un buzón compartido. Esto se debe a que un buzón compartido no tiene su propio contexto de seguridad (nombre de usuario y contraseña), por lo que no se le puede asignar ninguna clave. Si más de una persona es miembro y envía y recibe mensajes de correo electrónico que ha cifrado con sus propias claves, es posible que algunos miembros puedan leer el correo electrónico pero otros no, dependiendo de la clave pública con la que se haya cifrado el correo electrónico.

- **Conversión de buzones:** Puede convertir los buzones de usuario en buzones compartidos. Vea [Convertir un buzón de usuario en un buzón compartido](convert-user-mailbox-to-shared-mailbox.md).

- **Roles de administrador:** Los usuarios con roles de administrador global o administrador de Exchange pueden crear buzones compartidos.

- **Requisitos de la suscripción:** Para crear un buzón compartido, debe suscribirse a un plan de Microsoft 365 para negocios que incluya correo electrónico (servicio de Exchange Online). La suscripción a las Aplicaciones de Microsoft 365 para negocios no incluye correo electrónico. Microsoft 365 Empresa Estándar incluye correo electrónico.

- **Iniciar sesión:** No se espera un inicio de sesión directo en el buzón compartido por la cuenta de usuario asociada. Siempre debe bloquear el inicio de sesión de la cuenta de buzón compartido y mantenerlo bloqueado.

- **Demasiados usuarios:** Cuando un buzón compartido tiene demasiados usuarios designados que acceden a la vez, es posible que tengan problemas intermitentes para conectarse a este buzón. En este caso, puede considerar la posibilidad de reducir el número de usuarios o de usar una carga de trabajo diferente, como un grupo de Microsoft 365 o una carpeta pública.

- **Eliminación de mensajes:** Lamentablemente, no es posible impedir que los miembros eliminen los mensajes en un buzón compartido. La única manera de evitar este problema es crear un grupo de Microsoft 365 en lugar de un buzón compartido. Los grupos de Outlook son similares al buzón compartido. Para ver una comparación, consulte [Comparar grupos](../create-groups/compare-groups.md). Para obtener más información sobre los grupos, vea [Obtener más información sobre los grupos](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2).


> [!NOTE]
> Para acceder a un buzón de correo compartido, el usuario debe tener una licencia de Exchange Online, aunque el buzón de correo compartido no requiere ninguna licencia independiente. Cada buzón compartido tiene una cuenta de usuario correspondiente. ¿Ha notado que no se le pidió que proporcionase una contraseña cuando creó el buzón de correo compartido? La cuenta tiene una contraseña, pero se ha generado por el sistema (desconocida). No debe usar la cuenta para iniciar sesión en el buzón compartido. Sin una licencia, los buzones compartidos están limitados a 50 GB. Para aumentar el límite de tamaño a 100 GB, el buzón compartido debe tener asignada una licencia de Exchange Online Plan 2 o una licencia de Exchange Online Plan 1 con una licencia complementaria de Archivad de Exchange Online. Esto también le permitirá habilitar el archivo de expansión automática para una cantidad ilimitada de capacidad de almacenamiento de archivos. Del mismo modo, si desea colocar un buzón compartido en retención por litigio, el buzón compartido debe tener una licencia de Exchange Online Plan 2 o una licencia de Exchange Online Plan 1 con una licencia complementaria de Exchange Online Archiving. Si desea aplicar funciones avanzadas como Microsoft Defender para Office 365, eDiscovery avanzado o directivas de retención automática, el buzón de correo compartido debe tener licencia para esas características.

## <a name="related-content"></a>Contenido relacionado

[Crear un buzón compartido](create-a-shared-mailbox.md)

[Configurar un buzón compartido](configure-a-shared-mailbox.md)

[Convertir un buzón de usuario en un buzón compartido](convert-user-mailbox-to-shared-mailbox.md)

[Quitar la licencia de un buzón compartido](remove-license-from-shared-mailbox.md)

[Resolver problemas con los buzones compartidos](resolve-issues-with-shared-mailboxes.md)