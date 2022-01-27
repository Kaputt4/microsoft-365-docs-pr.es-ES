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
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
description: Los buzones compartidos se usan cuando varias personas necesitan acceder al mismo buzón. Obtenga información sobre lo que debe saber antes de crear un buzón compartido.
ms.openlocfilehash: 2fbf07fbe71ccb42411f5808aa923d7179d2f13d
ms.sourcegitcommit: 400ef9ac34247978e3de7ecc0b376c4abb6c99d8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2022
ms.locfileid: "62241316"
---
# <a name="about-shared-mailboxes"></a>Acerca de los buzones compartidos

Los buzones compartidos se usan cuando varios usuarios necesitan tener acceso al mismo buzón, como la dirección de correo electrónico del soporte técnico o información de la empresa, el escritorio de recepción u otra función que puedan compartir varios usuarios.

Los usuarios con permisos para el buzón del grupo pueden enviar como o enviar en nombre de la dirección de correo electrónico del buzón si el administrador le ha concedido permisos de usuario para hacerlo. Esto es especialmente útil para los buzones de ayuda y soporte técnico, ya que los usuarios pueden enviar mensajes de correo electrónico desde "Soporte técnico de Contoso" o "Escritorio de recepción del edificio A".

## <a name="before-you-begin"></a>Antes de empezar

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

- **Demasiados usuarios:** Cuando hay demasiados usuarios designados que acceden simultáneamente a un buzón compartido (no se recomienda más de 25), pueden no conectarse intermitentemente a este buzón o tener incoherencias como que los mensajes se dupliquen en la bandeja de salida. En este caso, puede considerar reducir el número de usuarios o usar una carga de trabajo diferente, como un grupo Microsoft 365 o una carpeta pública.

- **Eliminación de mensajes:** Lamentablemente, no es posible impedir que los miembros eliminen los mensajes en un buzón compartido. La única manera de evitar este problema es crear un grupo de Microsoft 365 en lugar de un buzón compartido. Los grupos de Outlook son similares al buzón compartido. Para ver una comparación, consulte [Comparar grupos](../create-groups/compare-groups.md). Para obtener más información sobre los grupos, vea [Obtener más información sobre los grupos](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2).

- **Multi-Geo** En un entorno multige geográfico, los buzones compartidos deben tener una licencia del mismo modo que se concede una licencia a un buzón de usuario. Tenga en cuenta que no se admite la auditoría entre buzones de correo. Por ejemplo, si se asignan permisos a un usuario para tener acceso a un buzón compartido en una ubicación geográfica diferente, las acciones de buzón que realiza el usuario no se registran en el registro de auditoría del buzón de correo compartido. 


> [!NOTE]
> Para acceder a un buzón de correo compartido, el usuario debe tener una licencia de Exchange Online, aunque el buzón de correo compartido no requiere ninguna licencia independiente. Cada buzón compartido tiene una cuenta de usuario correspondiente. ¿Ha notado que no se le pidió que proporcionase una contraseña cuando creó el buzón de correo compartido? La cuenta tiene una contraseña, pero se ha generado por el sistema (desconocida). No debe usar la cuenta para iniciar sesión en el buzón compartido. Sin una licencia, los buzones compartidos están limitados a 50 GB. Para aumentar el límite de tamaño a 100 GB, el buzón compartido debe tener asignada una licencia de Exchange Online Plan 2. La Exchange Online de plan 1 con una Archivado de Exchange Online de complemento solo aumentará el tamaño del buzón de archivo. Esto también le permitirá habilitar el archivado de expansión automática para una capacidad de almacenamiento de archivo adicional. Del mismo modo, si desea colocar un buzón compartido en retención por litigio, el buzón compartido debe tener una licencia de Exchange Online Plan 2 o una licencia de Exchange Online Plan 1 con una licencia complementaria de Exchange Online Archiving. Si desea aplicar funciones avanzadas como Microsoft Defender para Office 365, eDiscovery avanzado o directivas de retención automática, el buzón de correo compartido debe tener licencia para esas características.

## <a name="related-content"></a>Contenido relacionado

[Crear un buzón compartido](create-a-shared-mailbox.md) (artículo)\
[Configurar un buzón compartido](configure-a-shared-mailbox.md) (artículo)\
[Convertir un buzón de usuario en un buzón compartido](convert-user-mailbox-to-shared-mailbox.md) (artículo)\
[Quitar la licencia de un buzón compartido](remove-license-from-shared-mailbox.md) (artículo)\
[Resolver problemas con los buzones compartidos](resolve-issues-with-shared-mailboxes.md) (artículo)
