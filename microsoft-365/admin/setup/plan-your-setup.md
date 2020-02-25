---
title: Planear la configuración de Office 365 para empresas
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- MET150
- MOE150
ms.assetid: eb926624-018b-4486-bf11-5fba6ee4d645
description: Obtenga información sobre lo que necesita hacer para configurar su Office 365 para empresas.
ms.openlocfilehash: 3b38f0092b323175c6a12170105e781fab21934d
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42247841"
---
# <a name="plan-your-setup-of-office-365-for-business"></a>Planear la configuración de Office 365 para empresas

Este artículo es para las personas que se han suscrito a un plan de empresa de Office 365.
  
Hay algunas cosas que debe tener en cuenta y la información que necesita tener a mano antes de pasar la organización a Office 365.
  
## <a name="info-to-have-on-hand-before-you-run-the-office-365-setup-wizard"></a>Información que debe tener a mano antes de ejecutar el asistente de configuración de Office 365

Cuando esté listo para ejecutar al Asistente de configuración de Office 365 y mover su dominio a Office 365, debe tener a mano la siguiente información:
  
- Lista de usuarios que quiere agregar a Office 365. Aunque ya los haya agregado a Office 365, si va a actualizar la información de su dominio, deberá introducir sus nombres aquí.

- ¿Cómo va a notificar a sus empleados sus Id. de usuario de Office 365 y la contraseña para que pueden iniciar sesión? ¿Va a llamarles con la información? ¿O va a enviarla a su dirección de correo personal? No tendrán acceso a su correo electrónico de Office 365, por lo no lo pueden usar.

- Si tiene un nombre de dominio para su organización (como contoso.com) **y** planea usar el correo electrónico de Office 365, necesitará saber dónde está registrado su dominio y tiene información de inicio de sesión.

## <a name="what-happens-when-you-run-the-office-365-setup-wizard"></a>¿Qué ocurre al ejecutar el asistente de configuración de Office 365?

El Asistente para la instalación le guía por la instalación de las aplicaciones de Office 365 en el equipo, la adición y la comprobación del dominio, la adición de usuarios y la asignación de licencias a ellos, y la conexión del dominio.

> [!NOTE]
> Si necesita [asignar roles de administrador en Office 365 para empresas](../add-users/assign-admin-roles.md) a los usuarios que ha agregado en el asistente, puede hacerlo más adelante en la página **usuarios** . 
  
