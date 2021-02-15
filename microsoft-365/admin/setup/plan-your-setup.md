---
title: Planear la configuración de Microsoft 365 para empresas
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
ms.openlocfilehash: 9158ad5a56b78fd8173ae81a2e9e4a5bd51633ca
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926827"
---
# <a name="plan-your-setup-of-microsoft-365-for-business"></a>Planear la configuración de Microsoft 365 para empresas

Este artículo está pensado para personas que se han suscrito a un plan de Microsoft 365 para empresas.
  
Antes de mover su organización a Microsoft 365, hay requisitos que debe cumplir, información que necesita tener a mano y decisiones que debe tomar.


  
## <a name="info-to-have-on-hand-before-you-run-the-setup-wizard"></a>Información que se debe tener a mano antes de ejecutar el asistente de configuración

Cuando estés listo para ejecutar el asistente para instalación y mover tu dominio a Microsoft 365, esta es la información que necesitarás tener a mano:
  
- Lista de personas que desea agregar a Microsoft 365. Incluso si ya los ha agregado a Microsoft 365, si va a actualizar la información del dominio, debe escribir sus nombres aquí.

- Cómo va a notificar a los empleados su id. de usuario y contraseña para que puedan iniciar sesión. ¿Vas a llamarlos con la información? ¿O enviarlo a su dirección de correo electrónico personal? No tendrán acceso a su correo electrónico, por lo que no podrá usarlo.

- Si tiene un nombre de dominio para su organización (como **contoso.com)** y tiene previsto usar el correo electrónico de Microsoft, deberá saber dónde está registrado su dominio y tener información de inicio de sesión.

## <a name="what-happens-when-you-run-the-microsoft-365-setup-wizard"></a>Qué sucede al ejecutar el Asistente para instalación de Microsoft 365

El asistente de configuración le guiará a través de la instalación de las aplicaciones de Microsoft 365 en el equipo, la adición y comprobación de su dominio, la adición de usuarios y la asignación de licencias a ellos, y la conexión de su dominio.

> [!NOTE]
> Si necesita asignar roles de administrador en [Microsoft 365](../add-users/assign-admin-roles.md) para empresas a los usuarios que agregue en el asistente, puede hacerlo más adelante en la página **Usuarios.** 
  
