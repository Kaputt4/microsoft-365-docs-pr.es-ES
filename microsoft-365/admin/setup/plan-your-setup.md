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
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_O365_Setup
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- MET150
- MOE150
ms.assetid: eb926624-018b-4486-bf11-5fba6ee4d645
description: Obtenga información sobre los requisitos y consideraciones para realizar el cambio a Microsoft 365 para empresas.
ms.openlocfilehash: a5f777a411f82de30c1d7dc69f07f92eadbbedce
ms.sourcegitcommit: 7dc7e9fd76adf848f941919f86ca25eecc704015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2022
ms.locfileid: "65317480"
---
# <a name="plan-your-setup-of-microsoft-365-for-business"></a>Planear la configuración de Microsoft 365 para empresas

Este artículo está destinado a las personas que se han suscrito a un Microsoft 365 para un plan de negocio.
  
Antes de mover la organización a Microsoft 365, hay requisitos que debe cumplir, información que debe tener a mano y decisiones que debe tomar.

## <a name="overview-of-microsoft-365-for-business-setup"></a>Introducción a Microsoft 365 para la configuración empresarial

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Vjso?autoplay=false]

¡Enhorabuena por su decisión de trasladar su negocio a la nube con Microsoft 365! Tanto si tiene una persona en su empresa como si tiene 20, hacer un poco de planeamiento le ayudará a sacar el máximo partido a Microsoft 365 para empresas.

## <a name="info-to-have-on-hand-before-you-run-the-setup-wizard"></a>Información que se debe tener a mano antes de ejecutar el asistente para la instalación

Cuando esté listo para ejecutar el asistente para la instalación y mover el dominio a Microsoft 365, esta es la información que necesitará tener a mano:
  
- Lista de personas que desea agregar a Microsoft 365. Incluso si ya los ha agregado a Microsoft 365, si va a actualizar la información de dominio, debe escribir sus nombres aquí.

- Cómo va a notificar a los empleados su id. de usuario y contraseña para que puedan iniciar sesión. ¿Vas a llamarlos con la información? ¿O enviarla a su dirección de correo electrónico personal? No tendrán acceso a su correo electrónico, por lo que no puede usarlo.

- Si tiene un nombre de dominio para su organización (por ejemplo, contoso.com) **y** planea usar el correo electrónico de Microsoft, deberá saber dónde está registrado el dominio y tener información de inicio de sesión.

## <a name="what-happens-when-you-run-the-microsoft-365-setup-wizard"></a>¿Qué ocurre al ejecutar el asistente para la instalación de Microsoft 365?

El asistente para la instalación le guiará a través de la instalación de las aplicaciones de Microsoft 365 en el equipo, la adición y comprobación del dominio, la adición de usuarios y la asignación de licencias a ellas y la conexión del dominio.

> [!NOTE]
> Si necesita [asignar roles de administrador en Microsoft 365 para empresas](../add-users/assign-admin-roles.md) a los usuarios que agregue en el asistente, puede hacerlo más adelante en la página **Usuarios**. 
  
