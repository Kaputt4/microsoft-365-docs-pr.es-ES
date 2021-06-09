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
description: Microsoft 365 está diseñado para permitir a los clientes de todo el mundo conectarse al servicio mediante una conexión a Internet. A medida que el servicio evoluciona, la seguridad, el rendimiento y la confiabilidad de Microsoft 365 se mejoran en función de los clientes que usan Internet para establecer una conexión al servicio.
ms.openlocfilehash: 4d80bdf5642b2456ac8293291c720429f7f18fb1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905481"
---
# <a name="assessing-microsoft-365-network-connectivity"></a>Evaluar la conectividad de red de Microsoft 365

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Microsoft 365 está diseñado para permitir a los clientes de todo el mundo conectarse al servicio mediante una conexión a Internet. A medida que el servicio evoluciona, la seguridad, el rendimiento y la confiabilidad de Microsoft 365 se mejoran en función de los clientes que usan Internet para establecer una conexión al servicio.
  
Los clientes que planean usar Microsoft 365 deben evaluar sus necesidades de conectividad a Internet existentes y previstas como parte del proyecto de implementación. Para las implementaciones de clase empresarial, la conectividad a Internet confiable y de tamaño adecuado es una parte fundamental del consumo de Microsoft 365 características y escenarios.
  
Muchas personas y organizaciones diferentes pueden realizar evaluaciones de red según su tamaño y preferencias. El ámbito de red de la evaluación también puede variar en función de dónde se encuentra en el proceso de implementación. To help you get a better understanding of what it takes to perform a network assessment, we've produced a network assessment guide to help you understand the options available to you. Esta evaluación determinará qué pasos y recursos deben agregarse al proyecto de implementación para que pueda adoptar correctamente Microsoft 365.
  
Una evaluación completa de la red proporcionará posibles soluciones a los desafíos de diseño de redes junto con los detalles de implementación. Algunas evaluaciones de red mostrarán que la conectividad de red óptima a Microsoft 365 se puede adaptar con cambios menores de configuración o diseño en la infraestructura de salida de Internet y de red existente.

Algunas evaluaciones indicarán que la conectividad de red Microsoft 365 requerirá inversiones adicionales en componentes de red. Por ejemplo, las redes empresariales que abarcan sucursales y varias regiones geográficas pueden requerir inversiones en soluciones SD-WAN o una infraestructura de enrutamiento optimizada para admitir la conectividad a Internet a Microsoft 365. En ocasiones, una evaluación indicará que la conectividad de red a Microsoft 365 está influenciada por los requisitos de regulación o rendimiento para escenarios como Skype Empresarial calidad de [medios en línea](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917). Estos requisitos adicionales pueden llevar a inversiones en infraestructura de conectividad a Internet, optimización de enrutamiento y conectividad directa especializada.

Algunos recursos que le ayudarán a evaluar la red:

