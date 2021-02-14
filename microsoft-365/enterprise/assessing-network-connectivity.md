---
title: Evaluar la conectividad de red de Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/23/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 64b420ef-0218-48f6-8a34-74bb27633b10
description: Microsoft 365 está diseñado para permitir que los clientes de todo el mundo se conecten al servicio mediante una conexión a Internet. A medida que el servicio evoluciona, la seguridad, el rendimiento y la confiabilidad de Microsoft 365 se mejoran en función de los clientes que usan Internet para establecer una conexión al servicio.
ms.openlocfilehash: c0bca2f354d71aa2f4f0c2b6fd05cb4786368b43
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694020"
---
# <a name="assessing-microsoft-365-network-connectivity"></a>Evaluar la conectividad de red de Microsoft 365

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Microsoft 365 está diseñado para permitir que los clientes de todo el mundo se conecten al servicio mediante una conexión a Internet. A medida que el servicio evoluciona, la seguridad, el rendimiento y la confiabilidad de Microsoft 365 se mejoran en función de los clientes que usan Internet para establecer una conexión al servicio.
  
Los clientes que planean usar Microsoft 365 deben evaluar sus necesidades de conectividad a Internet existentes y previstas como parte del proyecto de implementación. Para las implementaciones de clase empresarial, la conectividad a Internet confiable y con un tamaño adecuado es una parte fundamental del consumo de características y escenarios de Microsoft 365.
  
Muchas personas y organizaciones diferentes pueden realizar evaluaciones de red en función de su tamaño y preferencias. El ámbito de red de la evaluación también puede variar en función de dónde se encuentra en el proceso de implementación. Para ayudarle a comprender mejor lo que se necesita para realizar una evaluación de red, hemos producido una guía de evaluación de red que le ayudará a comprender las opciones disponibles. Esta evaluación determinará qué pasos y recursos se deben agregar al proyecto de implementación para permitirle adoptar correctamente Microsoft 365.
  
Una evaluación completa de la red proporcionará posibles soluciones a los desafíos de diseño de redes junto con los detalles de implementación. Algunas evaluaciones de red mostrarán que la conectividad de red óptima a Microsoft 365 se puede adaptar con pequeños cambios de configuración o diseño en la infraestructura de red e internet existente.

Algunas evaluaciones indicarán que la conectividad de red a Microsoft 365 requerirá inversiones adicionales en componentes de red. Por ejemplo, las redes empresariales que abarcan sucursales y varias regiones geográficas pueden requerir inversiones en soluciones SD-WAN o una infraestructura de enrutamiento optimizada para admitir la conectividad a Internet a Microsoft 365. En ocasiones, una evaluación indicará que la conectividad de red a Microsoft 365 está influenciada por la regulación o los requisitos de rendimiento para escenarios como la calidad de medios de [Skype Empresarial Online.](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917) Estos requisitos adicionales pueden llevar a inversiones en infraestructura de conectividad a Internet, optimización de enrutamiento y conectividad directa especializada.

Algunos recursos que le ayudarán a evaluar la red:

