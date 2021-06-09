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
description: Comprenda la infraestructura de red de Contoso y cómo la empresa usa su tecnología SD-WAN para obtener un rendimiento de red óptimo para Microsoft 365 servicios en la nube empresariales.
ms.openlocfilehash: d5f3581b81d33bdc200321692b82d57a96d09298
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754019"
---
# <a name="networking-for-the-contoso-corporation"></a>Redes para Contoso Corporation

Para adoptar una infraestructura inclusiva en la nube, Contoso ideó un cambio fundamental en la forma en que se desplaza el tráfico de red a los servicios en la nube. En lugar de un modelo interno de concentrador y radio que centra la conectividad de red y el tráfico para el siguiente nivel de la jerarquía de oficina, asignaron ubicaciones de usuario a la salida de Internet local y conexiones locales a la ubicación de red de Microsoft 365 más cercana en Internet.

## <a name="networking-infrastructure"></a>Infraestructura de red

Estos son los elementos de red que vinculan las oficinas de Contoso en todo el mundo:

- Red WAN de conmutación de etiquetas multiprotocolo (MPLS)

  Una red WAN de MPLS conecta la sede central de París con las oficinas regionales y las oficinas regionales a las oficinas satélite en una configuración de radio y concentrador. La red permite a los usuarios tener acceso a los servidores locales que integran aplicaciones de línea de negocio en la sede central de París. También enruta cualquier tráfico genérico de Internet a la oficina de París, donde los dispositivos de seguridad de red limpian las solicitudes. Dentro de cada oficina, los enrutadores entregan tráfico a hosts con cable o puntos de acceso inalámbrico en subredes, que usan el espacio de direcciones IP privadas.

- Acceso directo a Internet local para Microsoft 365 tráfico

  Cada oficina tiene un dispositivo WAN (SD-WAN) definido por software que tiene uno o más circuitos de red ISP de Internet local con su propia conectividad a Internet a través de un servidor proxy. Esto suele implementarse como un vínculo WAN a un ISP local que también proporciona direcciones IP públicas y un servidor DNS local.

- Presencia en Internet

  Contoso es propietario del nombre de dominio público contoso \. com. El sitio web público de Contoso para ordenar productos es un conjunto de servidores en un centro de datos conectado a Internet en el campus de París. Contoso usa un intervalo de direcciones IP públicas /24 en Internet.

En la figura 1 se muestra la infraestructura de red de Contoso y sus conexiones a Internet.

![La red contoso](../media/contoso-networking/contoso-networking-fig1.png)
 
**Figura 1: La red contoso**

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a>Uso de SD-WAN para la conectividad de red óptima a Microsoft

Contoso siguió los [principios de conectividad de red de Microsoft 365](microsoft-365-network-connectivity-principles.md) para:

- Identificar y diferenciar el tráfico de red de Microsoft 365
- Conexiones de red de salida de forma local
- Evitar las redirecciones de red
- Omitir los dispositivos de seguridad de red duplicados

Hay tres categorías de tráfico de red para Microsoft 365: *Optimize*, *Allow* y *Default*. Optimizar y permitir el tráfico es un tráfico de red de confianza que está cifrado y protegido en los puntos de conexión y está destinado a la Microsoft 365 red.

Contoso decidió:

- Use la salida directa de Internet para optimizar y permitir el tráfico de categorías y para reenviar todo el tráfico de categoría predeterminado a la conexión central de Internet basada en París.

- Implemente dispositivos SD-WAN en cada oficina como una forma sencilla de seguir estos principios y lograr un rendimiento de red óptimo para Microsoft 365 servicios basados en la nube.

  Los dispositivos SD-WAN tienen un puerto LAN para la red de oficina local y varios puertos WAN. Un puerto WAN se conecta a su red MPLS. Otro se conecta a un circuito isp local. El dispositivo SD-WAN enruta el tráfico de las categorías Optimizar y Permitir en el vínculo de ISP.

## <a name="the-contoso-line-of-business-app-infrastructure"></a>La infraestructura de aplicaciones de línea de negocio de Contoso

