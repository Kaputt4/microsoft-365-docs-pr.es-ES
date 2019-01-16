---
title: Directivas recomendadas para proteger documentos - Microsoft 365 Enterprise | Microsoft Docs
description: Se explican las directivas recomendadas por Microsoft para proteger el acceso a archivos de SharePoint.
author: BrendaCarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
ms.date: 06/07/2018
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.openlocfilehash: 72dd50649dba9e290d50c2831557c06db3cb7586
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "26871444"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>Recomendaciones de directiva para proteger los archivos y los sitios de SharePoint
En este artículo se describe cómo implementar la identidad recomendada y las directivas de acceso de dispositivo para proteger SharePoint Online y OneDrive para la empresa. Esta guía se basa en la [identidad y las directivas de acceso de dispositivo comunes](identity-access-policies.md). 

Estas recomendaciones se basan en tres diferentes niveles de seguridad y protección para los archivos de SharePoint que se pueden aplicar en función de la granularidad de sus necesidades: **línea de base**, **confidencial**y **altamente regulado**. Encontrará más información acerca de estos niveles de seguridad y los sistemas operativos de cliente recomendado, estas recomendaciones en la [Introducción a la](microsoft-365-policies-configurations.md)que hace referencia.

Además de implementar esta guía, asegúrese de configurar los sitios de SharePoint con la cantidad adecuada de protección, incluido el establecimiento de los permisos adecuados para contenido confidencial y altamente regulado. Para obtener más información sobre la creación de sitios para la protección de línea de base, confidencial y altamente regulado, vea [archivos y sitios de SharePoint Online seguro](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files). 

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a>Actualización de directivas comunes para incluir SharePoint y OneDrive para la empresa
El siguiente diagrama ilustra el conjunto de directivas recomendadas para la protección de archivos en SharePoint Online y OneDrive para la empresa. Indica qué directivas se deben actualizarse o creadas recientemente para agregar protección para SharePoint Online y OneDrive para la empresa.

![Resumen de directivas para SharePoint Online y OneDrive](../images/identity-access-ruleset-sharepoint.png)

Si ha incluido SharePoint Online cuando crea las políticas comunes, sólo tiene que crear las nuevas directivas. Al configurar las reglas de acceso condicional, SharePoint Online incluye OneDrive para la empresa.

Las nuevas directivas de implementan la protección de dispositivo contenido confidencial y altamente regulado aplicando los requisitos de acceso específico a los sitios de SharePoint que especifique. 

En la siguiente tabla se enumera las directivas que necesite revisar y actualizar o crear nuevos para SharePoint Online. Vinculación las directivas comunes a las instrucciones de configuración asociada en el artículo de [directivas de acceso comunes de identidad y el dispositivo](identity-access-policies.md) .


