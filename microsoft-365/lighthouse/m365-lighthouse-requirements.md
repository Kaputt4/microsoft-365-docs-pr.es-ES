---
title: Requisitos para Microsoft 365 Lighthouse
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Para proveedores de servicios administrados (MSP), obtenga una lista de requisitos para usar Microsoft 365 Lighthouse.
ms.openlocfilehash: 9c87744053ffe3bace90534287cd2b81697f3554
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395352"
---
# <a name="requirements-for-microsoft-365-lighthouse"></a>Requisitos para Microsoft 365 Lighthouse

> [!NOTE]
> Las características descritas en este artículo están en Versión preliminar, están sujetas a cambios y solo están disponibles para los partners que cumplan los requisitos enumerados en este artículo. Si su organización no tiene Microsoft 365 Lighthouse, vea [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).

Microsoft 365 Lighthouse es un portal de administración que ayuda a los proveedores de servicios administrados (MSP) a proteger y administrar dispositivos, datos y usuarios a escala para clientes de pequeñas y medianas empresas (SMB).  

Los MSP deben estar inscritos en el programa Proveedor de soluciones en la nube (CSP) como revendedor indirecto o socio de factura directa para usar Microsoft 365 Lighthouse.  

Además, cada inquilino de cliente MSP debe cumplir los requisitos Microsoft 365 Lighthouse requisitos siguientes: 
 
- Privilegios de administrador delegados (DAP) para msp 
- Al menos una Microsoft 365 Empresa Premium licencia 
- Menos de 500 usuarios con licencia  

## <a name="requirements-for-enablingdevice-management"></a>Requisitos para habilitar la administración de dispositivos   

Para ver los dispositivos de inquilino del cliente en las páginas de administración de dispositivos, un MSP debe:    

- Inscribir todos los dispositivos de cliente en Microsoft Endpoint Manager (MEM).Para obtener más información, vea [Inscribir dispositivos en Microsoft Intune](/mem/intune/enrollment/).
- Asignar directivas de cumplimiento a todos los dispositivos de cliente.Para obtener más información, vea [Create a compliance policy in Microsoft Intune](/mem/intune/protect/create-compliance-policy). 

## <a name="requirements-for-enabling-usermanagement"></a>Requisitos para habilitar la administración de usuarios 

Para que los datos de los clientes se muestren en informes en páginas de administración de usuarios, incluidos usuarios arriesgados, autenticación multifactor y restablecimiento de contraseña, los inquilinos de clientes deben tener licencias para Azure Active Directory Premium P1 o posterior. Azure AD Premium P1 se incluye con Microsoft 365 Empresa Premium.   

## <a name="requirements-for-enablingthreat-management"></a>Requisitos para habilitar la administración de amenazas 

Para ver los dispositivos de inquilino del cliente y las amenazas en las páginas de administración de amenazas, debe inscribir todos los dispositivos de inquilino del cliente en Microsoft Endpoint Manager (MEM) y protegerlos ejecutando Antivirus de Microsoft Defender.  

Para obtener más información, vea [Inscribir dispositivos en Microsoft Intune](/mem/intune/enrollment/).  

Antivirus de Microsoft Defender forma parte del Windows operativo y está habilitado de forma predeterminada en dispositivos que ejecutan Windows 10.  

> [!NOTE] 
> Si usa una solución antivirus que no es de Microsoft y no Antivirus de Microsoft Defender, Antivirus de Microsoft Defender se deshabilita automáticamente. Al desinstalar la solución antivirus que no es de Microsoft, Antivirus de Microsoft Defender se activa automáticamente para proteger los dispositivos Windows amenazas.    

## <a name="related-content"></a>Contenido relacionado   

[Configurar Microsoft 365 Lighthouse seguridad del portal](m365-lighthouse-configure-portal-security.md) (artículo)\
[Microsoft 365 Lighthouse de la página de cumplimiento de dispositivos](m365-lighthouse-device-compliance-page-overview.md) (artículo)\
[Microsoft 365 Lighthouse de la página Usuarios](m365-lighthouse-users-page-overview.md) (artículo)\
[Microsoft 365 Lighthouse de la página de administración de amenazas](m365-lighthouse-threat-management-page-overview.md) (artículo)\
[Microsoft 365 Lighthouse preguntas más frecuentes](m365-lighthouse-faq.yml)   (artículo)

