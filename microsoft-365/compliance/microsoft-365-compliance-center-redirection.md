---
title: Redirigir usuarios desde el Office 365 seguridad y cumplimiento al Centro de cumplimiento de Microsoft 365
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.service: O365-seccomp
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
description: Obtenga información sobre cómo redirigir automáticamente Office 365 usuarios del Centro de seguridad y cumplimiento al Centro de cumplimiento de Microsoft 365..
ms.collection: M365-security-compliance
ms.openlocfilehash: d31cb4d86d914c9406996c4e6fdf7bab9c5d02e0
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60201042"
---
# <a name="redirect-users-from-the-office-365-security-and-compliance-center-to-the-microsoft-365-compliance-center"></a>Redirigir usuarios desde el Office 365 seguridad y cumplimiento al Centro de cumplimiento de Microsoft 365

En este artículo se explica cómo funciona la redirección automática para los usuarios que tienen acceso a soluciones de cumplimiento desde el Centro de seguridad y cumplimiento de Office 365 (protection.office.com) hasta el Centro de cumplimiento de Microsoft 365 (compliance.microsoft.com).

## <a name="what-to-expect"></a>Qué esperar

La redirección automática está habilitada de forma predeterminada para todos los usuarios que tienen acceso a soluciones relacionadas con el cumplimiento en Office 365 seguridad y cumplimiento (protection.office.com):

- [eDiscovery avanzado](overview-ediscovery-20.md)
- [Cumplimiento de las comunicaciones](communication-compliance.md)
- [Búsqueda de contenido](search-for-content.md)
- [Core eDiscovery](get-started-core-ediscovery.md)
- [Clasificación de datos](data-classification-overview.md)
- [Prevención de pérdida de datos (DLP)](dlp-learn-about-dlp.md)
- [Solicitudes de interesados](/compliance/regulatory/gdpr-manage-gdpr-data-subject-requests-with-the-dsr-case-tool)
- [Gobierno de información](manage-information-governance.md)
- [Administración de registros](records-management.md)

Los usuarios se enruta automáticamente a las mismas soluciones de cumplimiento en el Centro de cumplimiento de Microsoft 365 (compliance.microsoft.com).

Esta característica y los controles asociados no habilitan la redirección automática de características de seguridad para Microsoft Defender para Office 365. Para habilitar el redireccionamiento de características de seguridad, vea [Redirecting accounts from Microsoft Defender for Office 365 to the Microsoft 365 security center](/microsoft-365/security/defender/microsoft-365-security-mdo-redirection) para obtener más información.

## <a name="can-i-go-back-to-using-the-former-portal"></a>¿Puedo volver a usar el portal anterior?

Si algo no funciona para usted o si hay algo que no puede completar a través del portal de Centro de cumplimiento de Microsoft 365, puede deshabilitar temporalmente el redireccionamiento automático para todos los usuarios.

> [!IMPORTANT]
> El Centro de cumplimiento de Microsoft 365 es el portal de administración de reemplazo para soluciones de cumplimiento actualmente administradas en el centro de seguridad y cumplimiento Office 365 de cumplimiento. Todas Microsoft 365 de cumplimiento normativo se administrarán únicamente en el Centro de cumplimiento de Microsoft 365. Deshabilitar la redirección a la Centro de cumplimiento de Microsoft 365 debe considerarse una solución a corto plazo.

Para volver al Centro Office 365 seguridad y cumplimiento (protection.microsoft.com) para todos los usuarios, siga estos pasos:

1. Inicie sesión en el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com) como administrador global o mediante cualquier cuenta con permisos de administrador de cumplimiento en Azure Active Directory.
2. Vaya **a** Configuración  >  **redirección del centro de cumplimiento**.
3. Alterna la opción Redirección automática a **Desactivado**.
4. Seleccione **Desactivar y** compartir comentarios cuando se le pida.

Una vez deshabilitado, los usuarios ya no se enrutarán a compliance.microsoft.com y se dirigirán al Centro de seguridad y cumplimiento de Office 365 (protection.microsoft.com). Los administradores globales o de cumplimiento pueden habilitar esta configuración de nuevo en cualquier momento.

## <a name="related-information"></a>Información relacionada

- [Centro de cumplimiento de Microsoft 365 información general](/microsoft-365/compliance/microsoft-365-compliance-center)
