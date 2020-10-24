---
title: Redes para Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda la infraestructura de red de Contoso y cómo usa su tecnología SD-WAN el rendimiento óptimo de la red para los servicios de nube de Microsoft 365 para empresas.
ms.openlocfilehash: d5f3581b81d33bdc200321692b82d57a96d09298
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754019"
---
# <a name="networking-for-the-contoso-corporation"></a>Redes para Contoso Corporation

Para adoptar una infraestructura de nube inclusiva, contoso diseñó un cambio fundamental en cómo viaja el tráfico de red hacia los servicios en la nube. En lugar de un modelo de concentrador y radio interno que enfoca la conectividad y el tráfico de la red para el siguiente nivel de la jerarquía de Office, asignaban ubicaciones de usuario a la salida de Internet local y conexiones locales a la ubicación de red de Microsoft 365 más cercana en Internet.

## <a name="networking-infrastructure"></a>Infraestructura de red

Estos son los elementos de red que vinculan las oficinas de Contoso en todo el mundo:

- Red WAN de conmutación de etiquetas multiprotocolo (MPLS)

  Una red WAN MPLS conecta la sede central de París con las oficinas regionales y las oficinas regionales a las oficinas satélite en una configuración de radios y concentradores. La red permite a los usuarios tener acceso a los servidores locales que forman las aplicaciones de línea de negocio en la sede central de París. También enruta todo el tráfico de Internet genérico a la oficina de París, donde los dispositivos de seguridad de red limpian las solicitudes. Dentro de cada oficina, los enrutadores entregan tráfico a los hosts con cable o a puntos de acceso inalámbrico en las subredes, que usan el espacio de direcciones IP privadas.

- Acceso directo a Internet local para el tráfico de Microsoft 365

  Cada oficina tiene un dispositivo WAN definido por software (SD-WAN) que tiene uno o varios circuitos de red ISP de Internet locales con su propia conectividad a Internet a través de un servidor proxy. Suele implementarse como un vínculo WAN a un ISP local que también proporciona direcciones IP públicas y un servidor DNS local.

- Presencia en Internet

  Contoso posee el \. nombre de dominio público com de contoso. El sitio web público de Contoso para pedir productos es un conjunto de servidores en un centro de información conectado a Internet en el campus de París. Contoso usa un intervalo de direcciones IP públicas a/24 en Internet.

La figura 1 muestra la infraestructura de red de Contoso y sus conexiones a Internet.

![La red de Contoso](../media/contoso-networking/contoso-networking-fig1.png)
 
**Figura 1: la red de Contoso**

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a>Uso de SD-WAN para la conectividad de red óptima a Microsoft

Contoso siguió los [principios de conectividad de red de Microsoft 365](microsoft-365-network-connectivity-principles.md) para:

- Identificar y diferenciar el tráfico de red de Microsoft 365
- Conexiones de red de salida de forma local
- Evitar las redirecciones de red
- Omitir los dispositivos de seguridad de red duplicados

Hay tres categorías de tráfico de red para Microsoft 365: *optimizar*, *permitir*y *predeterminado*. Optimizar y permitir el tráfico es el tráfico de red de confianza que se cifra y protege en los puntos de conexión y que se destina a la red de Microsoft 365.

Contoso decidió:

- Use la salida directa de Internet para optimizar y permitir el tráfico de categoría y reenviar todo el tráfico de categoría predeterminado a la conexión central a Internet basada en París.

- Implemente dispositivos SD-WAN en cada oficina como una forma sencilla de seguir estos principios y obtener un rendimiento de red óptimo para los servicios basados en la nube de Microsoft 365.

  Los dispositivos SD-WAN tienen un puerto LAN para la red de oficina local y varios puertos WAN. Un puerto WAN se conecta a su red MPLS. Otro se conecta a un circuito de ISP local. El dispositivo SD-WAN enruta el tráfico de las categorías Optimizar y Permitir en el vínculo de ISP.

## <a name="the-contoso-line-of-business-app-infrastructure"></a>La infraestructura de la aplicación de línea de negocio de Contoso

Contoso diseñó su infraestructura de aplicaciones de línea de negocio y de intranet de servidor para lo siguiente:

