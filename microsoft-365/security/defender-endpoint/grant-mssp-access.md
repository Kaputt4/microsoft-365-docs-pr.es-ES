---
title: Concesión de acceso al proveedor de servicios de seguridad administrado (MSSP)
description: Realice los pasos necesarios para configurar la integración de MSSP con el Microsoft Defender para punto de conexión
keywords: proveedor de servicios de seguridad administrados, mssp, configure, integration
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: article
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 280bac711494cd06d5fe54784e0f7d27b32e5945
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68224544"
---
# <a name="grant-managed-security-service-provider-mssp-access-preview"></a>Concesión de acceso al proveedor de servicios de seguridad administrados (MSSP) (versión preliminar)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-mssp-support-abovefoldlink)

> [!IMPORTANT]
> Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

Para implementar una solución de acceso delegado multiinquilino, siga estos pasos:

1. Habilite el [control de acceso basado en rol](rbac.md) en Defender para punto de conexión y conéctese con grupos de Active Directory (AD).

2. Configure [los paquetes de acceso de gobernanza](/azure/active-directory/governance/identity-governance-overview) para la solicitud de acceso y el aprovisionamiento.

3. Administrar solicitudes de acceso y auditorías en [Microsoft Myaccess](/azure/active-directory/governance/entitlement-management-request-approve).

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint"></a>Habilitación de controles de acceso basados en rol en Microsoft Defender para punto de conexión

1. **Creación de grupos de acceso para recursos de MSSP en Customer AAD: Groups**

    Estos grupos se vincularán a los roles que cree en Defender para punto de conexión. Para ello, en el inquilino de AD del cliente, cree tres grupos. En nuestro enfoque de ejemplo, creamos los siguientes grupos:

    - Analista de nivel 1
    - Analista de nivel 2
    - Aprobadores de analistas de MSSP

2. Cree roles de Defender para punto de conexión para los niveles de acceso adecuados en Customer Defender para punto de conexión.

    Para habilitar RBAC en el portal de Microsoft 365 Defender del cliente, acceda a **Configuración > Permisos > Roles** y "Activar roles" desde una cuenta de usuario con derechos de administrador global o administrador de seguridad.

    :::image type="content" source="images/mssp-access.png" alt-text="Acceso de MSSP" lightbox="images/mssp-access.png":::

    A continuación, cree roles de RBAC para satisfacer las necesidades del nivel SOC de MSSP. Vincule estos roles a los grupos de usuarios creados mediante "Grupos de usuarios asignados".

    Dos roles posibles:

    - **Analistas de nivel 1**

      Realice todas las acciones excepto la respuesta en vivo y administre la configuración de seguridad.

    - **Analistas de nivel 2**

      Funcionalidades de nivel 1 con la adición a la [respuesta en vivo](live-response.md)

    Para obtener más información, consulte [Uso del control de acceso basado en rol](rbac.md).

## <a name="configure-governance-access-packages"></a>Configuración de paquetes de acceso de gobernanza

1. **Adición de MSSP como organización conectada en Customer AAD: Identity Governance**

    Agregar el MSSP como una organización conectada permitirá al MSSP solicitar y tener acceso aprovisionado.

    Para ello, en el inquilino de AD del cliente, acceda a Identity Governance: Connected organization (Gobernanza de identidades: organización conectada). Agregue una nueva organización y busque el inquilino de MSSP Analyst a través del identificador de inquilino o dominio. Se recomienda crear un inquilino de AD independiente para los analistas de MSSP.

2. **Creación de un catálogo de recursos en Customer AAD: Identity Governance**

    Los catálogos de recursos son una colección lógica de paquetes de acceso creados en el inquilino de AD del cliente.

    Para ello, en el inquilino de AD del cliente, acceda a Identity Governance: Catalogs (Gobernanza de identidades: catálogos) y agregue **New Catalog (Nuevo catálogo**). En nuestro ejemplo, lo llamaremos **Accesos MSSP**.

    :::image type="content" source="images/goverance-catalog.png" alt-text="Página del nuevo catálogo" lightbox="images/goverance-catalog.png":::

    Para más información, consulte [Creación de un catálogo de recursos](/azure/active-directory/governance/entitlement-management-catalog-create).

3. **Creación de paquetes de acceso para recursos de MSSP Customer AAD: Identity Governance**

    Los paquetes de acceso son la recopilación de derechos y accesos que se concederán a un solicitante tras la aprobación.

    Para ello, en el inquilino de AD del cliente, acceda a Identity Governance: Access Packages (Gobernanza de identidades: paquetes de acceso) y agregue **New Access Package (Nuevo paquete de acceso).** Cree un paquete de acceso para los aprobadores de MSSP y cada nivel de analista. Por ejemplo, la siguiente configuración de analista de nivel 1 crea un paquete de acceso que:

    - Requiere que un miembro del grupo de AD **, los aprobadores de analistas de MSSP** , autorice nuevas solicitudes.
    - Tiene revisiones de acceso anuales, donde los analistas de SOC pueden solicitar una extensión de acceso.
    - Solo los usuarios pueden solicitarlo en el inquilino de SOC de MSSP.
    - El acceso automático expira después de 365 días

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/new-access-package.png" alt-text="Página Nuevo paquete de acceso" lightbox="images/new-access-package.png":::

    Para obtener más información, consulte [Creación de un nuevo paquete de acceso](/azure/active-directory/governance/entitlement-management-access-package-create).

4. **Proporcionar un vínculo de solicitud de acceso a los recursos de MSSP desde Customer AAD: Identity Governance**

    Los analistas de MSSP SOC usan el vínculo del portal Mi acceso para solicitar acceso a través de los paquetes de acceso creados. El vínculo es duradero, lo que significa que el mismo vínculo se puede usar con el tiempo para los nuevos analistas. La solicitud de analista entra en una cola para su aprobación por parte de los **aprobadores de analistas de MSSP**.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/access-properties.png" alt-text="Página Propiedades" lightbox="images/access-properties.png":::

    El vínculo se encuentra en la página de información general de cada paquete de acceso.

## <a name="manage-access"></a>Administrar el acceso

1. Revise y autorice las solicitudes de acceso en MyAccess del cliente o MSSP.

    Las solicitudes de acceso se administran en el cliente Mi acceso, por miembros del grupo de aprobadores de analistas de MSSP.

    Para ello, acceda a myaccess del cliente mediante: `https://myaccess.microsoft.com/@<Customer Domain>`.

    Ejemplo: `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`

2. Aprobar o denegar solicitudes en la sección **Aprobaciones** de la interfaz de usuario.

    En este momento, se ha aprovisionado el acceso de analista y cada analista debe poder acceder al portal de Microsoft 365 Defender del cliente:`https://security.microsoft.com/?tid=<CustomerTenantId>`

## <a name="related-topics"></a>Temas relacionados

- [Acceder al portal de clientes de MSSP](access-mssp-portal.md)
- [Configurar notificaciones de alerta](configure-mssp-notifications.md)
- [Capturar alertas del espacio empresarial del cliente](fetch-alerts-mssp.md)
