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
ms.openlocfilehash: 3db111179b0a85a0836ae429785233089d78bec1
ms.sourcegitcommit: 7374c7b013890744d74e5214f7f8d69ca7874466
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2022
ms.locfileid: "67408007"
---
# <a name="about-shared-mailboxes"></a>Acerca de los buzones compartidos

Los buzones compartidos se usan cuando varios usuarios necesitan tener acceso al mismo buzón, como la dirección de correo electrónico del soporte técnico o información de la empresa, el escritorio de recepción u otra función que puedan compartir varios usuarios.

Los usuarios con permisos para el buzón del grupo pueden enviar como o enviar en nombre de la dirección de correo electrónico del buzón si el administrador le ha concedido permisos de usuario para hacerlo. Esto es especialmente útil para los buzones de ayuda y soporte técnico, ya que los usuarios pueden enviar mensajes de correo electrónico desde "Soporte técnico de Contoso" o "Escritorio de recepción del edificio A".

## <a name="before-you-begin"></a>Antes de empezar

Antes de [crear un buzón compartido](create-a-shared-mailbox.md), estas son algunas cosas que debe saber:

- **Licencias:** El buzón compartido puede almacenar hasta 50 GB de datos sin que usted tenga que asignarle una licencia. Una vez superado ese límite, necesitará asignar una licencia al buzón para poder almacenar más datos. Para obtener más información sobre las licencias de los buzones compartidos, consulte [Límites de Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#StorageLimits). Cuando un buzón compartido alcanza el límite de almacenamiento, podrá recibir correo electrónico durante un tiempo, pero no podrá enviarlo. Después, dejará de recibir correo electrónico. Los remitentes del buzón recibirán un aviso de no entrega.

- **Permisos de usuario:** Debe dar a los usuarios permisos (suscripciones) para usar el buzón compartido. Solo las personas de su organización pueden usar los buzones de correo compartidos.

- **Usuarios externos:** No puede proporcionar acceso a su buzón compartido a usuarios ajenos a su negocio (como gente con una cuenta de Gmail). Si quiere hacerlo, le recomendamos que cree un grupo para Outlook. Para obtener más información, consulte [Crear un grupo de Microsoft 365 en el centro de administración](../create-groups/create-groups.md)

- **Usar con Outlook:** Además de usar Outlook en la Web desde el explorador para acceder a los buzones compartidos, también puede usar la aplicación Outlook para iOS o la aplicación Outlook para Android. Para obtener más información, consulte [Agregar un buzón compartido para Outlook Móvil](https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f). Otra opción es crear un grupo para el buzón compartido. Para obtener más información, vea [Comparar Grupos](../create-groups/compare-groups.md).

- **Cifrado:** No puede cifrar mensajes enviados desde un buzón compartido. Esto se debe a que un buzón compartido no tiene su propio contexto de seguridad (nombre de usuario y contraseña), por lo que no se le puede asignar ninguna clave. Si más de una persona es miembro y envía y recibe mensajes de correo electrónico que ha cifrado con sus propias claves, es posible que algunos miembros puedan leer el correo electrónico pero otros no, dependiendo de la clave pública con la que se haya cifrado el correo electrónico.

- **Conversión de buzones:** Puede convertir los buzones de usuario en buzones compartidos. Vea [Convertir un buzón de usuario en un buzón compartido](convert-user-mailbox-to-shared-mailbox.md).

- **Roles de administrador:** Los usuarios con roles de administrador global o administrador de Exchange pueden crear buzones compartidos.

- **Requisitos de la suscripción:** Para crear un buzón compartido, debe suscribirse a un plan de Microsoft 365 para negocios que incluya correo electrónico (servicio de Exchange Online). La suscripción a las Aplicaciones de Microsoft 365 para negocios no incluye correo electrónico. Microsoft 365 Empresa Estándar incluye correo electrónico.

- **Iniciar sesión:** No se espera un inicio de sesión directo en el buzón compartido por la cuenta de usuario asociada. Siempre debe bloquear el inicio de sesión de la cuenta de buzón compartido y mantenerlo bloqueado.

- **Demasiados usuarios:** Cuando hay demasiados usuarios designados que acceden simultáneamente a un buzón compartido (se recomienda no más de 25), pueden fallar intermitentemente en la conexión a este buzón o tener incoherencias como que los mensajes se dupliquen en la bandeja de salida. En este caso, puede considerar la posibilidad de reducir el número de usuarios o de usar una carga de trabajo diferente, como un grupo de Microsoft 365 o una carpeta pública.

- **Eliminación de mensajes:** Lamentablemente, no es posible impedir que los miembros eliminen los mensajes en un buzón compartido. La única manera de evitar este problema es [crear un grupo de Microsoft 365](/microsoft-365/admin/create-groups/create-groups) en lugar de un buzón compartido. Los grupos de Outlook son similares al buzón compartido. Para ver una comparación, consulte [Comparar grupos](../create-groups/compare-groups.md). Para obtener más información sobre los grupos, vea [Obtener información sobre los grupos de Microsoft 365](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2).

- **Multi-Geo** En un entorno multigeográfico, los buzones compartidos deben tener la misma licencia que un buzón de usuario. Tenga en cuenta que no se admite la auditoría de buzones entre ubicaciones geográficas. Por ejemplo, si se asignan permisos a un usuario para tener acceso a un buzón compartido en una ubicación geográfica diferente, las acciones de buzón que realiza el usuario no se registran en el registro de auditoría del buzón de correo compartido. 


> [!NOTE]
> Para acceder a un buzón de correo compartido, el usuario debe tener una licencia de Exchange Online, aunque el buzón de correo compartido no requiere ninguna licencia independiente. Cada buzón compartido tiene una cuenta de usuario correspondiente. ¿Ha notado que no se le pidió que proporcionase una contraseña cuando creó el buzón de correo compartido? La cuenta tiene una contraseña, pero se ha generado por el sistema (desconocida). No debe usar la cuenta para iniciar sesión en el buzón compartido. Sin una licencia, los buzones compartidos están limitados a 50 GB. Para aumentar el límite de tamaño a 100 GB, el buzón compartido debe tener asignada una licencia de Exchange Online Plan 2. La licencia de Exchange Online Plan 1 con una licencia de complemento de Archivado de Exchange Online solo aumentará el tamaño del buzón de archivo. Esto también le permitirá habilitar el archivo de expansión automática para una capacidad de almacenamiento de archivos adicional. Del mismo modo, si desea colocar un buzón compartido en retención por litigio, el buzón compartido debe tener una licencia de Exchange Online Plan 2 o una licencia de Exchange Online Plan 1 con una licencia complementaria de Exchange Online Archiving. Si desea aplicar funciones avanzadas como Microsoft Defender para Office 365, eDiscovery (Premium) o directivas de retención automática, el buzón de correo compartido debe tener licencia para esas características.

> [!NOTE]
> Antes de julio de 2018, todos los buzones compartidos sin licencia se aprovisionaban con un tamaño de 100 GB. Para obtener más información, vea [Corregir el aprovisionamiento y el tamaño del buzón compartido](https://techcommunity.microsoft.com/t5/exchange-team-blog/correcting-shared-mailbox-provisioning-and-sizing/ba-p/607991).

## <a name="related-content"></a>Contenido relacionado

[Crear un buzón compartido](create-a-shared-mailbox.md) (artículo)\
[Configurar un buzón compartido](configure-a-shared-mailbox.md) (artículo)\
[Convertir un buzón de usuario en un buzón compartido](convert-user-mailbox-to-shared-mailbox.md) (artículo)\
[Quitar la licencia de un buzón compartido](remove-license-from-shared-mailbox.md) (artículo)\
[Resolver problemas con los buzones compartidos](resolve-issues-with-shared-mailboxes.md) (artículo)
