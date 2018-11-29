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
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Los pasos para implementar la infraestructura de red de Microsoft 365 Enterprise.
ms.openlocfilehash: d575d8c3156ac1fc1a8a2bca96c875d4587ebf05
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871420"
---
# <a name="phase-1-networking-infrastructure-for-microsoft-365-enterprise"></a>Fase 1: Infraestructura de red para Microsoft 365 Enterprise

![](./media/deploy-foundation-infrastructure/networking_icon.png)

En Microsoft 365 Enterprise, se incluyen Office 365 y Windows Intune como parte de Enterprise Mobility + Security (EMS). Estos dos servicios basados en la nube usan la seguridad, el rendimiento y la confiabilidad de las conexiones de dispositivos cliente por Internet o con circuitos dedicados. Para hospedar estos servicios y ofrecerlos a clientes de todo el mundo, Microsoft diseñó una infraestructura de red que da prioridad al rendimiento y la integración. 

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

