---
title: Transferir datos manualmente entre dos cuentas
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
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
description: Descubra cómo transferir datos manualmente entre dos cuentas de Microsoft 365 cuando cambió el plan o el nombre de la compañía, o combinó varias suscripciones en una.
ms.openlocfilehash: b7b0bb9c9b95b31d98040ae90632ef87a7fb0e3b
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645148"
---
# <a name="transfer-data-manually-between-two-accounts"></a>Transferir datos manualmente entre dos cuentas

Prepárese para preparar sus bolsillos y bloquear un fragmento de tiempo en el calendario: transferir datos entre dos cuentas de Microsoft 365 es un proceso manual, complicado y que requiere mucho tiempo. Este no es un proceso automatizado o compatible. Le empezaremos a trabajar.
  
> [!CAUTION]
> Habrá tiempo de inaloos durante el proceso en el que el correo electrónico, Skype Empresarial y un sitio web público hospedado en Microsoft 365 no funcionarán. Los usuarios recibirán nuevos nombres de usuario y contraseñas, y tendrán que restablecer Outlook.

**Solo se transfieren datos manualmente siguiendo las instrucciones de este tema si se aplica una de las siguientes condiciones:**
  
- Debe cambiar a un plan de una familia de servicios diferente.

- El nombre de la compañía cambió y decidió crear una suscripción nueva y migrar los datos porque quiere usar nombres de dominio iniciales diferentes.

- Debes combinar varias suscripciones en una nueva.

> [!IMPORTANT]
> Si necesita cambiar el [plan](../../commerce/subscriptions/switch-to-a-different-plan.md) de suscripción y puede usar el Asistente para cambiar de planes, o si necesita transferir a un nuevo plan de suscripción en la misma familia de suscripciones incluso cuando el Asistente para cambiar de plan no funciona, no es necesario transferir manualmente los datos y no hay tiempo de in inversiones.

