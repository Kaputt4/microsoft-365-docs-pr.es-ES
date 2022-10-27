---
title: Transferencia manual de datos entre dos cuentas
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier2
- scotvorg
- M365-subscription-management
- Adm_O365
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 7dc5d983-84b2-4802-bef0-602ae1780a42
description: Busque cómo transferir datos manualmente entre dos cuentas de Microsoft 365 al cambiar el nombre del plan o de la empresa, o combinar varias suscripciones en una.
ms.openlocfilehash: feb2cafee627a44dafc7ee8621c1b2910ddd7470
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68718158"
---
# <a name="transfer-data-manually-between-two-accounts"></a>Transferencia manual de datos entre dos cuentas

Prepárese para desplegar las mangas y bloquear un fragmento de tiempo en el calendario: la transferencia de datos entre dos cuentas de Microsoft 365 es un proceso manual, complicado y lento. Este no es un proceso automatizado o compatible. Te empezaremos.
  
> [!CAUTION]
> Habrá tiempo de inactiva durante el proceso en el que el correo electrónico, Skype Empresarial y un sitio web público hospedado en Microsoft 365 no funcionarán. Los usuarios obtendrán nuevos nombres de usuario y contraseñas, y tendrán que restablecer Outlook.

**Solo se transfieren datos manualmente mediante las instrucciones de este tema si se aplica una de las siguientes opciones:**
  
- Debe cambiar a un plan de una familia de servicios diferente.

- El nombre de la empresa cambió y decidió crear una nueva suscripción y migrar los datos porque quiere usar nombres de dominio iniciales diferentes.

- Debe combinar varias suscripciones en una nueva.

> [!IMPORTANT]
> Si necesita cambiar el [plan de suscripción](../../commerce/subscriptions/switch-to-a-different-plan.md) y puede usar el Asistente para cambiar planes, o si necesita transferir a un nuevo plan de suscripción en la misma familia de suscripciones incluso cuando el Asistente para planes de conmutador no funciona, no es necesario transferir manualmente los datos y no hay tiempo de inactivación.

