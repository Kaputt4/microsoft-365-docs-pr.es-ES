---
title: Proporcionar acceso al proveedor de servicios de seguridad administrado (MSSP)
description: Más información sobre los cambios de la Centro de seguridad de Microsoft Defender al portal de Microsoft 365 Defender
keywords: Introducción al portal de Microsoft 365 Defender, Microsoft Defender para Office 365, Microsoft Defender para punto de conexión, MDO, MDE, panel único de cristal, portal convergente, portal de seguridad, portal de seguridad, portal de seguridad de Defender
ms.prod: m365-security
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
ms.openlocfilehash: 3df43fd4de6bd040db0acd13678434c7302aff5d
ms.sourcegitcommit: e8dd5cd434d17af7096d28d467a2b3b021cbb233
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "67050763"
---
# <a name="provide-managed-security-service-provider-mssp-access"></a>Proporcionar acceso al proveedor de servicios de seguridad administrado (MSSP) 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**Se aplica a:**

- [Microsoft 365 Defender](microsoft-365-defender.md)
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Para implementar una solución de acceso delegado multiinquilino, siga estos pasos:

1. Habilite el [control de acceso basado en rol](/microsoft-365/security/defender-endpoint/rbac) para Defender para punto de conexión a través del portal de Microsoft 365 Defender y conéctese con grupos de Azure Active Directory (Azure AD).

2. Configure [la administración de derechos para usuarios externos](/azure/active-directory/governance/entitlement-management-external-users) dentro de La gobernanza de identidades de Azure AD para habilitar las solicitudes de acceso y el aprovisionamiento.

3. Administrar solicitudes de acceso y auditorías en [Microsoft Myaccess](/azure/active-directory/governance/entitlement-management-request-approve).

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint-in-microsoft-365-defender-portal"></a>Habilitación de controles de acceso basados en rol en Microsoft Defender para punto de conexión en Microsoft 365 Defender portal

1. **Creación de grupos de acceso para recursos de MSSP en Customer AAD: Groups**

    Estos grupos se vincularán a los roles que cree en Defender para punto de conexión en Microsoft 365 Defender portal. Para ello, en el inquilino de AD del cliente, cree tres grupos. En nuestro enfoque de ejemplo, creamos los siguientes grupos:

    - Analista de nivel 1
    - Analista de nivel 2
    - Aprobadores de analistas de MSSP  

2. Cree roles de Defender para punto de conexión para los niveles de acceso adecuados en Customer Defender para punto de conexión en Microsoft 365 Defender roles y grupos del portal.

    Para habilitar RBAC en el portal de Microsoft 365 Defender del cliente, acceda a **los roles permisos > puntos de conexión & grupos > roles** con una cuenta de usuario con derechos de administrador global o administrador de seguridad.

    :::image type="content" source="../../media/mssp-access.png" alt-text="Detalles del acceso de MSSP en el portal de Microsoft 365 Defender" lightbox="../../media/mssp-access.png":::

    A continuación, cree roles de RBAC para satisfacer las necesidades del nivel SOC de MSSP. Vincule estos roles a los grupos de usuarios creados mediante "Grupos de usuarios asignados".

    Dos roles posibles:

    - **Analistas de nivel 1** <br>
      Realice todas las acciones excepto la respuesta en vivo y administre la configuración de seguridad.

    - **Analistas de nivel 2** <br>
      Funcionalidades de nivel 1 con la adición a la [respuesta en vivo](/microsoft-365/security/defender-endpoint/live-response).

    Para obtener más información, consulte [Administración del acceso al portal mediante el control de acceso basado en rol](/microsoft-365/security/defender-endpoint/rbac).

## <a name="configure-governance-access-packages"></a>Configuración de paquetes de acceso de gobernanza

