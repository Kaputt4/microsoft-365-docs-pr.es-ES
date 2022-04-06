---
title: Conceder acceso al proveedor de servicios de seguridad administrado (MSSP)
description: Siga los pasos necesarios para configurar la integración de MSSP con Microsoft Defender para endpoint
keywords: proveedor de servicios de seguridad administrados, mssp, configuración, integración
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c8a96f3dba51de09a7237279b4053b9f4ed9b4a7
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "64470491"
---
# <a name="grant-managed-security-service-provider-mssp-access-preview"></a>Conceder acceso al proveedor de servicios de seguridad administrado (MSSP) (versión preliminar)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-mssp-support-abovefoldlink)

> [!IMPORTANT]
> Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

Para implementar una solución de acceso delegado multiinquilino, siga estos pasos:

1. Habilite [el control de acceso basado en roles](rbac.md) en Defender para endpoint y conéctese con grupos de Active Directory (AD).

2. Configurar [paquetes de acceso de gobierno](/azure/active-directory/governance/identity-governance-overview) para la solicitud de acceso y el aprovisionamiento.

3. Administrar solicitudes de acceso y auditorías [en Microsoft Myaccess](/azure/active-directory/governance/entitlement-management-request-approve).

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint"></a>Habilitar controles de acceso basados en roles en Microsoft Defender para endpoint

1. **Crear grupos de acceso para recursos MSSP en Customer AAD: Groups**

    Estos grupos se vincularán a los roles que cree en Defender para endpoint. Para ello, en el inquilino de AD del cliente, cree tres grupos. En nuestro enfoque de ejemplo, creamos los siguientes grupos:

    - Analista de nivel 1
    - Analista de nivel 2
    - Aprobadores de analistas de MSSP

2. Cree roles de Defender para endpoint para niveles de acceso adecuados en Customer Defender for Endpoint.

    Para habilitar RBAC en el portal de Microsoft 365 Defender cliente, acceda a **Configuración > Permissions > Roles** y "Activar roles", desde una cuenta de usuario con derechos de administrador global o administrador de seguridad.

    :::image type="content" source="images/mssp-access.png" alt-text="Acceso de MSSP" lightbox="images/mssp-access.png":::

    A continuación, cree roles RBAC para satisfacer las necesidades de nivel SOC de MSSP. Vincule estos roles a los grupos de usuarios creados mediante "Grupos de usuarios asignados".

    Dos roles posibles:

    - **Analistas de nivel 1**

      Realice todas las acciones excepto la respuesta en directo y administre la configuración de seguridad.

    - **Analistas de nivel 2**

      Capacidades de nivel 1 con la adición a [la respuesta en directo](live-response.md)

    Para obtener más información, vea [Usar control de acceso basado en roles](rbac.md).

## <a name="configure-governance-access-packages"></a>Configurar paquetes de acceso de gobierno

1. **Agregar MSSP como organización conectada en customer AAD: Identity Governance**

    Agregar el MSSP como organización conectada permitirá al MSSP solicitar y tener accesos aprovisionados.

    Para ello, en el inquilino de AD del cliente, acceda a Identity Governance: Connected organization. Agregue una nueva organización y busque el inquilino de MSSP Analyst a través del identificador de inquilino o dominio. Se recomienda crear un inquilino de AD independiente para los analistas de MSSP.

2. **Crear un catálogo de recursos en Customer AAD: Identity Governance**

    Los catálogos de recursos son una colección lógica de paquetes de acceso, creados en el inquilino de AD del cliente.

    Para ello, en el inquilino de AD del cliente, acceda a Identity Governance: Catalogs y agregue **New Catalog**. En nuestro ejemplo, lo llamaremos **MSSP Accesses**.

    :::image type="content" source="images/goverance-catalog.png" alt-text="La nueva página de catálogo" lightbox="images/goverance-catalog.png":::

    Para obtener más información, vea [Crear un catálogo de recursos](/azure/active-directory/governance/entitlement-management-catalog-create).

3. **Crear paquetes de acceso para recursos MSSP Customer AAD: Identity Governance**

    Los paquetes de acceso son la colección de derechos y accesos que se concederá a un solicitante tras su aprobación.

    Para ello, en el inquilino de AD del cliente, acceda a Identity Governance: Access Packages y agregue **New Access Package**. Cree un paquete de acceso para los aprobadores de MSSP y cada nivel de analista. Por ejemplo, la siguiente configuración de Analista de nivel 1 crea un paquete de acceso que:

    - Requiere que un miembro del grupo de AD **aprobadores de analistas de MSSP** autorice nuevas solicitudes
    - Tiene revisiones de acceso anuales, donde los analistas de SOC pueden solicitar una extensión de acceso
    - Los usuarios solo pueden solicitarlo en el inquilino soc de MSSP
    - Access auto expira después de 365 días

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/new-access-package.png" alt-text="La página Nuevo paquete de acceso" lightbox="images/new-access-package.png":::

    Para obtener más información, vea [Create a new access package](/azure/active-directory/governance/entitlement-management-access-package-create).

4. **Proporcionar vínculo de solicitud de acceso a recursos MSSP desde customer AAD: Identity Governance**

    Los analistas de SOC de MSSP usan el vínculo Portal de My Access para solicitar acceso a través de los paquetes de acceso creados. El vínculo es duradero, lo que significa que el mismo vínculo puede usarse con el tiempo para los nuevos analistas. La solicitud de analista entra en una cola para su aprobación por parte de los aprobadores **de analistas de MSSP**.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/access-properties.png" alt-text="La página Propiedades" lightbox="images/access-properties.png":::

    El vínculo se encuentra en la página de información general de cada paquete de acceso.

## <a name="manage-access"></a>Administrar el acceso

1. Revise y autorice las solicitudes de acceso en Customer y/o MSSP myaccess.

    Las solicitudes de acceso se administran en el cliente My Access, por miembros del grupo Aprobadores de analistas de MSSP.

    Para ello, acceda a myaccess del cliente mediante: `https://myaccess.microsoft.com/@<Customer Domain>`.

    Ejemplo: `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`

2. Aprobar o denegar solicitudes en la sección **Aprobaciones** de la interfaz de usuario.

    En este momento, se ha aprovisionado el acceso de analistas y cada analista debe tener acceso al portal de Microsoft 365 Defender cliente:`https://security.microsoft.com/?tid=<CustomerTenantId>`

## <a name="related-topics"></a>Temas relacionados

- [Acceder al portal de clientes de MSSP](access-mssp-portal.md)
- [Configurar notificaciones de alerta](configure-mssp-notifications.md)
- [Capturar alertas del espacio empresarial del cliente](fetch-alerts-mssp.md)