|**Tasks**|**Pasos**|
|:-----|:-----|
|Compra el plan al que quieres moverte.  <br/> |Al registrarse, especifique el nombre de la empresa que se usará en los nombres de dominio iniciales:  *.onmicrosoft.com de su empresa*  ,  *suempresa*  -public.sharepoint.com y  *suempresa*  .sharepoint.com. Debe usar un nombre de  *su empresa*  diferente al que usó para las suscripciones existentes.  <br/> > [!NOTE]> Normalmente, se tarda un mínimo de varios meses después de cancelar una suscripción para liberar los nombres de dominio iniciales que usan  *su empresa*  de nuestros sistemas. Incluso si planea guardar todos los datos de su suscripción de Microsoft 365 anterior y cancelar esa suscripción, el valor de  *su empresa*  anterior no está disponible inmediatamente para su uso en una nueva suscripción.           |
|Quite el dominio personalizado de la suscripción antigua de Microsoft 365.  <br/> | Siga los [pasos necesarios antes de quitar un dominio](remove-a-domain.md) para quitar el nombre de dominio de las direcciones de correo electrónico de usuario y quitar los registros DNS para el correo electrónico y Lync para el dominio personalizado. Si hospeda su sitio web público en Microsoft 365, también tendrá que quitar el registro CNAME que apunta a él.  <br/> > [!IMPORTANT]> Después de quitar el registro MX que enruta el correo electrónico a este dominio personalizado, el correo electrónico dejará de funcionar hasta que haya agregado el dominio a la nueva cuenta, configure el nuevo registro MX y configure los usuarios. Al quitar los registros DNS de Lync, Lync dejará de funcionar. Y después de quitar el registro CNAME que apunta a su sitio web público, no estará disponible.           [Quite el dominio](remove-a-domain.md) .  <br/> |
|Configure el dominio personalizado para la nueva suscripción y configure los usuarios.  <br/> | Configure la nueva suscripción, incluida la creación de los registros DNS necesarios para el dominio personalizado.  <br/>  Cree los usuarios con direcciones de correo electrónico en el dominio personalizado.  <br/> |
|Transferir datos de la suscripción anterior a la nueva.  <br/> | Inicie sesión en ambas cuentas en ventanas de explorador independientes:  <br/>  Haga clic con el botón derecho en el icono del explorador y abra dos ventanas del explorador privado. Puede usar credenciales diferentes en las dos ventanas para iniciar sesión en ambas cuentas.  <br/> [Transferencia de la configuración administrativa entre suscripciones](#email) <br/> [Transferencia de datos y estructura de sitio de equipo](#transfer-team-site-structure-and-data) <br/> [Transferencia de un sitio web público entre suscripciones](#transfer-a-public-website-between-subscriptions) <br/> [Transferencia de la configuración administrativa entre suscripciones](#email) <br/> |
|Cancele la suscripción del plan con el que ha terminado llamando a Soporte técnico de Microsoft para Microsoft 365.  <br/> | Compruebe que la nueva suscripción funciona y que se han transferido todos los datos.  <br/>  [Póngase en contacto con el servicio de atención al cliente](../../business-video/get-help-support.md) para cancelar la suscripción anterior.  <br/> |

## <a name="transfer-administrative-settings-between-subscriptions"></a>Transferencia de la configuración administrativa entre suscripciones

Vaya a las páginas siguientes de cada cuenta y configure la nueva cuenta en función de la configuración de la cuenta anterior.
  
Si va a transferir datos de Microsoft 365 a Microsoft 365 Mediana Empresa o Microsoft 365 Enterprise, las páginas de administración se estructuran de manera diferente. Vea un [vídeo: Introducción a Microsoft 365 Enterprise](../index.yml) y vaya a los siguientes lugares para ver la configuración del administrador.
  
Para Microsoft 365 Enterprise y Microsoft 365 Mediana Empresa:
  
|**Ubicación**|**Finalidad**|
|:-----|:-----|
| \> Administración **configuración del servicio** **microsoft 365** \> <br/> |Seleccione cada pestaña para la configuración de correo, sitios, Lync, software de usuario, contraseñas, comunidad, administración de derechos y dispositivos móviles.  <br/> |
| \> Administración **Exchange** <br/> | configuración de Exchange Online  <br/> |
| \> Administración **SharePoint** <br/> | Configuración de SharePoint Online  <br/> |
| \> **Administración Skype Empresarial** <br/> |Configuración de Skype Empresarial adicional  <br/> |

Para Microsoft 365 Small Business
  
|**Ubicación**|**Finalidad**|
|:-----|:-----|
| \> Administración **Administrar la configuración de toda la organización** <br/> |Configuración administrativa  <br/> |

## <a name="transfer-a-public-website-between-subscriptions"></a>Transferencia de un sitio web público entre suscripciones

Si tiene un sitio web público hospedado en Microsoft 365, debe guardarlo y volver a crearlo en su nueva suscripción.
  
> [!NOTE]
> Si el sitio web público está hospedado en un proveedor de hospedaje DNS, no se requieren cambios. No se verá afectado por la transición.
  
Para guardar una biblioteca de documentos o contenido de lista de un entorno de SharePoint Online en recursos compartidos de archivos o en un equipo local, consulte [Migración manual del contenido de SharePoint Online](/sharepoint/troubleshoot/migration-tool/content-manual-migration).
  
> [!NOTE]
> La aplicación de migración de sitios públicos no puede transferir datos a otra suscripción.
  
## <a name="transfer-team-site-structure-and-data"></a>Transferencia de datos y estructura de sitio de equipo

Hay varias maneras de guardar o transferir datos del sitio del equipo:
  
- Puede guardar el sitio anterior como una plantilla e importar la plantilla en el nuevo sitio.

- Para transferir documentos, vuelva a crear manualmente la jerarquía en el nuevo sitio. A continuación, puede abrir ambos sitios de grupo de SharePoint al mismo tiempo, abrir ambas bibliotecas de documentos con el Explorador de Windows y copiar y pegar los documentos. Vea [Vídeo: Copiar o mover archivos de biblioteca mediante Abrir con el Explorador](https://support.microsoft.com/office/d18d21a0-1f9f-4f6c-ac45-d52afa0a4a2e).

- Para transferir datos de lista, guarde una [plantilla de lista](https://support.microsoft.com/office/c3884ad1-bc49-44b8-b3d6-3bc6a01eb393) y use la plantilla guardada para volver a crear la lista en el nuevo sitio.

- Para guardar una biblioteca de documentos o contenido de lista de un entorno de SharePoint Online (OneDrive para la Empresa o sitios de equipo) en recursos compartidos de archivos o en un equipo local, vea [Información sobre la migración manual del contenido de SharePoint Online](/sharepoint/troubleshoot/migration-tool/content-manual-migration).

## <a name="transfer-users-data-between-subscriptions"></a>Transferencia de datos de usuarios entre suscripciones

### <a name="email"></a>Correo electrónico:

Pida a los usuarios que [muevan su correo electrónico, contactos, tareas e información de calendario](https://support.microsoft.com/office/0996ece3-57c6-49bc-977b-0d1892e2aacc) después de configurar la nueva suscripción. Pueden acceder a su correo electrónico antiguo mediante su nombre de usuario inicial, como sue@contoso.onmicrosoft.com.
  
### <a name="onedrive-for-business-data"></a>OneDrive para la Empresa datos:

Pida a los usuarios que [copien o sincronicen OneDrive para la Empresa contenido en su equipo](https://support.microsoft.com/office/59b1de2b-519e-4d3a-8f45-51647cf291cd) y, a continuación, vuelvan a agregarlo a su nueva suscripción.

### <a name="onenote"></a>OneNote 

Pida a los usuarios que [realicen una copia de seguridad de OneNote](https://support.microsoft.com/office/back-up-notes-f58b34b0-611d-435e-87fa-7942a1767af4?ui=en-us&rs=en-us&ad=us) y [que restauren las notas de una copia de seguridad](https://support.microsoft.com/en-us/office/restore-notes-from-a-backup-5daf9cb0-6769-4998-a5de-f044fdd0d831?ui=en-us&rs=en-us&ad=us) en sus nuevas suscripciones.
