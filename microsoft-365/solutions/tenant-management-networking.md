---
title: Paso 2. Redes óptimas para los inquilinos de Microsoft 365 para empresas
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
ms.custom:
- Ent_Solutions
description: Optimice el acceso de red a los inquilinos de Microsoft 365.
ms.openlocfilehash: 1e57911a6e8c51af3ae00ff0f9053bf9273e0e17
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908776"
---
# <a name="step-2-optimal-networking-for-your-microsoft-365-for-enterprise-tenants"></a>Paso 2. Redes óptimas para los inquilinos de Microsoft 365 para empresas

Microsoft 365 para empresas incluye aplicaciones de productividad en la nube como Teams y Exchange Online, y Microsoft Intune, junto con muchos servicios de identidad y seguridad de Microsoft Azure. Todos estos servicios basados en la nube dependen de la seguridad, el rendimiento y la confiabilidad de las conexiones de los dispositivos cliente en la red local o en cualquier ubicación de Internet. 

Para optimizar el acceso a la red para su espacio empresarial, necesita:

- Optimice la ruta de acceso entre los usuarios locales y la ubicación más cercana a la red global de Microsoft.
- Optimice el acceso a la red global de Microsoft para los usuarios remotos que usan una solución VPN de acceso remoto.
- Use Network Insights para diseñar el perímetro de red de las ubicaciones de las oficinas.
- Optimizar el acceso a activos específicos hospedados en sitios de SharePoint con la red CDN de Office 365.
- Configurar dispositivos perimetrales de red y proxy para omitir el procesamiento del tráfico de confianza de Microsoft 365 con la lista de puntos de conexión y automatizar la actualización de la lista a medida que se realizan los cambios.

## <a name="enterprise-on-premises-workers"></a>Trabajadores locales de empresa

Para las redes empresariales, debe optimizar la experiencia del usuario final habilitando el acceso de red de mayor rendimiento entre los clientes y los puntos de conexión de Microsoft 365 más cercanos. La calidad de la experiencia del usuario final está directamente relacionada con el rendimiento y la capacidad de respuesta de la aplicación que usa el usuario. Por ejemplo, Microsoft Teams se basa en una latencia baja para que las llamadas telefónicas de los usuarios, las conferencias y las colaboraciones de pantalla compartida no sean problemas.

El objetivo principal del diseño de red debe ser minimizar la latencia reduciendo el tiempo de ida y vuelta (RTT) de los dispositivos cliente a la red global de Microsoft, la red troncal de red pública de Microsoft que interconecta todos los centros de datos de Microsoft con puntos de entrada de aplicaciones en la nube de baja latencia y alta disponibilidad, conocidos como puertas frontales, que se extienden por todo el mundo.

Este es un ejemplo de una red empresarial tradicional.

![Una red empresarial tradicional con acceso central a Internet](../media/tenant-management-overview/tenant-management-networking-traditional.png)

En esta ilustración, las sucursales se conectan a una oficina central a través de dispositivos de red de área extensa (WAN) y una red troncal WAN. El acceso a Internet se hace a través de un dispositivo de seguridad o proxy en el perímetro de red de la oficina central y un proveedor de servicios de Internet (ISP). En Internet, la red global de Microsoft tiene una serie de puertas frontales en regiones de todo el mundo. Las organizaciones también pueden usar ubicaciones intermedias para el procesamiento de paquetes y la seguridad adicionales para el tráfico. El inquilino de Microsoft 365 de una organización se encuentra dentro de la red global de Microsoft.

Los problemas con esta configuración para los servicios en la nube de Microsoft 365 son:

- Para los usuarios de sucursales, el tráfico se envía a puertas frontales no locales, lo que aumenta la latencia.
- El envío de tráfico a ubicaciones intermedias crea unas chinenas de red que realizan procesamiento de paquetes duplicados en el tráfico de confianza, lo que aumenta la latencia.
- Los dispositivos perimetrales de red realizan procesamientos de paquetes innecesarios y duplicados en el tráfico de confianza, lo que aumenta la latencia.

