---
title: Administrar cuentas de usuario de Microsoft 365
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
description: Obtenga información sobre cómo administrar cuentas de usuario de Microsoft 365.
ms.openlocfilehash: a7b6d89a0f66605dde168b85d74fcd8e513afc15
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327764"
---
# <a name="manage-microsoft-365-user-accounts"></a>Administrar cuentas de usuario de Microsoft 365

Puede administrar las cuentas de usuario de Microsoft 365 de varias maneras, según la configuración. Puede administrar cuentas de usuario en el Centro de administración de [Microsoft 365,](https://docs.microsoft.com/microsoft-365/admin/add-users/) [PowerShell,](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)en Servicios de dominio de Active Directory (AD DS) o en el portal de administración de Azure Active Directory (Azure AD). 

Tan pronto como compre Microsoft 365, el Centro de administración de Microsoft 365 y PowerShell se pueden usar para administrar cuentas. Al administrar identidades de nube, cada persona de la organización tiene un nombre de cuenta de usuario y una contraseña independientes. Si desea integrarse con la infraestructura local y hacer que las cuentas de usuario se sincronicen con Microsoft 365, puede usar Azure AD Connect para proporcionar sincronización de identidades y contraseñas para la funcionalidad de inicio de sesión único (SSO).
  
## <a name="plan-for-where-and-how-you-will-manage-your-user-accounts"></a>Planear dónde y cómo administrará las cuentas de usuario

El lugar y la forma en que puede administrar las cuentas de usuario depende del modelo de identidad que desee usar para Microsoft 365. Los dos modelos generales son híbridos y solo en la nube.
  
### <a name="cloud-only"></a>Solo de nube

Puede crear y administrar usuarios en el Centro de administración de Microsoft 365. También puede usar PowerShell o el Centro de administración de Azure AD. 
    
### <a name="hybrid"></a>Híbrido

Las cuentas de usuario se sincronizan con Microsoft 365 desde AD DS, por lo que debe usar las herramientas locales de AD DS para administrar cuentas de usuario. 
    
## <a name="managing-accounts"></a>Administración de cuentas

Al decidir la forma en que la organización creará y administrará las cuentas, tenga en cuenta los siguientes requisitos:
  
- El software de sincronización de directorios debe instalarse en los servidores del entorno local para conectar las identidades entre Microsoft 365 y AD DS.
    
- Cualquier opción de sincronización de directorios, incluidas las opciones de SSO, requiere que los atributos de AD DS cumplan los estándares. Los detalles de qué atributos se usan en el directorio y qué limpieza (si es necesario) se describen en Preparar la sincronización de directorios [con Microsoft 365.](prepare-for-directory-synchronization.md) 
    
- Planee cómo va a crear cuentas de Microsoft 365.
    
En la tabla siguiente se enumeran las distintas herramientas de administración de cuentas.
    
|Herramienta|Notas|
|:-----|:-----|
|Centro de administración de Microsoft 365  <br/> |[Agregar usuarios individualmente o de forma masiva](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) <br/>  Proporciona una interfaz web sencilla para agregar y cambiar cuentas de usuario.  <br/>  No se puede usar para cambiar usuarios si la sincronización de directorios está habilitada (se puede establecer la asignación de licencias y ubicación).  <br/>  No se puede usar con opciones de SSO.  <br/> |
|Windows PowerShell  <br/> |[Administrar Microsoft 365 con Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=698471) <br/>  Permite agregar usuarios en usuarios masivos mediante un script Windows PowerShell usuario.  <br/>  Se puede usar para asignar licencias y ubicación a las cuentas, independientemente de cómo se crean las cuentas.  <br/> |
|Importación masiva  <br/> |[Agregar varios usuarios al mismo tiempo](add-several-users-at-the-same-time.md) <br/>  Permite importar un archivo CSV para agregar un grupo de usuarios a Microsoft 365.  <br/>  No se puede usar con opciones de SSO.  <br/> |
|Azure AD  <br/> |Obtiene una edición gratuita de Azure AD con su suscripción a Microsoft 365. Puede realizar funciones como el restablecimiento de contraseña de autoservicio para los usuarios de la nube y la personalización de las páginas de inicio de sesión y del Panel de acceso mediante la edición gratuita. Para obtener una funcionalidad mejorada, puedes actualizar a la edición básica, Azure AD Premium P1 o Azure AD Premium P2. Consulta [las ediciones de Azure AD](https://go.microsoft.com/fwlink/p/?LinkId=698465) para obtener la lista de características compatibles.  <br/> |
|Sincronización de directorios  <br/> |[Integración de las identidades locales con Azure AD](https://go.microsoft.com/fwlink/p/?LinkID=624168) <br/>  Para la sincronización de directorios con o sin sincronización de contraseñas, use [Azure AD Connect con la configuración expresa.](https://go.microsoft.com/fwlink/p/?LinkID=698537)  <br/>  Para varios bosques y opciones de SSO, use [La instalación personalizada de Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkId=698430).  <br/>  Proporciona la infraestructura necesaria para habilitar SSO.  <br/>  Necesario para muchos escenarios híbridos, como la migración por fases y Exchange híbrido  <br/>  Sincroniza la seguridad y los grupos habilitados para correo desde AD DS.  <br/> |
|||
   
- Independientemente de cómo desee agregar las cuentas de usuario a Microsoft 365, debe administrar varias características de cuenta, como asignar licencias, especificar la ubicación, entre otras. Estas características se pueden administrar a largo plazo desde el Centro de administración de Microsoft 365 o también puede crear cuentas de [usuario con PowerShell.](https://go.microsoft.com/fwlink/p/?LinkId=717083)
    
    Si decide agregar y administrar todos los usuarios a través del centro de administración, especificará la ubicación y asignará licencias al mismo tiempo que crea la cuenta de Microsoft 365. Como resultado, no se requiere mucha planeación.
    
    > [!IMPORTANT]
    > Crear cuentas en Microsoft 365 sin asignar una licencia (por ejemplo, a SharePoint Online) significa que el propietario de la cuenta puede ver el Centro de Microsoft 365, pero no puede acceder a ninguno de los servicios de la suscripción de su empresa. Después de asignar una ubicación y la licencia, la cuenta se replica en el servicio o servicios que asignó. El usuario puede iniciar sesión en su cuenta y usar los servicios que le haya asignado. 
  
## <a name="see-also"></a>Vea también

[Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users)

[PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)  
