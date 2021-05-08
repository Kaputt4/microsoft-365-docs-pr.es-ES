---
title: Planear la configuración de Microsoft 365 para empresas
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- MET150
- MOE150
ms.assetid: eb926624-018b-4486-bf11-5fba6ee4d645
description: Obtenga información sobre los requisitos y consideraciones para realizar el cambio a Microsoft 365 para empresas.
ms.openlocfilehash: ba97253beed1544d8f993a462559037a0a1a4281
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244508"
---
# <a name="plan-your-setup-of-microsoft-365-for-business"></a>Planear la configuración de Microsoft 365 para empresas

Este artículo está pensado para personas que se han suscrito a un plan Microsoft 365 para empresas.
  
Antes de mover la organización a Microsoft 365, hay requisitos que debes cumplir, información que necesitas tener a mano y decisiones que debes tomar.


  
## <a name="info-to-have-on-hand-before-you-run-the-setup-wizard"></a>Información que debe tener a mano antes de ejecutar el asistente de configuración

Cuando estés listo para ejecutar el asistente de configuración y mover tu dominio a Microsoft 365, esta es la información que tendrás que tener a mano:
  
- Lista de personas que desea agregar a Microsoft 365. Incluso si ya los ha agregado a Microsoft 365, si está actualizando la información del dominio, debe escribir sus nombres aquí.

- Cómo va a notificar a los empleados su id. de usuario y contraseña para que puedan iniciar sesión. ¿Vas a llamarlos con la información? ¿O enviarlo a su dirección de correo electrónico personal? No tendrán acceso a su correo electrónico, por lo que no se puede usar.

- Si tiene un nombre de dominio para su organización (como **contoso.com)** y planea usar el correo electrónico de Microsoft, deberá saber dónde está registrado el dominio y tener información de inicio de sesión.

## <a name="what-happens-when-you-run-the-microsoft-365-setup-wizard"></a>Qué sucede al ejecutar el asistente para Microsoft 365 instalación de archivos

El asistente de configuración le guiará a través de la instalación de las aplicaciones Microsoft 365 en el equipo, agregar y comprobar el dominio, agregar usuarios y asignarles licencias y conectar su dominio.

> [!NOTE]
> Si necesita asignar roles de administrador en [Microsoft 365](../add-users/assign-admin-roles.md) para empresas a los usuarios que agregue en el asistente, puede hacerlo más adelante en la **página** Usuarios. 
  
