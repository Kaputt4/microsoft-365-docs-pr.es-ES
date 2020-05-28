---
title: Transferencia manual de datos entre dos cuentas
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 7dc5d983-84b2-4802-bef0-602ae1780a42
description: Obtenga información sobre cómo transferir datos manualmente entre dos cuentas de Microsoft 365 al cambiar el nombre de la empresa o del plan, o combinar varias suscripciones en una.
ms.openlocfilehash: 69476687915024accabdce2a603ebdd7e8b653af
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399877"
---
# <a name="transfer-data-manually-between-two-accounts"></a>Transferencia manual de datos entre dos cuentas

Prepárese para resumir las fundas y bloquear un trozo de tiempo en el calendario: la transferencia de datos entre dos cuentas de Microsoft 365 es un proceso manual, complejo y que consume mucho tiempo. No se trata de un proceso automatizado o admitido. Le ayudaremos a empezar.
  
> [!CAUTION]
> Se producirá un tiempo de inactividad durante el proceso en el que el correo electrónico, Skype empresarial y un sitio web público hospedado en Microsoft 365 no funcionarán. Los usuarios recibirán nuevos nombres de usuario y contraseñas y deberán restablecer Outlook.

**Transfiera los datos solo manualmente siguiendo las instrucciones de este tema si se aplica alguna de las siguientes opciones:**
  
- Debe cambiar a un plan de una familia de servicios diferente.

- El nombre de la compañía ha cambiado y ha decidido crear una nueva suscripción y migrar los datos porque desea usar nombres de dominio iniciales diferentes.

- Debe combinar varias suscripciones en una nueva.

> [!IMPORTANT]
> Si necesita [cambiar el plan de suscripción](../../commerce/subscriptions/switch-to-a-different-plan.md) y puede usar el Asistente para cambiar de planes o si necesita transferir a un nuevo plan de suscripción en la misma familia de suscripciones incluso cuando el Asistente para cambiar de planes no funciona, no es necesario transferir los datos de forma manual y no hay tiempo de inactividad.

