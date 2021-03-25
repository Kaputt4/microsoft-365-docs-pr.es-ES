---
title: 'Directivas de documentos seguros recomendadas: Microsoft 365 para empresas | Microsoft Docs'
description: Se explican las directivas recomendadas por Microsoft para proteger el acceso a archivos de SharePoint.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
audience: Admin
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: 1771f71e444233ffce60a4a56273d3062fe8b70d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204979"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>Recomendaciones de directiva para proteger archivos y sitios de SharePoint

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- SharePoint Online 


En este artículo se describe cómo implementar las directivas de identidad y acceso a dispositivos recomendadas para proteger SharePoint y OneDrive para la Empresa. Esta guía se basa en las directivas [comunes de acceso a dispositivos y identidades.](identity-access-policies.md)

Estas recomendaciones se basan en tres niveles diferentes de seguridad y protección para archivos de SharePoint que se pueden aplicar en función de la granularidad de sus necesidades: **línea** **base,** confidencial y altamente **regulado.** Puede obtener más información sobre estos niveles de seguridad y los sistemas operativos de cliente recomendados, a los que se hace referencia en estas recomendaciones [en la introducción](microsoft-365-policies-configurations.md).

Además de implementar esta guía, asegúrese de configurar los sitios de SharePoint con la cantidad de protección adecuada, incluida la configuración de permisos adecuados para contenido confidencial y altamente regulado.

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a>Actualizar directivas comunes para incluir SharePoint y OneDrive para la Empresa

Para proteger los archivos de SharePoint y OneDrive, en el siguiente diagrama se muestran las directivas que se actualizarán a partir de las directivas comunes de acceso a dispositivos y identidades.

