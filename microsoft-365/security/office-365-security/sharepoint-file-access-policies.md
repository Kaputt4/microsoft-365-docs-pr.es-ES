---
title: 'Directivas de documentos seguros recomendadas: Microsoft 365 para empresas | Microsoft Docs'
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
ms.openlocfilehash: 6effe1ffefaf7faeb90258163c539cdddcec2679
ms.sourcegitcommit: a4729532278de62f80f2160825d446f6ecd36995
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2022
ms.locfileid: "64570005"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>Recomendaciones de directiva para proteger SharePoint sitios y archivos

En este artículo se describe cómo implementar las directivas recomendadas Confianza cero identidad y acceso a dispositivos para proteger SharePoint y OneDrive para la Empresa. Esta guía se basa en las directivas [comunes de acceso a dispositivos y identidades](identity-access-policies.md).

Estas recomendaciones se basan en tres niveles diferentes de seguridad y protección para archivos SharePoint que se pueden aplicar en función de la granularidad de sus **necesidades: punto** de **partida, seguridad** empresarial y **especializada**. Puede obtener más información sobre estos niveles de seguridad y los sistemas operativos de cliente recomendados, a los que se hace referencia en estas recomendaciones [en la introducción](microsoft-365-policies-configurations.md).

Además de implementar esta guía, asegúrese de configurar los sitios SharePoint con la cantidad de protección adecuada, incluida la configuración de los permisos adecuados para el contenido de seguridad especializado y empresarial.

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a>Actualizar directivas comunes para incluir SharePoint y OneDrive para la Empresa

Para proteger los archivos de SharePoint y OneDrive, en el siguiente diagrama se muestran las directivas que se actualizarán a partir de las directivas comunes de acceso a dispositivos y identidades.

:::image type="content" source="../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png" alt-text="Resumen de las actualizaciones de directivas para proteger el acceso a SharePoint" lightbox="../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png":::

Si ha incluido SharePoint al crear las directivas comunes, solo necesita crear las nuevas directivas. Para las directivas de acceso condicional, SharePoint incluye OneDrive.

Las nuevas directivas implementan la protección de dispositivos para el contenido de seguridad especializado y empresarial mediante la aplicación de requisitos de acceso específicos a SharePoint que especifique.

En la tabla siguiente se enumeran las directivas que necesita revisar y actualizar o crear nuevas para SharePoint. Las directivas comunes se vinculan a las instrucciones de configuración asociadas en [el artículo Identidad común y directivas de acceso a dispositivos](identity-access-policies.md) .

