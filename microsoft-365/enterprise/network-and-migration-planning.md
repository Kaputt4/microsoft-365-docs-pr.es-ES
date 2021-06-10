---
title: Planeación de la migración y la red para Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- BCS160
ms.assetid: f5ee6c33-bcd7-4b0b-b0f8-dc1d9fb8d132
description: Este artículo contiene vínculos a información sobre planeación de red, pruebas y migración a Office 365.
ms.openlocfilehash: 99bcc1bd0447b192860fc0bcc67fc18d87c2d5fc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923593"
---
# <a name="network-and-migration-planning-for-office-365"></a>Planeación de la migración y la red para Office 365

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Este artículo contiene vínculos a información sobre la planeación y pruebas de red, y la migración a Office 365.
  
Antes de implementar por primera vez o migrar a Office 365, puede usar la información de estos temas para calcular el ancho de banda que necesita y, a continuación, probar y comprobar que tiene suficiente ancho de banda para implementar o migrar a Office 365.

Este artículo forma parte de [la planeación de red y el](./network-planning-and-performance.md)ajuste del rendimiento para Office 365 .

Para ver los pasos para optimizar la red para Microsoft 365 y otros servicios y plataformas en la nube de Microsoft, consulte el póster Microsoft [Cloud Networking for Enterprise Architects.](../solutions/cloud-architecture-models.md)
   
## <a name="estimate-network-bandwidth-requirements"></a>Estimar los requisitos de ancho de banda de red
<a name="EstimateBandwidthRequirements"> </a>

El Office 365 puede aumentar el uso del circuito de Internet de su organización. Es importante determinar si la cantidad de ancho de banda disponible actualmente es suficiente para controlar el aumento estimado una vez que Office 365 se implementa completamente y deja al menos un 20 % de capacidad para controlar los días más ocupados.
  
Para calcular el ancho de banda, siga estos pasos:
  
1. Evalúe el número de clientes que usarán cada salida de Internet. Deje que nuestra red de varios terabits controle la mayor parte de la conexión posible. 
    
2. Determine qué Office 365 y características estarán disponibles para que los clientes los usen. Es probable que tenga grupos de personas con diferentes servicios o perfiles de uso.
    