Si no completa el asistente para la instalación, puede completar las tareas de instalación en cualquier momento desde [el centro](https://go.microsoft.com/fwlink/p/?linkid=2024339) >  de **administraciónSetup**. Desde aquí puede migrar el correo electrónico y los contactos de otro servicio de correo electrónico, cambiar el dominio de la cuenta de administrador, administrar la información de facturación, agregar o quitar usuarios, restablecer contraseñas y realizar otras funciones empresariales. Para obtener más información sobre las diferencias entre el asistente para la instalación y la página **Configuración**, vea [Diferencias entre el asistente para la instalación de Microsoft 365 y la página Configuración](o365-setup-wizard-and-setup-page.md).

Si tiene problemas con algún paso, comuníquese con nosotros. [¡Estamos aquí para ayudar!](../../business-video/get-help-support.md).
  
## <a name="when-not-to-use-the-setup-wizard-active-directory-synchronization-and-hybrid-environments"></a>Cuándo no debería usar el asistente de configuración: Sincronización de Active Directory y entornos híbridos

Hay un par de escenarios que incluyen la migración de datos o usuarios desde entornos locales o la configuración de un sistema híbrido que incluye la sincronización de directorios. Si está en cualquiera de las categorías, siga las instrucciones de estos artículos:
  
- Para configurar la sincronización de directorios con el Active Directory local, consulte Configuración de la [sincronización de directorios para Microsoft 365](../../enterprise/set-up-directory-synchronization.md) y, para comprender los distintos modelos de identidad de Microsoft 365, consulte [Implementación de la infraestructura de identidad para Microsoft 365](../../enterprise/deploy-identity-solution-overview.md).

- Para configurar un Exchange híbrido, puede encontrar aquí el conjunto completo de instrucciones que le guiarán por todas las distintas formas de configurar un intercambio híbrido (incluida la configuración de registros DNS): [Exchange Server Deployment Assistant](/exchange/exchange-deployment-assistant)

- Para configurar un sistema híbrido de SharePoint, en especial las características de sitios y búsquedas híbridas, consulte [Búsquedas híbridas en SharePoint](/SharePoint/hybrid/hybrid-search-in-sharepoint).

## <a name="move-to-microsoft-365-all-at-once-or-in-stages"></a>Mover a Microsoft 365 todo a la vez o en fases

- **¿Desea mover su organización a Microsoft 365 todo a la vez?** Si es así, planea mover tu dominio a Microsoft 365 de inmediato. Para empezar, ejecute el asistente para la instalación de Microsoft 365; le pedirá que configure el dominio.

- **¿Desea pasar a Microsoft 365 gradualmente?** Si desea pasar a Microsoft 365 en fases, omita la ejecución del asistente de configuración de Microsoft 365 y considere la posibilidad de adoptar características Microsoft 365 en el orden siguiente:

    1. [Agregue los empleados a Microsoft 365](../add-users/add-users.md) para que puedan descargar e instalar las aplicaciones de Office.

    2. [Descargar e instalar las aplicaciones de Office](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) para usar Word, Excel y PowerPoint en el equipo y los dispositivos.

    3. [Configure Microsoft Teams](#plan-for-teams) para usarlas en las reuniones.

    4. [Mueva el contenido a Microsoft 365 almacenamiento en la nube](set-up-file-storage-and-sharing.md) (OneDrive o SharePoint sitios de equipo).

    5. Cuando esté listo, en el Centro de [administración](https://go.microsoft.com/fwlink/p/?linkid=2024339), seleccione **Configurar** en el panel de navegación izquierdo y use la página **Configuración** para [mover el dominio y el correo electrónico](add-domain.md).

## <a name="check-that-your-devices-meet-system-requirements"></a>Compruebe que los dispositivos cumplen los requisitos del sistema

Cada persona de su organización puede instalar el conjunto de aplicaciones de Office 2016 (Word, Excel, PowerPoint, etc.) en un máximo de cinco EQUIPOS y Mac. Consulte los requisitos de sistemas operativos y equipos para instalar [conjuntos de aplicaciones de Office 2016](https://go.microsoft.com/fwlink/?LinkId=534827) para la empresa.
  
Las aplicaciones móviles se pueden instalar en dispositivos iOS, Android y Windows. Puede encontrar información sobre la compatibilidad de dispositivos móviles y exploradores en [Requisitos del sistema para Office](https://go.microsoft.com/fwlink/?LinkId=534827).
  
## <a name="plan-for-email"></a>Plan para el correo electrónico

Si planea pasar de un servicio de correo electrónico existente a Microsoft 365, normalmente tarda dos días en realizar el cambio.
  
### <a name="plan-for-email-downtime"></a>Plan de inactividad de correo electrónico
  
Si va a usar Microsoft 365 para su correo electrónico:
  
- Para mover la dirección de correo electrónico de su empresa (como *rob\@ contoso.com*) de otro servicio de correo electrónico a Microsoft 365, debe dirigir el correo electrónico para que se entregue al nuevo buzón de Microsoft 365. Para ello, seleccione **Migrar los datos de los usuarios** en la página **Configuración** , donde le guiaremos a través de las actualizaciones que necesita realizar en el host de dominio, paso a paso.

- Después de actualizar el host de su dominio, los cambios suelen surtir efecto en solo una o dos horas. Pero tenga en cuenta que a veces los cambios pueden tardar hasta 72 horas en actualizarse a través de Internet.

- Dado que es posible que tenga tiempo de inactividad de correo electrónico, se recomienda cambiar al correo electrónico de Microsoft durante una noche o fin de semana cuando reciba menos correos electrónicos.

### <a name="plan-to-move-your-existing-email-contacts-and-calendar"></a>Planificar el cambio del correo electrónico, contactos y calendario existentes
  
Si va a usar Microsoft 365 para su cuenta de correo electrónico, puede traer su correo electrónico, contactos y calendario existentes con usted. La página **Configuración** le ayuda a mover el correo electrónico y los contactos existentes para la mayoría de los escenarios. También disponemos de guías paso a paso para mover uno o varios buzones.
  
|**¿Cuántos buzones?**|**Recomendación**|
|:-----|:-----|
|Tan solo algunos  <br/> |Si no desea usar la página **De instalación** para migrar los buzones, puede permitir que los propietarios de los buzones migren sus propios contactos y correo electrónico. Consulte [Migración de correo electrónico y contactos a Microsoft 365 para empresas](migrate-email-and-contacts-admin.md).  <br/> |
|Varios  <br/> |Si va a migrar desde Gmail, consulte Migración de [buzones de G Suite a Microsoft 365](/Exchange/mailbox-migration/migrating-imap-mailboxes/migrate-g-suite-mailboxes).  <br/> Si va a migrar desde otro proveedor de correo electrónico, incluido Exchange, consulte Formas de [migrar varias cuentas de correo electrónico a Microsoft 365](/Exchange/mailbox-migration/mailbox-migration).  <br/> |

## <a name="plan-for-file-storage-and-migration"></a>Plan de almacenamiento y migración de archivos

Microsoft 365 proporciona almacenamiento en la nube para individuos, organizaciones pequeñas y empresas. Para obtener instrucciones sobre qué almacenar dónde, consulte [Dónde puede almacenar documentos en Microsoft 365](https://support.microsoft.com/office/d18d21a0-1f9f-4f6c-ac45-d52afa0a4a2e).
  
- **Puede mover cientos de archivos** a [OneDrive](https://support.microsoft.com/office/45114744-6D42-45CD-8975-F9617819BDEB) o a un [sitio de equipo de SharePoint](https://support.microsoft.com/office/da549fb1-1fcb-4167-87d0-4693e93cb7a0#__toc384119242). Puede cargar 100 archivos a la vez. Evite cargar archivos con un tamaño superior a 2 GB, el tamaño de archivo máximo predeterminado.
  
- **Si desea mover varios miles de archivos** a Microsoft 365 almacenamiento, revise los [límites en línea de SharePoint](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits). Le recomendamos que use una herramienta de migración o considere la posibilidad de contratar un [socio](https://go.microsoft.com/fwlink/?linkid=391089) para ayudarle con la migración. Para más información sobre cómo migrar un gran número de archivos, vea la [Guía del usuario de migración de OneDrive y SharePoint Online](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets).
  
## <a name="plan-for-teams"></a>Planeamiento de Teams

Puede usar Microsoft Teams para realizar llamadas a otras personas de la organización que están en su suscripción. Por ejemplo, si su organización tiene 10 personas, puede llamar a e im entre sí mediante Teams sin ninguna configuración especial. Para obtener más información, consulte [Comenzar con Microsoft Teams](/MicrosoftTeams/get-started-with-teams-quick-start).

Para organizaciones más grandes o si está empezando desde implementaciones Skype Empresarial, locales o híbridas, consulte [Implementación de Microsoft Teams](/MicrosoftTeams/how-to-roll-out-teams).
  
## <a name="plan-for-integration-with-active-directory-or-other-software"></a>Plan de integración con Active Directory u otro software

- **¿Desea la integración con su entorno local de Active Directory?** Puede integrar la Active Directory local con Microsoft 365 mediante Azure Active Directory Conectar. Para obtener instrucciones, consulte [Configuración de la sincronización de directorios para Microsoft 365](../../enterprise/set-up-directory-synchronization.md).
  
- **¿Desea integrar Microsoft 365 con software realizado por otras empresas?** Si necesita integrar Microsoft 365 con otro software de su organización, le recomendamos que considere [la posibilidad de contratar un asociado](https://go.microsoft.com/fwlink/?linkid=391089) para ayudarle con la implementación.
  
## <a name="do-you-want-someone-to-help-you-set-up-microsoft-365"></a>¿Quieres que alguien te ayude a configurar Microsoft 365?

- **Si tiene menos de 50 empleados:**

  - **Pida ayuda a y le llamaremos**. Después de comprar Microsoft 365, puede acceder al centro de administración (no es necesario ejecutar el programa de instalación para acceder a él). En la parte inferior del centro de administración, seleccione **¿Necesita ayuda?** Describa el problema y le llamaremos. 
  - **Llame a [Microsoft 365 para soporte técnico para empresas](../../business-video/get-help-support.md) con sus preguntas**. ¡Estamos aquí para ayudarle! 
  - **Considere la posibilidad de contratar un [partner de Microsoft](https://go.microsoft.com/fwlink/?linkid=391089)**. Si tiene poco tiempo o tiene requisitos avanzados (como mover miles de archivos a Microsoft 365 almacenamiento en la nube o integrarse con otro software), un asociado experimentado puede ser de gran ayuda. 

- **Si tiene más de 50 empleados**, el [Centro de integración FastTrack](https://go.microsoft.com/fwlink/?LinkId=517115) puede ayudarle con la implementación.

## <a name="see-also"></a>Vea también

[Procedimientos recomendados para proteger Microsoft 365 para planes empresariales](../security-and-compliance/secure-your-business-data.md)
