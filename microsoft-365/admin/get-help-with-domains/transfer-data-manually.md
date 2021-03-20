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
description: Encuentre cómo transferir datos manualmente entre dos cuentas de Microsoft 365 al cambiar el plan o el nombre de la compañía, o combinar varias suscripciones en una.
ms.openlocfilehash: 9916da50f4589f949d35466ca6aa8f1d79cc40ea
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915511"
---
# <a name="transfer-data-manually-between-two-accounts"></a>Transferir datos manualmente entre dos cuentas

Prepárese para enrollar las mangas y bloquear un fragmento de tiempo en el calendario: transferir datos entre dos cuentas de Microsoft 365 es un proceso manual, complicado y que requiere mucho tiempo. No se trata de un proceso automatizado ni compatible. Empezaremos.
  
> [!CAUTION]
> Habrá tiempo de inanción durante el proceso en el que el correo electrónico, Skype Empresarial y un sitio web público hospedado en Microsoft 365 no funcionarán. Los usuarios recibirán nuevos nombres de usuario y contraseñas, y tendrán que restablecer Outlook.

**Solo transfiera datos manualmente con las instrucciones de este tema si se aplica una de las siguientes opciones:**
  
- Debe cambiar a un plan en una familia de servicios diferente.

- El nombre de la compañía cambió y decidió crear una nueva suscripción y migrar los datos porque desea usar nombres de dominio iniciales diferentes.

- Debes combinar varias suscripciones en una nueva.

> [!IMPORTANT]
> Si necesita cambiar su [plan](../../commerce/subscriptions/switch-to-a-different-plan.md) de suscripción y puede usar el Asistente para cambiar de planes, o si necesita transferir a un nuevo plan de suscripción en la misma familia de suscripciones incluso cuando el Asistente para cambiar de planes no funciona, no es necesario transferir manualmente los datos y no hay tiempo de inversiones.