Si no completa el asistente para la instalación, puede completar las tareas de configuración en cualquier momento desde el Centro [de administración](https://go.microsoft.com/fwlink/p/?linkid=2024339)  >  **Configuración**. Desde aquí puede migrar el correo electrónico y los contactos desde otro servicio de correo electrónico, cambiar el dominio de su cuenta de administrador, administrar la información de facturación, agregar o quitar usuarios, restablecer contraseñas y realizar otras funciones empresariales. Para obtener más información acerca de  las diferencias entre el asistente para la instalación y la página De instalación, vea [Diferencias](o365-setup-wizard-and-setup-page.md)entre el asistente para Microsoft 365 instalación y la página Configuración .

Si tiene problemas con algún paso, comuníquese con nosotros. [Estamos aquí para ayudarle.](../contact-support-for-business-products.md)
  
## <a name="when-not-to-use-the-setup-wizard-active-directory-synchronization-and-hybrid-environments"></a>Cuándo no debería usar el asistente de configuración: Sincronización de Active Directory y entornos híbridos

Hay un par de escenarios que incluyen la migración de datos o usuarios desde entornos locales o la configuración de un sistema híbrido que incluye la sincronización de directorios. Si está en cualquiera de las categorías, siga las instrucciones de estos artículos:
  
- Para configurar la sincronización de directorios con su Active Directory local, vea Configurar la sincronización de directorios para [Microsoft 365](../../enterprise/set-up-directory-synchronization.md)y para comprender los diferentes modelos de identidad de Microsoft 365, lea [Understanding Microsoft 365 identity and Azure Active Directory](../../enterprise/about-microsoft-365-identity.md).

- Para configurar un sistema híbrido de Exchange, en el siguiente vínculo encontrará el conjunto completo de instrucciones que le mostrarán todas las maneras de configurar un sistema híbrido de Exchange (incluida la configuración de registros DNS): [Asistente para la implementación de Microsoft Exchange Server](/exchange/exchange-deployment-assistant)

- Para configurar un sistema híbrido de SharePoint, en especial las características de sitios y búsquedas híbridas, consulte [Búsquedas híbridas en SharePoint](/SharePoint/hybrid/hybrid-search-in-sharepoint).

## <a name="move-to-microsoft-365-all-at-once-or-in-stages"></a>Pasar a Microsoft 365 a la vez o en fases

- **¿Desea mover su organización a Microsoft 365 a la vez?** Si es así, planea mover el dominio a Microsoft 365 inmediato. Comience ejecutando el asistente para Microsoft 365 instalación; le pedirá que configure su dominio.

- **¿Desea pasar a Microsoft 365 gradualmente?** Si desea pasar a Microsoft 365 fases, omita la ejecución del asistente para la instalación de Microsoft 365 y considere la posibilidad de adoptar Microsoft 365 características en el siguiente orden:

    1. [Agrega a tus empleados Microsoft 365](../add-users/add-users.md) para que puedan descargar e instalar las Office aplicaciones.

    2. [Descargar e instalar las aplicaciones de Office](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) para usar Word, Excel y PowerPoint en el equipo y los dispositivos.

    3. [Configure los Microsoft Teams](#plan-for-teams) usar para las reuniones.

    4. [Mueva el contenido a Microsoft 365 almacenamiento en la](set-up-file-storage-and-sharing.md) nube (OneDrive o SharePoint de grupo).

    5. Cuando esté listo, en el Centro  de [administración,](https://go.microsoft.com/fwlink/p/?linkid=2024339)seleccione Configurar  en el panel de navegación izquierdo y use la página Configuración para mover el dominio y [el correo electrónico.](add-domain.md)

## <a name="check-that-your-devices-meet-system-requirements"></a>Compruebe que los dispositivos cumplen los requisitos del sistema

Cada persona de la organización puede instalar el conjunto de aplicaciones de Office 2016 (Word, Excel, PowerPoint, y así sucesivamente) en hasta cinco equipos PC y Mac. Consulte los requisitos de sistemas operativos y equipos para instalar [conjuntos de aplicaciones de Office 2016](https://go.microsoft.com/fwlink/?LinkId=534827) para la empresa.
  
Las aplicaciones móviles se pueden instalar en dispositivos iOS, Android y Windows móviles. Puede encontrar información sobre la compatibilidad de dispositivos móviles y exploradores en [Requisitos del sistema para Office](https://go.microsoft.com/fwlink/?LinkId=534827).
  
## <a name="plan-for-email"></a>Plan para el correo electrónico

Si está planeando pasar de un servicio de correo electrónico existente a Microsoft 365, normalmente tarda dos días en realizar el cambio.
  
### <a name="plan-for-email-downtime"></a>Plan de inactividad de correo electrónico
  
Si vas a usar el Microsoft 365 para el correo electrónico:
  
- Para mover la dirección de correo electrónico de su empresa (como robar *\@ contoso.com*) de otro servicio de correo electrónico a Microsoft 365, debe dirigir el correo para que se entregue a su nuevo buzón Microsoft 365 correo electrónico. Para ello, seleccione  Migrar los datos  de los usuarios en la página Configuración, donde le guiaremos a través de las actualizaciones que necesita realizar en el host de su dominio, paso a paso.

- Después de actualizar el host de su dominio, los cambios suelen surtir efecto en solo una o dos horas. Pero ten en cuenta que, a veces, los cambios pueden tardar hasta 72 horas en actualizarse a través de Internet.

- Dado que es posible que tenga tiempo de inactividad del correo electrónico, le recomendamos que planee cambiar al correo electrónico de Microsoft durante una noche o un fin de semana cuando reciba menos correos electrónicos.

### <a name="plan-to-move-your-existing-email-contacts-and-calendar"></a>Planificar el cambio del correo electrónico, contactos y calendario existentes
  
Si vas a usar Microsoft 365 para tu cuenta de correo electrónico, puedes traer el correo electrónico, los contactos y el calendario existentes. La **página Configuración** le ayuda a mover el correo electrónico y los contactos existentes para la mayoría de los escenarios. También disponemos de guías paso a paso para mover uno o varios buzones.
  
|**¿Cuántos buzones?**|**Recomendación**|
|:-----|:-----|
|Tan solo algunos  <br/> |Si no desea usar la  página de instalación para migrar los buzones, puede permitir que los propietarios de buzones migren su propio correo electrónico y contactos. Vea [Migrar correo electrónico y contactos a Microsoft 365 para empresas.](migrate-email-and-contacts-admin.md)  <br/> |
|Varios  <br/> |Si estás migrando desde Gmail, consulta Migrar buzones [de G Suite a Microsoft 365](/Exchange/mailbox-migration/migrating-imap-mailboxes/migrate-g-suite-mailboxes).  <br/> Si está migrando desde otro proveedor de correo electrónico, incluido Exchange, vea Formas de migrar varias cuentas de correo electrónico a [Microsoft 365](/Exchange/mailbox-migration/mailbox-migration).  <br/> |

## <a name="plan-for-file-storage-and-migration"></a>Plan de almacenamiento y migración de archivos

Microsoft 365 proporciona almacenamiento en la nube para individuos, pequeñas organizaciones y empresas. Para obtener instrucciones sobre cómo almacenar dónde, vea [Where you can store documents in Microsoft 365](../../business-video/store-files.md).
  
- **Puede mover cientos de archivos a** [OneDrive](https://support.microsoft.com/office/45114744-6D42-45CD-8975-F9617819BDEB) o a un SharePoint [de grupo](https://support.microsoft.com/office/da549fb1-1fcb-4167-87d0-4693e93cb7a0#__toc384119242). Puede cargar 100 archivos a la vez. Evite cargar archivos con un tamaño superior a 2 GB, el tamaño de archivo máximo predeterminado.
  
- **Si desea mover varios miles de archivos** a Microsoft 365 almacenamiento, revise el SharePoint Online [Limits](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits). Le recomendamos que use una herramienta de migración o considere la posibilidad de contratar un [socio](https://go.microsoft.com/fwlink/?linkid=391089) para ayudarle con la migración. Para más información sobre cómo migrar un gran número de archivos, vea la [Guía del usuario de migración de OneDrive y SharePoint Online](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets).
  
## <a name="plan-for-teams"></a>Planeación de Teams

Puedes usar Microsoft Teams para realizar llamadas a otras personas de la organización que estén en tu suscripción. Por ejemplo, si su organización tiene 10 personas, puede llamarse y mensajería instantánea entre sí Teams sin ninguna configuración especial. Para obtener más información, vea [Introducción a Microsoft Teams](/MicrosoftTeams/get-started-with-teams-quick-start).

Para organizaciones más grandes o si está empezando desde implementaciones Skype Empresarial, locales o híbridas, vea How [to roll out Microsoft Teams](/MicrosoftTeams/how-to-roll-out-teams).
  
## <a name="plan-for-integration-with-active-directory-or-other-software"></a>Plan de integración con Active Directory u otro software

- **¿Desea la integración con su entorno local de Active Directory?** Puede integrar su Active Directory local con Microsoft 365 mediante Azure Active Directory Conectar. Para obtener instrucciones, vea [Configurar la sincronización de directorios para Microsoft 365](../../enterprise/set-up-directory-synchronization.md).
  
- **¿Desea integrar Microsoft 365 software creado por otras empresas?** Si necesita integrar Microsoft 365 con otro software de su organización, le recomendamos que considere la posibilidad de contratar [un partner](https://go.microsoft.com/fwlink/?linkid=391089) para ayudarle con la implementación.
  
## <a name="do-you-want-someone-to-help-you-set-up-microsoft-365"></a>¿Desea que alguien le ayude a configurar Microsoft 365?

- **Si tiene menos de 50 empleados:**

  - **Pida ayuda a y le llamaremos**. Después de comprar Microsoft 365, puede acceder al Centro de administración (no es necesario ejecutar el programa de instalación para llegar a él). En la parte inferior del centro de administración, seleccione **¿Necesita ayuda?** Describa el problema y le llamaremos. 
  - **Llame [Microsoft 365 soporte técnico para empresas](../contact-support-for-business-products.md) con sus preguntas**. ¡Estamos aquí para ayudarle! 
  - **Considere la posibilidad de contratar un [partner de Microsoft](https://go.microsoft.com/fwlink/?linkid=391089)**. Si tiene poco tiempo o tiene requisitos avanzados (como mover miles de archivos Microsoft 365 un almacenamiento en la nube o integrarse con otro software), un partner experimentado puede ser una gran ayuda. 

- **Si tiene más de 50 empleados**, el [Centro de integración FastTrack](https://go.microsoft.com/fwlink/?LinkId=517115) puede ayudarle con la implementación.