No es necesario que sea complicado optimizar el rendimiento de la red de Microsoft 365. Puede obtener el mejor rendimiento posible siguiendo algunos principios clave:

- Identifique el tráfico de red de Microsoft 365, que es el tráfico de confianza destinado a los servicios en la nube de Microsoft.
- Permitir la salida de sucursal local del tráfico de red de Microsoft 365 a Internet desde cada ubicación donde los usuarios se conecten a Microsoft 365.
- Evita las chines de red.
- Permitir que el tráfico de Microsoft 365 omita los servidores proxy y los dispositivos de inspección de paquetes.

Si implementa estos principios, obtiene una red empresarial optimizada para Microsoft 365.

![Una red empresarial optimizada para Microsoft 365](../media/tenant-management-overview/tenant-management-networking-optimized.png)

En esta ilustración, las sucursales tienen su propia conexión a Internet a través de un dispositivo de dispositivo WAN definido por software (SDWAN), que envía tráfico de Confianza de Microsoft 365 a la puerta principal regionalmente más cercana. En la oficina central, el tráfico de Microsoft 365 de confianza omite el dispositivo de seguridad o proxy y ya no se usan dispositivos intermedios.

A continuación se muestra cómo la configuración optimizada resuelve los problemas de latencia de una red empresarial tradicional:

- El tráfico de Confianza de Microsoft 365 omite la red troncal WAN y se envía a las puertas frontales locales de todas las oficinas, disminuyendo la latencia.
- Las chineadas de red que realizan procesamiento de paquetes duplicados se omiten para el tráfico de confianza de Microsoft 365, lo que reduce la latencia.
- Los dispositivos perimetrales de red que realizan procesamiento de paquetes innecesarios y duplicados se omiten para el tráfico de confianza de Microsoft 365, lo que reduce la latencia.

Para obtener más información, consulte Información general sobre la conectividad de [red de Microsoft 365.](../enterprise/microsoft-365-networking-overview.md)

## <a name="remote-workers"></a>Trabajadores remotos

Si los trabajadores remotos usan un cliente VPN tradicional para obtener acceso remoto a la red de su organización, compruebe que el cliente VPN tiene compatibilidad de túnel dividido. Sin el túnel dividido, todo el tráfico de trabajo remoto se envía por la conexión VPN, donde debe reenviarse a los dispositivos perimetrales de la organización, procesarse y, después, enviarse por Internet. Aquí le mostramos un ejemplo.

![Tráfico de red de clientes de VPN sin túneles](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-before-tunneling.png)

En esta ilustración, el tráfico de Microsoft 365 debe tomar una ruta indirecta a través de su organización, que podría reenviarse a una puerta frontal de la red global de Microsoft lejos de la ubicación física del cliente VPN. Esta ruta indirecta agrega latencia al tráfico de red y reduce el rendimiento general. 

Con el túnel dividido, puede configurar el cliente VPN para excluir determinados tipos de tráfico de la conexión VPN a la red de la organización.

Para optimizar el acceso a los recursos en la nube de Microsoft 365, configure los clientes VPN de túnel dividido para excluir el tráfico a los puntos de conexión de Microsoft 365 de la categoría **Optimizar** por la conexión VPN. Para obtener más información, vea las categorías de puntos de conexión de [Office 365](../enterprise/microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories) y las listas [de](../enterprise/microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling) puntos de conexión de la categoría Optimizar para el túnel dividido.

Este es el flujo de tráfico resultante para el túnel dividido, en el que la mayor parte del tráfico a las aplicaciones en la nube de Microsoft 365 omite la conexión VPN.

![Tráfico de red de clientes de VPN sin túneles](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-after-tunneling.png)

En esta ilustración, el cliente VPN envía y recibe el tráfico crucial del servicio en la nube de Microsoft 365 directamente a través de Internet y a la puerta principal más cercana a la red global de Microsoft.

Para obtener más información e instrucciones, consulte [Optimizar la conectividad de Office 365 para usuarios remotos usando el túnel dividido de VPN](../enterprise/microsoft-365-vpn-split-tunnel.md).

## <a name="using-network-insights-preview"></a>Uso de Network Insights (versión preliminar)