3. Medir el uso de red para un grupo piloto de clientes. Asegúrese de que los clientes piloto son representativos de los diferentes perfiles de personas de la organización, así como de las distintas ubicaciones geográficas. Puede consultar los resultados en nuestras [](https://techcommunity.microsoft.com/t5/exchange-team-blog/announcing-the-exchange-client-network-bandwidth-calculator-beta/ba-p/601744) calculadoras antiguas para Exchange y [](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365) [Microsoft Teams](/microsoftteams/prepare-network) caso práctico que hemos realizado en nuestra propia red. 
    
4. Use las medidas del grupo piloto para extrapolar las necesidades de toda la organización y volver a probar para validar las estimaciones antes de realizar cambios en la red.
    
## <a name="test-your-existing-network"></a>Probar la red existente
<a name="calculators"> </a>

 **Herramientas de red.** Pruebe y valide el ancho de banda de Internet para determinar las restricciones de descarga, carga y latencia. Estas herramientas le ayudarán a determinar las capacidades de la red para la migración, así como después de que esté completamente implementado. 
    
- [Analizador de conectividad remota de Microsoft:](https://go.microsoft.com/fwlink/p/?LinkId=517243)prueba la conectividad en Exchange Online entorno.
    
- Use microsoft [Asistente de soporte y recuperación for Office 365](https://diagnostics.office.com/#/Download?env=SOC) para solucionar Outlook y Office 365 problemas. 
    
## <a name="best-practices-for-network-planning-and-improving-migration-performance-for-office-365"></a>Procedimientos recomendados para planear la red y mejorar el rendimiento de la migración para Office 365
<a name="BestPractices"> </a>

Profundizar un poco más en estos procedimientos recomendados para obtener más información sobre cómo mejorar Office 365 experiencia.
  
1. ¿Quieres empezar a ayudar a los usuarios de inmediato? Consulte [Procedimientos recomendados](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166) para usar Office 365 en una red lenta para obtener sugerencias sobre el uso de Office 365, incluidos SharePoint Online, Exchange Online y Lync Online, cuando la red simplemente no está cooperando. En este artículo se vincula a una gran cantidad de contenido en TechNet y Support.office.com para optimizar la experiencia de Office 365 e incluye información sobre formas sencillas de personalizar las páginas web y cómo establecer la configuración de Internet Explorer para obtener la mejor experiencia Office 365 usuario. 
    
2. Lea [Office 365 principios](./microsoft-365-network-connectivity-principles.md) de conectividad de red para comprender los principios de conectividad para administrar de forma Office 365 tráfico y obtener el mejor rendimiento posible. Este artículo le ayudará a comprender las instrucciones más recientes para optimizar de forma segura la conectividad de red de Office 365. 
    
3. Mejore el rendimiento de la migración de correo administrando cuidadosamente la programación de Windows actualizaciones. Puede actualizar los equipos cliente en lotes y asegurarse de que todos los equipos cliente se actualicen antes de migrar a Office 365 para regular el uso del ancho de banda de red. Para obtener más información, vea Actualización manual y [configuración de escritorios para Office 365 para las actualizaciones más recientes.](https://support.microsoft.com/gp/office-2013-365-update)
    
4. Office 365 tráfico de red funciona mejor cuando se trata como un servicio de Internet de confianza y se permite omitir gran parte del filtrado y el examen tradicionales que algunas organizaciones realizan en el tráfico de red a servicios de Internet que no son de confianza. Esto suele incluir la eliminación del procesamiento saliente, como la autenticación de usuario proxy y la inspección de paquetes, así como garantizar la salida local a Internet con la traducción de direcciones de red (NAT) adecuada y suficiente capacidad de ancho de banda para controlar el aumento de las solicitudes de red. Consulte [Managing Office 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)para obtener instrucciones adicionales sobre cómo configurar la red para controlar Office 365 como un servicio de Internet de confianza en la red.
    
1. Asegúrese [de administrar Office 365 de conexión](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a). El tráfico adicional que se Office 365 da como resultado un aumento de las conexiones de proxy salientes, así como un aumento del tráfico seguro a través de TLS/SSL.
    
2. Si los servidores proxy salientes requieren autenticación de usuario, es posible que experimente una conectividad lenta o una pérdida de funcionalidad. Omitir el requisito de autenticación para los Office 365 puede reducir esta sobrecarga.
    
3. Si tiene un gran número de calendarios y buzones compartidos, es posible que vea un aumento en el número de conexiones de Outlook a Exchange. Por ejemplo, el Outlook puede abrir hasta dos conexiones adicionales para cada calendario compartido en uso. En esta situación, asegúrese de que el proxy de salida puede controlar las conexiones o omitir el proxy para las conexiones a Office 365 para Outlook.
    
4. Determine el número máximo de dispositivos admitidos para una dirección IP pública y cómo equilibrar la carga entre varias direcciones IP. Para obtener más información, consulte [Compatibilidad de NAT con Office 365](nat-support-with-microsoft-365.md).
    
5. Si va a inspeccionar las conexiones salientes de los equipos de la red, omitir este filtrado a los dominios Office 365 mejorará la conectividad y el rendimiento. Además, omitir la inspección saliente a menudo elimina la necesidad de una única salida de Internet y habilita la salida de Internet local para Office 365 de red destinada.
    
6. Algunos clientes encuentran que la configuración de red interna puede afectar al rendimiento. Configuración como el tamaño máximo de la unidad de transmisión (MTU), la negociación automática de red o la detección automática, y las rutas sub-óptimas a Internet son lugares comunes para buscar.
    
## <a name="network-planning-reference-for-office-365"></a>Referencia de planeación de red para Office 365
<a name="NetReference"> </a>

Estos temas contienen información detallada Office 365 de referencia de red.
  
- [Administrar puntos de conexión de Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
    
- [Redes de entrega de contenido](content-delivery-networks.md)
    
- [Registros externos del Sistema de nombres de dominio para Office 365](external-domain-name-system-records.md)
    
- [Compatibilidad con IPv6 en servicios de Office 365](ipv6-support.md)
    
- [Principios de conectividad de red de Office 365](./microsoft-365-network-connectivity-principles.md)
    
- [Office 365 de vídeo con preguntas más frecuentes (PREGUNTAS FRECUENTES)](office-365-video-networking-faq.md)
    
- [Planificación de dispositivos de red que se conecten a servicios de Office 365](plan-for-network-devices.md)
    
- [Guías de instalación para Office 365 servicios](setup-guides-for-microsoft-365.md)
 
## <a name="see-also"></a>Consulte también

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)