Si no completa el Asistente para la instalación, puede completar las tareas de configuración en cualquier momento desde la**instalación**del [Centro](https://go.microsoft.com/fwlink/p/?linkid=2024339) > de administración. Desde aquí, puede migrar el correo electrónico y los contactos desde otro servicio de correo electrónico, cambiar el dominio de la cuenta de administrador, administrar la información de facturación, agregar o quitar usuarios, restablecer contraseñas y realizar otras funciones empresariales. Para obtener más información acerca de las diferencias entre el Asistente para la instalación y la página **configuración** , consulte [diferencias entre el Asistente para instalación de Office 365 y la página Configuración](o365-setup-wizard-and-setup-page.md).

Si tiene problemas con algún paso, comuníquese con nosotros. [Estamos aquí para ayudarle.](../contact-support-for-business-products.md)
  
## <a name="when-not-to-use-the-setup-wizard-active-directory-synchronization-and-hybrid-environments"></a>Cuándo no debería usar el asistente de configuración: Sincronización de Active Directory y entornos híbridos

Hay un par de escenarios que incluyen la migración de datos o de usuarios desde entornos locales o la configuración de un sistema híbrido que incluye la sincronización de directorios. Si se encuentran en cualquiera de las dos categorías, siga las instrucciones de estos artículos:
  
- Para configurar la sincronización de directorios con Active Directory local, vea [Configurar la sincronización de directorios en Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization); para conocer los distintos modelos de identidad de Office 365, vea [Información acerca de la identidad de Office 365 y Azure Active Directory](https://docs.microsoft.com/office365/enterprise/about-office-365-identity).

- Para configurar un sistema híbrido de Exchange, en el siguiente vínculo encontrará el conjunto completo de instrucciones que le mostrarán todas las maneras de configurar un sistema híbrido de Exchange (incluida la configuración de registros DNS): [Asistente para la implementación de Microsoft Exchange Server](https://aka.ms/exdeploy)

- Para configurar un sistema híbrido de SharePoint, en especial las características de sitios y búsquedas híbridas, consulte [Búsquedas híbridas en SharePoint](https://docs.microsoft.com/SharePoint/hybrid/hybrid-search-in-sharepoint).

## <a name="move-to-office-365-all-at-once-or-in-stages"></a>Mover a Office 365 todo a la vez o en fases

- **¿Desea mover su organización a Office 365 todo a la vez?** Si es así, planee mover su dominio inmediatamente a Office 365. Para empezar, ejecute al Asistente de configuración de Office 365; se le pedirá que configure su dominio.

- **¿Desea cambiar a Office 365 gradualmente?** Si quiere mover a Office 365 por fases, omita la ejecución del Asistente de configuración de Office 365 y considere la posibilidad de adoptar las características de Office 365 en el siguiente orden:

    1. [Agregar sus empleados a Office 365](../add-users/add-users.md) para que puedan descargar e instalar las aplicaciones de Office.

    2. [Descargar e instalar las aplicaciones de Office](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658.aspx) para usar Word, Excel y PowerPoint en el equipo y los dispositivos.

    3. [Configure Microsoft Teams](#plan-for-teams) para que lo use para sus reuniones.

    4. [Mueva el contenido al almacenamiento en la nube de Office 365](set-up-file-storage-and-sharing.md) (sitios de grupo de OneDrive o SharePoint).

    5. Cuando esté listo, en el [centro de administración](https://go.microsoft.com/fwlink/p/?linkid=2024339), seleccione **configurar** en el panel de navegación de la izquierda y use la página de **configuración** para [mover el dominio y el correo electrónico](add-domain.md).

## <a name="check-that-your-devices-meet-system-requirements"></a>Compruebe que los dispositivos cumplen los requisitos del sistema

Cada persona de su organización puede instalar el conjunto de aplicaciones de Office 2016 (Word, Excel, PowerPoint, etc.) en un máximo de cinco equipos PC y Mac. Consulte los requisitos de sistemas operativos y equipos para instalar [conjuntos de aplicaciones de Office 2016](https://go.microsoft.com/fwlink/?LinkId=534827) para la empresa.
  
Las aplicaciones móviles se pueden instalar en dispositivos iOS, Android y Windows. Puede encontrar información sobre la compatibilidad de dispositivos móviles y exploradores en [Requisitos del sistema para Office](https://go.microsoft.com/fwlink/?LinkId=534827).
  
## <a name="plan-for-email"></a>Plan para el correo electrónico

Si tiene previsto cambiar de un servicio de correo electrónico existente a Office 365, normalmente tardará dos días en realizar el cambio.
  
### <a name="plan-for-email-downtime"></a>Plan de inactividad de correo electrónico
  
Si tiene pensado usar Office 365 para su correo electrónico:
  
- Para cambiar la dirección de correo electrónico de la empresa (como *Rob@contoso.com*) de otro servicio de correo electrónico a Office 365, debe dirigir el correo para que se entregue en el nuevo buzón de Office 365. Para ello, seleccione **migrar los datos de los usuarios** en la página de **configuración** , donde le guiaremos a través de las actualizaciones que necesita realizar en su host de dominio, paso a paso.

- Después de actualizar el host de su dominio, los cambios suelen surtir efecto en solo una o dos horas. Pero tenga en cuenta que a veces puede pasar hasta 72 horas para que los cambios se actualicen en Internet.

- Debido a la posibilidad de inactividad del correo, le recomendamos planificar el cambio a correo de Office 365 durante la noche o en fin de semana, cuando reciba menos correos electrónicos.

### <a name="plan-to-move-your-existing-email-contacts-and-calendar"></a>Planificar el cambio del correo electrónico, contactos y calendario existentes
  
Si va a usar Office 365 para su cuenta de correo, puede llevarse su correo, contactos y calendario existentes. La página de **configuración** ayuda a mover el correo electrónico y los contactos existentes en la mayoría de los escenarios. También disponemos de guías paso a paso para mover uno o varios buzones.
  
|**¿Cuántos buzones?**|**Recomendación**|
|:-----|:-----|
|Tan solo algunos  <br/> |Si no desea usar la página de **configuración** para migrar los buzones, puede dejar que los propietarios de buzones migren su propio correo electrónico y contactos. Vea [Migrar correo electrónico y contactos a Office 365 para empresas](migrate-email-and-contacts-admin.md).  <br/> |
|Varios  <br/> |Si va a migrar desde Gmail, vea [migrar buzones de G Suite a Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/migrating-imap-mailboxes/migrate-g-suite-mailboxes).  <br/> Si va a migrar desde otro proveedor de correo electrónico, incluido Exchange, consulte [formas de migrar varias cuentas de correo electrónico a Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).  <br/> |

## <a name="plan-for-file-storage-and-migration"></a>Plan de almacenamiento y migración de archivos

Office 365 proporciona almacenamiento en la nube para particulares, pequeñas organizaciones y empresas. Para obtener información sobre qué almacenar y dónde, consulte [Dónde puede almacenar documentos en Office 365](https://support.office.com/article/c7c20284-bc94-47f4-9728-d28e9daf0790.aspx).
  
- **Puede mover cientos de archivos** a [OneDrive](https://support.office.com/article/45114744-6D42-45CD-8975-F9617819BDEB.aspx) o a un [sitio de grupo de SharePoint](https://support.office.com/article/da549fb1-1fcb-4167-87d0-4693e93cb7a0.aspx#__toc384119242). Puede cargar 100 archivos a la vez. Evite cargar archivos con un tamaño superior a 2 GB, el tamaño de archivo máximo predeterminado.
  
- **Si quiere mover varios miles de archivos** al almacenamiento de Office 365, revise los [límites de SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkID=856113). Le recomendamos que use una herramienta de migración o considere la posibilidad de contratar un [socio](https://go.microsoft.com/fwlink/?linkid=391089) para ayudarle con la migración. Para más información sobre cómo migrar un gran número de archivos, vea la [Guía del usuario de migración de OneDrive y SharePoint Online](https://go.microsoft.com/fwlink/?LinkId=723574).
  
## <a name="plan-for-teams"></a>Planeación de Microsoft Teams

Puede usar Microsoft Teams para realizar llamadas a otros usuarios de su organización que estén en su suscripción. Por ejemplo, si su organización tiene 10 personas, puede llamar y enviar un mensaje instantáneo mediante Teams sin necesidad de realizar ninguna configuración especial. Para obtener más información, consulte Introducción [a Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/get-started-with-teams-quick-start).

Para organizaciones más grandes o si empieza desde Skype empresarial, local o implementaciones híbridas, consulte [How to implemente Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/how-to-roll-out-teams).
  
## <a name="plan-for-integration-with-active-directory-or-other-software"></a>Plan de integración con Active Directory u otro software

- **¿Desea la integración con su entorno local de Active Directory?** Puede integrar su Active Directory local con Office 365 utilizando Azure Active Directory Connect. Para ver las instrucciones, consulte [Configurar la sincronización de directorios en Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization).
  
- **Quiere integrar Office 365 con otro software de otras compañías?** Si necesita integrar Office 365 con otro software en su organización, le recomendamos que considere la posibilidad de [contratar a un socio](https://go.microsoft.com/fwlink/?linkid=391089) para ayudarle con la implementación.
  
## <a name="do-you-want-someone-to-help-you-set-up-office-365"></a>¿Quiere que alguien le ayude a configurar Office 365?

- **Si tiene menos de 50 empleados:**

  - **Pida ayuda a y le llamaremos**. Después de comprar Office 365, puede obtener acceso al centro de administración (no es necesario ejecutar el programa de instalación para obtener acceso a él). En la parte inferior del centro de administración, seleccione **¿necesita ayuda?** Describa el problema y le llamaremos. 
  - **Llame al [soporte técnico de Office 365 para empresas](../contact-support-for-business-products.md) con sus preguntas**. ¡Estamos aquí para ayudarle! 
  - **Considere la posibilidad de contratar un [partner de Microsoft](https://go.microsoft.com/fwlink/?linkid=391089)**. Si no dispone de mucho tiempo o tiene requisitos avanzados (como por ejemplo, mover miles de archivos al almacenamiento en la nube de Office 365 o la integración con otro software), un socio con experiencia puede ser de gran ayuda. 

- **Si tiene más de 50 empleados**, el [Centro de integración FastTrack](https://go.microsoft.com/fwlink/?LinkId=517115) puede ayudarle con la implementación. 
