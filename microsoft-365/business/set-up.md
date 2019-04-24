---
title: Configurar Microsoft 365 Business mediante el Asistente para configuración
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Obtenga información sobre cómo configurar Microsoft 365 Business completando cuatro pasos.
ms.openlocfilehash: a1c8a41c3e291983276280a063248bdd10a7f85a
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283951"
---
# <a name="set-up-microsoft-365-business-by-using-the-setup-wizard"></a>Configurar Microsoft 365 Business mediante el Asistente para configuración

Complete los pasos 1-4 a continuación.
  
### <a name="set-up-microsoft-365-business"></a>Configurar Microsoft 365 Business

Vea un vídeo sobre cómo configurar Microsoft 365 Business si no tiene un Active Directory local:
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/0705c337-f3e8-4d28-bb6c-530cd28e99f2?autoplay=false]
  
Los pasos de configuración incluyen información para los programadores que incluyen Active Directory local. Si desea seguir teniendo acceso a los dispositivos Unidos a un dominio, lea los siguientes artículos para conocer de dos formas diferentes de habilitarlo y completar los pasos antes de ejecutar el Asistente para la instalación:
  
- [Habilitar los dispositivos Windows 10 Unidos a un dominio para que los administre Microsoft 365 Business](manage-windows-devices.md)
    
    -Ésta es la forma recomendada.
    
- [Acceso a recursos locales desde un dispositivo unido a Azure AD en Microsoft 365 Business](access-resources.md)
    
### <a name="step-1-personalize-sign-in"></a>Paso 1: personalizar el inicio de sesión

