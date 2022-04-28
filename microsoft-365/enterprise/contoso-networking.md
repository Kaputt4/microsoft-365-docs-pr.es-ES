---
title: Redes para Contoso Corporation
author: kelleyvice-msft
f1.keywords:
- NOCSH
ms.author: kvice
manager: scotv
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda la infraestructura de red de Contoso y cómo la empresa usa su tecnología SD-WAN para lograr un rendimiento de red óptimo para Microsoft 365 para los servicios en la nube empresariales.
ms.openlocfilehash: f8450b63bed68de414c0ea585b6f5e199c87ad90
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65093951"
---
# <a name="networking-for-the-contoso-corporation"></a>Redes para Contoso Corporation

Para adoptar una infraestructura inclusiva en la nube, Contoso ideó un cambio fundamental en el modo en que viaja el tráfico de red a los servicios en la nube. En lugar de un modelo de concentrador y radio interno que centra la conectividad de red y el tráfico para el siguiente nivel de la jerarquía de office, asignaron ubicaciones de usuario a la salida local de Internet y conexiones locales a la ubicación de red Microsoft 365 más cercana en Internet.

## <a name="networking-infrastructure"></a>Infraestructura de red

Estos son los elementos de red que vinculan las oficinas de Contoso en todo el mundo:

- Red WAN de conmutación de etiquetas multiprotocolo (MPLS)

  Una red WAN de MPLS conecta la sede central de París con oficinas regionales y oficinas regionales con oficinas satélite en una configuración de radio y centro. La red permite a los usuarios acceder a servidores locales que componen aplicaciones de línea de negocio en la sede central de París. También enruta cualquier tráfico genérico de Internet a la oficina de París, donde los dispositivos de seguridad de red limpian las solicitudes. Dentro de cada oficina, los enrutadores entregan tráfico a hosts conectados o puntos de acceso inalámbrico en subredes, que usan el espacio de direcciones IP privadas.

- Acceso directo a Internet local para el tráfico de Microsoft 365

  Cada oficina tiene un dispositivo WAN definido por software (SD-WAN) que tiene uno o varios circuitos de red ISP de Internet locales con su propia conectividad a Internet a través de un servidor proxy. Normalmente, esto se implementa como un vínculo WAN a un ISP local que también proporciona direcciones IP públicas y un servidor DNS local.

- Presencia en Internet

  Contoso posee el nombre de dominio público contosocom\.. El sitio web público de Contoso para ordenar productos es un conjunto de servidores en un centro de datos conectado a Internet en el campus de París. Contoso usa un intervalo de direcciones IP públicas /24 en Internet.

En la figura 1 se muestra la infraestructura de red de Contoso y sus conexiones a Internet.

![La red contoso.](../media/contoso-networking/contoso-networking-fig1.png)
 
**Figura 1: La red de Contoso**

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a>Uso de SD-WAN para la conectividad de red óptima a Microsoft

Contoso siguió los [principios de conectividad de red de Microsoft 365](microsoft-365-network-connectivity-principles.md) para:

- Identificar y diferenciar el tráfico de red de Microsoft 365
- Conexiones de red de salida de forma local
- Evitar las redirecciones de red
- Omitir los dispositivos de seguridad de red duplicados

Hay tres categorías de tráfico de red para Microsoft 365: *Optimizar*, *Permitir* y *Predeterminado*. Optimizar y permitir el tráfico es el tráfico de red de confianza que se cifra y protege en los puntos de conexión y está destinado a la red Microsoft 365.

Contoso decidió:

- Use la salida directa de Internet para optimizar y permitir el tráfico de categorías y reenviar todo el tráfico de categoría predeterminado a la conexión a Internet central basada en París.

- Implemente dispositivos SD-WAN en cada oficina como una manera sencilla de seguir estos principios y lograr un rendimiento de red óptimo para Microsoft 365 servicios basados en la nube.

  Los dispositivos SD-WAN tienen un puerto LAN para la red de oficina local y varios puertos WAN. Un puerto WAN se conecta a su red MPLS. Otro se conecta a un circuito ISP local. El dispositivo SD-WAN enruta el tráfico de las categorías Optimizar y Permitir en el vínculo de ISP.

## <a name="the-contoso-line-of-business-app-infrastructure"></a>La infraestructura de aplicaciones de línea de negocio de Contoso

