---
title: Solucionar problemas de la sincronización de directorios para Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: Admin
ms.topic: troubleshooting
ms.service: microsoft-365-enterprise
ms.localizationpriority: high
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- admindeeplinkMAC
ms.collection:
- scotvorg
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MBS150
ms.assetid: 79c43023-5a47-45ae-8068-d8a26eee6bc2
description: Describe las causas comunes de problemas con la sincronización de directorios en Office 365 y ofrece unos cuantos métodos para ayudar a identificarlos y resolverlos.
ms.openlocfilehash: 79484dc0c948a842c25cf0026b9e13849edb80f1
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68165611"
---
# <a name="fixing-problems-with-directory-synchronization-for-microsoft-365"></a>Solucionar problemas de la sincronización de directorios para Microsoft 365

La sincronización de directorios permite continuar con la administración de usuarios y grupos en una implementación local y sincronizar las adiciones, las eliminaciones y los cambios en la nube. Pero la configuración es algo complicada y en ocasiones puede resultar difícil identificar el origen de los problemas. Contamos con los recursos para ayudarle a identificar posibles problemas y a resolverlos.
  
## <a name="how-do-i-know-if-something-is-wrong"></a>¿Cómo puedo saber si algo va mal?

La primera indicación que algo va mal es cuando el icono del estado de DirSync en el centro de administración de Microsoft 365 indica que hay un problema.
  
You will also receive a mail (to the alternate email and to your admin email) from Microsoft 365 that indicates your tenant has encountered directory synchronization errors. For details see [Identify directory synchronization errors in Microsoft 365](identify-directory-synchronization-errors.md).
  
## <a name="how-do-i-get-azure-active-directory-connect-tool"></a>¿Cómo puedo obtener la herramienta Azure Active Directory Connect?

En el [Centro de administración de Microsoft 365](https://admin.microsoft.com), vaya a **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">**Usuarios activos**</a>. Haga clic en el menú **Más** (puntos suspensivos) y seleccione **Sincronización de directorios**. 
  
Siga las [instrucciones del asistente](set-up-directory-synchronization.md) para descargar Azure AD Connect. 
  
Si todavía está usando la sincronización (DirSync) de Azure Active Directory (Azure AD), eche un vistazo a [Cómo solucionar los problemas de instalación de la herramienta de sincronización de Azure Active Directory y de los mensajes de error del asistente de configuración en Microsoft 365](/troubleshoot/azure/active-directory/installation-configuration-wizard-errors) para obtener información sobre los requisitos del sistema para instalar dirsync, los permisos que necesita y cómo solucionar los errores comunes. 
  
Para actualizar desde la sincronización de Azure AD a Azure AD Connect, vea [las instrucciones de actualización](/azure/active-directory/hybrid/how-to-dirsync-upgrade-get-started).
  
## <a name="resolving-common-causes-of-problems-with-directory-synchronization-in-microsoft-365"></a>Resolver causas comunes de los problemas de la sincronización de directorios de Microsoft 365

### <a name="synchronized-objects-arent-appearing-or-updating-online-or-im-getting-synchronization-error-reports-from-the-service"></a>Los objetos sincronizados no aparecen o no se actualizan en línea, o recibo informes de errores de sincronización del servicio.

- [Resistencia de atributo duplicado y sincronización de identidad](/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency)

### <a name="i-have-an-alert-in-the-admin-center-or-am-receiving-automated-emails-that-there-hasnt-been-a-recent-synchronization-event"></a>Tengo una alerta en el centro de administración o recibo correos electrónicos automatizados que indican que no ha habido ningún evento de sincronización reciente
- [Solucionar problemas de conectividad con Azure AD Connect](/azure/active-directory/hybrid/tshoot-connect-connectivity)
- [Cuentas y permisos de Azure AD Connect](/azure/active-directory/hybrid/reference-connect-accounts-permissions)
- [Sincronización de Azure AD Connect: Cómo administrar la cuenta de servicio de Azure AD](/azure/active-directory/hybrid/how-to-connect-azureadaccount)
- [La sincronización de directorios con Azure Active Directory se detiene o le advierte que la sincronización no se ha registrado en más de un día](https://support.microsoft.com/help/2882421/directory-synchronization-to-azure-active-directory-stops-or-you-re-warned-that-sync-hasn-t-registered-in-more-than-a-day)

### <a name="password-hashes-arent-synchronizing-or-im-seeing-an-alert-in-the-admin-center-that-there-hasnt-been-a-recent-password-hash-synchronization"></a>Los hash de contraseñas no se sincronizan o veo una alerta en el centro de administración que indica que no ha habido ninguna sincronización de los hash de contraseñas reciente
- [Implementar la sincronización de hash de contraseñas con la sincronización de Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)

### <a name="im-seeing-an-alert-that-object-quota-exceeded"></a>Veo una alerta que indica que se ha superado la cuota de objetos
- We have a built-in object quota to help protect the service. If you have too many objects in your directory that need to sync to Microsoft 365, you'll have to [Contact support for business products](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) to increase your quota.

### <a name="i-need-to-know-which-attributes-are-synchronized"></a>Necesito saber qué atributos están sincronizados
- Puede ver una lista de todos los atributos sincronizados entre la instalación local y la nube [aquí](https://go.microsoft.com/fwlink/p/?LinkId=396719).

### <a name="i-cant-manage-or-remove-objects-that-were-synchronized-to-the-cloud"></a>No puedo administrar o quitar objetos sincronizados con la nube
- ¿Está listo para administrar objetos en la nube exclusivamente? ¿O un objeto que se eliminó en la implementación local ha quedado atascado en la nube? Eche un vistazo a [Solución de problemas de errores durante la sincronización](/azure/active-directory/hybrid/tshoot-connect-sync-errors) y [artículo de soporte técnico](/troubleshoot/azure/active-directory/cannot-manage-objects) para obtener instrucciones sobre cómo resolver estos problemas.

### <a name="i-got-an-error-message-that-my-company-has-exceeded-the-number-of-objects-that-can-be-synchronized"></a>Un mensaje de error indica que mi compañía ha excedido el número de objetos que se pueden sincronizar
- Puede leer más sobre este problema [aquí](/troubleshoot/azure/active-directory/exceed-number-objects-synced).
   
## <a name="other-resources"></a>Otros recursos

- [Script para corregir los nombres principales de usuario duplicados](/samples/browse/?redirectedfrom=TechNet-Gallery)
    
- [Cómo preparar un dominio no enrutable (por ejemplo, el dominio local) para la sincronización de directorios](prepare-a-non-routable-domain-for-directory-synchronization.md)
    
- [Script para contar el total de objetos sincronizados](/samples/browse/?redirectedfrom=TechNet-Gallery)
    
- [Solución de problemas de AD FS 2.0](https://go.microsoft.com/fwlink/p/?LinkId=396727)
    
- [Usar PowerShell para corregir atributos DisplayName vacíos de grupos habilitados para correo](https://go.microsoft.com/fwlink/p/?LinkId=396728)
    
- [Usar PowerShell para corregir UPN duplicados](https://go.microsoft.com/fwlink/p/?LinkId=396730)
    
- [Usar PowerShell para corregir direcciones de correo duplicadas](https://go.microsoft.com/fwlink/p/?LinkId=396731)