|**Tareas** |**Pasos**|
|:-----|:-----|
|Compre el plan al que desea mover.  <br/> |Cuando se registra, especifica el nombre de la compañía que se va a usar en los nombres de dominio *iniciales:* su empresa .onmicrosoft.com,  su empresa -public.sharepoint.com y su empresa *.sharepoint.com.* Debes usar un nombre de  *empresa*  diferente del que tenías para las suscripciones existentes.  <br/> > [!NOTE]> suele ser necesario un mínimo de varios meses después de cancelar una suscripción para liberar los nombres de dominio iniciales que usan su compañía  *desde*  nuestros sistemas. Incluso si planea guardar todos los datos de la suscripción antigua de Microsoft  365 y cancelarla, el valor antiguo de su compañía no estará disponible inmediatamente para su uso en una nueva suscripción.           |
|Quite el dominio personalizado de la suscripción antigua de Microsoft 365.  <br/> | Siga los [pasos necesarios antes de](remove-a-domain.md) quitar un dominio para quitar el nombre de dominio de las direcciones de correo electrónico del usuario y quitar los registros DNS para el correo electrónico y Lync para el dominio personalizado. Si hospeda su sitio web público en Microsoft 365, también tendrá que quitar el registro CNAME que apunta a él.  <br/> > [!IMPORTANT]> Después de quitar el registro MX que enruta el correo electrónico a este dominio personalizado, el correo electrónico dejará de funcionar hasta que haya agregado el dominio a su nueva cuenta, configure el nuevo registro MX y configure los usuarios. Cuando quite los registros DNS de Lync, Lync dejará de funcionar. Y después de quitar el registro CNAME que apunta a su sitio web público, no estará disponible.           [Quite el dominio](remove-a-domain.md) .  <br/> |
|Configure su dominio personalizado para la nueva suscripción y configure los usuarios.  <br/> | Configure su nueva suscripción, incluida la creación de los registros DNS necesarios para su dominio personalizado.  <br/>  Cree los usuarios, con direcciones de correo electrónico en su dominio personalizado.  <br/> |
|Transferir datos de la suscripción antigua a la nueva suscripción.  <br/> | Inicie sesión en ambas cuentas en ventanas de explorador independientes:  <br/>  Haga clic con el botón secundario en el icono del explorador y abra dos ventanas privadas del explorador. Puede usar credenciales diferentes en las dos ventanas para iniciar sesión en ambas cuentas.  <br/> [Transferir la configuración administrativa entre suscripciones](#email) <br/> [Transferencia de datos y estructura del sitio de grupo](#transfer-team-site-structure-and-data) <br/> [Transferir un sitio web público entre suscripciones](#transfer-a-public-website-between-subscriptions) <br/> [Transferir la configuración administrativa entre suscripciones](#email) <br/> |
|Cancele la suscripción del plan con el que ha terminado llamando al Soporte técnico de Microsoft para Microsoft 365.  <br/> | Compruebe que la nueva suscripción funciona y que se han transferido todos los datos.  <br/>  [Póngase en contacto con el soporte](../contact-support-for-business-products.md) al cliente para cancelar la suscripción anterior.  <br/> |

## <a name="transfer-administrative-settings-between-subscriptions"></a>Transferir la configuración administrativa entre suscripciones

Ve a las páginas siguientes de cada cuenta y configura la nueva cuenta en función de la configuración de la cuenta antigua.
  
Si transfiere datos de Microsoft 365 a Microsoft 365 Mediana Empresa o Microsoft 365 Enterprise, las páginas de administración se estructuran de forma diferente. Vea un [vídeo: Presentación de Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365/admin/)y vaya a los siguientes lugares para ver la configuración de administración.
  
Para Microsoft 365 Enterprise y Microsoft 365 Mediana Empresa:
  
|**Location**|**Finalidad**|
|:-----|:-----|
|**Administrador** \> **Microsoft 365** \> **Configuración del servicio** <br/> |Seleccione cada pestaña para la configuración de correo, sitios, Lync, software de usuario, contraseñas, comunidad, administración de derechos y móvil.  <br/> |
|**Administrador** \> **Exchange** <br/> | Configuración de Exchange Online  <br/> |
|**Administrador** \> **SharePoint** <br/> | Configuración de SharePoint Online  <br/> |
|**Administrador** \> **Skype Empresarial** <br/> |Configuración adicional de Skype Empresarial  <br/> |

Para Microsoft 365 Pequeña Empresa
  
|**Location**|**Finalidad**|
|:-----|:-----|
|**Administrador** \> **Administrar la configuración de toda la organización** <br/> |Configuración administrativa  <br/> |

## <a name="transfer-a-public-website-between-subscriptions"></a>Transferir un sitio web público entre suscripciones

Si tiene un sitio web público hospedado en Microsoft 365, debe guardarlo y volver a crearlo en su nueva suscripción.
  
> [!NOTE]
> Si su sitio web público está hospedado en un proveedor de hospedaje DNS, no es necesario realizar ningún cambio. No se verá afectado por la transición.
  
Para guardar una biblioteca de documentos o contenido de lista de un entorno de SharePoint Online en recursos compartidos de archivos o en un equipo local, vea Migración manual de [contenido de SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkId=402910).
  
> [!NOTE]
> La aplicación de migración de sitios públicos no puede transferir datos a una suscripción diferente.
  
## <a name="transfer-team-site-structure-and-data"></a>Transferencia de datos y estructura del sitio de grupo

Hay varias formas de guardar o transferir datos del sitio de grupo:
  
- Puede guardar el sitio antiguo como plantilla e importar la plantilla al nuevo sitio.

- Para transferir documentos, primero vuelva a crear manualmente la jerarquía en el nuevo sitio. A continuación, puede abrir ambos sitios de grupo de SharePoint al mismo tiempo, abrir ambas bibliotecas de documentos con el Explorador de Windows y copiar y pegar los documentos. Vea [Vídeo: Copiar o mover archivos de biblioteca mediante Abrir con el Explorador.](https://support.microsoft.com/office/c7c20284-bc94-47f4-9728-d28e9daf0790)

- Para transferir datos de lista, guarde una [plantilla](https://support.microsoft.com/office/c3884ad1-bc49-44b8-b3d6-3bc6a01eb393)de lista y use la plantilla guardada para volver a crear la lista en el nuevo sitio.

- Para guardar una biblioteca de documentos o contenido de lista desde un entorno de SharePoint Online (OneDrive para la Empresa o sitios de grupo) en recursos compartidos de archivos o en un equipo local, vea Información sobre la migración manual de contenido de [SharePoint Online.](https://support.microsoft.com/kb/2783484)

## <a name="transfer-users-data-between-subscriptions"></a>Transferir datos de usuarios entre suscripciones

### <a name="email"></a>Correo electrónico:

Pida a los usuarios [que muevan su correo electrónico, contactos, tareas](https://support.microsoft.com/office/0996ece3-57c6-49bc-977b-0d1892e2aacc) e información del calendario después de configurar la nueva suscripción. Pueden acceder a su correo electrónico antiguo con su nombre de usuario inicial, como sue@contoso.onmicrosoft.com.
  
### <a name="onedrive-for-business-data"></a>Datos de OneDrive para la Empresa:

Pida a los usuarios que copien o sincronicen el contenido de [OneDrive](https://support.microsoft.com/office/59b1de2b-519e-4d3a-8f45-51647cf291cd)para la Empresa en su equipo y, a continuación, vuelvan a agregarlo a su nueva suscripción.

### <a name="onenote"></a>OneNote 

Pida a los usuarios [que realicen una copia de](https://support.microsoft.com/office/back-up-notes-f58b34b0-611d-435e-87fa-7942a1767af4?ui=en-us&rs=en-us&ad=us) seguridad de OneNote y que [restauren](https://support.microsoft.com/en-us/office/restore-notes-from-a-backup-5daf9cb0-6769-4998-a5de-f044fdd0d831?ui=en-us&rs=en-us&ad=us) las notas de una copia de seguridad en sus nuevas suscripciones.
