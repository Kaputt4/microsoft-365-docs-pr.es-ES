---
title: Planeación de la configuración de Microsoft 365 para empresas
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
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: eb926624-018b-4486-bf11-5fba6ee4d645
description: Obtenga información sobre lo que necesita hacer para configurar su Microsoft 365 para empresas.
ms.openlocfilehash: 7509e2c4801adbca492e5f5446c5b97eae31dccf
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "44778954"
---
# <a name="plan-your-setup-of-microsoft-365-for-business"></a>Planeación de la configuración de Microsoft 365 para empresas

Este artículo está destinado a las personas que se han suscrito a un plan de 365 para la empresa de Microsoft.
  
Hay algunas cosas que debe tener en cuenta y la información que necesita tener a mano antes de mover la organización a Microsoft 365.
  
## <a name="info-to-have-on-hand-before-you-run-the-setup-wizard"></a>Información que debe tener a mano antes de ejecutar el Asistente de configuración

Cuando esté listo para ejecutar el Asistente de configuración y mover su dominio a Microsoft 365, esta es la información que necesitará tener a mano:
  
- Lista de personas que desea agregar a Microsoft 365. Incluso si ya los ha agregado a Microsoft 365, si está actualizando la información de dominio, debe escribir sus nombres aquí.

- Cómo vas a informar a los empleados de su identificador de usuario y contraseña para que puedan iniciar sesión. ¿Se va a llamar con la información? ¿O enviarla a su dirección de correo electrónico personal? No tendrán acceso a su correo electrónico, por lo que no podrá usarlo.

- Si tiene un nombre de dominio para su organización (como contoso.com) **y** planea usar el correo electrónico de Microsoft, tendrá que saber dónde está registrado su dominio y tener información de inicio de sesión.

## <a name="what-happens-when-you-run-the-microsoft-365-setup-wizard"></a>Qué sucede cuando se ejecuta el Asistente para la instalación de Microsoft 365

El Asistente para la instalación le guiará por la instalación de las aplicaciones de Microsoft 365 en el equipo, la adición y la comprobación del dominio, la adición de usuarios y la asignación de licencias a ellos, y la conexión del dominio.

> [!NOTE]
> Si necesita [asignar roles de administrador en Microsoft 365 para empresas](../add-users/assign-admin-roles.md) a los usuarios que ha agregado en el asistente, puede hacerlo más adelante en la página **usuarios** . 
  