1. **Adición de MSSP como organización conectada en Customer AAD: Identity Governance**

    Agregar el MSSP como una organización conectada permitirá al MSSP solicitar y tener acceso aprovisionado. 

    Para ello, en el inquilino de AD del cliente, acceda a Identity Governance: Connected organization (Gobernanza de identidades: organización conectada). Agregue una nueva organización y busque el inquilino de MSSP Analyst a través del identificador de inquilino o dominio. Se recomienda crear un inquilino de AD independiente para los analistas de MSSP.

2. **Creación de un catálogo de recursos en Customer AAD: Identity Governance**

    Los catálogos de recursos son una colección lógica de paquetes de acceso creados en el inquilino de AD del cliente.

    Para ello, en el inquilino de AD del cliente, acceda a Identity Governance: Catalogs (Gobernanza de identidades: catálogos) y agregue **New Catalog (Nuevo catálogo**). En nuestro ejemplo, lo llamaremos **Accesos MSSP**.

    :::image type="content" source="../../media/goverance-catalog.png" alt-text="Un nuevo catálogo en el portal de Microsoft 365 Defender" lightbox="../../media/goverance-catalog.png":::


    Para más información, consulte [Creación de un catálogo de recursos](/azure/active-directory/governance/entitlement-management-catalog-create).

3. **Creación de paquetes de acceso para recursos de MSSP Customer AAD: Identity Governance**

    Los paquetes de acceso son la recopilación de derechos y accesos que se concederán a un solicitante tras la aprobación. 

    Para ello, en el inquilino de AD del cliente, acceda a Identity Governance: Access Packages (Gobernanza de identidades: paquetes de acceso) y agregue **New Access Package (Nuevo paquete de acceso).** Cree un paquete de acceso para los aprobadores de MSSP y cada nivel de analista. Por ejemplo, la siguiente configuración de analista de nivel 1 crea un paquete de acceso que:

    - Requiere que un miembro del grupo de AD **, los aprobadores de analistas de MSSP** , autorice nuevas solicitudes.
    - Tiene revisiones de acceso anuales, donde los analistas de SOC pueden solicitar una extensión de acceso.
    - Solo los usuarios pueden solicitarlo en el inquilino de SOC de MSSP.
    - El acceso automático expira después de 365 días

    :::image type="content" source="../../media/new-access-package.png" alt-text="Detalles de un nuevo paquete de acceso en el portal de Microsoft 365 Defender" lightbox="../../media/new-access-package.png":::

    Para obtener más información, consulte [Creación de un nuevo paquete de acceso](/azure/active-directory/governance/entitlement-management-access-package-create).

4. **Proporcionar un vínculo de solicitud de acceso a los recursos de MSSP desde Customer AAD: Identity Governance**

    Los analistas de MSSP SOC usan el vínculo del portal Mi acceso para solicitar acceso a través de los paquetes de acceso creados. El vínculo es duradero, lo que significa que el mismo vínculo se puede usar con el tiempo para los nuevos analistas. La solicitud de analista entra en una cola para su aprobación por parte de los **aprobadores de analistas de MSSP**.

    :::image type="content" source="../../media/access-properties.png" alt-text="Propiedades de acceso en el portal de Microsoft 365 Defender" lightbox="../../media/access-properties.png":::

    El vínculo se encuentra en la página de información general de cada paquete de acceso.

## <a name="manage-access"></a>Administrar el acceso

1. Revise y autorice las solicitudes de acceso en MyAccess del cliente o MSSP.

    Las solicitudes de acceso se administran en el cliente Mi acceso, por miembros del grupo de aprobadores de analistas de MSSP.

    Para ello, acceda a myaccess del cliente mediante: `https://myaccess.microsoft.com/@<Customer Domain>`.

    Ejemplo: `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`

2. Aprobar o denegar solicitudes en la sección **Aprobaciones** de la interfaz de usuario.

     En este momento, se ha aprovisionado el acceso de analista y cada analista debe poder acceder al portal de Microsoft 365 Defender del cliente:

    `https://security.microsoft.com/?tid=<CustomerTenantId>` con los permisos y roles que se les asignaron.
