---
title: Comparación de características de seguridad en planes de Microsoft 365 para pequeñas y medianas empresas
description: ¿Cómo se compara Defender para empresas con Defender para punto de conexión y Microsoft 365 Empresa Premium? Vea lo que se incluye en cada plan para que pueda tomar una decisión más informada para su empresa.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: reference
ms.service: microsoft-365-security
ms.subservice: mdb
ms.localizationpriority: medium
ms.date: 08/30/2022
ms.reviewer: shlomiakirav
ms.collection:
- SMB
- m365-initiative-defender-business
- m365-security-compliance
f1.keywords: NOCSH
ms.openlocfilehash: 622b1ab33ea2168ee7da050d0ad6a06ff7bf5ba0
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2022
ms.locfileid: "67598161"
---
# <a name="compare-security-features-in-microsoft-365-plans-for-small-and-medium-sized-businesses"></a>Comparación de características de seguridad en planes de Microsoft 365 para pequeñas y medianas empresas

Microsoft ofrece una amplia variedad de soluciones y servicios en la nube, incluidos planes para pequeñas y medianas empresas. Por ejemplo, [Microsoft 365 Empresa Premium](../../business/microsoft-365-business-overview.md) incluye funcionalidades de seguridad y administración de dispositivos, junto con características de productividad como las aplicaciones de Office. En este artículo se describen las características de seguridad de Microsoft 365 Empresa Premium, Microsoft Defender para Empresas y [Microsoft Defender para punto de conexión](../defender-endpoint/microsoft-defender-endpoint.md).


**Use este artículo para**:

