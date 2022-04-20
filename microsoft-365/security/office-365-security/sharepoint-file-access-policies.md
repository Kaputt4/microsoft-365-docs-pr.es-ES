---
title: 'Directivas de documentos seguros recomendadas: Microsoft 365 para | empresariales Microsoft Docs'
description: Se explican las directivas recomendadas por Microsoft para proteger el acceso a archivos de SharePoint.
ms.author: dansimp
author: dansimp
manager: dansimp
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
ms.openlocfilehash: 3a2a8e5be8fb78824e8670f94a2e087da9538329
ms.sourcegitcommit: 45bc65972d4007b2aa7760d4457a0d2699f81926
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2022
ms.locfileid: "64972153"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>Recomendaciones de directiva para proteger SharePoint sitios y archivos

En este artículo se describe cómo implementar las directivas de acceso a dispositivos e identidades de Confianza cero recomendadas para proteger SharePoint y OneDrive para la Empresa. Esta guía se basa en las [directivas comunes de acceso a dispositivos e identidades](identity-access-policies.md).

Estas recomendaciones se basan en tres niveles diferentes de seguridad y protección para SharePoint archivos que se pueden aplicar en función de la granularidad de sus necesidades: **punto de partida**, **empresa** y **seguridad especializada**. Puede obtener más información sobre estos niveles de seguridad y los sistemas operativos de cliente recomendados a los que hacen referencia estas recomendaciones en [la introducción](microsoft-365-policies-configurations.md).

Además de implementar esta guía, asegúrese de configurar SharePoint sitios con la cantidad adecuada de protección, incluidos los permisos adecuados para el contenido de seguridad especializado y empresarial.

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a>Actualización de directivas comunes para incluir SharePoint y OneDrive para la Empresa

Para proteger los archivos de SharePoint y OneDrive, en el diagrama siguiente se muestran las directivas que se van a actualizar a partir de las directivas comunes de acceso a dispositivos e identidades.

:::image type="content" source="../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png" alt-text="Resumen de las actualizaciones de directivas para proteger el acceso a SharePoint" lightbox="../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png":::

Si incluyó SharePoint al crear las directivas comunes, solo tendrá que crear las nuevas directivas. En el caso de las directivas de acceso condicional, SharePoint incluye OneDrive.

Las nuevas directivas implementan la protección de dispositivos para contenido de seguridad especializado y empresarial mediante la aplicación de requisitos de acceso específicos a SharePoint sitios que especifique.

En la tabla siguiente se enumeran las directivas que debe revisar y actualizar o crear nuevas para SharePoint. Las directivas comunes se vinculan a las instrucciones de configuración asociadas en el artículo [Common identity and device access policies (Directivas comunes de acceso a dispositivos e identidades](identity-access-policies.md) ).