Contoso diseñó su infraestructura de intranet de servidor y aplicación de línea de negocio para lo siguiente:

- En las oficinas satélite se usan servidores de almacenamiento en caché locales para almacenar documentos y sitios web internos a los que se accede frecuentemente.
- En los centros regionales se usan servidores de aplicaciones regionales para las oficinas regionales y satélite. Estos servidores se sincronizan con los de la sede de París.
- Los centros de datos del campus de París contienen servidores de aplicaciones centralizados que sirven a toda la organización.

La figura 2 muestra el porcentaje de capacidad de tráfico de red que se usa al obtener acceso a los servidores en toda la intranet de Contoso.

![La infraestructura de Contoso para aplicaciones internas](../media/contoso-networking/contoso-networking-fig2.png)
 
**Figura 2: La infraestructura de Contoso para aplicaciones internas**

Para las oficinas centrales de satélite o regionales, el 60 % de los recursos necesarios para los empleados pueden ser atendidos por servidores de oficinas centrales regionales y satélites. El 40 % adicional de solicitudes de recursos debe pasar por el vínculo WAN al campus de París.

## <a name="network-analysis-and-preparation-for-microsoft-365-for-enterprise"></a>Análisis de red y preparación de Microsoft 365 para empresas

La adopción correcta de Microsoft 365 para los servicios empresariales por parte de los usuarios de Contoso depende de una conectividad altamente disponible y de rendimiento a Internet o directamente a los servicios en la nube de Microsoft. Contoso realizó estos pasos para planear e implementar la conectividad optimizada para Microsoft 365 para los servicios de nube empresariales:

1. Crear un diagrama de red WAN de empresa para ayudar con la planeación

   Para iniciar su planeación de red, Contoso creó un diagrama que muestra sus ubicaciones de oficina, conectividad de red existente, dispositivos perimetrales de red existentes y clases de servicio que se administran en la red. Usaron este diagrama para cada paso posterior en la planeación e implementación de la conectividad de red.

2. Crear un plan para Microsoft 365 conectividad de red empresarial

   Contoso usó los Microsoft 365 de conectividad de red y las [arquitecturas](microsoft-365-network-connectivity-principles.md) de red de referencia de ejemplo para identificar SD-WAN como su topología preferida para Microsoft 365 conectividad.

3. Analizar el uso de conexión a Internet y el ancho de banda MPLS-WAN en cada oficina y aumentar el ancho de banda según sea necesario

   Se analizó el uso actual de cada oficina y se aumentaron los circuitos para que el tráfico Microsoft 365 basado en la nube funcionara con un promedio de 20 por ciento de capacidad sin usar.

4. Optimizar el rendimiento de los servicios de red de Microsoft

   Contoso determinó el conjunto de Office 365, Intune y puntos de conexión de Azure y firewalls configurados, dispositivos de seguridad y otros sistemas en la ruta de acceso a Internet para un rendimiento óptimo. Los puntos de conexión Office 365 optimizar y permitir tráfico de categorías se configuraron en los dispositivos SD-WAN para el enrutamiento a través del circuito ISP.

5. Configurar DNS interno

   DNS debe ser funcional y buscarse de forma local para el tráfico de Microsoft 365.

6. Validar la conectividad de puerto y punto de conexión de red

   Contoso ejecutó las herramientas de prueba de conectividad de red de Microsoft para validar la conectividad Microsoft 365 para los servicios de nube empresariales.

7. Optimizar los equipos de empleados para la conectividad de red

   Se comprobaron equipos individuales para asegurarse de que se instalaron las últimas actualizaciones del sistema operativo y de que la supervisión de seguridad de puntos de conexión estaba activa en todos los clientes.

## <a name="next-step"></a>Paso siguiente

Obtenga información sobre cómo Contoso está aprovechando sus servicios de dominio de [Active Directory](contoso-identity.md) locales en la nube para los empleados y la autenticación federada para clientes y socios empresariales.

## <a name="see-also"></a>Consulte también

[Guía básica de redes para Microsoft 365](networking-roadmap-microsoft-365.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Guías del laboratorio de pruebas](m365-enterprise-test-lab-guides.md)
