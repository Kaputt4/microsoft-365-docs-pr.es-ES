---
title: Administración de cuentas de usuario 365 de Microsoft
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
# <a name="manage-microsoft-365-user-accounts"></a>Administración de cuentas de usuario 365 de Microsoft

Puede administrar cuentas de usuario de Microsoft 365 de varias formas, según su configuración. Puede administrar cuentas de usuario en el [centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/), [PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md), en servicios de dominio de Active Directory (AD DS), o en el portal de administración de Azure Active Directory (Azure ad). 

En cuanto compre Microsoft 365, puede usar el centro de administración de Microsoft 365 y PowerShell para administrar cuentas. Al administrar las identidades de nube, todas las personas de la organización tienen un nombre de cuenta de usuario y una contraseña independientes. Si desea integrar con la infraestructura local y tener cuentas de usuario sincronizadas con Microsoft 365, puede usar Azure AD Connect para proporcionar la sincronización de identidades y contraseñas para la funcionalidad de inicio de sesión único (SSO).
  
## <a name="plan-for-where-and-how-you-will-manage-your-user-accounts"></a>Planeación de dónde y cómo se va a administrar las cuentas de usuario

Dónde y cómo puede administrar las cuentas de usuario depende del modelo de identidad que desee usar para el 365 de Microsoft. Los dos modelos generales son solo de nube y híbridos.
  
### <a name="cloud-only"></a>Solo de nube

Puede crear y administrar usuarios en el centro de administración de Microsoft 365. También puede usar PowerShell o el centro de administración de Azure AD. 
    
### <a name="hybrid"></a>Híbrido

Las cuentas de usuario se sincronizan con Microsoft 365 desde AD DS, por lo que debe usar las herramientas de AD DS local para administrar las cuentas de usuario. 
    
## <a name="managing-accounts"></a>Administración de cuentas

A la hora de decidir la forma en que su organización va a crear y administrar cuentas, tenga en cuenta los siguientes requisitos:
  
- El software de sincronización de directorios debe instalarse en los servidores del entorno local para conectar las identidades entre Microsoft 365 y AD DS.
    
- Cualquier opción de sincronización de directorios, incluidas las opciones de SSO, requiere que los atributos de AD DS cumplan los estándares. Los detalles de los atributos que se usan en el directorio y qué limpieza (si es necesario) se necesitan se describen en [preparar la sincronización de directorios con Microsoft 365](prepare-for-directory-synchronization.md). 
    
- Planee cómo va a crear cuentas de Microsoft 365.
    
En la siguiente tabla se enumeran las diferentes herramientas de administración de cuentas.
    
|Herramienta|Notas|
|:-----|:-----|
|Centro de administración de Microsoft 365  <br/> |[Agregar usuarios individualmente o de forma masiva](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) <br/>  Proporciona una interfaz web sencilla para agregar y cambiar cuentas de usuario.  <br/>  No se puede usar para cambiar usuarios si la sincronización de directorios está habilitada (se puede establecer la asignación de ubicación y licencia).  <br/>  No se puede usar con las opciones de SSO.  <br/> |
|Windows PowerShell  <br/> |[Administración de Microsoft 365 con Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=698471) <br/>  Permite agregar usuarios a usuarios en masa mediante un script de Windows PowerShell.  <br/>  Se puede usar para asignar una ubicación y licencias a las cuentas, independientemente de cómo se creen las cuentas.  <br/> |
|Importación masiva  <br/> |[Agregar varios usuarios al mismo tiempo](add-several-users-at-the-same-time.md) <br/>  Permite importar un archivo CSV para agregar un grupo de usuarios a Microsoft 365.  <br/>  No se puede usar con las opciones de SSO.  <br/> |
|Azure AD  <br/> |Obtendrá una edición gratuita de Azure AD con su suscripción a Microsoft 365. Puede realizar funciones como el restablecimiento de contraseña de autoservicio para los usuarios de la nube y la personalización de las páginas de inicio de sesión y panel de acceso con la edición gratuita. Para obtener funciones mejoradas, puede actualizar a la edición básica, a Azure AD Premium P1 o a Azure AD Premium P2. Consulte [Azure ad Editions](https://go.microsoft.com/fwlink/p/?LinkId=698465) para obtener la lista de características admitidas.  <br/> |
|Sincronización de directorios  <br/> |[Integración de las identidades locales con Azure AD](https://go.microsoft.com/fwlink/p/?LinkID=624168) <br/>  Para la sincronización de directorios con o sin sincronización de contraseñas, use [Azure ad Connect con configuración rápida](https://go.microsoft.com/fwlink/p/?LinkID=698537).  <br/>  Para varios bosques y opciones de SSO, use la [instalación personalizada de Azure ad Connect](https://go.microsoft.com/fwlink/p/?LinkId=698430).  <br/>  Proporciona la infraestructura necesaria para habilitar el SSO.  <br/>  Necesario para muchos escenarios híbridos, como la migración preconfigurada y el intercambio híbrido  <br/>  Sincroniza los grupos habilitados para correo y la seguridad de AD DS.  <br/> |
|||
   
- Independientemente de cómo pretenda agregar las cuentas de usuario a Microsoft 365, debe administrar varias características de cuenta, como la asignación de licencias, la especificación de la ubicación, etc. Estas características se pueden administrar a largo plazo desde el centro de administración de Microsoft 365 o también puede [crear cuentas de usuario con PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=717083).
    
    Si elige agregar y administrar a todos los usuarios a través del centro de administración, deberá especificar la ubicación y asignar licencias al mismo tiempo que crea la cuenta de Microsoft 365. Como resultado, no es necesario realizar mucha planeación.
    
    > [!IMPORTANT]
    > La creación de cuentas en Microsoft 365 sin asignar una licencia (en SharePoint Online, por ejemplo) significa que el propietario de la cuenta puede ver el centro de 365 de Microsoft, pero no puede tener acceso a ninguno de los servicios de la suscripción de la compañía. Después de asignar una ubicación y la licencia, la cuenta se replica en el servicio o los servicios que asignó. El usuario puede iniciar sesión en su cuenta y usar los servicios que se le asignaron. 
  
## <a name="see-also"></a>Vea también

[Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users)

[PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)  
