---
title: Requisitos para Microsoft 365 Lighthouse
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
ms-reviewer: crimora
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Para los proveedores de servicios administrados (MSP), obtenga una lista de los requisitos para usar Microsoft 365 Lighthouse.
ms.openlocfilehash: 6ed55b436d110c43ce0a87d12049988105c79c48
ms.sourcegitcommit: d1f51dbd12ceffe6a6aeebffde0f9a744486f2d4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2022
ms.locfileid: "67417442"
---
# <a name="requirements-for-microsoft-365-lighthouse"></a>Requisitos para Microsoft 365 Lighthouse

Microsoft 365 Lighthouse es un portal de administración que ayuda a los proveedores de servicios administrados (CSP) a proteger y administrar dispositivos, datos y usuarios a escala para clientes de pequeñas y medianas empresas (SMB).

Los CSP deben inscribirse en el programa Proveedor de soluciones en la nube (CSP) como revendedor indirecto o asociado de factura directa para usar Lighthouse.

Además, cada inquilino del cliente MSP debe calificar para Lighthouse cumpliendo los siguientes requisitos:

- Debe tener el acceso delegado configurado para que el proveedor de servicios administrados (MSP) pueda administrar el inquilino del cliente*
- Debe tener al menos un Microsoft 365 Empresa Premium, Microsoft 365 E3, Microsoft 365 E5, Windows 365 Business o Microsoft Defender para Empresas Licencia
- No debe tener más de 2500 usuarios con licencia

 \*Se requiere privilegios de Administración delegados granulares (GDAP) más una relación de revendedor indirecto o una relación de privilegios delegados de Administración (DAP) para incorporar clientes a Lighthouse. Si DAP y GDAP coexisten en un inquilino de cliente, los permisos de GDAP tienen prioridad para los técnicos de MSP en grupos de seguridad habilitados para GDAP. Próximamente, los clientes con relaciones solo de GDAP (sin relaciones de revendedor indirecto) podrán incorporarse a Lighthouse.

## <a name="requirements-for-enabling-device-management"></a>Requisitos para habilitar la administración de dispositivos

Para ver los dispositivos de inquilino del cliente en las páginas de administración de dispositivos, un MSP debe:

- Inscriba todos los dispositivos de cliente en Microsoft Endpoint Manager (MEM). Para obtener más información, consulte [Inscripción de dispositivos en Microsoft Intune](/mem/intune/enrollment/).
- Asigne directivas de cumplimiento a todos los dispositivos de cliente. Para obtener más información, vea [Crear una directiva de cumplimiento en Microsoft Intune](/mem/intune/protect/create-compliance-policy).

## <a name="requirements-for-enabling-user-management"></a>Requisitos para habilitar la administración de usuarios

Para que los datos de los clientes se muestren en los informes de las páginas de administración de usuarios, incluidos los usuarios de riesgo, la autenticación multifactor y el restablecimiento de contraseña, los inquilinos del cliente deben tener licencias para Azure Active Directory Premium P1 o posterior. Azure AD Premium P1 incluye Microsoft 365 Empresa Premium y Microsoft 365 E3. Azure AD Premium P2 se incluye con Microsoft 365 E5.

## <a name="requirements-for-enabling-threat-management"></a>Requisitos para habilitar la administración de amenazas

Para ver los dispositivos y amenazas de los inquilinos del cliente en las páginas de administración de amenazas, debe inscribir todos los dispositivos de inquilino del cliente en Microsoft Endpoint Manager (MEM) y protegerlos mediante la ejecución del Antivirus de Microsoft Defender.

Para obtener más información, consulte [Inscripción de dispositivos en Microsoft Intune](/mem/intune/enrollment/).

Antivirus de Microsoft Defender forma parte del sistema operativo Windows y está habilitado de forma predeterminada en dispositivos que ejecutan Windows 10.

> [!NOTE]
> Si usa una solución antivirus que no es de Microsoft y no antivirus de Microsoft Defender, antivirus de Microsoft Defender se deshabilita automáticamente. Al desinstalar la solución antivirus que no es de Microsoft, el Antivirus de Microsoft Defender se activa automáticamente para proteger los dispositivos Windows frente a amenazas.

## <a name="related-content"></a>Contenido relacionado

[Configuración de la seguridad del portal de Microsoft 365 Lighthouse](m365-lighthouse-configure-portal-security.md) (artículo)\
[Información general de la página Cumplimiento de dispositivos en Microsoft 365 Lighthouse](m365-lighthouse-device-compliance-page-overview.md) (artículo)\
[Información general de la página Usuarios de Microsoft 365 Lighthouse](m365-lighthouse-users-page-overview.md) (artículo)\
[Información general de la página Administración de amenazas en Microsoft 365 Lighthouse](m365-lighthouse-threat-management-page-overview.md) (artículo)\
[Preguntas más frecuentes sobre Microsoft 365 Lighthouse](m365-lighthouse-faq.yml) (artículo)