|**Tareas**|**Pasos**|
|:-----|:-----|
|Compre el plan al que desea desplazarse.  <br/> |Al registrarse, debe especificar el nombre de la compañía que se va a usar en los nombres de dominio iniciales: *yourcompany* . onmicrosoft.com, *yourcompany* -public.sharepoint.com y *yourcompany* . SharePoint.com. Debe usar un nombre de *yourcompany* diferente al que hizo para las suscripciones existentes.  <br/> > [!NOTE]> suele tardar un mínimo de varios meses después de cancelar una suscripción para liberar los nombres de dominio iniciales que usan *yourcompany* desde nuestros sistemas. Incluso si tiene previsto guardar todos los datos de su suscripción antigua de Microsoft 365 y cancelar esa suscripción, el antiguo valor de *yourcompany* no está disponible inmediatamente para su uso en una nueva suscripción.           |
|Quite su dominio personalizado de la suscripción a Microsoft 365 anterior.  <br/> | Siga los [pasos necesarios antes de quitar un dominio](remove-a-domain.md) para quitar el nombre de dominio de las direcciones de correo electrónico del usuario y quitar los registros DNS para el correo electrónico y Lync para el dominio personalizado. Si hospeda su sitio web público en Microsoft 365, también tendrá que quitar el registro CNAME que apunta a él.  <br/> > [!IMPORTANT]> después de quitar el registro MX que enruta el correo electrónico a este dominio personalizado, el correo electrónico dejará de funcionar hasta que haya agregado el dominio a la nueva cuenta, a configurar el nuevo registro MX y a configurar a los usuarios. Al quitar los registros DNS para Lync, Lync dejará de funcionar. Y, después de quitar el registro CNAME que señala a su sitio web público, no estará disponible.           [Quite el dominio](remove-a-domain.md) .  <br/> |
|Configure su dominio personalizado para su nueva suscripción y configure a los usuarios.  <br/> | Configure su suscripción nueva, incluida la creación de los registros DNS necesarios para su dominio personalizado.  <br/>  Cree los usuarios con direcciones de correo electrónico en su dominio personalizado.  <br/> |
|Transferir datos de su suscripción antigua a la nueva suscripción.  <br/> | Inicie sesión en ambas cuentas en ventanas del explorador independientes:  <br/>  Haga clic con el botón secundario en el icono de Internet Explorer y abra dos ventanas del explorador InPrivate. Puede usar diferentes credenciales en las dos ventanas para iniciar sesión en ambas cuentas.  <br/> [Transferir la configuración administrativa entre suscripciones](#email) <br/> [Estructura y datos del sitio de grupo de transferencia](#transfer-team-site-structure-and-data) <br/> [Transferir un sitio web público entre suscripciones](#transfer-a-public-website-between-subscriptions) <br/> [Transferir la configuración administrativa entre suscripciones](#email) <br/> |
|Para cancelar la suscripción para el plan con el que ya ha terminado llame al soporte técnico de Microsoft para Microsoft 365.  <br/> | Compruebe que la nueva suscripción funciona y que se han transferido todos los datos.  <br/>  [Póngase en contacto con el soporte técnico](../contact-support-for-business-products.md) para cancelar su suscripción antigua.  <br/> |

## <a name="transfer-administrative-settings-between-subscriptions"></a>Transferir la configuración administrativa entre suscripciones

Vaya a las siguientes páginas de cada cuenta y configure la nueva cuenta basándose en la configuración de la cuenta antigua.
  
Si está transfiriendo datos de Microsoft 365 a Microsoft 365 mediana empresa o Microsoft 365 Enterprise, las páginas de administración se estructuran de manera diferente. Vea un [vídeo: Introducción a Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365/admin/)y vaya a los siguientes lugares para ver la configuración de administración.
  
Para Microsoft 365 Enterprise y Microsoft 365 mediana empresa:
  
|**Ubicación**|**Finalidad**|
|:-----|:-----|
|**Administrador** \> de **Microsoft 365** \> **Configuración del servicio** <br/> |Seleccione cada pestaña para la configuración de correo, sitios, Lync, software de usuario, contraseñas, comunidad, administración de derechos y móvil.  <br/> |
|**Administrador** \> de **Exchange** <br/> | Configuración de Exchange Online  <br/> |
|**Administrador** \> de **SharePoint** <br/> | Configuración de SharePoint Online  <br/> |
|**Administrador** \> de **Skype empresarial** <br/> |Configuración adicional de Skype empresarial  <br/> |

Para Microsoft 365 Small Business
  
|**Ubicación**|**Finalidad**|
|:-----|:-----|
|**Administrador** \> de **Administrar la configuración de toda la organización** <br/> |Configuración administrativa  <br/> |

## <a name="transfer-a-public-website-between-subscriptions"></a>Transferir un sitio web público entre suscripciones

Si tiene un sitio web público hospedado en Microsoft 365, debe guardarlo y volver a crearlo en la nueva suscripción.
  
> [!NOTE]
> Si el sitio web público está hospedado en un proveedor de host DNS, no es necesario realizar ningún cambio. No se verá afectada por la transición.
  
Para guardar un contenido de lista o biblioteca de documentos de un entorno de SharePoint Online en recursos compartidos de archivos o en un equipo local, vea [migración manual del contenido de SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkId=402910).
  
> [!NOTE]
> La aplicación de migración de sitios públicos no puede transferir datos a una suscripción diferente.
  
## <a name="transfer-team-site-structure-and-data"></a>Estructura y datos del sitio de grupo de transferencia

Hay varias formas de guardar o transferir datos del sitio de Grupo:
  
- Puede guardar el sitio antiguo como una plantilla e importar la plantilla en el nuevo sitio.

- Para transferir documentos, primero vuelva a crear manualmente la jerarquía en el nuevo sitio. A continuación, puede abrir ambos sitios de grupo de SharePoint al mismo tiempo, abrir ambas bibliotecas de documentos con el explorador de Windows y copiar y pegar los documentos. Vea [vídeo: copiar o mover archivos de biblioteca mediante abrir con el explorador](https://support.office.com/article/where-to-store-files-c7c20284-bc94-47f4-9728-d28e9daf0790).

- Para transferir datos de listas, guarde una [plantilla de lista](https://support.microsoft.com/en-us/office/manage-list-templates-c3884ad1-bc49-44b8-b3d6-3bc6a01eb393)y use la plantilla guardada para volver a crear la lista en el nuevo sitio.

- Para guardar un contenido de una biblioteca de documentos o lista de un entorno de SharePoint Online (OneDrive para la empresa o sitios de grupo) en recursos compartidos de archivos o en un equipo local, vea la [información sobre la migración manual del contenido de SharePoint Online](https://support.microsoft.com/kb/2783484).

## <a name="transfer-users-data-between-subscriptions"></a>Transferir los datos de los usuarios entre suscripciones

### <a name="email"></a>Correo electrónico:

Pida a los usuarios que [muevan el correo electrónico, los contactos, las tareas y la información del calendario](https://support.office.com/article/0996ece3-57c6-49bc-977b-0d1892e2aacc.aspx) después de configurar la nueva suscripción. Pueden obtener acceso al correo electrónico antiguo mediante el nombre de usuario inicial, como sue@contoso.onmicrosoft.com.
  
### <a name="onedrive-for-business-data"></a>Datos de OneDrive para la empresa:

Pida a los usuarios que copien o sincronicen [el contenido de OneDrive para la empresa en su equipo](https://support.office.com/article/59b1de2b-519e-4d3a-8f45-51647cf291cd.aspx)y, a continuación, vuelva a agregarlo a su nueva suscripción.
