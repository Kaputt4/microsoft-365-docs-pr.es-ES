---
title: Redes para Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda la infraestructura de red de Contoso y cómo usa su tecnología SD-WAN para obtener un rendimiento de red óptimo de los servicios basados en la nube de Microsoft 365 Enterprise.
ms.openlocfilehash: 20279ac0aed1b7ad86e1fc8e1d78a412230eba52
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068355"
---
# <a name="networking-for-the-contoso-corporation"></a>Redes para Contoso Corporation

Para adoptar una infraestructura de nube inclusiva, los ingenieros de redes de Contoso materializaron el cambio fundamental en el modo en que el tráfico de red viaja a los servicios en la nube. En lugar de un modelo de concentrador y radio interno que centra la conectividad y el tráfico de red para el siguiente nivel de la jerarquía de la oficina de Contoso, trabajaron para asignar las ubicaciones de usuario a la salida de Internet local y las conexiones locales a las ubicaciones de red de Microsoft 365 más cercanas en Internet.

## <a name="contosos-networking-infrastructure"></a>Infraestructura de red de Contoso

Los elementos de la red de Contoso que vincula sus oficinas en todo el mundo son los siguientes:

- Red WAN de conmutación de etiquetas multiprotocolo (MPLS)

  Una red WAN MPLS conecta la sede central de París a las oficinas regionales y las oficinas regionales a las oficinas satélite en una configuración de concentrador y radio. Esto permite a los usuarios acceder a los servidores locales que conforman las aplicaciones de línea de negocio en la oficina de París. También enruta el tráfico de Internet genérico a la oficina de París, donde los dispositivos de seguridad de red limpian las solicitudes. En cada oficina, los enrutadores entregan el tráfico a hosts por cable o puntos de acceso inalámbricos en subredes, en las que se usa el espacio de direcciones IP privadas.

- Acceso a Internet directo local para el tráfico de Microsoft 365

  Cada oficina tiene un dispositivo WAN definido por software (SD-WAN) con uno o varios circuitos de red de ISP de Internet local con su propia conectividad a Internet a través de un servidor proxy. Esto suele implementarse como un vínculo WAN a un ISP local que también proporciona direcciones IP públicas y un servidor DNS local.

- Presencia en Internet

  Contoso posee el nombre de dominio público contoso.com. El sitio web público de Contoso para pedir productos es un conjunto de servidores en un centro de datos conectado a Internet en las instalaciones de París. Contoso usa un intervalo de direcciones IP públicas /24 en Internet.

En la ilustración 1, se muestra la infraestructura de red de Contoso y sus conexiones a Internet.

![Red de Contoso](../media/contoso-networking/contoso-networking-fig1.png)
 
**Ilustración 1: Red de Contoso**

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a>Uso de SD-WAN para la conectividad de red óptima a Microsoft

Contoso siguió los [principios de conectividad de red de Office 365](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles) para:

1. Identificar y diferenciar el tráfico de red de Office 365
2. Conexiones de red de salida de forma local
3. Evitar las redirecciones de red
4. Omitir los dispositivos de seguridad de red duplicados

Hay tres categorías de tráfico de red para Office 365: optimizar, permitir y predeterminado. El tráfico de las categorías Optimizar y Permitir es el tráfico de red de confianza que se cifra y protege en los puntos de conexión y se destina a la red de Microsoft 365.

Contoso decidió:

- Usar la salida de Internet directa para el tráfico de las categorías Optimizar y Permitir, y reenviar todo el tráfico de la categoría Predeterminado a la conexión de Internet de la central en París.

- Implementar dispositivos SD-WAN en cada una de las oficinas como una forma sencilla de seguir estos principios y obtener un rendimiento de red óptimo para los servicios basados en la nube de Microsoft 365.

  Los dispositivos SD-WAN tienen un puerto LAN para la red de oficina local y varios puertos WAN. Un puerto WAN se conecta a su red MPLS y otro puerto WAN se conecta a un circuito ISP local. El dispositivo SD-WAN enruta el tráfico de las categorías Optimizar y Permitir en el vínculo de ISP.

## <a name="contosos-line-of-business-app-infrastructure"></a>Infraestructura de aplicaciones de línea de negocio de Contoso

Contoso ha diseñado su infraestructura de intranet de servidores y aplicaciones de línea de negocio para lo siguiente:

