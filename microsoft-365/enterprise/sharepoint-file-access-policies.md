---
title: Directivas recomendadas para proteger documentos - Microsoft 365 Enterprise | Microsoft Docs
description: Se explican las directivas recomendadas por Microsoft para proteger el acceso a archivos de SharePoint.
author: BrendaCarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: bcarter
ms.date: 06/07/2018
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: f0cd296157e1d4856c27d1dc547de045510e788b
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600767"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>Recomendaciones de directivas para proteger los archivos y los sitios de SharePoint

En este artículo se describe cómo implementar la identidad recomendada y las directivas de acceso a dispositivos para proteger SharePoint Online y OneDrive para la empresa. Esta guía se basa en las [directivas comunes de identidad y acceso a dispositivos](identity-access-policies.md).

Estas recomendaciones se basan en tres niveles diferentes de seguridad y protección para los archivos de SharePoint que se pueden aplicar en función de la granularidad de sus necesidades: **línea base**, **confidencial**y **altamente regulable**. Puede obtener más información sobre estos niveles de seguridad y los sistemas operativos de cliente recomendados, a los que se hace referencia en estas recomendaciones en [la introducción](microsoft-365-policies-configurations.md).

Además de implementar esta guía, asegúrese de configurar los sitios de SharePoint con la cantidad adecuada de protección, incluida la configuración de los permisos adecuados para contenido confidencial y altamente regulado. Para obtener más información acerca de la creación de sitios para la protección de línea base, confidencial y altamente regulada, vea [proteger sitios y archivos de SharePoint Online](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files).

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a>Actualización de directivas comunes para incluir SharePoint y OneDrive para la empresa

El siguiente diagrama ilustra el conjunto de directivas recomendadas para proteger archivos en SharePoint Online y OneDrive para la empresa. Indica qué directivas deben actualizarse o recién creadas para agregar protección a SharePoint Online y OneDrive para la empresa.

![Resumen de directivas para SharePoint Online y OneDrive](../images/identity-access-ruleset-sharepoint.png)

Si incluyó SharePoint Online al crear las directivas comunes, solo tiene que crear las nuevas directivas. Al configurar reglas de acceso condicional, SharePoint Online incluye OneDrive para la empresa.

Las nuevas directivas implementan la protección de dispositivos para contenido sensible y altamente regulado mediante la aplicación de requisitos de acceso específicos a los sitios de SharePoint que se especifiquen.

En la siguiente tabla se enumeran las directivas que debe revisar y actualizar o crear nuevas para SharePoint Online. Las directivas comunes vinculan a las instrucciones de configuración asociadas en el artículo [Common Identity and Device Access Policies](identity-access-policies.md) .