|Nivel de protección|Directivas|Más información|
|---|---|---|
|**Punto de inicio**|[Requerir MFA cuando el riesgo de inicio de sesión *es medio* o *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Incluya SharePoint en la asignación de aplicaciones en la nube.|
||[Bloquear a los clientes que no sean compatibles con la autenticación moderna](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|Incluya SharePoint en la asignación de aplicaciones en la nube.|
||[Aplicar directivas de protección de datos de APP](identity-access-policies.md#apply-app-data-protection-policies)|Asegúrate de que todas las aplicaciones recomendadas estén incluidas en la lista de aplicaciones. Asegúrese de actualizar la directiva para cada plataforma (iOS, Android, Windows).|
||[Usar restricciones aplicadas por la aplicación en SharePoint](#use-app-enforced-restrictions-in-sharepoint)|Agregue esta nueva directiva. Esto indica Azure Active Directory (Azure AD) que use la configuración especificada en SharePoint. Esta directiva se aplica a todos los usuarios, pero solo afecta al acceso a los sitios incluidos en SharePoint de acceso.|
|**Empresarial**|[Requerir MFA cuando el riesgo de inicio de sesión *es bajo*, *medio* o *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Incluya SharePoint en las asignaciones de aplicaciones en la nube.|
||[Requerir equipos y *dispositivos móviles* compatibles](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Incluye SharePoint en la lista de aplicaciones en la nube.|
||[SharePoint de control de acceso](#sharepoint-access-control-policies): permitir el acceso de solo explorador a sitios SharePoint específicos desde dispositivos no administrados.|Esto evita la edición y descarga de archivos. Use PowerShell para especificar sitios.|
|**Seguridad especializada**|[*Requerir* siempre MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Incluya SharePoint en la asignación de aplicaciones en la nube.|
||[SharePoint de control de acceso](#use-app-enforced-restrictions-in-sharepoint): bloquear el acceso a sitios de SharePoint específicos desde dispositivos no administrados.|Use PowerShell para especificar sitios.|

## <a name="use-app-enforced-restrictions-in-sharepoint"></a>Usar restricciones aplicadas por la aplicación en SharePoint

Si implementa controles de acceso en SharePoint, las directivas de acceso condicional se crean en Azure AD para decirle a Azure AD que aplique las directivas que configure en SharePoint. De forma predeterminada, esta directiva se aplica a todos los usuarios, pero solo afecta al acceso a los sitios que especifique mediante PowerShell al crear los controles de acceso en SharePoint. La directiva también se puede establecer en el ámbito de usuarios, grupos o sitios específicos.

Para configurar esta directiva, vea "Bloquear o limitar el acceso a colecciones de sitios SharePoint o cuentas de OneDrive" en Controlar el acceso desde [dispositivos no administrados](/sharepoint/control-access-from-unmanaged-devices).

## <a name="sharepoint-access-control-policies"></a>SharePoint de control de acceso

Microsoft recomienda proteger el contenido de los sitios SharePoint con contenido de seguridad empresarial y especializado con controles de acceso a dispositivos. Para ello, cree una directiva que especifique el nivel de protección y los sitios a los que aplicar la protección.

- Enterprise web: permitir el acceso solo del explorador. Esto impide que los usuarios editen y descarguen archivos.
- Sitios de seguridad especializados: bloquear el acceso desde dispositivos no administrados.

Vea "Bloquear o limitar el acceso a colecciones de SharePoint de sitios o cuentas OneDrive específicas" en Controlar el acceso desde [dispositivos no administrados](/sharepoint/control-access-from-unmanaged-devices).

## <a name="how-these-policies-work-together"></a>Cómo funcionan conjuntamente estas directivas

Es importante comprender que los permisos SharePoint sitio se basan normalmente en la necesidad empresarial de acceso a los sitios. Estos permisos los administran los propietarios del sitio y pueden ser altamente dinámicos. El SharePoint de acceso a dispositivos garantiza la protección de estos sitios, independientemente de si los usuarios están asignados Azure AD un grupo asociado con el punto de partida, la empresa o la protección de seguridad especializada.

En la siguiente ilustración se proporciona un ejemplo de cómo SharePoint de acceso a dispositivos protegen el acceso a los sitios de un usuario.

:::image type="content" source="../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png" alt-text="Un ejemplo de cómo las directivas SharePoint de acceso a dispositivos protegen los sitios" lightbox="../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png":::

James tiene asignadas directivas de acceso condicional de punto de partida, pero se le puede dar acceso a SharePoint con protección de seguridad especializada o empresarial.

- Si James accede a un sitio del que es miembro con protección de seguridad especializada o empresarial mediante su PC, se concede su acceso.
- Si James accede a un sitio de protección empresarial, es miembro del uso de su teléfono no administrado, que está permitido para los usuarios de punto de partida, recibirá acceso de solo explorador al sitio de empresa debido a la directiva de acceso de dispositivos configurada para este sitio.
- Si James tiene acceso a un sitio de seguridad especializado, es miembro del uso de su teléfono no administrado, se bloqueará debido a la directiva de acceso configurada para este sitio. Solo puede acceder a este sitio con su equipo administrado.

## <a name="next-step"></a>Paso siguiente

:::image type="content" source="../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png" alt-text="Paso 4: Directivas para Microsoft 365 aplicaciones en la nube" lightbox="../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png":::


Configurar directivas de acceso condicional para:

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)