- En las oficinas satélite se usan servidores de almacenamiento en caché locales para almacenar documentos y sitios web internos a los que se accede frecuentemente.
- En los centros regionales se usan servidores de aplicaciones regionales para las oficinas regionales y satélite. Estos servidores se sincronizan con los de la sede de París.
- Los centros de datos que contienen los servidores de aplicaciones centralizados que sirven a toda la organización se encuentran en las instalaciones de París.

En la ilustración 2, se muestra el porcentaje de tráfico de red cuando se obtiene acceso a los servidores de la intranet de Contoso.

![Infraestructura de Contoso para aplicaciones internas](../media/contoso-networking/contoso-networking-fig2.png)
 
**Ilustración 2: Infraestructura de Contoso para aplicaciones internas**

Para los usuarios de oficinas de centros regionales o satélite, el 60 % de los recursos que necesitan los empleados pueden obtenerse de los servidores de oficinas de concentradores regionales o satélite. El 40 % adicional de solicitudes de recursos debe realizarse a través del vínculo WAN a las instalaciones de París.

## <a name="contosos-network-analysis-and-preparation-of-their-network-for-microsoft-365-enterprise"></a>Análisis de red de Contoso y preparación de su red para Microsoft 365 Enterprise

La adopción correcta de los servicios de Microsoft 365 Enterprise por parte de los usuarios de Contoso depende de la alta disponibilidad y del rendimiento de la conectividad a Internet, o bien directamente a los servicios en la nube de Microsoft. Contoso siguió estos pasos para planear e implementar la conectividad optimizada a los servicios en la nube de Microsoft 365 Enterprise:

1. Creación de un diagrama de red WAN de la empresa para ayudar con la planificación

   Contoso inició la planificación de la red creando un diagrama en el que se muestran sus ubicaciones, la conectividad de red y los dispositivos perimetrales de red existentes, y las clases de servicio que se administran en la red. Usaron este diagrama en todos los pasos siguientes de la planificación e implementación de la conectividad de red.

2. Crear un plan para la conectividad de red de Microsoft 365 Enterprise

   Contoso usó los [principios de conectividad de red de Office 365](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles) y proporcionó arquitecturas de red de referencia para determinar SD-WAN como su topología preferida para la conectividad de Office 365.

3. Se analizó el uso de la conexión a Internet y el ancho de banda WAN MPLS en cada oficina y se aumentó el ancho de banda si era necesario.

   En todas las oficinas se analizó el uso actual y se aumentaron los circuitos para que el tráfico basado en la nube de Microsoft 365 pronosticado fuera operativo con una media del 20 % de la capacidad sin usar.

4. Optimización del rendimiento para los servicios de red de Microsoft

   Contoso determinó el conjunto de puntos de conexión de Office 365, Intune y Azure, y configuró firewalls, dispositivos de seguridad y otros sistemas en la ruta de acceso a Internet para obtener un rendimiento óptimo. Se configuraron puntos de conexión para el tráfico de la categoría optimizar y permitir de Office 365 en los dispositivos SD-WAN para enrutar a través del circuito ISP.

5. Configuración de DNS interno

   DNS debe ser funcional y buscarse de forma local para el tráfico de Office 365.

6. Validación de los puntos de conexión de red y la conectividad de los puertos

   Contoso ejecutó herramientas de pruebas de conectividad de red proporcionadas por Microsoft para validar la conectividad de los servicios en la nube de Microsoft 365 Enterprise.

7. Optimización de los equipos de los empleados para la conectividad de red

   Los equipos se comprobaron de forma individual para asegurarse de que se habían instalado las actualizaciones del sistema operativo más recientes y que la supervisión de la seguridad de los puntos de conexión estaba activa en todos los clientes.

## <a name="next-step"></a>Siguiente paso

[Obtenga información sobre](contoso-identity.md) cómo aprovecha Contoso sus Servicios de dominio de Active Directory(AD DS) locales en la nube para la autenticación de federación y empleados para los clientes y socios empresariales.

## <a name="see-also"></a>Vea también

[Redes para Microsoft 365 Enterprise](networking-infrastructure.md)

[Guía de implementación](deploy-microsoft-365-enterprise.md)

[Guías del laboratorio de pruebas](m365-enterprise-test-lab-guides.md)
