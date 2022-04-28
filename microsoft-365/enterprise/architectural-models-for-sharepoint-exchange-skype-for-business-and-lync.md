---
title: Modelos de arquitectura para SharePoint, Exchange, Skype Empresarial y Lync
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 05/16/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Ent_Architecture
ms.assetid: 5b49fa68-f8f2-4705-af96-5f5475e8539a
search.appverid:
- MET150
description: Obtenga pósteres de TI que describan los modelos arquitectónicos, la implementación y las opciones de plataforma para SharePoint, Exchange, Skype Empresarial y Lync.
ms.openlocfilehash: 859d952fc9a2e4e9315c7fef3e56b4e59d0f60d6
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65096884"
---
# <a name="architectural-models-for-sharepoint-exchange-skype-for-business-and-lync"></a>Modelos de arquitectura para SharePoint, Exchange, Skype Empresarial y Lync

En los pósteres de TI de este artículo se describen los modelos arquitectónicos y las opciones de implementación de SharePoint, Exchange, Skype Empresarial y Lync. También proporcionan información de diseño para implementar SharePoint en Microsoft Azure.
  
Mediante el uso de Microsoft 365, puede proporcionar servicios de colaboración y comunicación conocidos a través de la nube. Con algunas excepciones, la experiencia del usuario sigue siendo la misma tanto si se mantiene una implementación local como si se usa Microsoft 365. 

Esta experiencia de usuario unificada complica la decisión de dónde colocar cada carga de trabajo. También plantea preguntas:
  
- ¿Cómo se elige una plataforma para cargas de trabajo individuales?
    
- ¿Tiene sentido conservar los servicios locales?
    
- ¿En qué escenario es adecuada una implementación híbrida?
    
- ¿Cómo encaja Azure en la imagen?
    
- ¿Qué configuraciones de Office cargas de trabajo de servidor Soporte técnico de Azure?
    
> [!TIP]
> La mayoría de los pósteres de este artículo están disponibles en varios idiomas. Los idiomas disponibles son chino, inglés, francés, alemán, italiano, japonés, coreano, portugués, ruso y español. Para descargar un póster en uno de estos idiomas, en la imagen en miniatura del póster, seleccione **Más idiomas**.
  
Queremos conocer su opinión. Envíenos un correo electrónico a [cloudadopt@microsoft.com](mailto:cloudadopt@microsoft.com). 
  
Use los siguientes vínculos para obtener los pósteres que necesita:
  
- **Modelos arquitectónicos**: use estos recursos para determinar la plataforma y la configuración ideales para SharePoint 2016 y Skype Empresarial 2015.
    
  - [Modelos arquitectónicos de Microsoft SharePoint 2016](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2016_ArchModel)
    
  - [bases de datos de SharePoint Server 2016](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2016_Databases)
    
  - [Modelos arquitectónicos de Microsoft Skype Empresarial 2015](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SfB2015_ArchModel)
    
- **Plataforma**: use estos recursos para determinar la plataforma y la configuración ideales para SharePoint 2013, Exchange 2013 y Lync 2013.
    
  - [opciones de plataforma de SharePoint 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2013_Options)
    
  - [opciones de plataforma de Exchange 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Exch2013_options)
    
  - [Opciones de la plataforma Lync 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Lync2013_Options)
    