|Nivel de protección|Policies|Más información|
|:---------------|:-------|:----------------|
|**Línea base**|[Requerir MFA al inicio de sesión de riesgo es *medio* o *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Incluir SharePoint Online en la asignación de aplicaciones de nube|
|        |[Clientes de bloque que no admiten la autenticación moderna](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|Incluir SharePoint Online en la asignación de aplicaciones de nube|
|        |[Definir directivas de protección de aplicaciones](identity-access-policies.md#define-app-protection-policies)|Asegúrese de que todas las aplicaciones recomendadas se incluyen en la lista de aplicaciones. Asegúrese de actualizar la directiva para cada plataforma (iOS, Android, Windows)|
|        |[Requerir PCs compatibles con](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Incluir SharePoint Online en la lista de aplicaciones en la nube|
|        |[Aplicación de uso aplica restricciones en SharePoint Online](#use-app-enforced-restrictions-in-sharepoint-online)|Agregue esta nueva directiva. Esto indica a Azure AD para usar la configuración especificada en SharePoint Online. Esta regla se aplica a todos los usuarios, pero sólo afecta al acceso a los sitios que se incluyen en directivas de acceso de SharePoint Online|
|**Confidencial**|[Requerir MFA al inicio de sesión de riesgo es *bajo*, *medio* o *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Incluir SharePoint Online en las asignaciones de aplicaciones de nube|
|         |[Requerir compatible con PC *y* dispositivos móviles](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Incluir SharePoint Online en la lista de aplicaciones en la nube|
||[Directiva de control de acceso a SharePoint Online](#sharepoint-online-access-control-policies): permitir el acceso de sólo explorador a determinados sitios de SharePoint desde dispositivos no administrados|Esto evita la edición y la descarga de archivos. Uso de PowerShell para especificar los sitios|
|**Extremadamente regulado**|[*Siempre* requieren MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Incluir SharePoint Online en la asignación de aplicaciones de nube|
||[Directiva de control de acceso a SharePoint Online](#use-app-enforced-restrictions-in-sharepoint-online): bloquear el acceso a determinados sitios de SharePoint desde dispositivos no administrados|Uso de PowerShell para especificar los sitios|

## <a name="use-app-enforced-restrictions-in-sharepoint-online"></a>Use las restricciones impuestas por aplicación en SharePoint Online
Si implementa los controles de acceso en SharePoint Online, debe crear esta directiva de acceso condicional en Azure AD para indicar a Azure AD para aplicar las directivas de que configuración en SharePoint Online. Esta regla se aplica a todos los usuarios, pero sólo afecta al acceso a los sitios que especifique mediante PowerShell cuando cree los controles de acceso en SharePoint Online.

Para configurar esta Consulte directiva "bloquear o limitar el acceso a las colecciones de sitios de SharePoint específicas o las cuentas de OneDrive" en este artículo: [controlar el acceso desde dispositivos no administrados](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622).


## <a name="sharepoint-online-access-control-policies"></a>Directivas de control de acceso de SharePoint Online
Microsoft recomienda que proteger contenido en sitios de SharePoint con contenido confidencial y altamente regulado con controles de acceso de dispositivo. Para ello, mediante la creación de una directiva que especifica el nivel de protección y los sitios que se va a aplicar la protección a. 
- Sitios confidenciales: permitir el acceso de sólo explorador. Esto evita que los usuarios de edición y descarga de archivos.
- Altamente regulado sitios: bloquear el acceso desde dispositivos no administrados.

Vea "bloquear o limitar el acceso a las colecciones de sitios de SharePoint específicas o las cuentas de OneDrive" en este artículo: [controlar el acceso desde dispositivos no administrados](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622) . 

## <a name="how-these-policies-work-together"></a>Cómo funcionan conjuntamente estas directivas
Es importante comprender que los permisos del sitio de SharePoint se basan normalmente en necesidad empresarial de acceso a sitios. Estos permisos son administrados por los propietarios de sitios y pueden ser muy dinámicos. Uso de directivas de acceso de dispositivo garantiza protección a estos sitios, independientemente de si los usuarios se asignan a un grupo de Azure AD de SharePoint había asociado con la línea de base, confidencial, o altamente regulado protección. 

La ilustración siguiente proporciona un ejemplo de cómo las directivas de acceso de dispositivo de SharePoint protegen el acceso a sitios.

![Cómo protegen los sitios SharePoint directivas de acceso de dispositivo](../images/SharePoint-rules-scenario.png)

En la ilustración:
- James está asignado a las directivas de acceso condicional asociadas a la protección de línea de base, pero puede tener acceso a los sitios de SharePoint asociados a la protección de información sensible o altamente regulado. 
- Si James obtiene acceso a un sitio confidencial o altamente regulado es un miembro del uso de su PC, su acceso siempre que sea compatible con su PC.
- Si James obtiene acceso a un sitio confidencial que es un miembro de usar su teléfono no administrado, lo que está permitido para los usuarios de la línea de base, recibirá sólo explorador acceso al sitio confidencial debido a la directiva de acceso de dispositivo configurado para este sitio. 
- Si James obtiene acceso a un sitio altamente regulado es un miembro de usar su teléfono no administrado, se bloqueará debido a la directiva de acceso configurada para este sitio. Solo puede obtener acceso a este sitio utilizando su PC administrado y compatible con.


<!---
##Block access to content from unmanaged devices (SharePoint admin center)
In the case of SharePoint Online, when a conditional access policy is applied to enforce Intune app protection policies, this might not apply to all applications that access SharePoint Online. Some applications, such as Exchange, have access to some SharePoint resources. For example, Exchange allows attaching SharePoint files by default. Conditional access policies applied to SharePoint Online will not restrict this access. 

To ensure baseline protection is applied uniformly, regardless of which service is accessing SharePoint Online and OneDrive for Business, configure access controls directly in SharePoint admin center. We recommend you configure the following:
- Block access from unmanaged devices. This includes devices that aren't compliant or joined to a domain. 
- Block access from app that don't use modern authentication.

See [Control access from unmanaged devices](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622).
-->



## <a name="next-steps"></a>Pasos siguientes
[Protección de archivos y sitios de SharePoint Online](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files)
