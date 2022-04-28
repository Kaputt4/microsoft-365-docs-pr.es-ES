---
title: Administrar cuentas de usuario Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: Admin
ms.topic: overview
ms.prod: office-online-server
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
- admindeeplinkMAC
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Obtenga información sobre cómo administrar cuentas de usuario Microsoft 365.
ms.openlocfilehash: dbd1c0a3c1c6fdb10d157299552e83a77f495e3c
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65098348"
---
# <a name="manage-microsoft-365-user-accounts"></a>Administrar cuentas de usuario Microsoft 365

Puede administrar Microsoft 365 cuentas de usuario de varias maneras diferentes, en función de la configuración. Puede administrar cuentas de usuario en el [Centro de administración de Microsoft 365](/admin), [PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md), en Servicios de dominio de Active Directory (AD DS) o en el Azure Active Directory ( Azure AD) portal de administración. 

En cuanto compre Microsoft 365, los <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a> y PowerShell se pueden usar para administrar cuentas. Al administrar identidades en la nube, cada persona de la organización tiene un nombre de cuenta de usuario y una contraseña independientes. Si desea integrarse con la infraestructura local y tener cuentas de usuario sincronizadas con Microsoft 365, puede usar Azure AD Conectar para proporcionar sincronización de identidades y contraseñas para la funcionalidad de inicio de sesión único (SSO).
  
## <a name="plan-for-where-and-how-you-will-manage-your-user-accounts"></a>Planear dónde y cómo administrará las cuentas de usuario

Dónde y cómo puede administrar las cuentas de usuario depende del modelo de identidad que quiera usar para la Microsoft 365. Los dos modelos generales son solo en la nube e híbridos.
  
### <a name="cloud-only"></a>Solo de nube

Los usuarios se crean y administran en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a>. También puede usar PowerShell o el centro de administración de Azure AD. 
    
### <a name="hybrid"></a>Híbrido

Las cuentas de usuario se sincronizan con Microsoft 365 de AD DS, por lo que debe usar herramientas de AD DS locales para administrar cuentas de usuario. 
    
## <a name="managing-accounts"></a>Administración de cuentas

Al decidir de qué manera su organización creará y administrará cuentas, tenga en cuenta los siguientes requisitos:
  
- El software de sincronización de directorios debe instalarse en servidores del entorno local para conectar las identidades entre Microsoft 365 y AD DS.
    
- Cualquier opción de sincronización de directorios, incluidas las opciones de SSO, requiere que los atributos de AD DS cumplan los estándares. Los detalles de qué atributos se usan en el directorio y qué limpieza (si existe) se describen en [Preparación de la sincronización de directorios para Microsoft 365](prepare-for-directory-synchronization.md). 
    
- Planee cómo va a crear cuentas de Microsoft 365.
    
En la tabla siguiente se enumeran las distintas herramientas de administración de cuentas.
    
|Herramienta|Notas|
|:-----|:-----|
|Centro de administración de Microsoft 365  <br/> |[Agregar usuarios de forma individual o masiva](../admin/add-users/add-users.md) <br/>  Proporciona una interfaz web sencilla para agregar y cambiar cuentas de usuario.  <br/>  No se puede usar para cambiar los usuarios si la sincronización de directorios está habilitada (se puede establecer la asignación de licencias y la ubicación).  <br/>  No se puede usar con las opciones de SSO.  <br/> |
|Windows PowerShell  <br/> |[Administración de Microsoft 365 con Windows PowerShell](./manage-microsoft-365-with-microsoft-365-powershell.md) <br/>  Permite agregar usuarios en masa mediante un script de Windows PowerShell.  <br/>  Se puede usar para asignar la ubicación y las licencias a las cuentas, independientemente de cómo se creen las cuentas.  <br/> |
|Importación masiva  <br/> |[Agregar varios usuarios al mismo tiempo](add-several-users-at-the-same-time.md) <br/>  Permite importar un archivo CSV para agregar un grupo de usuarios a Microsoft 365.  <br/>  No se puede usar con las opciones de SSO.  <br/> |
|Azure AD  <br/> |Obtendrá una edición gratuita de Azure AD con su suscripción de Microsoft 365. Puede realizar funciones como el autoservicio de restablecimiento de contraseña para usuarios en la nube y la personalización de las páginas de inicio de sesión y Panel de acceso mediante la edición gratuita. Para obtener una funcionalidad mejorada, puede actualizar a la edición básica, Azure AD Premium P1 o Azure AD Premium P2. Consulte [Azure AD ediciones](/azure/active-directory/fundamentals/active-directory-whatis) para obtener la lista de características admitidas.  <br/> |
|Sincronización de directorios  <br/> |[Integración de las identidades locales con Azure AD](/azure/active-directory/hybrid/whatis-hybrid-identity) <br/>  Para la sincronización de directorios con o sin sincronización de contraseñas, use [Azure AD Conectar con la configuración rápida](/azure/active-directory/hybrid/how-to-connect-install-express).  <br/>  Para varios bosques y opciones de SSO, use [Instalación personalizada de Azure AD Conectar](/azure/active-directory/hybrid/how-to-connect-install-custom).  <br/>  Proporciona la infraestructura necesaria para habilitar el inicio de sesión único.  <br/>  Necesario para muchos escenarios híbridos, como la migración por fases y la Exchange híbrida  <br/>  Sincroniza la seguridad y los grupos habilitados para correo desde AD DS.  <br/> |
|||
   
- Independientemente de cómo quiera agregar las cuentas de usuario a Microsoft 365, debe administrar varias características de cuenta, como la asignación de licencias, la especificación de la ubicación, etc. Estas características se pueden administrar a largo plazo desde el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a> o también puede [crear cuentas de usuario con PowerShell](./create-user-accounts-with-microsoft-365-powershell.md).
    
    Si decide agregar y administrar todos los usuarios a través del centro de administración, especificará la ubicación y asignará licencias al mismo tiempo que creará la cuenta de Microsoft 365. Como resultado, no se requiere mucha planificación.
    
    > [!IMPORTANT]
    > La creación de cuentas en Microsoft 365 sin asignar una licencia (por ejemplo, a SharePoint Online) significa que el propietario de la cuenta puede ver el centro de Microsoft 365, pero no puede acceder a ninguno de los servicios de la suscripción de su empresa. Después de asignar una ubicación y la licencia, la cuenta se replica en el servicio o servicios asignados. El usuario puede iniciar sesión en su cuenta y usar los servicios que le ha asignado. 
  
## <a name="see-also"></a>Vea también

[Centro de administración de Microsoft 365](/admin)

[PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)