Si no completa el Asistente para la instalación, puede completar las tareas de configuración en cualquier momento desde la instalación del [centro de administración](https://go.microsoft.com/fwlink/p/?linkid=2024339)  >  **Setup**. Desde aquí, puede migrar el correo electrónico y los contactos desde otro servicio de correo electrónico, cambiar el dominio de la cuenta de administrador, administrar la información de facturación, agregar o quitar usuarios, restablecer contraseñas y realizar otras funciones empresariales. Para obtener más información acerca de las diferencias entre el Asistente de configuración y la página de **configuración** , vea [diferencias entre el Asistente para instalación de Microsoft 365 y la página de configuración](o365-setup-wizard-and-setup-page.md).

Si tiene problemas con algún paso, comuníquese con nosotros. [Estamos aquí para ayudarle.](../contact-support-for-business-products.md)
  
## <a name="when-not-to-use-the-setup-wizard-active-directory-synchronization-and-hybrid-environments"></a>Cuándo no debería usar el asistente de configuración: Sincronización de Active Directory y entornos híbridos

Hay un par de escenarios que incluyen la migración de datos o de usuarios desde entornos locales o la configuración de un sistema híbrido que incluye la sincronización de directorios. Si se encuentran en cualquiera de las dos categorías, siga las instrucciones de estos artículos:
  
- Para configurar la sincronización de directorios con Active Directory local, consulte Configurar la [sincronización de directorios para Microsoft 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization)y para comprender los diferentes modelos de identidad de Microsoft 365, lea [understanding Microsoft 365 Identity y Azure Active Directory](https://docs.microsoft.com/office365/enterprise/about-office-365-identity).

- Para configurar un sistema híbrido de Exchange, en el siguiente vínculo encontrará el conjunto completo de instrucciones que le mostrarán todas las maneras de configurar un sistema híbrido de Exchange (incluida la configuración de registros DNS): [Asistente para la implementación de Microsoft Exchange Server](https://aka.ms/exdeploy)

- Para configurar un sistema híbrido de SharePoint, en especial las características de sitios y búsquedas híbridas, consulte [Búsquedas híbridas en SharePoint](https://docs.microsoft.com/SharePoint/hybrid/hybrid-search-in-sharepoint).

## <a name="move-to-microsoft-365-all-at-once-or-in-stages"></a>Migrar a Microsoft 365 todos a la vez o en fases

- **¿Desea mover su organización a Microsoft 365 todo a la vez?** Si es así, planea mover el dominio a Microsoft 365 inmediatamente. Para empezar, ejecute el Asistente para la instalación de Microsoft 365; le pedirá que configure su dominio.

- **¿Desea cambiar a Microsoft 365 gradualmente?** Si desea pasar a Microsoft 365 en fases, omita la ejecución del Asistente para la instalación de Microsoft 365 y considere la posibilidad de adoptar las características de Microsoft 365 en el orden siguiente:

    1. [Agregue sus empleados a Microsoft 365](../add-users/add-users.md) para que puedan descargar e instalar las aplicaciones de Office.

    2. [Descargar e instalar las aplicaciones de Office](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) para usar Word, Excel y PowerPoint en el equipo y los dispositivos.

    3. [Configure Microsoft Teams](#plan-for-teams) para que lo use para sus reuniones.

    4. [Mueva el contenido al almacenamiento en la nube de Microsoft 365](set-up-file-storage-and-sharing.md) (sitios de grupo de OneDrive o SharePoint).

    5. Cuando esté listo, en el [centro de administración](https://go.microsoft.com/fwlink/p/?linkid=2024339), seleccione **configurar** en el panel de navegación de la izquierda y use la página de **configuración** para [mover el dominio y el correo electrónico](add-domain.md).

## <a name="check-that-your-devices-meet-system-requirements"></a>Compruebe que los dispositivos cumplen los requisitos del sistema

Cada persona de su organización puede instalar el conjunto de aplicaciones de Office 2016 (Word, Excel, PowerPoint, etc.) en un máximo de cinco equipos PC y Mac. Consulte los requisitos de sistemas operativos y equipos para instalar [conjuntos de aplicaciones de Office 2016](https://go.microsoft.com/fwlink/?LinkId=534827) para la empresa.
  
Las aplicaciones móviles se pueden instalar en dispositivos iOS, Android y Windows. Puede encontrar información sobre la compatibilidad de dispositivos móviles y exploradores en [Requisitos del sistema para Office](https://go.microsoft.com/fwlink/?LinkId=534827).
  
## <a name="plan-for-email"></a>Plan para el correo electrónico

Si tiene previsto cambiar de un servicio de correo electrónico existente a Microsoft 365, normalmente tardará dos días en realizar el cambio.
  
### <a name="plan-for-email-downtime"></a>Plan de inactividad de correo electrónico
  
Si va a usar Microsoft 365 para su correo electrónico:
  
- Para mover la dirección de correo electrónico de la empresa (como *rob \@ contoso.com*) desde otro servicio de correo electrónico a Microsoft 365, debe dirigir el correo para que se entregue en el nuevo buzón de Microsoft 365. Para ello, seleccione **migrar los datos de los usuarios** en la página de **configuración** , donde le guiaremos a través de las actualizaciones que necesita realizar en su host de dominio, paso a paso.

- Después de actualizar el host de su dominio, los cambios suelen surtir efecto en solo una o dos horas. Pero tenga en cuenta que a veces puede pasar hasta 72 horas para que los cambios se actualicen en Internet.

- Como es posible que se haya producido un tiempo de inactividad de correo electrónico, le recomendamos que cambie a correo electrónico de Microsoft durante la noche o el fin de semana cuando reciba menos correos electrónicos.

### <a name="plan-to-move-your-existing-email-contacts-and-calendar"></a>Planificar el cambio del correo electrónico, contactos y calendario existentes
  
Si va a usar Microsoft 365 para su cuenta de correo electrónico, puede llevarse el correo electrónico, los contactos y el calendario existentes. La página de **configuración** ayuda a mover el correo electrónico y los contactos existentes en la mayoría de los escenarios. También disponemos de guías paso a paso para mover uno o varios buzones.
  
|**¿Cuántos buzones?**|**Recomendación**|
|:-----|:-----|
|Tan solo algunos  <br/> |Si no desea usar la página de **configuración** para migrar los buzones, puede dejar que los propietarios de buzones migren su propio correo electrónico y contactos. Consulte [migrar el correo electrónico y los contactos a Microsoft 365 para empresas](migrate-email-and-contacts-admin.md).  <br/> |
|Varios  <br/> |Si va a migrar desde Gmail, consulte [migrar buzones G Suite a Microsoft 365](https://docs.microsoft.com/Exchange/mailbox-migration/migrating-imap-mailboxes/migrate-g-suite-mailboxes).  <br/> Si va a migrar desde otro proveedor de correo electrónico, incluido Exchange, consulte [formas de migrar varias cuentas de correo electrónico a Microsoft 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).  <br/> |

## <a name="plan-for-file-storage-and-migration"></a>Plan de almacenamiento y migración de archivos

Microsoft 365 proporciona almacenamiento en la nube para particulares, pequeñas organizaciones y empresas. Para obtener instrucciones sobre qué almacenar donde, vea dónde [puede almacenar documentos en Microsoft 365](https://support.microsoft.com/office/c7c20284-bc94-47f4-9728-d28e9daf0790).
  
- **Puede mover cientos de archivos** a [OneDrive](https://support.microsoft.com/office/45114744-6D42-45CD-8975-F9617819BDEB) o a un [sitio de grupo de SharePoint](https://support.microsoft.com/office/da549fb1-1fcb-4167-87d0-4693e93cb7a0#__toc384119242). Puede cargar 100 archivos a la vez. Evite cargar archivos con un tamaño superior a 2 GB, el tamaño de archivo máximo predeterminado.
  
- **Si desea mover varios miles de archivos** a almacenamiento de Microsoft 365, revise los [límites de SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkID=856113). Le recomendamos que use una herramienta de migración o considere la posibilidad de contratar un [socio](https://go.microsoft.com/fwlink/?linkid=391089) para ayudarle con la migración. Para más información sobre cómo migrar un gran número de archivos, vea la [Guía del usuario de migración de OneDrive y SharePoint Online](https://go.microsoft.com/fwlink/?LinkId=723574).
  
## <a name="plan-for-teams"></a>Planeación de Microsoft Teams

Puede usar Microsoft Teams para realizar llamadas a otros usuarios de su organización que estén en su suscripción. Por ejemplo, si su organización tiene 10 personas, puede llamar y enviar un mensaje instantáneo mediante Teams sin necesidad de realizar ninguna configuración especial. Para obtener más información, consulte Introducción [a Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/get-started-with-teams-quick-start).

Para organizaciones más grandes o si empieza desde Skype empresarial, local o implementaciones híbridas, consulte [How to implemente Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/how-to-roll-out-teams).
  
## <a name="plan-for-integration-with-active-directory-or-other-software"></a>Plan de integración con Active Directory u otro software

- **¿Desea la integración con su entorno local de Active Directory?** Puede integrar su Active Directory local con Microsoft 365 mediante Azure Active Directory Connect. Para obtener instrucciones, consulte [configurar la sincronización de directorios para Microsoft 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization).
  
- **¿Desea integrar Microsoft 365 con software realizado por otras compañías?** Si necesita integrar Microsoft 365 con otro software en su organización, le recomendamos que considere la posibilidad de [contratar a un socio](https://go.microsoft.com/fwlink/?linkid=391089) para ayudarle con la implementación de.
  
## <a name="do-you-want-someone-to-help-you-set-up-microsoft-365"></a>¿Desea que alguien le ayude a configurar Microsoft 365?

- **Si tiene menos de 50 empleados:**

  - **Pida ayuda a y le llamaremos**. Después de comprar Microsoft 365, puede obtener acceso al centro de administración (no es necesario ejecutar el programa de instalación para acceder a él). En la parte inferior del centro de administración, seleccione **¿necesita ayuda?** Describa el problema y le llamaremos. 
  - **Llame al [soporte técnico de Microsoft 365 para empresas](../contact-support-for-business-products.md) con sus preguntas**. ¡Estamos aquí para ayudarle! 
  - **Considere la posibilidad de contratar un [partner de Microsoft](https://go.microsoft.com/fwlink/?linkid=391089)**. Si tiene poco tiempo o tiene requisitos avanzados (como mover miles de archivos a almacenamiento en la nube de Microsoft 365 o integrar con otro software), un asociado experimentado puede ser una gran ayuda. 

- **Si tiene más de 50 empleados**, el [Centro de integración FastTrack](https://go.microsoft.com/fwlink/?LinkId=517115) puede ayudarle con la implementación. 