- Vea [Microsoft 365 de conectividad de red para](microsoft-365-networking-overview.md) obtener información conceptual sobre Microsoft 365 redes.
- Consulte [Microsoft 365 principios](./microsoft-365-network-connectivity-principles.md) de conectividad de red para comprender los principios de conectividad para administrar de forma segura Microsoft 365 tráfico y obtener el mejor rendimiento posible.
- Regístrate en [Microsoft FastTrack para](https://www.microsoft.com/fasttrack) obtener asistencia guiada Microsoft 365 planeación, diseño e implementación. 
- Vea la [sección Microsoft 365](assessing-network-connectivity.md#the-microsoft-365-connectivity-test) prueba de conectividad de Microsoft 365 para ejecutar pruebas de conectividad básicas que proporcionan instrucciones específicas sobre las mejoras de conectividad de red que se pueden realizar entre una ubicación de usuario determinada y Microsoft 365.

> [!NOTE]
> Se requiere autorización de Microsoft para usar ExpressRoute para Office 365. Microsoft revisa todas las solicitudes de clientes y solo autoriza a ExpressRoute Office 365 uso cuando el requisito normativo de un cliente requiere conectividad directa. Si tiene estos requisitos, proporcione el extracto de texto y el vínculo web al reglamento que interprete para que la conectividad directa sea necesaria en el Formulario de solicitud de [ExpressRoute](https://aka.ms/O365ERReview) para Office 365 para iniciar una revisión de Microsoft. Las suscripciones no autorizadas que intenten crear filtros de Office 365 recibirán un [mensaje de error](https://support.microsoft.com/kb/3181709).
  
Puntos clave a tener en cuenta al planear la evaluación de red para Microsoft 365:
  
- Microsoft 365 es un servicio seguro, confiable y de alto rendimiento que se ejecuta a través de Internet pública. Seguimos invirtiendo para mejorar estos aspectos del servicio. Todos los Microsoft 365 están disponibles a través de la conectividad a Internet.

- Estamos optimizando continuamente los aspectos principales de Microsoft 365 como la disponibilidad, el alcance global y el rendimiento de la conectividad basada en Internet. Por ejemplo, muchos Microsoft 365 aprovechan un conjunto en expansión de nodos perimetrales orientados a Internet. Esta red perimetral ofrece la mejor proximidad y rendimiento a las conexiones que llegan a través de Internet.

- Al considerar el uso de Microsoft 365 para cualquiera de los servicios incluidos, como las capacidades de voz, vídeo o reunión en línea de Teams o Skype Empresarial, los clientes deben completar una evaluación de la red de extremo a extremo y cumplir los requisitos de conectividad con [Microsoft FastTrack.](https://www.microsoft.com/fasttrack)

Si está evaluando Microsoft 365 y no está seguro de dónde empezar con la evaluación de red o ha encontrado desafíos de diseño de red que necesita ayuda para superar, trabaje con su equipo de cuenta de Microsoft.

## <a name="the-microsoft-365-connectivity-test"></a>La Microsoft 365 de conectividad

La [prueba de conectividad](https://aka.ms/netonboard) Microsoft 365 es una herramienta de evaluación de red de prueba de concepto (POC) que ejecuta pruebas básicas de conectividad con el inquilino de Microsoft 365 y realiza recomendaciones específicas de diseño de red para un rendimiento Microsoft 365 óptimo. La herramienta destaca las opciones comunes de diseño perimetral de red de gran tamaño que son útiles para la exploración web de Internet, pero afectan al rendimiento de aplicaciones SaaS grandes, como Microsoft 365.

La herramienta de incorporación de red hace lo siguiente:

- Detecta la ubicación o puede especificar una ubicación para probar
- Comprueba la ubicación de la salida de red
- Prueba la ruta de acceso de red a la puerta Microsoft 365 de servicio más cercana
- Proporciona pruebas avanzadas mediante una aplicación Windows 10 que realiza recomendaciones de diseño de red perimetral relacionadas con servidores proxy, firewalls y DNS. La herramienta también ejecuta pruebas de rendimiento para Skype Empresarial Online, Microsoft Teams, SharePoint Online y Exchange Online.

La herramienta tiene dos componentes: una interfaz de usuario basada en explorador que recopila información básica de conectividad y una aplicación de Windows 10 descargable que ejecuta pruebas avanzadas y devuelve datos de evaluación adicionales.

La herramienta basada en explorador muestra la siguiente información:

- Pestaña Resultados e impacto
  - La ubicación en un mapa de la puerta principal del servicio en uso
  - La ubicación en un mapa de otras puertas frontales de servicio que proporcionarían una conectividad óptima
  - Rendimiento relativo en comparación con otros Microsoft 365 clientes cercanos
- Pestaña Detalles y soluciones
  - Ubicación del usuario por ciudad y país
  - Ubicación de salida de red por ciudad, estado y país
  - Distancia de salida de usuario a red
  - Microsoft 365 Exchange Online de la puerta principal del servicio
  - Servicio Microsoft 365 Exchange Online de servicio óptimo para la ubicación del usuario
  - Clientes de su área metropolitana con un mejor rendimiento

La aplicación descargable Pruebas avanzadas proporciona la siguiente información adicional:

- Ficha Detalles y soluciones (anexada)
  - Puerta de enlace predeterminada del usuario
  - Servidor DNS de cliente
  - Resolución recursiva dns de cliente
  - Exchange Online Servidor DNS
  - SharePoint Servidor DNS en línea
  - Identificación del servidor proxy
  - Comprobación de conectividad de medios
  - Pérdida de paquetes de calidad de medios
  - Latencia de calidad de medios
  - Vibración de calidad de medios
  - Reordenación de paquetes de calidad multimedia
- Pruebas de conectividad a varios puntos de conexión específicos de la característica
- Diagnósticos de ruta de acceso de red que incluyen datos de tracert y latencia para los servicios Exchange Online, SharePoint Online y Teams web

Puede leer acerca de la Microsoft 365 de conectividad y proporcionar comentarios en el [poc](https://techcommunity.microsoft.com/t5/Office-365-Networking/Updated-Office-365-Network-Onboarding-Tool-POC-with-new-network/m-p/711130#M130) de prueba de conectividad Microsoft 365 actualización con la nueva entrada de blog recomendaciones de diseño de red. La información sobre actualizaciones futuras de esta herramienta y otras actualizaciones Microsoft 365 de red se publicará en el [blog Office 365 networking.](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking)
  
Este es un breve vínculo que puede usar para volver: [ https://aka.ms/o365networkconnectivity .](./microsoft-365-network-connectivity-principles.md)
  
## <a name="related-topics"></a>Temas relacionados

[Información general de conectividad de red de Microsoft 365](microsoft-365-networking-overview.md)

[Principios de conectividad de red de Microsoft 365](./microsoft-365-network-connectivity-principles.md)

[Administrar puntos de conexión de Office 365](managing-office-365-endpoints.md)

[Direcciones URL e intervalos de direcciones IP de Office 365](urls-and-ip-address-ranges.md)

[Dirección IP de Office 365 y servicio web de URL](microsoft-365-ip-web-service.md)

[Microsoft 365 de red y rendimiento](network-planning-and-performance.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)