La información de red son métricas de rendimiento recopiladas de su inquilino de Microsoft 365 que le ayudan a diseñar perímetros de red para las ubicaciones de las oficinas. Cada información proporciona detalles en directo sobre las características de rendimiento de un problema especificado para cada ubicación geográfica en la que los usuarios locales acceden a su espacio empresarial.

Hay dos perspectivas de red de nivel de inquilino que se pueden mostrar para el inquilino:

- [Conexiones de ejemplo de Exchange afectadas por problemas de conectividad](../enterprise/office-365-network-mac-perf-insights.md#exchange-sampled-connections-impacted-by-connectivity-issues)
- [Conexiones de ejemplo de SharePoint afectadas por problemas de conectividad](../enterprise/office-365-network-mac-perf-insights.md#sharepoint-sampled-connections-impacted-by-connectivity-issues)

Estas son las conclusiones de red específicas para cada ubicación de la oficina:

- [Salida de red contralada](../enterprise/office-365-network-mac-perf-insights.md#backhauled-network-egress)
- [Mejor rendimiento detectado para clientes cercanos](../enterprise/office-365-network-mac-perf-insights.md#better-performance-detected-for-customers-near-you)
- [Uso de una puerta de servicio de Exchange Online no óptima](../enterprise/office-365-network-mac-perf-insights.md#use-of-a-non-optimal-exchange-online-service-front-door)
- [Uso de una puerta de servicio de SharePoint Online no óptima](../enterprise/office-365-network-mac-perf-insights.md#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [Baja velocidad de descarga desde la puerta principal de SharePoint](../enterprise/office-365-network-mac-perf-insights.md#low-download-speed-from-sharepoint-front-door)
- [Salida de red óptima para usuarios de China](../enterprise/office-365-network-mac-perf-insights.md#china-user-optimal-network-egress)

>[!IMPORTANT]
>La información de red, las recomendaciones de rendimiento y las evaluaciones del Centro de administración de Microsoft 365 se encuentran actualmente en estado de versión preliminar. Solo está disponible para los inquilinos de Microsoft 365 que se han inscrito en el programa de vista previa de características.

Para obtener más información, [vea Microsoft 365 Network Insights](../enterprise/office-365-network-mac-perf-insights.md).

## <a name="sharepoint-performance-with-the-office-365-cdn"></a>Rendimiento de SharePoint con la red CDN de Office 365

Una red de entrega de contenido (CDN) basada en la nube le permite reducir los tiempos de carga, ahorrar ancho de banda y acelerar la capacidad de respuesta. Una red CDN mejora el rendimiento al almacenar en caché activos estáticos, como archivos gráficos o de vídeo, más cerca de los exploradores que los solicitan, lo que ayuda a acelerar las descargas y reducir la latencia. Puede usar la red de entrega de contenido (CDN) integrada de Office 365, incluida con SharePoint en Microsoft 365 E3 y E5, para hospedar activos estáticos con el objeto de proporcionar un mejor rendimiento para sus páginas de SharePoint.

La CDN de Office 365 se compone de varias redes CDN que permite hospedar archivos estáticos en varias ubicaciones u _orígenes_ y a realizar la entrega desde redes de alta velocidad globales. Según el tipo de contenido que desee hospedar en la red CDN de Office 365, puede agregar orígenes públicos, privados o ambos.  

Cuando se implementa y configura, la red CDN de Office 365 carga activos de orígenes públicos y privados y los pone a disposición para un acceso rápido a los usuarios ubicados a través de Internet.

![Red CDN de Office 365 implementada para usuarios](../media/O365-CDN/o365-cdn-flow-transparent.svg "Red CDN de Office 365 implementada para usuarios")

Para obtener más información, vea Usar la red CDN de [Office 365 con SharePoint Online.](../enterprise/use-microsoft-365-cdn-with-spo.md)

## <a name="automated-endpoint-listing"></a>Lista de puntos de conexión automatizados

Para que los clientes locales, los dispositivos perimetrales y los servicios de análisis de paquetes basados en la nube omitan el procesamiento del tráfico de Confianza de Microsoft 365, debe configurarlos con el conjunto de puntos de conexión (intervalos de direcciones IP y nombres DNS) correspondientes a los servicios de Microsoft 365. Estos puntos de conexión se pueden configurar manualmente en firewalls y otros dispositivos de seguridad perimetral, archivos PAC para que los equipos cliente omitan servidores proxy o dispositivos SD-WAN en las sucursales. Sin embargo, los puntos de conexión cambian con el tiempo, lo que requiere un mantenimiento manual continuo de las listas de puntos de conexión en estas ubicaciones.

Para automatizar la lista y la administración de cambios para los puntos de conexión de Microsoft 365 en sus archivos PAC de cliente y dispositivos de red, use la dirección IP de [Office 365](../enterprise/microsoft-365-ip-web-service.md)y el servicio web basado en REST de url. Este servicio le ayuda a identificar y diferenciar mejor el tráfico de red de Microsoft 365, lo que facilita evaluar, configurar y mantenerse al día con los últimos cambios.

Puede usar PowerShell, Python u otros lenguajes para determinar los cambios en los puntos de conexión a lo largo del tiempo y configurar los archivos PAC y los dispositivos de red perimetral.

El proceso básico es:

1. Use el servicio web de url y dirección IP de Office 365 y el mecanismo de configuración que prefiera para configurar los archivos PAC y los dispositivos de red con el conjunto actual de puntos de conexión de Microsoft 365.
2. Ejecuta un número periódico diario para comprobar si hay cambios en los puntos de conexión o usa un método de notificación.
3. Cuando se detecten cambios, vuelva a generar y redistribuir el archivo PAC para los equipos cliente y realice los cambios en los dispositivos de red.

Para obtener más información, vea [dirección IP de Office 365 y servicio web de url.](../enterprise/microsoft-365-ip-web-service.md)

## <a name="results-of-step-2"></a>Resultados del paso 2

Para su espacio empresarial de Microsoft 365 con redes óptimas, ha determinado:

- Cómo optimizar el rendimiento de la red para los usuarios locales agregando conexiones a Internet a todas las sucursales y eliminando las bifurcaciones de red.
- Cómo implementar la lista automatizada de puntos de conexión de confianza para los archivos PAC basados en cliente y los dispositivos y servicios de red, incluidas las actualizaciones continuas (más adecuadas para redes empresariales).
- Cómo admitir el acceso de trabajadores remotos a los recursos locales.
- Cómo usar Network Insights
- Cómo implementar la red CDN de Office 365.

Este es un ejemplo de una organización empresarial y su espacio empresarial con una red óptima.

![Ejemplo de un inquilino con redes óptimas](../media/tenant-management-overview/tenant-management-tenant-build-step2.png)

[Ver una versión más grande de esta imagen](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-management-overview/tenant-management-tenant-build-step2.png)

En esta ilustración, el inquilino de esta organización empresarial tiene:

- Acceso a Internet local para cada sucursal con un dispositivo SDWAN que reenvía el tráfico de Confianza de Microsoft 365 a una puerta principal local.
- No hay chinedores de red.
- Dispositivos perimetrales de proxy y seguridad de la oficina central que reenvía el tráfico de confianza de Microsoft 365 a una puerta principal local.

## <a name="ongoing-maintenance-for-optimal-networking"></a>Mantenimiento continuo para una red óptima

De forma continua, es posible que deba:

- Actualiza los dispositivos perimetrales y los archivos PAC implementados para los cambios en los puntos de conexión o comprueba que el proceso automatizado funciona correctamente.
- Administre los activos en la red CDN de Office 365.
- Actualiza la configuración de túnel dividido en los clientes VPN para los cambios en los puntos de conexión.

## <a name="next-step"></a>Paso siguiente

[![Paso 3. Sincronizar las identidades y aplicar inicios de sesión seguros](../media/tenant-management-overview/tenant-management-step-grid-identity.png)](tenant-management-identity.md)

Continúe con [la identidad](tenant-management-identity.md) para sincronizar sus cuentas y grupos locales y aplicar inicios de sesión de usuario seguros.