- En las oficinas satélite se usan servidores de almacenamiento en caché locales para almacenar documentos y sitios web internos a los que se accede frecuentemente.
- En los centros regionales se usan servidores de aplicaciones regionales para las oficinas regionales y satélite. Estos servidores se sincronizan con los de la sede de París.
- Los centros de recursos de la sede de París contienen servidores de aplicaciones centralizados que sirven a toda la organización.

En la figura 2 se muestra el porcentaje de capacidad de tráfico de red que se usa para obtener acceso a los servidores de la intranet de contoso.

![Infraestructura de Contoso para aplicaciones internas](../media/contoso-networking/contoso-networking-fig2.png)
 
**Figura 2: infraestructura de Contoso para aplicaciones internas**

Para las oficinas satélite o regionales, el 60 por ciento de los recursos que necesitan los empleados pueden ser atendidos por servidores de oficinas centrales y de concentradores. El 40 por ciento adicional de solicitudes de recursos debe pasar por el vínculo WAN a la sede de París.

## <a name="network-analysis-and-preparation-for-microsoft-365-for-enterprise"></a>Análisis y preparación de la red para Microsoft 365 para empresas

La adopción satisfactoria de Microsoft 365 para los servicios empresariales por parte de los usuarios de Contoso depende de la conectividad de alta disponibilidad y de la performidad a Internet o directamente a los servicios en la nube de Microsoft. Contoso llevó a cabo estos pasos para planear e implementar la conectividad optimizada a Microsoft 365 para Enterprise Cloud Services:

1. Crear un diagrama de red WAN de una compañía para ayudar con la planeación

   Para empezar la planeación de la red, contoso creó un diagrama que muestra sus ubicaciones de oficina, la conectividad de red existente, los dispositivos perimetrales de red existentes y las clases de servicio que se administran en la red. Usaron este diagrama para cada paso posterior de la planeación e implementación de la conectividad de red.

2. Crear un plan para Microsoft 365 para conectividad de red empresarial

   Contoso usó los [principios de conectividad de red de Microsoft 365](microsoft-365-network-connectivity-principles.md) y las arquitecturas de red de referencia de ejemplo para identificar SD-WAN como su topología preferida para la conectividad de Microsoft 365.

3. Analizar el uso de conexión a Internet y el ancho de banda de MPLS-WAN en cada oficina y aumentar el ancho de banda según sea necesario

   Se analizó el uso actual de cada oficina y se aumentaron los circuitos, de modo que el tráfico basado en la nube de Microsoft 365 previsto se operara con un promedio del 20% de capacidad sin usar.

4. Optimizar el rendimiento de los servicios de red de Microsoft

   Contoso determinó el conjunto de extremos de Office 365, Intune y Azure, y firewalls configurados, dispositivos de seguridad y otros sistemas en la ruta de acceso a Internet para obtener un rendimiento óptimo. Los puntos de conexión de Office 365 optimizar y permitir el tráfico de categoría se configuraron en los dispositivos SD-WAN para enrutar a través del circuito del ISP.

5. Configuración de DNS interno

   DNS debe ser funcional y buscarse de forma local para el tráfico de Microsoft 365.

6. Validar el punto de conexión de red y la conectividad de Puerto

   Contoso ejecutó las herramientas de prueba de conectividad de red de Microsoft para validar la conectividad para los servicios de nube de Microsoft 365 para empresas.

7. Optimizar los equipos de los empleados para la conectividad de red

   Se comprobaron los equipos individuales para asegurarse de que se instalaron las últimas actualizaciones del sistema operativo y que la supervisión de seguridad de extremos estaba activa en todos los clientes.

## <a name="next-step"></a>Paso siguiente

Obtenga información sobre cómo Contoso está [aprovechando sus servicios de dominio de Active Directory local en la nube](contoso-identity.md) para los empleados y la autenticación de Federación para clientes y socios comerciales.

## <a name="see-also"></a>Recursos adicionales

[Guía de redes para Microsoft 365](networking-roadmap-microsoft-365.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Guías del laboratorio de pruebas](m365-enterprise-test-lab-guides.md)