- Vea [información general sobre la conectividad de red de Microsoft 365](microsoft-365-networking-overview.md) para obtener información conceptual sobre las redes de Microsoft 365.
- Consulte los Principios de conectividad de red de [Microsoft 365](https://aka.ms/o365networkingprinciples) para comprender los principios de conectividad para administrar de forma segura el tráfico de Microsoft 365 y obtener el mejor rendimiento posible.
- Regístrese en [Microsoft FastTrack para](https://www.microsoft.com/fasttrack) obtener asistencia guiada con la planeación, el diseño y la implementación de Microsoft 365. 
- Consulte la sección de pruebas de conectividad de [Microsoft 365](assessing-network-connectivity.md#the-microsoft-365-connectivity-test) a continuación para ejecutar pruebas de conectividad básicas que proporcionan instrucciones específicas sobre las mejoras de conectividad de red que se pueden realizar entre una ubicación de usuario determinada y Microsoft 365.

> [!NOTE]
> Se requiere autorización de Microsoft para usar ExpressRoute para Office 365. Microsoft revisa todas las solicitudes de los clientes y solo autoriza el uso de ExpressRoute para Office 365 cuando los requisitos normativos de un cliente exigen conectividad directa. Si tiene estos requisitos, proporcione el extracto de texto y el vínculo web al reglamento que interpreta para significar que se requiere conectividad directa en el formulario de solicitud de ExpressRoute para [Office 365](https://aka.ms/O365ERReview) para comenzar una revisión de Microsoft. Las suscripciones no autorizadas que intentan crear filtros de ruta para Office 365 recibirán un [mensaje de error.](https://support.microsoft.com/kb/3181709)
  
Puntos clave que se deben tener en cuenta al planear la evaluación de red para Microsoft 365:
  
- Microsoft 365 es un servicio seguro, confiable y de alto rendimiento que se ejecuta a través de Internet público. Seguimos invirtiendo para mejorar estos aspectos del servicio. Todos los servicios de Microsoft 365 están disponibles a través de la conectividad a Internet.

- Estamos optimizando continuamente aspectos básicos de Microsoft 365, como la disponibilidad, el alcance global y el rendimiento de la conectividad basada en Internet. Por ejemplo, muchos servicios de Microsoft 365 aprovechan un conjunto en expansión de nodos perimetrales orientados a Internet. Esta red perimetral ofrece la mejor proximidad y rendimiento a las conexiones que llegan a través de Internet.

- Al considerar el uso de Microsoft 365 para cualquiera de los servicios incluidos, como Teams o Skype Empresarial Online, funciones de voz, vídeo o reunión, los clientes deben completar una evaluación de la red de un extremo a otro y cumplir los requisitos de conectividad con [Microsoft FastTrack.](https://www.microsoft.com/fasttrack)

Si está evaluando Microsoft 365 y no está seguro de dónde comenzar con su evaluación de red o ha encontrado desafíos de diseño de red que necesita ayuda para superar, trabaje con su equipo de cuenta de Microsoft.

## <a name="the-microsoft-365-connectivity-test"></a>La prueba de conectividad de Microsoft 365

La prueba de conectividad de [Microsoft 365](https://aka.ms/netonboard) es una herramienta de evaluación de red de prueba de concepto (POC) que ejecuta pruebas de conectividad básicas con su inquilino de Microsoft 365 y hace recomendaciones de diseño de red específicas para un rendimiento óptimo de Microsoft 365. La herramienta destaca las opciones comunes de diseño perimetral de red empresarial de gran tamaño que son útiles para la exploración web de Internet, pero afectan al rendimiento de aplicaciones SaaS de gran tamaño, como Microsoft 365.

La herramienta de incorporación de red hace lo siguiente:

- Detecta la ubicación o puede especificar una ubicación para probar
- Comprueba la ubicación de la salida de red
- Prueba la ruta de acceso de red a la puerta principal del servicio de Microsoft 365 más cercana
- Proporciona pruebas avanzadas con una aplicación descargable de Windows 10 que realiza recomendaciones de diseño de red perimetral relacionadas con servidores proxy, firewalls y DNS. La herramienta también ejecuta pruebas de rendimiento para Skype Empresarial Online, Microsoft Teams, SharePoint Online y Exchange Online.

La herramienta tiene dos componentes: una interfaz de usuario basada en explorador que recopila información de conectividad básica y una aplicación descargable de Windows 10 que ejecuta pruebas avanzadas y devuelve datos de evaluación adicionales.

La herramienta basada en el explorador muestra la siguiente información:

- Pestaña Resultados y impacto
  - La ubicación en un mapa de la puerta principal del servicio en uso
  - Ubicación en un mapa de otras puertas frontales de servicio que proporcionarían una conectividad óptima
  - Rendimiento relativo en comparación con otros clientes de Microsoft 365 cercanos
- Pestaña Detalles y soluciones
  - Ubicación del usuario por ciudad y país
  - Ubicación de salida de red por ciudad, estado y país
  - Distancia de salida de usuario a red
  - Ubicación de la puerta principal del servicio de Exchange Online de Microsoft 365
  - Puertas frontales del servicio de Microsoft 365 Exchange Online óptimos para la ubicación del usuario
  - Clientes de tu área de metro con mejor rendimiento

La aplicación descargable Pruebas avanzadas proporciona la siguiente información adicional:

- Pestaña Detalles y soluciones (anexado)
  - Puerta de enlace predeterminada del usuario
  - Servidor DNS de cliente
  - Resolución recursiva de DNS de cliente
  - Servidor DNS de Exchange Online
  - Servidor DNS de SharePoint Online
  - Identificación del servidor proxy
  - Comprobación de conectividad de medios
  - Pérdida de paquetes de calidad de medios
  - Latencia de calidad de medios
  - Vibración de calidad de medios
  - Reordenación de paquetes de calidad de medios
- Pruebas de conectividad a varios extremos específicos de la característica
- Diagnósticos de ruta de acceso de red que incluyen datos de seguimiento y latencia para los servicios de Exchange Online, SharePoint Online y Teams

Puede leer sobre la prueba de conectividad de Microsoft 365 y proporcionar comentarios en el POC de prueba de conectividad de [Microsoft 365](https://techcommunity.microsoft.com/t5/Office-365-Networking/Updated-Office-365-Network-Onboarding-Tool-POC-with-new-network/m-p/711130#M130) actualizado con una nueva entrada de blog de recomendaciones de diseño de red. La información sobre actualizaciones futuras de esta herramienta y otras actualizaciones de red de Microsoft 365 se publicará en el blog de redes de [Office 365.](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking)
  
Este es un vínculo breve que puede usar para volver: [ https://aka.ms/o365networkconnectivity .](https://aka.ms/o365networkconnectivity)
  
## <a name="related-topics"></a>Temas relacionados

[Información general de conectividad de red de Microsoft 365](microsoft-365-networking-overview.md)

[Principios de conectividad de red de Microsoft 365](https://aka.ms/o365networkingprinciples)

[Administrar puntos de conexión de Office 365](managing-office-365-endpoints.md)

[Direcciones URL e intervalos de direcciones IP de Office 365](urls-and-ip-address-ranges.md)

[Dirección IP de Office 365 y servicio web de URL](microsoft-365-ip-web-service.md)

[Ajuste de red y rendimiento de Microsoft 365](network-planning-and-performance.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)
