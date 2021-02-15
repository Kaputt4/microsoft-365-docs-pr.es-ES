---
title: Microsoft Defender para puntos de conexión en el Centro de seguridad de Microsoft 365
description: Obtenga información sobre los cambios del Centro de seguridad de Microsoft Defender al Centro de seguridad de Microsoft 365
keywords: Introducción al Centro de seguridad de Microsoft 365, OATP, MDATP, MDO, MDE, panel único de cristal, portal convergente, portal de seguridad, portal de seguridad de defender
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
manager: dansimp
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.openlocfilehash: 96d5a3bdbd0acbf428f01cc3bb5afefaa95950b4
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242986"
---
# <a name="provide-managed-security-service-provider-mssp-access"></a>Proporcionar acceso de proveedor de servicios de seguridad administrados (MSSP) 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**Se aplica a:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2146631)

Para implementar una solución de acceso delegado multiinquilino, siga estos pasos:

1. Habilite [el control de acceso basado en roles](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac) en Defender para puntos de conexión en el Centro de seguridad de Microsoft 365 y conéctese con grupos de Azure Active Directory (Azure AD).

2. Configurar [paquetes de acceso de gobierno](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) para la solicitud de acceso y el aprovisionamiento.

3. Administrar solicitudes de acceso y auditorías [en Microsoft Myaccess](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-request-approve).

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint-in-microsoft-365-security-center"></a>Habilitar controles de acceso basados en roles en Microsoft Defender para puntos de conexión en el Centro de seguridad de Microsoft 365

1. **Crear grupos de acceso para recursos de MSSP en AAD de cliente: grupos**

    Estos grupos se vincularán a los roles que cree en Defender para puntos de conexión en el Centro de seguridad de Microsoft 365. Para ello, en el inquilino de AD del cliente, cree tres grupos. En nuestro enfoque de ejemplo, creamos los siguientes grupos:

    - Analista de nivel 1 
    - Analista de nivel 2 
    - Aprobadores de analista de MSSP  


2. Crear roles de Defender para puntos de conexión para niveles de acceso adecuados en Customer Defender para Endpoint en grupos y roles del Centro de seguridad de Microsoft 365.

    Para habilitar RBAC en el Centro de seguridad de Microsoft 365 del cliente, obtenga acceso a los roles permisos > Extremos & grupos **> Roles** con una cuenta de usuario con derechos de administrador global o administrador de seguridad.

    ![Imagen del acceso de MSSP](../../media/mssp-access.png)

    A continuación, cree roles RBAC para satisfacer las necesidades del nivel soC de MSSP. Vincule estos roles a los grupos de usuarios creados a través de "Grupos de usuarios asignados".

    Dos roles posibles:

    - **Analistas de nivel 1** <br>
      Realice todas las acciones excepto la respuesta en directo y administre la configuración de seguridad.

    - **Analistas de nivel 2** <br>
      Capacidades de nivel 1 con adición a [la respuesta en directo](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)

    Para obtener más información, vea [Usar control de acceso basado en roles.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)



## <a name="configure-governance-access-packages"></a>Configurar paquetes de acceso de gobierno

1.  **Agregar MSSP como organización conectada en AAD de cliente: Gobierno de identidades**
    
    Agregar el MSSP como organización conectada permitirá que el MSSP solicite y tenga accesos aprovisionados. 

    Para ello, en el inquilino de AD del cliente, acceda a Identity Governance: Organización conectada. Agregue una nueva organización y busque su inquilino de MSSP Analyst a través del identificador de inquilino o dominio. Se recomienda crear un inquilino de AD independiente para los analistas de MSSP.

2. **Crear un catálogo de recursos en customer AAD: Identity Governance**

    Los catálogos de recursos son una colección lógica de paquetes de acceso, creados en el inquilino de AD del cliente.

    Para ello, en el inquilino de AD del cliente, acceda a Identity Governance: Catalogs y agregue **New Catalog**. En nuestro ejemplo, lo llamaremos **MSSP Accesses**. 

    ![Imagen del nuevo catálogo](../../media/goverance-catalog.png)

    Para obtener más información, [vea Crear un catálogo de recursos.](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-catalog-create)


3. **Crear paquetes de acceso para recursos MSSP Customer AAD: Identity Governance**

    Los paquetes de acceso son la colección de derechos y accesos que se concederá a un solicitante tras su aprobación. 

    Para ello, en el inquilino de AD del cliente, acceda a Identity Governance: Access Packages y agregue **New Access Package**. Crea un paquete de acceso para los aprobadores de MSSP y cada nivel de analista. Por ejemplo, la siguiente configuración de analista de nivel 1 crea un paquete de acceso que:

    - Requiere que un miembro del grupo ad **MSSP Analyst Approvers** autorice nuevas solicitudes
    - Tiene revisiones de acceso anuales, donde los analistas de SOC pueden solicitar una extensión de acceso
    - Solo pueden solicitarlo los usuarios del inquilino soC de MSSP
    - El acceso automático expira después de 365 días

    ![Imagen del nuevo paquete de acceso](../../media/new-access-package.png)

    Para obtener más información, vea [Crear un nuevo paquete de acceso.](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-access-package-create)


4. **Proporcionar un vínculo de solicitud de acceso a recursos de MSSP desde AAD de cliente: Gobierno de identidades**

    Los analistas de SOC de MSSP usan el vínculo mi portal de acceso para solicitar acceso a través de los paquetes de acceso creados. El vínculo es duradero, lo que significa que el mismo vínculo puede usarse con el tiempo para nuevos analistas. La solicitud de analista entra en una cola para su aprobación por parte de los aprobadores del analista **de MSSP**.


    ![Imagen de las propiedades de acceso](../../media/access-properties.png)

    El vínculo se encuentra en la página de información general de cada paquete de acceso.

## <a name="manage-access"></a>Administrar el acceso 

1. Revise y autorice las solicitudes de acceso en El cliente y/o MSSP myaccess.

    Las solicitudes de acceso las administran los miembros del grupo Aprobadores de analistas de MSSP en el cliente Mi acceso.

    Para ello, accede a myaccess del cliente mediante:  `https://myaccess.microsoft.com/@<Customer Domain >` . 

    Ejemplo:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`   
2. Aprobar o denegar solicitudes en la **sección Aprobaciones** de la interfaz de usuario.

     En este punto, se ha aprovisionado el acceso de analista y cada analista debe poder acceder al Centro de seguridad de Microsoft 365 del cliente: 

    `https://security.microsoft.com/?tid=<CustomerTenantId>` con los permisos y roles que se asignaron.

> [!IMPORTANT]
> Actualmente, el acceso delegado a Microsoft Defender para Endpoint en el Centro de seguridad de Microsoft 365 permite el acceso a un único inquilino por ventana del explorador. 