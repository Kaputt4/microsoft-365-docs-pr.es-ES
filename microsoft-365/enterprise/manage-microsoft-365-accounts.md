---
title: Administrar Microsoft 365 de usuario
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Obtenga información sobre cómo administrar Microsoft 365 cuentas de usuario.
ms.openlocfilehash: c0387bf50228e0eeb763b4807b15c8d57e02eeac
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909567"
---
# <a name="manage-microsoft-365-user-accounts"></a>Administrar Microsoft 365 de usuario

Puede administrar las cuentas Microsoft 365 usuario de varias maneras diferentes, según la configuración. Puede administrar cuentas de usuario en el Centro de administración de [Microsoft 365](../admin/add-users/index.yml), [PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md), en Servicios de dominio de Active Directory (AD DS) o en el portal de administración de Azure Active Directory (Azure AD). 

Tan pronto como compre Microsoft 365, el centro Microsoft 365 administración y PowerShell se pueden usar para administrar cuentas. Al administrar identidades en la nube, cada persona de la organización tiene un nombre de cuenta de usuario y una contraseña independientes. Si desea integrarse con la infraestructura local y tener cuentas de usuario sincronizadas con Microsoft 365, puede usar Azure AD Conectar para proporcionar sincronización de identidades y contraseñas para la funcionalidad de inicio de sesión único (SSO).
  
## <a name="plan-for-where-and-how-you-will-manage-your-user-accounts"></a>Planear dónde y cómo administrará sus cuentas de usuario

Dónde y cómo puede administrar sus cuentas de usuario depende del modelo de identidad que desee usar para su Microsoft 365. Los dos modelos generales son híbridos y solo en la nube.
  
### <a name="cloud-only"></a>Solo de nube

Puede crear y administrar usuarios en el centro Microsoft 365 administración. También puede usar PowerShell o el Centro de administración de Azure AD. 
    
### <a name="hybrid"></a>Híbrido

Las cuentas de usuario se sincronizan con Microsoft 365 de AD DS, por lo que debes usar las herramientas locales de AD DS para administrar cuentas de usuario. 
    
## <a name="managing-accounts"></a>Administración de cuentas

Al decidir la forma en que la organización creará y administrará cuentas, tenga en cuenta los siguientes requisitos:
  
- El software de sincronización de directorios debe instalarse en servidores dentro del entorno local para conectar las identidades entre Microsoft 365 y su AD DS.
    
- Cualquier opción de sincronización de directorios, incluidas las opciones de SSO, requiere que los atributos de AD DS cumplan los estándares. Los detalles de qué atributos se usan en el directorio y qué limpieza (si la hay) se describen en [Preparar](prepare-for-directory-synchronization.md)la sincronización de directorios para Microsoft 365 . 
    
- Planee cómo va a crear Microsoft 365 cuentas.
    
En la tabla siguiente se enumeran las distintas herramientas de administración de cuentas.
    
|Herramienta|Notas|
|:-----|:-----|
|Centro de administración de Microsoft 365  <br/> |[Agregar usuarios de forma individual o masiva](../admin/add-users/add-users.md) <br/>  Proporciona una interfaz web sencilla para agregar y cambiar cuentas de usuario.  <br/>  No se puede usar para cambiar los usuarios si la sincronización de directorios está habilitada (se puede establecer la asignación de ubicación y licencia).  <br/>  No se puede usar con opciones de SSO.  <br/> |
|Windows PowerShell  <br/> |[Administrar Microsoft 365 con Windows PowerShell](./manage-microsoft-365-with-microsoft-365-powershell.md) <br/>  Permite agregar usuarios en usuarios masivos mediante un script Windows PowerShell usuario.  <br/>  Se puede usar para asignar ubicación y licencias a cuentas, independientemente de cómo se crean las cuentas.  <br/> |
|Importación masiva  <br/> |[Agregar varios usuarios al mismo tiempo](add-several-users-at-the-same-time.md) <br/>  Permite importar un archivo CSV para agregar un grupo de usuarios a Microsoft 365.  <br/>  No se puede usar con opciones de SSO.  <br/> |
|Azure AD  <br/> |Obtiene una edición gratuita de Azure AD con su Microsoft 365 suscripción. Puede realizar funciones como el restablecimiento de contraseñas de autoservicio para los usuarios de la nube y la personalización de las páginas del Panel de acceso y inicio de sesión mediante la edición gratuita. Para obtener funcionalidad mejorada, puede actualizar a la edición básica, Azure AD Premium P1 o Azure AD Premium P2. Consulta [Ediciones de Azure AD](/azure/active-directory/fundamentals/active-directory-whatis) para obtener la lista de características admitidas.  <br/> |
|Sincronización de directorios  <br/> |[Integración de identidades locales con Azure AD](/azure/active-directory/hybrid/whatis-hybrid-identity) <br/>  Para la sincronización de directorios con o sin sincronización de contraseñas, use [Azure AD Conectar con la configuración express](/azure/active-directory/hybrid/how-to-connect-install-express).  <br/>  Para varios bosques y opciones de SSO, use [Instalación personalizada de Azure AD Conectar](/azure/active-directory/hybrid/how-to-connect-install-custom).  <br/>  Proporciona la infraestructura necesaria para habilitar SSO.  <br/>  Necesario para muchos escenarios híbridos, como la migración por fases y la migración Exchange  <br/>  Sincroniza la seguridad y los grupos habilitados para correo desde su AD DS.  <br/> |
|||
   
- Independientemente de cómo desee agregar las cuentas de usuario a Microsoft 365, debe administrar varias características de cuenta, como asignar licencias, especificar la ubicación, entre otras. Estas características se pueden administrar a largo plazo desde el centro de administración Microsoft 365 o también puede crear [cuentas de usuario con PowerShell](./create-user-accounts-with-microsoft-365-powershell.md).
    
    Si elige agregar y administrar todos los usuarios a través del Centro de administración, especificará la ubicación y asignará licencias al mismo tiempo que crea la cuenta Microsoft 365 usuario. Como resultado, no se requiere mucha planeación.
    
    > [!IMPORTANT]
    > Crear cuentas en Microsoft 365 sin asignar una licencia (por ejemplo, a SharePoint Online) significa que el propietario de la cuenta puede ver el centro de Microsoft 365 pero no puede acceder a ninguno de los servicios de la suscripción de su empresa. Después de asignar una ubicación y la licencia, la cuenta se replica en el servicio o los servicios que asignó. El usuario puede iniciar sesión en su cuenta y usar los servicios que les asignó. 
  
## <a name="see-also"></a>Consulte también

[Centro de administración de Microsoft 365](../admin/add-users/index.yml)

[PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)