---
title: 'Paso 2: Proporcionar acceso remoto a los servicios y aplicaciones locales'
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-scenario
ms.custom: ''
description: Asegúrese de que los trabajadores remotos puedan tener acceso a los recursos locales y optimizar el acceso a los servicios en la nube de Microsoft 365.
ms.openlocfilehash: 11fb3e37efe67103780fc4d234837da3bc15d97f
ms.sourcegitcommit: 23a90ed17cddf3b0db8d4084c8424f0fabd7b1de
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2022
ms.locfileid: "62886305"
---
# <a name="step-2-provide-remote-access-to-on-premises-apps-and-services"></a>Paso 2: Proporcionar acceso remoto a los servicios y aplicaciones locales

Si su organización usa una solución VPN de acceso remoto, generalmente con servidores VPN en el borde de su red y clientes VPN instalados en los dispositivos de sus usuarios, sus usuarios pueden usar conexiones VPN de acceso remoto para acceder a aplicaciones y servidores locales. Pero es posible que deba optimizar el tráfico a los servicios basados ​​en la nube de Microsoft 365.

Si los usuarios no usan una solución de VPN, puede usar el proxy de aplicación de Azure Active Directory (Azure AD) y la VPN de punto a sitio de Azure (P2S) para ofrecer acceso en función de si todas las aplicaciones se basan en la web.

Estas son las principales configuraciones para acceso remoto:

- Ya está usando una solución de VPN de acceso remoto.
- No está usando una solución de VPN de acceso remoto y desea que los trabajadores remotos usen sus equipos personales.
- No está usando una solución de VPN de acceso remoto, tiene una identidad híbrida y solo necesita el acceso remoto a aplicaciones locales basadas en la web.
- No está usando una solución de VPN de acceso remoto y necesita tener acceso a aplicaciones locales, algunas de las cuales no se basan en la web.

Vea este diagrama de flujo para ver las opciones de configuración de acceso remoto descritas en este artículo.

:::image type="content" source="../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-flowchart.png" alt-text="Diagrama de flujo de configuración de acceso remoto." lightbox="../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-flowchart.png":::