|Nivel de protección|Directivas|Más información|
|---|---|---|
|**Punto de inicio**|[Requerir MFA cuando el riesgo de inicio de sesión es *medio* o *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Incluya SharePoint en la asignación de aplicaciones en la nube.|
||[Bloquear a los clientes que no sean compatibles con la autenticación moderna](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|Incluya SharePoint en la asignación de aplicaciones en la nube.|
||[Aplicación de directivas de protección de datos de APLICACIONES](identity-access-policies.md#apply-app-data-protection-policies)|Asegúrese de que todas las aplicaciones recomendadas se incluyen en la lista de aplicaciones. Asegúrese de actualizar la directiva para cada plataforma (iOS, Android, Windows).|
||[Uso de restricciones aplicadas por la aplicación en SharePoint](#use-app-enforced-restrictions-in-sharepoint)|Agregue esta nueva directiva. Esto indica a Azure Active Directory (Azure AD) que use la configuración especificada en SharePoint. Esta directiva se aplica a todos los usuarios, pero solo afecta al acceso a los sitios incluidos en SharePoint directivas de acceso.|
|**Empresarial**|[Requerir MFA cuando el riesgo de inicio de sesión es *bajo*, *medio* o *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Incluya SharePoint en las asignaciones de aplicaciones en la nube.|
||[Requerir equipos *compatibles y* dispositivos móviles](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Incluya SharePoint en la lista de aplicaciones en la nube.|
||[SharePoint directiva de control de acceso](#sharepoint-access-control-policies): permitir el acceso solo del explorador a sitios SharePoint específicos desde dispositivos no administrados.|Esto impide la edición y descarga de archivos. Use PowerShell para especificar sitios.|
|**Seguridad especializada**|[*Siempre* se requiere MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Incluya SharePoint en la asignación de aplicaciones en la nube.|
||[SharePoint directiva de control de acceso](#use-app-enforced-restrictions-in-sharepoint): bloquear el acceso a sitios SharePoint específicos desde dispositivos no administrados.|Use PowerShell para especificar sitios.|

## <a name="use-app-enforced-restrictions-in-sharepoint"></a>Uso de restricciones aplicadas por la aplicación en SharePoint

Si implementa controles de acceso en SharePoint, las directivas de acceso condicional se crean en Azure AD para indicar a Azure AD que aplique las directivas que configure en SharePoint. De forma predeterminada, esta directiva se aplica a todos los usuarios, pero solo afecta al acceso a los sitios especificados mediante PowerShell al crear los controles de acceso en SharePoint. La directiva también se puede limitar a usuarios, grupos o sitios específicos.

Para configurar esta directiva, consulte "Bloquear o limitar el acceso a colecciones de sitios o cuentas de OneDrive específicas de SharePoint" en [Control del acceso desde dispositivos no administrados](/sharepoint/control-access-from-unmanaged-devices).

## <a name="sharepoint-access-control-policies"></a>SharePoint directivas de control de acceso

Microsoft recomienda proteger el contenido de SharePoint sitios con contenido de seguridad empresarial y especializado con controles de acceso a dispositivos. Para ello, cree una directiva que especifique el nivel de protección y los sitios a los que aplicar la protección.

- Enterprise sitios: permitir el acceso solo al explorador. Esto impide que los usuarios editen y descarguen archivos.
- Sitios de seguridad especializados: bloquear el acceso desde dispositivos no administrados.

Consulte "Bloquear o limitar el acceso a colecciones de sitios o cuentas de OneDrive específicas de SharePoint" en [Control del acceso desde dispositivos no administrados](/sharepoint/control-access-from-unmanaged-devices).

## <a name="how-these-policies-work-together"></a>Cómo funcionan juntas estas directivas

Es importante comprender que los permisos de SharePoint sitio suelen basarse en la necesidad empresarial de acceso a los sitios. Estos permisos los administran los propietarios del sitio y pueden ser muy dinámicos. El uso de SharePoint directivas de acceso a dispositivos garantiza la protección de estos sitios, independientemente de si los usuarios están asignados a un grupo de Azure AD asociado con el punto de partida, la empresa o la protección de seguridad especializada.

En la ilustración siguiente se proporciona un ejemplo de cómo SharePoint directivas de acceso a dispositivos protegen el acceso a sitios de un usuario.

:::image type="content" source="../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png" alt-text="Ejemplo de cómo SharePoint directivas de acceso a dispositivos protegen los sitios" lightbox="../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png":::

James tiene asignadas directivas de acceso condicional de punto de partida, pero se le puede conceder acceso a sitios SharePoint con protección de seguridad empresarial o especializada.

- Si James accede a un sitio del que es miembro con protección de seguridad empresarial o especializada mediante su PC, se concede su acceso.
- Si James accede a un sitio de protección empresarial al que es miembro del uso de su teléfono no administrado, que está permitido para los usuarios de punto de partida, recibirá acceso de solo explorador al sitio de empresa debido a la directiva de acceso del dispositivo configurada para este sitio.
- Si James accede a un sitio de seguridad especializado del que es miembro mediante su teléfono no administrado, se le bloqueará debido a la directiva de acceso configurada para este sitio. Solo puede acceder a este sitio mediante su pc administrado.

## <a name="next-step"></a>Paso siguiente

:::image type="content" source="../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png" alt-text="Paso 4: Directivas para Microsoft 365 aplicaciones en la nube" lightbox="../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png":::

Configurar directivas de acceso condicional para:

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)
