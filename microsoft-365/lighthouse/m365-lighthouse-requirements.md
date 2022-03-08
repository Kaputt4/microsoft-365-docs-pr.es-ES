---
title: Requisitos para Microsoft 365 Lighthouse
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
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
description: Para proveedores de servicios administrados (MSP), obtenga una lista de requisitos para usar Microsoft 365 Lighthouse.
ms.openlocfilehash: 51dd2404f03dc58d5975a37c386ba9c8f1333763
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63327257"
---
# <a name="requirements-for-microsoft-365-lighthouse"></a>Requisitos para Microsoft 365 Lighthouse

Microsoft 365 Lighthouse es un portal de administración que ayuda a los proveedores de servicios administrados (MSP) a proteger y administrar dispositivos, datos y usuarios a escala para clientes de pequeñas y medianas empresas (SMB).  

Los MSP deben estar inscritos en el programa Proveedor de soluciones en la nube (CSP) como revendedor indirecto o socio de factura directa para usar Lighthouse.  

Además, cada inquilino de cliente MSP debe cumplir los siguientes requisitos: 
 
- Privilegios de administrador delegados (DAP) o privilegios de administrador delegados pormenorizados (GDAP) para el MSP 
- Al menos una Microsoft 365 Empresa Premium o Microsoft 365 E3 licencia 
- Menos de 1000 usuarios con licencia  

## <a name="requirements-for-enablingdevice-management"></a>Requisitos para habilitar la administración de dispositivos

Para ver los dispositivos de inquilino del cliente en las páginas de administración de dispositivos, un MSP debe:

- Inscribir todos los dispositivos de cliente en Microsoft Endpoint Manager (MEM).Para obtener más información, consulta [Inscribir dispositivos en Microsoft Intune](/mem/intune/enrollment/).
- Asignar directivas de cumplimiento a todos los dispositivos de cliente.Para obtener más información, vea [Create a compliance policy in Microsoft Intune](/mem/intune/protect/create-compliance-policy). 

## <a name="requirements-for-enabling-usermanagement"></a>Requisitos para habilitar la administración de usuarios 

Para que los datos de los clientes se muestren en informes de páginas de administración de usuarios, incluidos usuarios arriesgados, autenticación multifactor y restablecimiento de contraseña, los inquilinos de clientes deben tener licencias para Azure Active Directory Premium P1 o posterior. Azure AD Premium P1 se incluye con Microsoft 365 Empresa Premium y Microsoft 365 E3.   

## <a name="requirements-for-enablingthreat-management"></a>Requisitos para habilitar la administración de amenazas 

Para ver los dispositivos y amenazas del inquilino del cliente en las páginas de administración de amenazas, debe inscribir todos los dispositivos de inquilino del cliente en Microsoft Endpoint Manager (MEM) y protegerlos ejecutando Antivirus de Microsoft Defender.  

Para obtener más información, consulta [Inscribir dispositivos en Microsoft Intune](/mem/intune/enrollment/).  

Antivirus de Microsoft Defender forma parte del sistema operativo Windows y está habilitado de forma predeterminada en dispositivos que ejecutan Windows 10.  

> [!NOTE] 
> Si usa una solución antivirus que no es de Microsoft y no Antivirus de Microsoft Defender, Antivirus de Microsoft Defender se deshabilita automáticamente. Al desinstalar la solución antivirus que no es de Microsoft, Antivirus de Microsoft Defender se activa automáticamente para proteger los dispositivos Windows de amenazas.    

## <a name="related-content"></a>Contenido relacionado

[Configurar Microsoft 365 Lighthouse seguridad del portal](m365-lighthouse-configure-portal-security.md) (artículo)\
[Microsoft 365 Lighthouse de la página de cumplimiento de dispositivos](m365-lighthouse-device-compliance-page-overview.md) (artículo)\
[Microsoft 365 Lighthouse de la página Usuarios (](m365-lighthouse-users-page-overview.md)artículo)\
[Microsoft 365 Lighthouse de la página de administración de amenazas](m365-lighthouse-threat-management-page-overview.md) (artículo)\
[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (article)