Con conexiones de acceso remoto, también puede usar [Escritorio remoto](https://support.microsoft.com/help/4028379/windows-10-how-to-use-remote-desktop) para conectar a los usuarios a un equipo local. Por ejemplo, un trabajador remoto puede usar Escritorio remoto para conectarse al equipo en su oficina desde su dispositivo Windows, iOS o Android. Una vez que estén conectados de forma remota, podrán usarlo como si estuvieran sentados frente a él.

## <a name="optimize-performance-for-remote-access-vpn-clients-to-microsoft-365-cloud-services"></a>Optimizar el rendimiento de los clientes VPN de acceso remoto a los servicios en la nube de Microsoft 365

Si los trabajadores remotos usan un cliente VPN tradicional para obtener acceso remoto a la red de su organización, compruebe que el cliente VPN tiene compatibilidad de túnel dividido.

Sin el túnel dividido, todo el tráfico de trabajo remoto se envía por la conexión VPN, donde debe reenviarse a los dispositivos perimetrales de la organización, procesarse y, después, enviarse por Internet.

:::image type="content" source="../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-before-tunneling.png" alt-text="Tráfico de red de clientes de VPN sin túneles." lightbox="../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-before-tunneling.png":::

El tráfico de Microsoft 365 debe tomar una ruta indirecta a través de su organización, que podría reenviarse a un punto de entrada de la red de Microsoft lejos de la ubicación física del cliente VPN. Esta ruta indirecta agrega latencia al tráfico de la red y disminuye el rendimiento general.

Con el túnel dividido, puede configurar el cliente VPN para excluir determinados tipos de tráfico de la conexión VPN a la red de la organización.

Para optimizar el acceso a los recursos en la nube de Microsoft 365, configure los clientes VPN de túnel dividido para excluir el tráfico a los puntos de conexión de Microsoft 365 de la categoría **Optimizar** por la conexión VPN. Para obtener más información, consulte [Office 365 endpoint categories](../enterprise/microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories) (Categorías de puntos de conexión de Office 365). Vea la lista de puntos de conexión de la categoría Optimizar [aquí](../enterprise/urls-and-ip-address-ranges.md).

Este es el flujo de tráfico resultante, en el que la mayor parte del tráfico de las aplicaciones en la nube de Microsoft 365 omiten la conexión VPN.

:::image type="content" source="../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-after-tunneling.png" alt-text="Tráfico de red de clientes de VPN con túneles." lightbox="../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-after-tunneling.png":::

Esto permite que el cliente VPN envíe y reciba tráfico esencial de servicio en la nube de Microsoft 365 directamente por Internet y al punto de entrada más cercano a la red de Microsoft.

Para obtener más información e instrucciones, consulte [Optimizar la conectividad de Office 365 para usuarios remotos usando el túnel dividido de VPN](../enterprise/microsoft-365-vpn-split-tunnel.md).

## <a name="deploy-remote-access-when-all-your-apps-are-web-apps-and-you-have-hybrid-identity"></a>Implementación del acceso remoto cuando todas las aplicaciones son aplicaciones web y tiene una identidad híbrida

Si sus trabajadores remotos no usan un cliente VPN tradicional y sus grupos y cuentas de usuario locales están sincronizados con Azure AD, puede usar Azure AD Application Proxy para proporcionar acceso remoto seguro para aplicaciones basadas en web hospedadas en servidores locales. Entre las aplicaciones basadas en web se incluyen los sitios de SharePoint, los servidores de Outlook Web Access, o cualquier otra línea de aplicaciones empresariales basada en web.

Estos son los componentes del proxy de la aplicación Azure AD.

:::image type="content" source="../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-application-proxy.png" alt-text="Componentes del proxy de la aplicación Azure AD." lightbox="../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-application-proxy.png":::

Para más información, vea esta [información general sobre el proxy de aplicación de Azure AD](/azure/active-directory/manage-apps/application-proxy).

> [!NOTE]
> El proxy de aplicación de Azure AD no está incluido en una suscripción de Microsoft 365. Debe pagar para usarlo con una suscripción de Azure por separado.

## <a name="deploy-remote-access-when-not-all-your-apps-are-web-apps"></a>Implementar el acceso remoto cuando no todas las aplicaciones son aplicaciones web

Si sus trabajadores remotos no usan un cliente VPN tradicional y tiene aplicaciones que no están basadas en la web, puede usar una VPN de Azure Point-to-Site (P2S).

Una conexión VPN de P2S crea una conexión segura desde el dispositivo de un trabajador remoto a la red de la organización a través de una red virtual de Azure.

:::image type="content" source="../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-p2s-vpn.png" alt-text="Componentes de la red privada virtual de Azure P2S." lightbox="../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-p2s-vpn.png":::

Para obtener más información, vea esta [introducción a la red virtual privada de P2S](/azure/vpn-gateway/point-to-site-about).

> [!NOTE]
> La VPN de Azure P2S no está incluida en una suscripción de Microsoft 365. Debe pagar para usarlo con una suscripción de Azure por separado.

## <a name="deploy-windows-365-to-provide-remote-access-for-remote-workers-using-personal-devices"></a>Implementación de Windows 365 para proporcionar acceso remoto para trabajadores remotos con dispositivos personales

Para dar servicio a los trabajadores remotos que solo pueden usar sus dispositivos personales y no administrados, use Windows 365 para crear y asignar escritorios virtuales para que los usuarios puedan usarlos desde casa. Con una conexión de red local (OPNC), los equipos en la nube de Windows 365 pueden actuar igual que los equipos conectados a la red de su organización.

:::image type="content" source="../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-windows-365.png" alt-text="Componentes de Windows 365." lightbox="../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-windows-365.png":::

Para obtener más información, vea esta [introducción a Windows 365](/windows-365/overview).

> [!NOTE]
> Windows 365 no está incluido en una suscripción de Microsoft 365. Debe pagar para usarlo con una suscripción por separado.

## <a name="protect-your-remote-desktop-services-connections-with-the-remote-desktop-services-gateway"></a>Proteja las conexiones de los servicios de escritorio remoto con la puerta de enlace de servicios de escritorio remoto

Si usa los servicios de escritorio remoto (RDS) para permitir que los empleados se conecten a equipos con Windows de su red local, debería usar una puerta de enlace de servicios de escritorio remoto de Microsoft en su red perimetral. La puerta de enlace usa la Seguridad de la capa de transporte (TLS) para cifrar el tráfico e impide que el equipo local que hospeda RDS se exponga directamente a Internet.

:::image type="content" source="../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-remote-desktop.png" alt-text="Conexiones de los servicios de escritorio remoto con la puerta de enlace de servicios de escritorio remoto." lightbox="../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-remote-desktop.png":::

Vea [este artículo](https://www.microsoft.com/security/blog/2020/04/16/security-guidance-remote-desktop-adoption/) para obtener más información.

## <a name="admin-technical-resources-for-remote-access"></a>Recursos técnicos administrativos para el acceso remoto

- [Cómo optimizar rápidamente el tráfico de Office 365 para el personal remoto y reducir la carga de su infraestructura](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571)
- [Optimizar la conectividad de Office 365 para usuarios remotos que usan túnel dividido de VPN](../enterprise/microsoft-365-vpn-split-tunnel.md)

## <a name="results-of-step-2"></a>Resultados del paso 2

Después de implementar una solución de acceso remoto para los trabajadores remotos:

| Configuración de acceso remoto | Resultados |
|:-------|:-----|
| Se ha establecido una solución de VPN de acceso remoto | Se configuró el cliente VPN de acceso remoto para túnel dividido y para la categoría Optimizar de los puntos de conexión de Microsoft 365. |
| No cuenta con una solución de VPN de acceso remoto y solo necesita el acceso remoto a aplicaciones locales basadas en la web | Configuró el proxy de aplicación de Azure. |
| No está usando una solución de VPN de acceso remoto y necesita tener acceso a las aplicaciones locales, algunas de las cuales no se basan en la web | Configuró la red privada virtual de P2S de Azure. |
| Los trabajadores remotos usan sus dispositivos personales desde casa | Ha configurado Windows 365. |
| Los trabajadores remotos usan conexiones de RDS a sistemas locales | Ha implementado una puerta de enlace de servicios de escritorio remoto en la red perimetral. |
|||

## <a name="next-step"></a>Paso siguiente

[![Paso 3: Implementar los servicios de cumplimiento y seguridad de Microsoft 365.](../media/empower-people-to-work-remotely/remote-workers-step-grid-3.png)](empower-people-to-work-remotely-security-compliance.md)

Continúe con el [paso 3](empower-people-to-work-remotely-security-compliance.md) para implementar los servicios de seguridad y cumplimiento de Microsoft 365 para proteger sus aplicaciones, datos y dispositivos.