1. Inicie sesión en [Microsoft 365 Business](https://portal.microsoft.com) usando las credenciales de administrador global. Elija el icono **Administrador** para ir al centro de administración. 
    
2. Elija **Iniciar instalación** (según su estado, es posible que vea **Continuar instalación** en su lugar) en el centro de administración para iniciar el asistente. 
    
3. Escriba el nombre de dominio que desea utilizar (por ejemplo, contoso.com).
    
    Prosiga y escriba su dominio, aunque lo haya verificado al usar Azure AD Connect, por ejemplo. Los dos pasos siguientes no se aplican en caso de que haya usado Azure AD Connect para comprobar su dominio.
    
4. Siga los pasos del Asistente para [crear registros DNS en cualquier proveedor de hospedaje DNS para Office 365](https://support.office.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166) que compruebe que es el propietario del dominio. 
    
    Puede ver un ejemplo de vídeo de [vídeo: configurar Office 365 en el nuevo centro de administración](https://support.office.com/article/a8c2002a-34bc-4ab3-93d8-9b5156c48bf8). Tenga en cuenta que este vídeo no incluye los pasos de protección de datos de Microsoft 365 Business.
    
    ![Screenshot of the Business Cloud Suite setup wizard.](media/3c4fd40c-2de1-4a87-8ee0-78d3928c7bb7.png)
  
### <a name="step-2-add-users-and-assign-licenses"></a>Paso 2: agregar usuarios y asignar licencias

1. Puede agregar usuarios aquí, o puede [agregar usuarios más adelante](add-users-m365b.md) en el centro de administración. 
    
    Todos los usuarios que agregue tendrán una licencia de Microsoft 365 Business asignada automáticamente.
    
2. Si su suscripción a Microsoft 365 Business tiene usuarios existentes (por ejemplo, si usó Azure AD Connect), verá una opción para asignarles licencias ahora. Siga y agrégueles licencias también.
    
3. También verá una opción para compartir las credenciales con los nuevos usuarios que ha agregado. Puede elegir imprimirlas, enviarlas por correo electrónico o descargarlas.
    
4. Omita la migración de mensajes de correo electrónico y elija **Siguiente** en la página **Migrar los mensajes de correo electrónico**. 
    
    Si va a cambiar de otro proveedor de correo electrónico y desea copiar los datos más adelante, puede migrar el [correo electrónico y los contactos a Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).
    
    ![Screenshot of two new users added in the setup wizard](media/8f729967-5c65-4ceb-b737-18119db40564.png)
  
### <a name="step-3-connect-your-domain"></a>Paso 3: conectar su dominio

> [!NOTE]
> Si decidió usar el dominio. en Microsoft o si usó Azure AD Connect, no verá este paso. 
  
Para configurar servicios, es necesario actualizar algunos registros en su registrador de dominio o host DNS.
  
1. Normalmente, el asistente para configuración detecta el registrador y le proporciona un vínculo con instrucciones paso a paso para actualizar los registros NS en el sitio web del registrador. Si no es así, [cambie los servidores DNS para configurar Office 365 con cualquier registrador de dominios](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).
    
2. Se configurarán automáticamente el correo electrónico y otros servicios
    
### <a name="step-4-manage-devices-and-work-files"></a>Paso 4: administrar dispositivos y archivos de trabajo

1. En la página **Proteger los archivos de trabajo en sus dispositivos móviles** establezca las dos opciones **Proteger los archivos de trabajo cuando los dispositivos se extravían por pérdida o robo** y **Administrar la forma en la que los usuarios obtienen acceso a los archivos de Office desde dispositivos móviles** en **Activado**. También puede tener acceso a cada subconfiguración haciendo clic en las comillas angulares que hay junto a cada configuración.
  
  Todos los archivos de trabajo de los usuarios con licencia ahora están protegidos en dispositivos iOS y Android, en cuanto [instalan las aplicaciones de Office](set-up-mobile-devices.md) (y se autentican con sus credenciales de Microsoft 365 Business). 
  
  ![Screenshot of protect work files on your mobile devices page](media/3139a9aa-6228-4e74-8166-c6a886d7319f.PNG)
  
2. En la página **establecer la configuración** de dispositivos de Windows 10, establezca la configuración **proteger dispositivos Windows 10** en **activada**.
  
   También puede obtener acceso a cada subconfiguración haciendo clic en la comilla angular situada junto a ella.
  
3. Establezca la configuración **Instalar Office en dispositivos Windows 10** en **Sí** si todos los usuarios tienen equipos Windows 10 y ninguna instalación de Office existente o de Hacer clic y ejecutar de Office. Si este no es el caso, establezca esta opción en **No**. También puede [instalar Office automáticamente](auto-install-or-uninstall-office.md) más adelante desde el centro de administración después de preparar los equipos de usuario. Para obtener instrucciones, consulte [preparar la instalación del cliente de Office](prepare-for-office-client-deployment.md).
  
    Los archivos de trabajo de los usuarios con licencia en dispositivos con Windows 10 se proyectarán en cuanto se unan a un [dispositivo con Windows 10](set-up-windows-devices.md) a un dominio de Microsoft 365 Business Azure ad o [instalen Windows 10 en un equipo nuevo](https://support.office.com/article/c654bd23-d256-4ac7-8fba-0c993bf5a771.aspx) al mismo tiempo que se unen a Microsoft 365 Dominio empresarial de Azure AD. 
  
4. Haga clic en **Siguiente** y ya ha terminado la configuración. 
  
    Envíenos comentarios en este paso para ayudarnos a mejorar la experiencia.
  
    ![Screenshot of Prepare Windows 10 devices page](media/bff701c1-48a3-44f4-aa95-9d959d57c85b.PNG)
  
## <a name="additional-security-settings"></a>Opciones de configuración de seguridad adicionales

Además de la configuración de seguridad y cumplimiento del Asistente para instalación, también puede configurar las siguientes opciones adicionales:
  
- Configurar la protección contra datos adjuntos no seguros. **Protección contra amenazas avanzada** (ATP) identifica contenido malintencionado y, a continuación, bloquea la entrega de datos adjuntos no seguros, lo que ayuda a protegerte contra las tramas de suplantación de identidad Para activar la protección de datos adjuntos, consulte [configurar las directivas de datos adjuntos seguros de Office 365 ATP](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775#setpolicy).
    
- Proteja su entorno cuando los usuarios hacen clic en vínculos malintencionados. ATP examina los vínculos del correo electrónico en el momento en el que el usuario hace clic en ellos. Si un vínculo no es seguro, se advierte al usuario de que no va a visitar el sitio ni que se le informe de que se ha bloqueado el sitio. Esto ayuda a proteger contra las tramas de suplantación de identidad. [Configurar las directivas de vínculos seguros de office 365 ATP](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc) o [configurar las directivas de vínculos seguros de atp de Office 365](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc).
    
- Puede conservar todo el contenido del buzón, incluidos los elementos eliminados, al poner el buzón completo de un usuario en retención por **juicio**. Para obtener instrucciones, consulte 
- [Configurar la retención de correo electrónico con el archivado de Exchange Online](security-features.md#set-up-email-retention-with-exchange-online-archiving).
    
- Configure **directivas de retención**personalizadas, por ejemplo, para preservar una cantidad de tiempo específica o eliminar contenido de forma permanente al final del período de retención. Puede habilitar las directivas de retención personalizadas en el centro de valores y cumplimiento, ir a **retención**de **gobierno** \> de datos y, a continuación, seguir los pasos del asistente. Para obtener más información, vea [información general sobre las directivas de retención](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).
    
## <a name="next-steps"></a>Pasos siguientes

En el caso de los usuarios que tienen licencia, el siguiente paso es configurar los dispositivos.<br/> Consulte [Configurar dispositivos Windows para los usuarios de Microsoft 365 Business](set-up-windows-devices.md) y [Configurar dispositivos móviles para los usuarios de Microsoft 365 Business](set-up-mobile-devices.md). <br/>Consulte [Administrar Microsoft 365 Business](manage.md) para ver vínculos relacionados con los temas sobre cómo configurar directivas de protección de aplicaciones y dispositivos y cómo eliminar datos de dispositivos de usuario. 
  


