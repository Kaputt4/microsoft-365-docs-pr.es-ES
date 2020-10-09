---
title: 'Directivas de documentos seguras recomendadas: Microsoft 365 para Enterprise | Microsoft docs'
description: Se explican las directivas recomendadas por Microsoft para proteger el acceso a archivos de SharePoint.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 3235046a9c3decf441a14fb05519ddd5806ba8f0
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2020
ms.locfileid: "48399763"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>Recomendaciones de directivas para proteger los archivos y los sitios de SharePoint

En este artículo se describe cómo implementar la identidad recomendada y las directivas de acceso a dispositivos para proteger SharePoint y OneDrive para la empresa. Esta guía se basa en las [directivas comunes de identidad y acceso a dispositivos](identity-access-policies.md).

Estas recomendaciones se basan en tres niveles diferentes de seguridad y protección para los archivos de SharePoint que se pueden aplicar en función de la granularidad de sus necesidades: **línea base**, **confidencial**y **altamente regulable**. Puede obtener más información sobre estos niveles de seguridad y los sistemas operativos de cliente recomendados, a los que se hace referencia en estas recomendaciones en [la introducción](microsoft-365-policies-configurations.md).

Además de implementar esta guía, asegúrese de configurar los sitios de SharePoint con la cantidad adecuada de protección, incluida la configuración de los permisos adecuados para contenido confidencial y altamente regulado.

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a>Actualización de directivas comunes para incluir SharePoint y OneDrive para la empresa

Para proteger los archivos en SharePoint y OneDrive, en el siguiente diagrama se ilustran las directivas que se deben actualizar desde las directivas comunes de identidad y acceso a dispositivos.