- **SharePoint Server 2013 en Azure**: use estos pósteres de TI para diseñar y configurar cargas de trabajo de SharePoint Server 2013 en servicios de infraestructura de Azure.
    
  - [Sitios de Internet en Azure mediante SharePoint Server 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Azure_sharepoint2013)
    
  - [Ejemplo de diseño: sitios de Internet en Azure para SharePoint 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#DesignSampleInternetSites)
    
  - [SharePoint recuperación ante desastres en Azure](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#sharepoint_recovery_Azure)
    
## <a name="architectural-models-posters"></a>Pósteres de modelos de arquitectura

Los pósteres de TI de SharePoint 2016 y Skype Empresarial 2015 proporcionan una manera de comparar los métodos de implementación en un formato fácil de imprimir. Los pósteres muestran todas las opciones de configuración o plataforma. Proporcionan la siguiente información para cada opción:
  
- **Información general**: breve resumen de la plataforma, incluido un diagrama conceptual.
    
- **Mejor para**: escenarios comunes que son idealmente adecuados para la plataforma.
    
- **Requisitos de licencia**: las licencias que necesita para la implementación.
    
- **Tareas de arquitectura**: las decisiones que debe tomar como arquitecto.
    
- **Tareas o responsabilidades profesionales de TI**: las responsabilidades diarias que el personal de TI debe planear.
    
<a name="SP2016_ArchModel"> </a>
### <a name="microsoft-sharepoint-server-2016-architectural-models"></a>Modelos de arquitectura de Microsoft SharePoint Server 2016

|Elemento|Descripción|
|---|---|
|[![Miniatura del póster modelos arquitectónicos de SharePoint Server 2016.](../media/7d3e590c-1f3b-42cf-920d-9edac8fa3e04.png)          ](https://www.microsoft.com/download/details.aspx?id=52650) <br/> [PDF](https://download.microsoft.com/download/4/F/A/4FA0F94B-EE2F-41DB-A047-D9864FEF41E9/SharePoint2016ArchitecturalModels.pdf)  \| [Visio](https://download.microsoft.com/download/4/F/A/4FA0F94B-EE2F-41DB-A047-D9864FEF41E9/SharePoint2016ArchitecturalModels.vsdx)  \| [Más idiomas](https://www.microsoft.com/download/details.aspx?id=52650)|En este póster de TI se describen las configuraciones locales de SharePoint Online, Azure y SharePoint que los arquitectos de soluciones y responsables de la toma de decisiones empresariales necesitan conocer. <br/><br/> - **SharePoint Online (SaaS):** consuma SharePoint a través de un modelo de suscripción de software como servicio (SaaS). <br/> - **SharePoint híbrido**: mueva los sitios y aplicaciones de SharePoint a la nube a su propio ritmo. <br/> - **SharePoint en Azure (IaaS):** amplíe el entorno local en Azure e implemente allí SharePoint servidores de 2016. (Este modelo se recomienda para entornos de alta disponibilidad o recuperación ante desastres y entornos de desarrollo y pruebas). <br/> - **SharePoint local**: planee, implemente, mantenga y personalice el entorno de SharePoint en un centro de datos que mantenga.|
   
<a name="SP2016_Databases"> </a>
### <a name="sharepoint-server-2016-databases"></a>Bases de datos de SharePoint Server 2016

|Elemento|Descripción|
|---|---|
|[![Miniatura del póster de bases de datos de SharePoint Server 2016.](../media/c53e9de7-3bf8-446d-8766-e6700c8dd8e1.png)](https://www.microsoft.com/download/details.aspx?id=55041) <br/> [PDF](https://download.microsoft.com/download/D/5/D/D5DC1121-8BC5-4953-834F-1B5BB03EB691/DBrefguideSPS2016_tabloid.pdf)  \| [Visio](https://download.microsoft.com/download/D/5/D/D5DC1121-8BC5-4953-834F-1B5BB03EB691/DBrefguideSPS2016_tabloid.vsdx)  \| [Más idiomas](https://www.microsoft.com/download/details.aspx?id=55041)|Este póster de TI es una referencia rápida para las bases de datos de SharePoint Server 2016. Verá los detalles de cada base de datos: <br/><br/> - Tamaño <br/> - Instrucciones de escalado <br/> - Patrones de E/S <br/> - Requisitos <br/><br/>  En la primera página se muestran las bases de datos del sistema de SharePoint y las aplicaciones de servicio que tienen varias bases de datos. En la segunda página se muestran todas las aplicaciones de servicio que tienen las bases de datos únicas. <br/><br/>  Para obtener más información, vea [Tipos de base de datos y descripciones en SharePoint Server 2016](/SharePoint/technical-reference/database-types-and-descriptions).|
   
<a name="SfB2015_ArchModel"> </a>
### <a name="microsoft-skype-for-business-2015-architectural-models"></a>Modelos de arquitectura de Microsoft Skype Empresarial 2015

|Elemento|Descripción|
|---|---|
|[![Miniatura del póster de modelos arquitectónicos de Skype Empresarial.](../media/132288c0-6ae4-4394-88ab-b57dae367714.png)](https://www.microsoft.com/download/details.aspx?id=55022) <br/> [PDF](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.pdf)  \| [Visio](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.vsd)  \| [Más idiomas](https://www.microsoft.com/download/details.aspx?id=55022)|En este póster se describe Skype Empresarial en línea, local, híbrido y en la nube de intercambio de sucursales privadas (PBX). También describe la integración con configuraciones de Exchange y SharePoint que los arquitectos de soluciones y responsables de la toma de decisiones empresariales necesitan conocer. <br/><br/> El póster está destinado a profesionales de TI para dar a conocer los modelos arquitectónicos fundamentales a través de los cuales se pueden consumir Skype Empresarial Online y Skype Empresarial local. <br/><br/>Comience con la configuración que mejor se adapte a las necesidades y planes de su organización. Considere y use otras configuraciones según sea necesario. Por ejemplo, es posible que desee considerar la integración con Exchange y SharePoint o una solución que aproveche la oferta de PBX en la nube de Microsoft.|
   
## <a name="platform-options-posters"></a>Pósteres de opciones de plataforma

Los pósteres de TI de SharePoint 2013, Exchange 2013 y Lync 2013 proporcionan una manera de comparar los métodos de implementación de un vistazo. Cada póster muestra todas las configuraciones o opciones de plataforma. Proporciona la siguiente información para cada opción:
  
- **Información general**: breve resumen de la plataforma, incluido un diagrama conceptual.
    
- **Mejor para**: escenarios comunes que son idealmente adecuados para la plataforma.
    
- **Requisitos de licencia**: las licencias que necesita para la implementación.
    
- **Tareas de arquitectura**: las decisiones que debe tomar como arquitecto.
    
- **Tareas o responsabilidades profesionales de TI**: las responsabilidades diarias que el personal de TI debe planear.
    
<a name="SP2013_Options"> </a>
## <a name="sharepoint-2013-platform-options"></a>Opciones de plataforma para SharePoint 2013

|Elemento|Descripción|
|---|---|
|[![Imagen en miniatura del póster de opciones de la plataforma de SharePoint 2013.](../media/SP-PlatformOptions.jpg)](https://www.microsoft.com/download/details.aspx?id=40332) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=324594)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=324593)  \| [Más idiomas](https://www.microsoft.com/download/details.aspx?id=40332)|Para los responsables de la toma de decisiones empresariales y los arquitectos, este póster muestra las opciones de plataforma para SharePoint 2013, SharePoint en Microsoft 365, híbrido local con implementaciones de Microsoft 365, Azure y solo locales. Incluye información general de cada arquitectura, recomendaciones, requisitos de licencia y listas de tareas de arquitectos y profesionales de TI para cada plataforma. En el póster se resaltan varias soluciones de SharePoint en Azure.|
   
<a name="Exch2013_options"> </a>
## <a name="exchange-2013-platform-options"></a>Opciones de plataforma para Exchange 2013

|Elemento|Descripción|
|---|---|
|[![Imagen en miniatura del póster de opciones de plataforma de Exchange.](../media/ITPro-Other-Exchange2013PlatformOptions.jpg)          ](https://www.microsoft.com/download/details.aspx?id=42676) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkID=398740)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkID=398742)  \| [Más idiomas](https://www.microsoft.com/download/details.aspx?id=42676)|Para los responsables de la toma de decisiones empresariales y los arquitectos, en este póster se describen las opciones de plataforma para Exchange 2013. Los clientes pueden elegir entre Exchange Online con Microsoft 365, Exchange híbrida, Exchange Server local y Exchange hospedadas. En el póster se detalla cada opción arquitectónica, incluidos los escenarios ideales para cada uno, los requisitos de licencia y las responsabilidades de profesionales de TI.|
   
<a name="Lync2013_Options"> </a>
## <a name="lync-2013-platform-options"></a>Opciones de plataforma para Lync 2013

|Elemento|Descripción|
|---|---|
|[![Imagen en miniatura del póster de opciones de plataforma de Lync 2013.](../media/Lync-PlatformOptions.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41677) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkID=391837)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkID=391839)  \| [Más idiomas](https://www.microsoft.com/download/details.aspx?id=41677)|Para los responsables de la toma de decisiones empresariales y los arquitectos, en este póster se describen las opciones de plataforma para Lync 2013. Los clientes pueden elegir entre Lync Online con Microsoft 365, Lync híbrido, Lync Server local y Lync hospedado. En el póster de TI se detalla cada opción arquitectónica, incluidos los escenarios ideales para cada uno, los requisitos de licencia y las responsabilidades de profesionales de TI.|
   
<a name="Lync2013_Options"> </a>
## <a name="sharepoint-in-azure-solutions-posters"></a>Pósteres de soluciones de SharePoint en Azure

Los pósteres de TI de SharePoint en Azure muestran soluciones basadas en Azure que usan SharePoint Server 2013.
  
<a name="Azure_sharepoint2013"> </a>
### <a name="internet-sites-in-microsoft-azure-using-sharepoint-server-2013"></a>Sitios de Internet en Microsoft Azure mediante SharePoint Server 2013

|Elemento|Descripción|
|---|---|
|[![Imagen de los sitios de Internet en Azure con el póster de SharePoint Server 2013.](../media/MS-AZ-SPInternetSites.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41992) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392552)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392551)  \| [Más idiomas](https://www.microsoft.com/download/details.aspx?id=41992)|En este póster se describen las actividades de diseño clave y la arquitectura recomendada para sitios accesibles desde Internet en Azure.  <br/><br/> Para más información, consulte los siguientes artículos:  <br/><br/> - [Sitios de Internet en Azure mediante SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md) <br/> - [Arquitecturas de Azure para SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
<a name="DesignSampleInternetSites"> </a>
### <a name="internet-sites-in-azure-for-sharepoint-2013"></a>Sitios de Internet en Azure para SharePoint 2013

|Elemento|Descripción|
|---|---|
|[![Imagen de los sitios de Internet en Microsoft Azure para el póster de SharePoint Server 2013.](../media/MS-AZ-InternetSitesDesignSample.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41991) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392549)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392548)  \| [Más idiomas](https://www.microsoft.com/download/details.aspx?id=41991)|Use este ejemplo de diseño como punto de partida para su propia arquitectura de un sitio accesible desde Internet en Azure mediante SharePoint Server 2013. <br/><br/> Para más información, consulte los siguientes artículos:  <br/><br/> - [Sitios de Internet en Azure mediante SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md) <br/> - [Arquitecturas de Azure para SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
<a name="sharepoint_recovery_Azure"> </a>
### <a name="sharepoint-disaster-recovery-to-microsoft-azure"></a>Recuperación ante desastres de SharePoint en Microsoft Azure

|Elemento|Descripción|
|---|---|
|[![Imagen del póster del proceso de recuperación ante desastres de SharePoint en Azure.](../media/SP-DR-Azure.png)          ](https://www.microsoft.com/download/details.aspx?id=41993) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392555)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392554)  \| [Más idiomas](https://www.microsoft.com/download/details.aspx?id=41993)|En este póster de TI se muestran los principios de arquitectura de un entorno de recuperación ante desastres en Azure. <br/><br/> Para obtener más información, consulte los siguientes artículos:  <br/><br/> - [recuperación ante desastres de SharePoint Server 2013 en Azure](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md) <br/> - [Arquitecturas de Azure para SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
## <a name="see-also"></a>Vea también

- [Centro de soluciones y arquitectura de Microsoft 365](../solutions/index.yml)
  
- [Modelos de arquitectura de la nube de Microsoft](../solutions/cloud-architecture-models.md)
  
- [Microsoft 365 guías de laboratorio de pruebas](m365-enterprise-test-lab-guides.md)
  
- [Soluciones híbridas](hybrid-solutions.md)