Contoso diseñó su infraestructura de intranet de servidor y aplicación de línea de negocio para lo siguiente:

- En las oficinas satélite se usan servidores de almacenamiento en caché locales para almacenar documentos y sitios web internos a los que se accede frecuentemente.
- En los centros regionales se usan servidores de aplicaciones regionales para las oficinas regionales y satélite. Estos servidores se sincronizan con los de la sede de París.
- Los centros de datos del campus de París contienen servidores de aplicaciones centralizados que atienden a toda la organización.

En la figura 2 se muestra el porcentaje de capacidad de tráfico de red que se usa al acceder a servidores a través de la intranet de Contoso.

![Infraestructura de Contoso para aplicaciones internas.](../media/contoso-networking/contoso-networking-fig2.png)
 
**Figura 2: Infraestructura de Contoso para aplicaciones internas**

En el caso de las oficinas de centros de conectividad por satélite o regionales, el 60 % de los recursos necesarios para los empleados se pueden atender mediante servidores de oficinas de centro de conectividad regionales y satélite. El 40 % adicional de las solicitudes de recursos debe ir a través del vínculo WAN al campus de París.

## <a name="network-analysis-and-preparation-for-microsoft-365-for-enterprise"></a>Análisis y preparación de redes para Microsoft 365 para empresas

La adopción correcta de Microsoft 365 para servicios empresariales por parte de los usuarios de Contoso depende de una conectividad altamente disponible y eficaz a Internet o directamente a los servicios en la nube de Microsoft. Contoso ha realizado estos pasos para planear e implementar la conectividad optimizada para Microsoft 365 para servicios en la nube empresariales:

1. Creación de un diagrama de red wan de empresa para ayudar con el planeamiento

   Para iniciar su planeamiento de red, Contoso creó un diagrama que muestra sus ubicaciones de oficina, la conectividad de red existente, los dispositivos perimetrales de red existentes y las clases de servicio que se administran en la red. Usaron este diagrama para cada paso posterior en la planeación e implementación de la conectividad de red.

2. Creación de un plan para Microsoft 365 para la conectividad de red empresarial

   Contoso usó los [principios de conectividad de red Microsoft 365 y las arquitecturas](microsoft-365-network-connectivity-principles.md) de red de referencia de ejemplo para identificar SD-WAN como su topología preferida para la conectividad Microsoft 365.

3. Analice el uso de la conexión a Internet y el ancho de banda MPLS-WAN en cada oficina y aumente el ancho de banda según sea necesario.

   Se analizó el uso actual de cada oficina y se aumentaron los circuitos para que el tráfico previsto Microsoft 365 basado en la nube funcionara con un promedio del 20 % de capacidad sin usar.

4. Optimización del rendimiento de los servicios de red de Microsoft

   Contoso determinó el conjunto de puntos de conexión de Office 365, Intune y Azure y configuró firewalls, dispositivos de seguridad y otros sistemas en la ruta de acceso a Internet para un rendimiento óptimo. Los puntos de conexión para Office 365 optimizar y permitir el tráfico de categoría se configuraron en los dispositivos SD-WAN para el enrutamiento a través del circuito ISP.

5. Configuración de DNS interno

   DNS debe ser funcional y buscarse de forma local para el tráfico de Microsoft 365.

6. Validación de la conectividad de puerto y punto de conexión de red

   Contoso ejecutó herramientas de prueba de conectividad de red de Microsoft para validar la conectividad de Microsoft 365 para servicios en la nube empresariales.

7. Optimización de equipos de empleados para la conectividad de red

   Se comprobaron equipos individuales para asegurarse de que se instalaron las actualizaciones más recientes del sistema operativo y de que la supervisión de seguridad del punto de conexión estaba activa en todos los clientes.

## <a name="next-step"></a>Paso siguiente

Obtenga información sobre cómo Contoso [aprovecha sus Active Directory local Domain Services en la nube](contoso-identity.md) para los empleados y federa la autenticación para clientes y asociados empresariales.

## <a name="see-also"></a>Vea también

[Plan de trabajo de redes para Microsoft 365](networking-roadmap-microsoft-365.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Guías del laboratorio de pruebas](m365-enterprise-test-lab-guides.md)
