---
title: 'Fase 1: Infraestructura de red para Microsoft 365 Enterprise'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Los pasos para implementar la infraestructura de red de Microsoft 365 Enterprise.
ms.openlocfilehash: 9b8c23d543eca97147801d70e42de7105266c52d
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "33399964"
---
# <a name="phase-1-networking-infrastructure-for-microsoft-365-enterprise"></a>Fase 1: Infraestructura de red para Microsoft 365 Enterprise

![](./media/deploy-foundation-infrastructure/networking_icon.png)

Microsoft 365 Enterprise incluye Office 365 y Microsoft Intune como parte de Enterprise Management + Security (EMS). Ambos servicios en la nube se basan en la seguridad, rendimiento y confiabilidad de conexiones de los dispositivos del cliente a través de Internet o circuitos dedicados. Para hospedar estos servicios y hacer que estén disponibles para los clientes de todo el mundo, Microsoft ha diseñado una infraestructura de red que destaca por el rendimiento e integración. 

En esta fase, se describen las consideraciones clave para crear una conexión estable a los servicios en la nube de Microsoft 365 Enterprise. Para obtener información general, vea [Principios de redes de Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).

>[!Note]
>Si ya implementó una infraestructura de red, vea los [criterios de salida](networking-exit-criteria.md) de esta fase para asegurarse de que cumple con las condiciones obligatorias y opcionales de Microsoft 365 Enterprise.

## <a name="plan-and-deploy-your-microsoft-365-enterprise-networking-infrastructure"></a>Planear e implementar la infraestructura de red de Microsoft 365 Enterprise 

Siga este procedimiento para preparar la infraestructura de red para los requisitos y funciones de Microsoft 365 Enterprise.

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[Preparar la red para Microsoft 365](networking-provide-bandwidth-cloud-services.md)|
|![](./media/stepnumbers/Step2.png)|[Configurar conexiones a Internet locales para cada oficina](networking-dns-resolution-same-location.md)|
|![](./media/stepnumbers/Step3.png)|[Evitar las redirecciones de red](networking-avoid-network-hairpins.md)|
|![](./media/stepnumbers/Step4.png)|[Configurar la omisión de tráfico](networking-configure-proxies-firewalls.md)|
|![](./media/stepnumbers/Step5.png)|[Optimizar el rendimiento del servicio de Office 365 y el cliente](networking-optimize-tcp-performance.md)|


Cuando complete estos pasos, vaya a los [criterios de salida](networking-exit-criteria.md) de esta fase para asegurarse de que cumple con las condiciones obligatorias y opcionales de Microsoft 365 Enterprise.

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Cómo Microsoft migra a Microsoft 365 Enterprise

Eche un vistazo en Microsoft y aprenda cómo se prepara la empresa para una red de Microsoft optimizada para los servicios de nube de Office 365 con [Optimización del rendimiento de red para Microsoft Office 365](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365).

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Cómo Contoso implementó Microsoft 365 Enterprise

Vea cómo Contoso Corporation, una empresa multinacional ficticia pero representativa, [optimizó su red](contoso-networking.md) para los servicios en la nube de Microsoft 365.

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Siguiente paso

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[Preparar la red para Microsoft 365](networking-provide-bandwidth-cloud-services.md)|