- [Compare Microsoft Defender para Empresas con Microsoft 365 Empresa Premium](#compare-microsoft-defender-for-business-to-microsoft-365-business-premium).
- [Compare Defender para empresas (independiente) con las ofertas empresariales de Defender para punto de conexión](#compare-microsoft-defender-for-business-to-microsoft-defender-for-endpoint-plans-1-and-2).

> [!TIP]
> Defender for Business está disponible como una solución de seguridad independiente para pequeñas y medianas empresas. Defender for Business ahora se incluye en Microsoft 365 Empresa Premium. Si ya tiene Microsoft 365 Empresa Básico o Estándar, considere la posibilidad de actualizar a Microsoft 365 Empresa Premium o agregar Defender for Business a la suscripción actual para obtener más funcionalidades de protección contra amenazas para los dispositivos.

## <a name="compare-microsoft-defender-for-business-to-microsoft-365-business-premium"></a>Comparar Microsoft Defender para Empresas con Microsoft 365 Empresa Premium

> [!NOTE]
> En este artículo se proporciona información general de alto nivel de las características y funcionalidades que se incluyen en Microsoft Defender para Empresas (como un plan independiente) y Microsoft 365 Empresa Premium (que incluye Defender para empresas). No está pensado para ser una descripción del servicio o un documento de contrato de licencia. Para obtener información más detallada, consulte [Guía de licencias de Microsoft 365 para el cumplimiento de & de seguridad](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

| Plan | Descripción |
|:---|:---|
| **[Defender para empresas](mdb-overview.md)** (independiente) | **Protección antivirus, antimalware y ransomware para dispositivos**<ul><li>[Protección de última generación](../defender-endpoint/microsoft-defender-antivirus-in-windows-10.md) (protección antivirus/antimalware en dispositivos junto con protección en la nube)</li><li>[Reducción de la superficie expuesta a ataques](../defender-endpoint/overview-attack-surface-reduction.md) (protección de red, firewall y reglas de reducción de superficie expuesta a ataques) <sup>[[a](#fna)]</sup></li><li>[Detección y respuesta de puntos de conexión](../defender-endpoint/overview-endpoint-detection-response.md) (detección basada en comportamiento y acciones de respuesta manual)</li><li>[Investigación y respuesta automatizadas](../defender/m365d-autoir.md) (con recuperación automática para las amenazas detectadas)</li><li>[Administración de vulnerabilidades de Microsoft Defender](mdb-view-tvm-dashboard.md) (ver los dispositivos expuestos y las recomendaciones)</li><li>[Compatibilidad multiplataforma para dispositivos](mdb-onboard-devices.md) (Windows, Mac, iOS y Android) <sup>[[b](#fnb)]</sup></li><li>[Administración centralizada e informes](mdb-get-started.md) (portal de Microsoft 365 Defender)</li><li>[API para la integración](../defender-endpoint/management-apis.md) (para asociados de Microsoft o sus herramientas y aplicaciones personalizadas)</li></ul> |
| **[Microsoft 365 Empresa Premium](../../business-premium/index.md)** | **Funcionalidades de Defender para empresas, junto con productividad y funcionalidades de seguridad adicionales**<ul><li>[Microsoft 365 Empresa Estándar](../../admin/admin-overview/what-is-microsoft-365-for-business.md) (aplicaciones y servicios de Office y Microsoft Teams)</li><li>[Activación de equipos compartidos](/deployoffice/overview-shared-computer-activation) (para implementar Aplicaciones Microsoft 365)</li><li>[Windows 10/11 Empresa](../../business-premium/m365bp-upgrade-windows-10-pro.md) (actualización de versiones anteriores de Windows Pro)</li><li>[Windows Autopilot](/mem/autopilot/windows-autopilot) (para configurar y configurar dispositivos Windows)</li><li>[Exchange Online Protection](../office-365-security/exchange-online-protection-overview.md) (antiphishing, antispam, antimalware e inteligencia spoof para correo electrónico)</li><li>[Microsoft Defender para Office 365 Plan 1](../office-365-security/overview.md) (antiphishing avanzado, detecciones en tiempo real, datos adjuntos seguros, vínculos seguros)</li><li>[Archivado de expansión automática](../../compliance/autoexpanding-archiving.md) (para correo electrónico)</li><li>[Azure Active Directory Premium Plan 1](/azure/active-directory/fundamentals/active-directory-whatis) (administración de identidades)</li><li>[Microsoft Intune](/mem/intune/fundamentals/what-is-intune) (incorporación y administración de dispositivos)</li><li>[Plan 1 de Azure Information Protection Premium](/azure/information-protection/what-is-information-protection) (protección para información confidencial)</li><li>[Azure Virtual Desktop](/azure/virtual-desktop/overview) (máquinas virtuales seguras y administradas de forma centralizada en la nube)</li></ul> |

  
(<a id="fna">a</a>) Microsoft Intune es necesario modificar o personalizar las reglas de reducción de superficie expuesta a ataques. Intune se incluye en Microsoft 365 Empresa Premium.

(<a id="fnb">b</a>) se requiere Microsoft Intune para incorporar dispositivos iOS y Android. Consulte [Incorporación de dispositivos a Microsoft Defender para empresas](mdb-onboard-devices.md).

## <a name="compare-microsoft-defender-for-business-to-microsoft-defender-for-endpoint-plans-1-and-2"></a>Comparar Microsoft Defender para Empresas con los planes 1 y 2 de Microsoft Defender para punto de conexión

Defender for Business ofrece las funcionalidades de nivel empresarial de Defender para punto de conexión a pequeñas y medianas empresas. En la tabla siguiente se comparan las características y funcionalidades de seguridad de Defender para empresas con las ofertas empresariales, Microsoft Defender para punto de conexión los planes 1 y 2.

|Característica o funcionalidad|[Defender para Empresas](mdb-overview.md)<br/>(independiente)|[Plan 1 de Defender para punto de conexión](../defender-endpoint/defender-endpoint-plan-1.md)<br/>(para clientes empresariales) |[Plan 2 de Defender para punto de conexión](../defender-endpoint/microsoft-defender-endpoint.md)<br/>(para clientes empresariales) |
|---|---|---|---|
|[Administración centralizada](../defender-endpoint/manage-atp-post-migration.md) <sup>[[1](#fn1)]</sup> | :::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Included"::: |:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Included":::|:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Included":::|
|[Configuración de cliente simplificada](mdb-simplified-configuration.md)|:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Included":::| | |
|[Administración de vulnerabilidades de Microsoft Defender](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)|:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Included":::| |:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Included":::|
|[Capacidades de reducción de superficie expuesta a ataques](../defender-endpoint/overview-attack-surface-reduction.md)|:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Included":::|:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Included":::|:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Included":::|
|[Protección de última generación](../defender-endpoint/next-generation-protection.md)|:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Included":::|:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Included":::|:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Included":::|
|[Detección y respuesta de puntos de conexión](../defender-endpoint/overview-endpoint-detection-response.md) <sup>[[2](#fn2)]</sup>|:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Included"::: | |:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Included":::|
|[Investigación y respuesta automatizadas](../defender-endpoint/automated-investigations.md) <sup>[[3](#fn3)]</sup>|:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Included"::: ||:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Included":::|
|[Búsqueda de amenazas](../defender-endpoint/advanced-hunting-overview.md) y seis meses de retención de datos <sup>[[4](#fn4)]</sup> | | |:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Included":::|
|[Análisis de amenazas](../defender-endpoint/threat-analytics.md) <sup>[[5](#fn5)]</sup>|:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Included"::: | |:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Included":::|
|[Compatibilidad multiplataforma.](../defender-endpoint/minimum-requirements.md) <br/>(Sistema operativo Windows, Mac, iOS y Android) <sup>[[6](#fn6)]</sup>|:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Included"::: |:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Included":::|:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Included":::|
|[Expertos en amenazas de Microsoft](../defender-endpoint/microsoft-threat-experts.md)| | |:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Included":::|
|API de asociados|:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Included":::|:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Included":::|:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Included":::|
|[integración Microsoft 365 Lighthouse](../../lighthouse/m365-lighthouse-overview.md) <br/>(Para ver los incidentes de seguridad entre los inquilinos del cliente) <sup>[[7](#fn7)]</sup>|:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Included"::: |:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Included"::: |:::image type="content" source="../../media/d238e041-6854-4a78-9141-049224df0795.png" alt-text="Included"::: |

(<a id="fn1">1</a>) Incorporación y administración de dispositivos en el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) o mediante Microsoft Intune, administrados en el Centro de administración de Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)).

(<a id="fn2">2</a>) Las funcionalidades de detección y respuesta de puntos de conexión (EDR) en Defender for Business incluyen la detección basada en comportamiento y las siguientes acciones de respuesta manual: 
- Ejecutar examen de antivirus
- Aislar el dispositivo
- Detener y poner en cuarentena un archivo
- Adición de un indicador para bloquear o permitir un archivo

(<a id="fn3">3</a>) En Defender para empresas, la investigación y la respuesta automatizadas están activadas de forma predeterminada, en todo el inquilino. Desactivar la investigación y la respuesta automatizadas afecta a la protección en tiempo real. Consulte [Revisión de la configuración de las características avanzadas](mdb-configure-security-settings.md#review-settings-for-advanced-features).  

(<a id="fn4">4</a>) No hay ninguna vista de escala de tiempo en Defender para empresas.

(<a id="fn5">5</a>) En Defender para empresas, el análisis de amenazas está optimizado para pequeñas y medianas empresas.

(<a id="fn6">6</a>) Consulte [Incorporación de dispositivos para Microsoft Defender para Empresas](mdb-onboard-devices.md).

(<a id="fn7">7</a>) La capacidad de ver incidentes entre inquilinos mediante Defender para punto de conexión es nueva.

Consulte también [Comparar planes de seguridad de puntos de conexión de Microsoft](../defender-endpoint/defender-endpoint-plan-1-2.md).

## <a name="next-steps"></a>Pasos siguientes

- [Consulte los requisitos de Microsoft Defender para Empresas](mdb-requirements.md)
- [Obtener Microsoft Defender para Empresas](get-defender-business.md)
- [Aprenda a configurar y configurar Microsoft Defender para Empresas](mdb-setup-configuration.md)
