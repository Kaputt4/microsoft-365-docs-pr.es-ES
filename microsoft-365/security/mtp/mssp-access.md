---
title: Proporcionar acceso al proveedor de servicios de seguridad administrado (MSSP)
description: Obtenga información sobre los cambios del Centro de seguridad de Microsoft Defender al Centro de seguridad de Microsoft 365
keywords: Introducción al Centro de seguridad de Microsoft 365, OATP, MDATP, MDO, MDE, panel único de cristal, portal convergente, portal de seguridad, portal de seguridad, portal de seguridad de defender
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
ms.openlocfilehash: db9279ba1bc5fe11f3a31884a05b4403f0cb67f3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906705"
---
# <a name="provide-managed-security-service-provider-mssp-access"></a>Proporcionar acceso al proveedor de servicios de seguridad administrado (MSSP) 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**Se aplica a:**

- [Microsoft 365 Defender](./microsoft-threat-protection.md)
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2146631)

Para implementar una solución de acceso delegado multiinquilino, siga estos pasos:

1. Habilite [el control de](/windows/security/threat-protection/microsoft-defender-atp/rbac) acceso basado en roles en Defender for Endpoint en el Centro de seguridad de Microsoft 365 y conéctese con grupos de Azure Active Directory (Azure AD).

2. Configurar [paquetes de acceso de gobierno](/azure/active-directory/governance/identity-governance-overview) para la solicitud de acceso y el aprovisionamiento.

3. Administrar solicitudes de acceso y auditorías [en Microsoft Myaccess](/azure/active-directory/governance/entitlement-management-request-approve).

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint-in-microsoft-365-security-center"></a>Habilitar controles de acceso basados en roles en Microsoft Defender para endpoint en el Centro de seguridad de Microsoft 365

1. **Crear grupos de acceso para recursos MSSP en Customer AAD: Groups**

    Estos grupos se vincularán a los roles que cree en Defender for Endpoint en el Centro de seguridad de Microsoft 365. Para ello, en el inquilino de AD del cliente, cree tres grupos. En nuestro enfoque de ejemplo, creamos los siguientes grupos:

    - Analista de nivel 1 
    - Analista de nivel 2 
    - Aprobadores de analistas de MSSP  


2. Cree roles de Defender para puntos de conexión para niveles de acceso adecuados en Customer Defender for Endpoint en grupos y roles del centro de seguridad de Microsoft 365.

    Para habilitar RBAC en el centro de seguridad de Microsoft 365 del cliente, acceda a permisos > roles de puntos de conexión & grupos **> Roles** con una cuenta de usuario con derechos de administrador global o administrador de seguridad.

    ![Imagen del acceso de MSSP](../../media/mssp-access.png)

    A continuación, cree roles RBAC para satisfacer las necesidades de nivel SOC de MSSP. Vincule estos roles a los grupos de usuarios creados mediante "Grupos de usuarios asignados".

    Dos roles posibles:

    - **Analistas de nivel 1** <br>
      Realice todas las acciones excepto la respuesta en directo y administre la configuración de seguridad.

    - **Analistas de nivel 2** <br>
      Capacidades de nivel 1 con la adición a [la respuesta en directo](/windows/security/threat-protection/microsoft-defender-atp/live-response)

    Para obtener más información, vea [Use role-based access control](/windows/security/threat-protection/microsoft-defender-atp/rbac).



## <a name="configure-governance-access-packages"></a>Configurar paquetes de acceso de gobierno

1.  **Agregar MSSP como organización conectada en customer AAD: Identity Governance**
    
    Agregar el MSSP como organización conectada permitirá al MSSP solicitar y tener accesos aprovisionados. 

    Para ello, en el inquilino de AD del cliente, acceda a Identity Governance: Connected organization. Agregue una nueva organización y busque el inquilino de MSSP Analyst a través del identificador de inquilino o dominio. Se recomienda crear un inquilino de AD independiente para los analistas de MSSP.

2. **Crear un catálogo de recursos en Customer AAD: Identity Governance**

    Los catálogos de recursos son una colección lógica de paquetes de acceso, creados en el inquilino de AD del cliente.

    Para ello, en el inquilino de AD del cliente, acceda a Identity Governance: Catalogs y agregue **New Catalog**. En nuestro ejemplo, lo llamaremos **MSSP Accesses**. 

    ![Imagen del nuevo catálogo](../../media/goverance-catalog.png)

    Para obtener más información, vea [Create a catalog of resources](/azure/active-directory/governance/entitlement-management-catalog-create).


3. **Crear paquetes de acceso para recursos MSSP Customer AAD: Identity Governance**

    Los paquetes de acceso son la colección de derechos y accesos que se concederá a un solicitante tras su aprobación. 

    Para ello, en el inquilino de AD del cliente, acceda a Identity Governance: Access Packages y agregue **New Access Package**. Cree un paquete de acceso para los aprobadores de MSSP y cada nivel de analista. Por ejemplo, la siguiente configuración de Analista de nivel 1 crea un paquete de acceso que:

    - Requiere que un miembro del grupo de AD **aprobadores de analistas de MSSP** autorice nuevas solicitudes
    - Tiene revisiones de acceso anuales, donde los analistas de SOC pueden solicitar una extensión de acceso
    - Los usuarios solo pueden solicitarlo en el inquilino soc de MSSP
    - Access auto expira después de 365 días

    ![Imagen del nuevo paquete de acceso](../../media/new-access-package.png)

    Para obtener más información, vea [Create a new access package](/azure/active-directory/governance/entitlement-management-access-package-create).


4. **Proporcionar vínculo de solicitud de acceso a recursos MSSP desde customer AAD: Identity Governance**

    Los analistas de SOC de MSSP usan el vínculo Portal de My Access para solicitar acceso a través de los paquetes de acceso creados. El vínculo es duradero, lo que significa que el mismo vínculo puede usarse con el tiempo para los nuevos analistas. La solicitud de analista entra en una cola para su aprobación por parte de los aprobadores de analistas de **MSSP**.


    ![Imagen de las propiedades de access](../../media/access-properties.png)

    El vínculo se encuentra en la página de información general de cada paquete de acceso.

## <a name="manage-access"></a>Administrar el acceso 

1. Revise y autorice las solicitudes de acceso en Customer y/o MSSP myaccess.

    Las solicitudes de acceso se administran en el cliente My Access, por miembros del grupo Aprobadores de analistas de MSSP.

    Para ello, acceda a myaccess del cliente mediante:  `https://myaccess.microsoft.com/@<Customer Domain >` . 

    Ejemplo:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`   
2. Aprobar o denegar solicitudes en la sección **Aprobaciones** de la interfaz de usuario.

     En este momento, se ha aprovisionado el acceso de analistas y cada analista debe tener acceso al Centro de seguridad de Microsoft 365 del cliente: 

    `https://security.microsoft.com/?tid=<CustomerTenantId>` con los permisos y roles que se asignaron.

> [!IMPORTANT]
> El acceso delegado a Microsoft Defender para Endpoint en el Centro de seguridad de Microsoft 365 actualmente permite el acceso a un único espacio empresarial por ventana del explorador.