Si no completa el asistente para la instalación, puede completar las tareas de configuración en cualquier momento desde el programa [de instalación del centro de](https://go.microsoft.com/fwlink/p/?linkid=2024339)  >  **administración.** Desde aquí, puede migrar el correo electrónico y los contactos desde otro servicio de correo electrónico, cambiar el dominio de su cuenta de administrador, administrar la información de facturación, agregar o quitar usuarios, restablecer contraseñas y realizar otras funciones empresariales. Para obtener más información acerca de  las diferencias entre el Asistente para instalación y la página Instalación, vea Diferencias entre el Asistente para instalación de [Microsoft 365 y la página Instalación.](o365-setup-wizard-and-setup-page.md)

Si tiene problemas con algún paso, comuníquese con nosotros. [Estamos aquí para ayudarle.](../contact-support-for-business-products.md)
  
## <a name="when-not-to-use-the-setup-wizard-active-directory-synchronization-and-hybrid-environments"></a>Cuándo no debería usar el asistente de configuración: Sincronización de Active Directory y entornos híbridos

Hay un par de escenarios que incluyen la migración de datos o usuarios desde entornos locales o la configuración de un sistema híbrido que incluye la sincronización de directorios. Si está en cualquiera de las categorías, siga las instrucciones de estos artículos:
  
- Para configurar la sincronización de directorios con su Active Directory local, consulte Configurar la sincronización de directorios para [Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)y para comprender los diferentes modelos de identidad de Microsoft 365, lea Descripción de la identidad de [Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/about-microsoft-365-identity)y Azure Active Directory.

- Para configurar un sistema híbrido de Exchange, en el siguiente vínculo encontrará el conjunto completo de instrucciones que le mostrarán todas las maneras de configurar un sistema híbrido de Exchange (incluida la configuración de registros DNS): [Asistente para la implementación de Microsoft Exchange Server](https://aka.ms/exdeploy)

- Para configurar un sistema híbrido de SharePoint, en especial las características de sitios y búsquedas híbridas, consulte [Búsquedas híbridas en SharePoint](https://docs.microsoft.com/SharePoint/hybrid/hybrid-search-in-sharepoint).

## <a name="move-to-microsoft-365-all-at-once-or-in-stages"></a>Cambiar a Microsoft 365 a la vez o por fases

- **¿Desea mover su organización a Microsoft 365 a la vez?** Si es así, planee mover su dominio a Microsoft 365 inmediatamente. Comience ejecutando el Asistente para instalación de Microsoft 365; le pedirá que configure su dominio.

- **¿Desea pasar a Microsoft 365 gradualmente?** Si desea pasar a Microsoft 365 por fases, omita la ejecución del Asistente para instalación de Microsoft 365 y considere la posibilidad de adoptar las características de Microsoft 365 en el orden siguiente:

    1. [Agregue los empleados a Microsoft 365](../add-users/add-users.md) para que puedan descargar e instalar las aplicaciones de Office.

    2. [Descargar e instalar las aplicaciones de Office](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) para usar Word, Excel y PowerPoint en el equipo y los dispositivos.

    3. [Configurar Microsoft Teams para](#plan-for-teams) usarlo en las reuniones.

    4. [Mueva el contenido al almacenamiento en la nube de Microsoft 365](set-up-file-storage-and-sharing.md) (sitios de grupo de OneDrive o SharePoint).

    5. Cuando esté listo, en el centro  de [administración,](https://go.microsoft.com/fwlink/p/?linkid=2024339)seleccione El  programa de instalación en el panel de navegación izquierdo y use la página De instalación para mover el dominio y [el correo electrónico.](add-domain.md)

## <a name="check-that-your-devices-meet-system-requirements"></a>Compruebe que los dispositivos cumplen los requisitos del sistema

Cada persona de su organización puede instalar el conjunto de aplicaciones de Office 2016 (Word, Excel, PowerPoint, entre otros) en hasta cinco equipos PC y Mac. Consulte los requisitos de sistemas operativos y equipos para instalar [conjuntos de aplicaciones de Office 2016](https://go.microsoft.com/fwlink/?LinkId=534827) para la empresa.
  
Las aplicaciones móviles se pueden instalar en dispositivos iOS, Android y Windows. Puede encontrar información sobre la compatibilidad de dispositivos móviles y exploradores en [Requisitos del sistema para Office](https://go.microsoft.com/fwlink/?LinkId=534827).
  
## <a name="plan-for-email"></a>Plan para el correo electrónico

Si tiene previsto pasar de un servicio de correo electrónico existente a Microsoft 365, normalmente se necesitan dos días para realizar el cambio.
  
### <a name="plan-for-email-downtime"></a>Plan de inactividad de correo electrónico
  
Si va a usar Microsoft 365 para su correo electrónico:
  
- Para mover la dirección de correo electrónico de su empresa (como *Rob \@ contoso.com)* de otro servicio de correo electrónico a Microsoft 365, debe dirigir el correo para que se entregue a su nuevo buzón de Microsoft 365. Para ello, seleccione  Migrar los datos  de los usuarios en la página de instalación, donde le guiaremos paso a paso a través de las actualizaciones que necesita realizar en el host de dominio.

- Después de actualizar el host de su dominio, los cambios suelen surtir efecto en solo una o dos horas. Pero tenga en cuenta que a veces los cambios pueden tardar hasta 72 horas en actualizarse a través de Internet.

- Dado que es posible que tenga tiempo de inactividad de correo electrónico, le recomendamos que planee cambiar al correo electrónico de Microsoft durante una tarde o fin de semana cuando reciba menos correos electrónicos.

### <a name="plan-to-move-your-existing-email-contacts-and-calendar"></a>Planificar el cambio del correo electrónico, contactos y calendario existentes
  
Si va a usar Microsoft 365 para su cuenta de correo electrónico, puede traer el correo electrónico, los contactos y el calendario existentes. La **página de** instalación le ayuda a mover el correo electrónico y los contactos existentes para la mayoría de los escenarios. También disponemos de guías paso a paso para mover uno o varios buzones.
  
|**¿Cuántos buzones?**|**Recomendación**|
|:-----|:-----|
|Tan solo algunos  <br/> |Si no desea usar la  página de instalación para migrar los buzones, puede permitir que los propietarios de buzones migren su propio correo electrónico y contactos. Vea [Migrar el correo electrónico y los contactos a Microsoft 365 para empresas.](migrate-email-and-contacts-admin.md)  <br/> |
|Varios  <br/> |Si va a migrar desde Gmail, consulte Migrar buzones de [G Suite a Microsoft 365.](https://docs.microsoft.com/Exchange/mailbox-migration/migrating-imap-mailboxes/migrate-g-suite-mailboxes)  <br/> Si está migrando desde otro proveedor de correo electrónico, incluido Exchange, vea Formas de migrar varias cuentas de correo electrónico [a Microsoft 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).  <br/> |

## <a name="plan-for-file-storage-and-migration"></a>Plan de almacenamiento y migración de archivos

Microsoft 365 proporciona almacenamiento en la nube para personas, pequeñas organizaciones y empresas. Para obtener instrucciones sobre qué almacenar, consulte [Dónde puede almacenar documentos en Microsoft 365](https://support.microsoft.com/office/c7c20284-bc94-47f4-9728-d28e9daf0790).
  
- **Puede mover cientos de archivos** a [OneDrive](https://support.microsoft.com/office/45114744-6D42-45CD-8975-F9617819BDEB) o a un sitio [de grupo de SharePoint.](https://support.microsoft.com/office/da549fb1-1fcb-4167-87d0-4693e93cb7a0#__toc384119242) Puede cargar 100 archivos a la vez. Evite cargar archivos con un tamaño superior a 2 GB, el tamaño de archivo máximo predeterminado.
  
- **Si desea mover varios miles de archivos** al almacenamiento de Microsoft 365, revise los límites de [SharePoint Online.](https://go.microsoft.com/fwlink/p/?LinkID=856113) Le recomendamos que use una herramienta de migración o considere la posibilidad de contratar un [socio](https://go.microsoft.com/fwlink/?linkid=391089) para ayudarle con la migración. Para más información sobre cómo migrar un gran número de archivos, vea la [Guía del usuario de migración de OneDrive y SharePoint Online](https://go.microsoft.com/fwlink/?LinkId=723574).
  
## <a name="plan-for-teams"></a>Planeación de Teams

Puede usar Microsoft Teams para realizar llamadas a otras personas de su organización que estén en su suscripción. Por ejemplo, si su organización tiene 10 personas, puede llamar y mensajería instantánea entre sí usando Teams sin ninguna configuración especial. Para obtener más información, consulte [Introducción a Microsoft Teams.](https://docs.microsoft.com/MicrosoftTeams/get-started-with-teams-quick-start)

For larger organizations or if you're starting from Skype for Business, on-premises, or hybrid deployments, see [How to roll out Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/how-to-roll-out-teams).
  
## <a name="plan-for-integration-with-active-directory-or-other-software"></a>Plan de integración con Active Directory u otro software

- **¿Desea la integración con su entorno local de Active Directory?** Puede integrar su Active Directory local con Microsoft 365 con Azure Active Directory Connect. Para obtener instrucciones, [consulte Configurar la sincronización de directorios para Microsoft 365.](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)
  
- **¿Desea integrar Microsoft 365 con software creado por otras empresas?** Si necesita integrar Microsoft 365 con otro software de su organización, le recomendamos que considere la posibilidad de contratar [un partner](https://go.microsoft.com/fwlink/?linkid=391089) para ayudarle con su implementación.
  
## <a name="do-you-want-someone-to-help-you-set-up-microsoft-365"></a>¿Desea que alguien le ayude a configurar Microsoft 365?

- **Si tiene menos de 50 empleados:**

  - **Pida ayuda a y le llamaremos**. Después de comprar Microsoft 365, puede acceder al Centro de administración (no es necesario ejecutar el programa de instalación para acceder a él). En la parte inferior del centro de administración, seleccione **¿Necesita ayuda?** Describa el problema y le llamaremos. 
  - **Llame [al soporte técnico de Microsoft 365 para](../contact-support-for-business-products.md) empresas con sus preguntas.** ¡Estamos aquí para ayudarle! 
  - **Considere la posibilidad de contratar un [partner de Microsoft](https://go.microsoft.com/fwlink/?linkid=391089)**. Si tiene poco tiempo o tiene requisitos avanzados (como mover miles de archivos al almacenamiento en la nube de Microsoft 365 o integrarse con otro software), un partner experimentado puede ser de gran ayuda. 

- **Si tiene más de 50 empleados**, el [Centro de integración FastTrack](https://go.microsoft.com/fwlink/?LinkId=517115) puede ayudarle con la implementación. 