|**Tareas** |**Pasos**|
|:-----|:-----|
|Compra el plan al que quieres moverte.  <br/> |Cuando se registra, especifica el nombre de la compañía que se usará en los nombres de dominio *iniciales:* su empresa .onmicrosoft.com,  su empresa -public.sharepoint.com y su empresa *.sharepoint.com.* Debes usar un nombre de  *empresa*  diferente al que tenías para las suscripciones existentes.  <br/> > [!NOTE]> Suele ser necesario un mínimo de varios meses después de cancelar una suscripción para liberar los nombres de dominio iniciales que usan su empresa  *desde*  nuestros sistemas. Incluso si planea guardar todos los datos de su antigua suscripción de Microsoft  365 y cancelar esa suscripción, el valor antiguo de su empresa no está disponible inmediatamente para su uso en una nueva suscripción.           |
|Quite el dominio personalizado de la antigua suscripción de Microsoft 365.  <br/> | Siga los [pasos necesarios antes de](remove-a-domain.md) quitar un dominio para quitar el nombre de dominio de las direcciones de correo electrónico de usuario y quitar los registros DNS para el correo electrónico y Lync para el dominio personalizado. Si hospeda su sitio web público en Microsoft 365, también tendrá que quitar el registro CNAME que apunta a él.  <br/> > [!IMPORTANT]> Después de quitar el registro MX que enruta el correo electrónico a este dominio personalizado, el correo electrónico dejará de funcionar hasta que haya agregado el dominio a su nueva cuenta, configure el nuevo registro MX y configure los usuarios. Al quitar los registros DNS de Lync, Lync dejará de funcionar. Y después de quitar el registro CNAME que apunta a su sitio web público, no estará disponible.           [Quite el dominio](remove-a-domain.md) .  <br/> |
|Configure el dominio personalizado para la nueva suscripción y configure los usuarios.  <br/> | Configure la nueva suscripción, incluida la creación de los registros DNS necesarios para su dominio personalizado.  <br/>  Cree los usuarios, con direcciones de correo electrónico en su dominio personalizado.  <br/> |
|Transferir datos de la suscripción antigua a la nueva suscripción.  <br/> | Inicie sesión en ambas cuentas en ventanas de explorador independientes:  <br/>  Haga clic con el botón secundario en el icono del explorador y abra dos ventanas de explorador privado. Puede usar credenciales diferentes en las dos ventanas para iniciar sesión en ambas cuentas.  <br/> [Transferir la configuración administrativa entre suscripciones](#email) <br/> [Transferir datos y estructura de sitio de grupo](#transfer-team-site-structure-and-data) <br/> [Transferir un sitio web público entre suscripciones](#transfer-a-public-website-between-subscriptions) <br/> [Transferir la configuración administrativa entre suscripciones](#email) <br/> |
|Cancele la suscripción del plan con el que ha terminado llamando al Soporte técnico de Microsoft para Microsoft 365.  <br/> | Compruebe que la nueva suscripción funciona y que se han transferido todos los datos.  <br/>  [Póngase en contacto con el soporte](../contact-support-for-business-products.md) técnico del cliente para cancelar la suscripción anterior.  <br/> |

## <a name="transfer-administrative-settings-between-subscriptions"></a>Transferir la configuración administrativa entre suscripciones

Vaya a las páginas siguientes de cada cuenta y configure la nueva cuenta en función de la configuración de la cuenta antigua.
  
Si va a transferir datos de Microsoft 365 a Microsoft 365 Midsize Business o Microsoft 365 Enterprise, las páginas de administración se estructuran de forma diferente. Vea un [vídeo: Introducción a Microsoft 365 Enterprise](../index.yml)y vaya a los siguientes lugares para ver la configuración de administración.
  
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
> Si el sitio web público está hospedado en un proveedor de hospedaje DNS, no se requieren cambios. No se verá afectado por la transición.
  
Para guardar una biblioteca de documentos o contenido de lista de un entorno de SharePoint Online en recursos compartidos de archivos o en un equipo local, vea Migración manual del contenido [de SharePoint Online](/sharepoint/troubleshoot/migration-tool/content-manual-migration).
  
> [!NOTE]
> La aplicación de migración de sitios públicos no puede transferir datos a una suscripción diferente.
  
## <a name="transfer-team-site-structure-and-data"></a>Transferir datos y estructura de sitio de grupo

Hay varias maneras de guardar o transferir datos del sitio de grupo:
  
- Puede guardar el sitio antiguo como una plantilla e importar la plantilla en el nuevo sitio.

- Para transferir documentos, primero vuelva a crear manualmente la jerarquía en el nuevo sitio. A continuación, puede abrir ambos sitios de grupo de SharePoint al mismo tiempo, abrir ambas bibliotecas de documentos con el Explorador de Windows y copiar y pegar los documentos. Vea [Vídeo: Copiar o mover archivos de biblioteca mediante Abrir con el Explorador](https://support.microsoft.com/office/c7c20284-bc94-47f4-9728-d28e9daf0790).

- Para transferir datos de lista, guarde una plantilla [de](https://support.microsoft.com/office/c3884ad1-bc49-44b8-b3d6-3bc6a01eb393)lista y use la plantilla guardada para volver a crear la lista en el nuevo sitio.

- Para guardar una biblioteca de documentos o contenido de lista desde un entorno de SharePoint Online (OneDrive para la Empresa o sitios de grupo) para guardar recursos compartidos o en un equipo local, vea [Information about manual migration of SharePoint Online content](https://support.microsoft.com/kb/2783484).

## <a name="transfer-users-data-between-subscriptions"></a>Transferir datos de usuarios entre suscripciones

### <a name="email"></a>Correo electrónico:

Pida a los usuarios [que muevan su correo electrónico, contactos, tareas](https://support.microsoft.com/office/0996ece3-57c6-49bc-977b-0d1892e2aacc) e información de calendario después de configurar la nueva suscripción. Pueden llegar a su correo electrónico antiguo usando su nombre de usuario inicial, como sue@contoso.onmicrosoft.com.
  
### <a name="onedrive-for-business-data"></a>Datos de OneDrive para la Empresa:

Pida a los usuarios que copien o sincronicen contenido de [OneDrive para](https://support.microsoft.com/office/59b1de2b-519e-4d3a-8f45-51647cf291cd)la Empresa en su equipo y, a continuación, vuelvan a agregarlo a su nueva suscripción.

### <a name="onenote"></a>OneNote 

Pida a los usuarios que realicen una copia [de seguridad de OneNote](https://support.microsoft.com/office/back-up-notes-f58b34b0-611d-435e-87fa-7942a1767af4?ui=en-us&rs=en-us&ad=us) y que [restablezcan las notas de una copia de seguridad en](https://support.microsoft.com/en-us/office/restore-notes-from-a-backup-5daf9cb0-6769-4998-a5de-f044fdd0d831?ui=en-us&rs=en-us&ad=us) sus nuevas suscripciones.