[![Resumen de las actualizaciones de directivas para proteger el acceso a Teams y sus servicios dependientes](../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)

Si incluyó SharePoint al crear las directivas comunes, solo necesita crear las nuevas directivas. Para las directivas de acceso condicional, SharePoint incluye OneDrive.

Las nuevas directivas implementan la protección de dispositivos para contenido confidencial y altamente regulado mediante la aplicación de requisitos de acceso específicos a los sitios de SharePoint que especifique.

En la tabla siguiente se enumeran las directivas que necesita revisar y actualizar o crear nuevas para SharePoint. Las directivas comunes se vinculan a las instrucciones de configuración asociadas en [el artículo Identidad común y directivas de acceso a dispositivos.](identity-access-policies.md)

|Nivel de protección|Directivas|Más información|
|---|---|---|
|**Baseline**|[Requerir MFA cuando el riesgo de inicio de sesión *es medio* o *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Incluir SharePoint en la asignación de aplicaciones en la nube.|
||[Bloquear a los clientes que no sean compatibles con la autenticación moderna](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|Incluir SharePoint en la asignación de aplicaciones en la nube.|
||[Aplicar directivas de protección de datos de APP](identity-access-policies.md#apply-app-data-protection-policies)|Asegúrate de que todas las aplicaciones recomendadas estén incluidas en la lista de aplicaciones. Asegúrate de actualizar la directiva para cada plataforma (iOS, Android, Windows).|
||[Exigir equipos PC compatibles](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Incluir SharePoint en la lista de aplicaciones en la nube.|
||[Usar restricciones aplicadas por la aplicación en SharePoint](#use-app-enforced-restrictions-in-sharepoint)|Agregue esta nueva directiva. Esto indica a Azure Active Directory (Azure AD) que use la configuración especificada en SharePoint. Esta directiva se aplica a todos los usuarios, pero solo afecta al acceso a los sitios incluidos en las directivas de acceso de SharePoint.|
|**Confidencial**|[Requerir MFA cuando el riesgo de inicio de sesión *es bajo,* *medio* o *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Incluir SharePoint en las asignaciones de aplicaciones en la nube.|
||[Requerir equipos y *dispositivos* móviles compatibles](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Incluir SharePoint en la lista de aplicaciones en la nube.|
||[Directiva de control de acceso de SharePoint:](#sharepoint-access-control-policies)permitir el acceso de solo explorador a sitios específicos de SharePoint desde dispositivos no administrados.|Esto evita la edición y descarga de archivos. Use PowerShell para especificar sitios.|
|**Extremadamente regulado**|[*Requerir* siempre MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Incluir SharePoint en la asignación de aplicaciones en la nube.|
||[Directiva de control de acceso de SharePoint:](#use-app-enforced-restrictions-in-sharepoint)bloquear el acceso a sitios específicos de SharePoint desde dispositivos no administrados.|Use PowerShell para especificar sitios.|
|

## <a name="use-app-enforced-restrictions-in-sharepoint"></a>Usar restricciones aplicadas por la aplicación en SharePoint

Si implementa controles de acceso en SharePoint, debe crear esta directiva de acceso condicional en Azure AD para que le diga a Azure AD que aplique las directivas que configure en SharePoint. Esta directiva se aplica a todos los usuarios, pero solo afecta al acceso a los sitios que especifique con PowerShell al crear los controles de acceso en SharePoint.

Para configurar esta directiva, vea "Bloquear o limitar el acceso a determinadas colecciones de sitios de SharePoint o cuentas de OneDrive" en Control access [from unmanaged devices](/sharepoint/control-access-from-unmanaged-devices).

## <a name="sharepoint-access-control-policies"></a>Directivas de control de acceso de SharePoint

Microsoft recomienda proteger el contenido de los sitios de SharePoint con contenido confidencial y altamente regulado con controles de acceso a dispositivos. Para ello, cree una directiva que especifique el nivel de protección y los sitios a los que aplicar la protección.

- Sitios confidenciales: permitir el acceso solo del explorador. Esto impide que los usuarios editen y descarguen archivos.
- Sitios altamente regulados: bloquear el acceso desde dispositivos no administrados.

Vea "Bloquear o limitar el acceso a colecciones de sitios de SharePoint específicas o cuentas de OneDrive" en [Control access from unmanaged devices](/sharepoint/control-access-from-unmanaged-devices).

## <a name="how-these-policies-work-together"></a>Cómo funcionan conjuntamente estas directivas

Es importante comprender que los permisos de sitio de SharePoint suelen basarse en la necesidad empresarial de acceso a los sitios. Estos permisos los administran los propietarios del sitio y pueden ser altamente dinámicos. El uso de directivas de acceso a dispositivos de SharePoint garantiza la protección de estos sitios, independientemente de si los usuarios están asignados a un grupo de Azure AD asociado con la protección de línea base, confidencial o altamente regulada.

En la siguiente ilustración se proporciona un ejemplo de cómo las directivas de acceso a dispositivos de SharePoint protegen el acceso a los sitios de un usuario.

[![Ejemplo de cómo las directivas de acceso a dispositivos de SharePoint protegen los sitios](../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

[Ver una versión más grande de esta imagen](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

James tiene asignadas directivas de acceso condicional de línea base, pero se le puede dar acceso a sitios de SharePoint con protección confidencial o altamente regulada.

- Si James tiene acceso a un sitio confidencial o altamente regulado, es miembro del uso de su equipo, su acceso se concede siempre que su EQUIPO cumpla con las normas.
- Si James tiene acceso a un sitio confidencial, es miembro del uso de su teléfono no administrado, que está permitido para los usuarios de línea base, recibirá acceso de solo explorador al sitio confidencial debido a la directiva de acceso de dispositivos configurada para este sitio.
- Si James tiene acceso a un sitio altamente regulado, es miembro del uso de su teléfono no administrado, se bloqueará debido a la directiva de acceso configurada para este sitio. Solo puede acceder a este sitio con su equipo administrado y compatible.

## <a name="next-step"></a>Paso siguiente

![Paso 4: Directivas para aplicaciones en la nube de Microsoft 365](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Configurar directivas de acceso condicional para:

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)