[![Resumen de las actualizaciones de directivas para proteger el acceso a los equipos y sus servicios dependientes](../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)

[Ver una versión más grande de esta imagen](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)

Si ha incluido SharePoint al crear las directivas comunes, solo tiene que crear las nuevas directivas. Para las directivas de acceso condicional, SharePoint incluye OneDrive.

Las nuevas directivas implementan la protección de dispositivos para contenido sensible y altamente regulado mediante la aplicación de requisitos de acceso específicos a los sitios de SharePoint que se especifiquen.

En la siguiente tabla se enumeran las directivas que debe revisar y actualizar o crear una nueva para SharePoint. Las directivas comunes vinculan a las instrucciones de configuración asociadas en el artículo [Common Identity and Device Access Policies](identity-access-policies.md) .

|Nivel de protección|Directivas|Más información|
|:---------------|:-------|:----------------|
|**Baseline**|[Requerir MFA cuando el riesgo de inicio de sesión sea *medio* o *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Incluya SharePoint en la asignación de aplicaciones en la nube.|
|        |[Bloquear a los clientes que no sean compatibles con la autenticación moderna](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|Incluya SharePoint en la asignación de aplicaciones en la nube.|
|        |[Aplicar directivas de protección de datos de aplicaciones](identity-access-policies.md#apply-app-data-protection-policies)|Asegúrese de que todas las aplicaciones recomendadas se incluyen en la lista de aplicaciones. Asegúrese de actualizar la Directiva para cada plataforma (iOS, Android, Windows).|
|        |[Exigir equipos PC compatibles](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Incluir SharePoint en la lista de aplicaciones en la nube.|
|        |[Usar restricciones de aplicación forzada en SharePoint](#use-app-enforced-restrictions-in-sharepoint)|Agregar esta nueva Directiva. Esto indica a Azure Active Directory (Azure AD) que use la configuración especificada en SharePoint. Esta Directiva se aplica a todos los usuarios, pero solo afecta al acceso a los sitios incluidos en las directivas de acceso de SharePoint.|
|**Confidencial**|[Requerir MFA cuando el riesgo de inicio de sesión es *bajo*, *medio* o *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Incluya SharePoint en las asignaciones de aplicaciones en la nube.|
|         |[Requerir equipos *y* dispositivos móviles compatibles](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Incluya SharePoint en la lista de aplicaciones en la nube.|
||[Directiva de control de acceso de SharePoint](#sharepoint-access-control-policies): permitir el acceso solo del explorador a sitios específicos de SharePoint desde dispositivos no administrados.|Esto evita la edición y descarga de archivos. Usar PowerShell para especificar sitios.|
|**Extremadamente regulado**|[Requerir *siempre* MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Incluya SharePoint en la asignación de aplicaciones en la nube.|
||[Directiva de control de acceso de SharePoint](#use-app-enforced-restrictions-in-sharepoint): bloquear el acceso a sitios específicos de SharePoint desde dispositivos no administrados.|Usar PowerShell para especificar sitios.|

## <a name="use-app-enforced-restrictions-in-sharepoint"></a>Usar restricciones de aplicación forzada en SharePoint

Si implementa controles de acceso en SharePoint, debe crear esta directiva de acceso condicional en Azure AD para decir a Azure AD que aplique las directivas que configure en SharePoint. Esta Directiva se aplica a todos los usuarios, pero solo afecta al acceso a los sitios que se especifiquen mediante PowerShell al crear los controles de acceso en SharePoint.

Para configurar esta Directiva, vea "bloquear o limitar el acceso a colecciones de sitios de SharePoint específicas o cuentas de OneDrive" en [controlar el acceso desde dispositivos no administrados](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices).

## <a name="sharepoint-access-control-policies"></a>Directivas de control de acceso de SharePoint

Microsoft recomienda proteger el contenido de los sitios de SharePoint con contenido sensible y altamente regulado con controles de acceso a dispositivos. Para ello, cree una directiva que especifique el nivel de protección y los sitios a los que se aplicará la protección.

- Sitios confidenciales: permitir el acceso solo del explorador. Esto impide que los usuarios editen y descarguen archivos.
- Sitios altamente regulados: bloquear el acceso desde dispositivos no administrados.

Vea "bloquear o limitar el acceso a colecciones de sitios de SharePoint específicas o cuentas de OneDrive" en [controlar el acceso desde dispositivos no administrados](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices).

## <a name="how-these-policies-work-together"></a>Funcionamiento conjunto de estas directivas

Es importante comprender que los permisos de sitio de SharePoint suelen basarse en la necesidad empresarial de acceso a los sitios. Estos permisos los administran los propietarios del sitio y pueden ser muy dinámicos. El uso de directivas de acceso a dispositivos de SharePoint garantiza la protección de estos sitios, independientemente de si los usuarios están asignados a un grupo de Azure AD asociado con una protección de línea base, sensible o altamente regulada.

En la siguiente ilustración se muestra un ejemplo de cómo las directivas de acceso a dispositivos de SharePoint protegen el acceso a los sitios de un usuario.

[![Ejemplo de cómo protegen las directivas de acceso a dispositivos de SharePoint los sitios](../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

[Ver una versión más grande de esta imagen](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

James tiene directivas de acceso condicional de línea base asignadas, pero se le puede dar acceso a los sitios de SharePoint con protección sensible o altamente regulada.

- Si James obtiene acceso a un sitio sensible o altamente regulado, es miembro del uso de su equipo, se concede su acceso siempre que su equipo sea compatible.
- Si James obtiene acceso a un sitio confidencial, es miembro del uso de su teléfono no administrado, lo que se permite a los usuarios de línea base, recibirá acceso solo del explorador al sitio confidencial debido a la Directiva de acceso de dispositivos configurada para este sitio.
- Si James obtiene acceso a un sitio altamente regulado, es miembro del uso de su teléfono no administrado, se bloqueará debido a la Directiva de acceso configurada para este sitio. Solo puede acceder a este sitio mediante su equipo administrado y compatible.

## <a name="next-step"></a>Paso siguiente

![Paso 4: directivas para las aplicaciones en la nube de Microsoft 365](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Configure las directivas de acceso condicional para:

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)