|Nivel de protección|Directivas|Más información|
|:---------------|:-------|:----------------|
|**Baseline**|[Requerir MFA cuando el riesgo de inicio de sesión sea *medio* o *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Incluir SharePoint Online en la asignación de aplicaciones en la nube|
|        |[Bloquear a los clientes que no sean compatibles con la autenticación moderna](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|Incluir SharePoint Online en la asignación de aplicaciones en la nube|
|        |[Definir directivas de protección de aplicaciones](identity-access-policies.md#define-app-protection-policies)|Asegúrese de que todas las aplicaciones recomendadas se incluyen en la lista de aplicaciones. Asegúrese de actualizar la Directiva para cada plataforma (iOS, Android, Windows)|
|        |[Exigir equipos PC compatibles](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Incluir SharePoint Online en la lista de aplicaciones en la nube|
|        |[Usar restricciones de aplicación forzada en SharePoint Online](#use-app-enforced-restrictions-in-sharepoint-online)|Agregar esta nueva Directiva. Esto indica a Azure AD que use la configuración especificada en SharePoint Online. Esta regla se aplica a todos los usuarios, pero solo afecta al acceso a los sitios incluidos en las directivas de acceso de SharePoint Online|
|**Confidencial**|[Requerir MFA cuando el riesgo de inicio de sesión es *bajo*, *medio* o *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Incluir SharePoint Online en las asignaciones de aplicaciones en la nube|
|         |[Requerir equipos *y* dispositivos móviles compatibles](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Incluir SharePoint Online en la lista de aplicaciones en la nube|
||[Directiva de control de acceso de SharePoint Online](#sharepoint-online-access-control-policies): permitir el acceso solo del explorador a sitios específicos de SharePoint desde dispositivos no administrados|Esto evita la edición y descarga de archivos. Usar PowerShell para especificar sitios|
|**Extremadamente regulado**|[Requerir *siempre* MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Incluir SharePoint Online en la asignación de aplicaciones en la nube|
||[Directiva de control de acceso de SharePoint Online](#use-app-enforced-restrictions-in-sharepoint-online): bloquear el acceso a sitios específicos de SharePoint desde dispositivos no administrados|Usar PowerShell para especificar sitios|

## <a name="use-app-enforced-restrictions-in-sharepoint-online"></a>Usar restricciones de aplicación forzada en SharePoint Online

Si implementa controles de acceso en SharePoint Online, debe crear esta directiva de acceso condicional en Azure AD para decir a Azure AD que aplique las directivas que configure en SharePoint Online. Esta regla se aplica a todos los usuarios, pero solo afecta al acceso a los sitios que se especifiquen mediante PowerShell al crear los controles de acceso en SharePoint Online.

Para configurar esta Directiva, vea "bloquear o limitar el acceso a colecciones de sitios de SharePoint específicas o cuentas de OneDrive" en este artículo: [controlar el acceso desde dispositivos no administrados](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622).

## <a name="sharepoint-online-access-control-policies"></a>Directivas de control de acceso de SharePoint Online

Microsoft recomienda proteger el contenido de los sitios de SharePoint con contenido sensible y altamente regulado con controles de acceso a dispositivos. Para ello, cree una directiva que especifique el nivel de protección y los sitios a los que se aplicará la protección.

- Sitios confidenciales: permitir el acceso solo del explorador. Esto impide que los usuarios editen y descarguen archivos.
- Sitios altamente regulados: bloquear el acceso desde dispositivos no administrados.

Vea "bloquear o limitar el acceso a colecciones de sitios de SharePoint específicas o cuentas de OneDrive" en este artículo: [controlar el acceso desde dispositivos no administrados](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622).

## <a name="how-these-policies-work-together"></a>Funcionamiento conjunto de estas directivas

Es importante comprender que los permisos de sitio de SharePoint suelen basarse en la necesidad empresarial de acceso a los sitios. Estos permisos los administran los propietarios del sitio y pueden ser muy dinámicos. El uso de directivas de acceso a dispositivos de SharePoint garantiza la protección de estos sitios, independientemente de si los usuarios están asignados a un grupo de Azure AD asociado con una protección de línea base, sensible o altamente regulada.

En la siguiente ilustración se muestra un ejemplo de cómo las directivas de acceso a dispositivos de SharePoint protegen el acceso a los sitios.

![Cómo protegen las directivas de acceso a dispositivos de SharePoint los sitios](../images/SharePoint-rules-scenario.png)

En la ilustración:

- James se asigna a las directivas de acceso condicional asociadas con la protección de línea de base, pero se le puede conceder acceso a los sitios de SharePoint asociados con una protección sensible o altamente regulada.
- Si James obtiene acceso a un sitio sensible o altamente regulado, es miembro del uso de su equipo, se concede su acceso siempre que su equipo sea compatible.
- Si James obtiene acceso a un sitio confidencial, es miembro del uso de su teléfono no administrado, lo que se permite a los usuarios de línea base, recibirá acceso solo del explorador al sitio confidencial debido a la Directiva de acceso de dispositivos configurada para este sitio.
- Si James obtiene acceso a un sitio altamente regulado, es miembro del uso de su teléfono no administrado, se bloqueará debido a la Directiva de acceso configurada para este sitio. Solo puede acceder a este sitio mediante su equipo administrado y compatible.

## <a name="next-steps"></a>Siguientes pasos

[Protección de archivos y sitios de SharePoint Online](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files)
