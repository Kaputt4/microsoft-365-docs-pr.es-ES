---
title: Opciones de migración de SharePoint 2007 que se deben tener en cuenta
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
search.appverid:
- MET150
- SPS150
- OSU140
- SPO160
- SPB160
- OSI150
- OSI160
- BSA160
- OSU160
ms.assetid: 66325a43-5816-4f8e-81ba-c11b71345b7c
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
description: Este artículo contiene información para los usuarios que usan SharePoint Server 2007 para ayudarles a planear su actualización.
ms.openlocfilehash: 3e37a01f1a2d387cda6723a8df1f73734fa3ba9d
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694959"
---
# <a name="sharepoint-2007-migration-options-to-consider"></a>Opciones de migración de SharePoint 2007 que se deben tener en cuenta

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Microsoft SharePoint 2007 y SharePoint Server 2007 han alcanzado el final del soporte técnico. Es el momento de actualizar. En este artículo se proporciona información sobre las opciones de migración.
  
## <a name="common-upgrade-strategies-for-sharepoint"></a>Estrategias de actualización comunes para SharePoint

Hay varios métodos para actualizar un entorno de SharePoint Server. Si tiene una granja Microsoft Office SharePoint Server 2007, estos son algunos ejemplos de los métodos de actualización:
  
- Base de datos adjunta
    
- Actualización en paralelo
    
- Actualización local
    
- Actualización híbrida (local con bases de datos desasociadas/base de datos adjunta independiente)
    
- Entornos híbridos de SharePoint (conectarse en línea a SharePoint local)
    
- Mover manualmente datos entre colecciones de sitios o bibliotecas
    
- Actualización del Asistente de FastTrack a Microsoft 365 ([Asesor de implementación de SharePoint Online)](https://aka.ms/spoguidance)
    
- API de migración a SharePoint Online (SPO) en Microsoft 365
    
¿Qué funciona mejor para usted?
  
Su conocimiento de lo que hace y para lo que se usa la granja de servidores es una fuerza táctica en lo que respecta a la actualización. La forma en que los usuarios usan la granja de servidores de SharePoint le ayudará a elegir entre sus opciones.
  
> [!TIP]
> Microsoft Office SharePoint Server 2007 también tiene una actualización gradual no cubierta aquí. Para ver una lista de artículos de actualización específicos de pasos, vea el plan de fin de soporte técnico de [SharePoint Server 2007.](sharepoint-2007-end-of-support.md) 
  
Recuerde comprobar el ciclo [de vida del producto](https://support.microsoft.com/lifecycle/search) y los requisitos del sistema para cualquier versión de SharePoint a la que actualice. Esto es así para que tenga en cuenta cuándo será necesaria la siguiente actualización (por ejemplo, si hace una pausa en un producto heredado como SharePoint Server 2010 para planear más actualizaciones, asegúrese de que conoce la fecha de finalización del soporte técnico) y de estar seguro de que tiene hardware compatible con el plan. 
  
Si tiene previsto realizar la transición de algunos o todos los sitios de SharePoint a Microsoft 365 en la nube, este es el momento de marcar un vínculo a las descripciones del servicio de [Microsoft 365 y Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library) Necesitará las descripciones de servicio para obtener información sobre las características de SharePoint Online y cómo pueden diferir de SharePoint Server local. Actualización funcional Microsoft Office granjas de servidores de SharePoint Server 2007. Si la instalación tiene sitios rotos, corrijalos antes de la actualización.
  
## <a name="a-note-about-managing-risk"></a>Una nota sobre la administración de riesgos

Los métodos como "en paralelo" son importantes en el esquema de lógica de actualización. Cuando se actualiza en paralelo, se mantiene la granja de servidores de Microsoft Office SharePoint Server 2007, pero se crea una granja de servidores a partir de ella (SharePoint Server 2010) en nuevo hardware. Esto ayuda de tres maneras:
  
1. Puede realizar copias de seguridad de las bases de datos Microsoft Office SharePoint Server 2007 para actualizarlas por separado, mediante la base de datos adjunta.
    
2. Si ve que solo se usan un pequeño número de bibliotecas de documentos críticas y otra información en la granja de servidores de Microsoft Office SharePoint Server 2007, puede elegir mover manualmente datos de Microsoft Office SharePoint Server 2007 a SharePoint Server 2010, o llevar solo sitios y webs específicos a la siguiente versión (lo que puede facilitar el trabajo).
    
3. Cuanto menos haga en la granja Microsoft Office de servidores de SharePoint Server 2007, más seguros son los datos que contiene la granja de servidores al actualizar.
    
Los métodos como la actualización In-Place actuarán directamente en la granja de servidores de Microsoft Office SharePoint Server 2007, lo que le dará menos opciones fáciles para abandonar una ruta de acceso y empezar de nuevo con su entorno familiar. En la medida de lo posible, cree algunas medidas de seguridad (como realizar y probar copias de seguridad del entorno original). Por ejemplo, si la granja de servidores de Microsoft Office SharePoint Server 2007 es virtual y está duplicada para fines de copia de seguridad y restauración, haga una copia de seguridad y restaure las bases de datos más actuales antes de la ventana de servicio para la actualización. Saber que tiene la opción de restaurar copias de seguridad de bases de datos no solo le dará un error seguro, sino que puede darle tranquilidad.
  
> [!TIP]
> Existen documentos de procedimientos recomendados para la actualización [Microsoft Office SharePoint Server 2007,](https://technet.microsoft.com/library/cc261992%28v=office.12%29.aspx) [SharePoint Server 2010,](https://technet.microsoft.com/library/cc261992%28v=office.14%29.aspx) [SharePoint Server 2013](https://technet.microsoft.com/library/cc261992%28v=office.15%29.aspx)y [SharePoint Server 2016](https://technet.microsoft.com/library/cc261992%28v=office.16%29.aspx). También puede buscar partners [de Microsoft que](https://partnercenter.microsoft.com/pcv/search) tengan experiencia con actualizaciones o migraciones de Microsoft 365. 
  
## <a name="make-your-plan"></a>Realizar el plan

Si necesita actualizar, necesita un plan y el tamaño único no se ajusta a todos en estos casos. El plan puede ser tan sencillo como "Crear una suscripción de Microsoft 365 con SharePoint Online, registrar un dominio y redirigir a los usuarios para que guarden sus archivos allí". Y puede que no lo sea. Esa decisión es la que usted toma y se debe a lo que usted y sus usuarios necesitan realmente.
  
> [!NOTE]
> Es arriesgado ejecutarse en software cuyo ciclo de vida ha finalizado. Los productos que no son compatibles ya no se revisión cuando se encuentran problemas. Esto también significa que si surgen nuevas amenazas de seguridad, no habrá revisiones de seguridad ni correcciones porque ya no se admiten los productos de fin de ciclo de vida. Evite esta situación. 
  
### <a name="first-know-your-farm"></a>En primer lugar, conozca la granja de servidores

Al actualizar, la toma de decisiones debe basarse en lo que hace la granja de servidores para su organización. ¿Qué necesidad satisface? ¿Cuál es su rol? Cada granja de servidores de la empresa puede tener un rol diferente. Algunas de las granjas de servidores de SharePoint pueden ser  *críticas,*  otras pueden ser archivos de archivos, y otras pueden ser de mantenimiento seguro. O bien, si la granja de servidores rellena muchos roles a la vez, es posible que deba saber qué hacen las colecciones de sitios, webs o incluso bibliotecas de documentos, las personalizaciones y su importancia. Analizar los datos en este nivel puede parecer mucho trabajo, pero ahorra tiempo y esfuerzo para dominar el dominio antes de actualizarlo o migrarlo. Una vez que conozca todas las partes móviles y los bits más importantes, también sabrá lo que ha superado y puede dejar atrás. Ese conocimiento solo le beneficiará en el futuro. 
  
Por lo tanto, ¿qué dicen los usuarios que es lo más importante sobre la granja de servidores de SharePoint Server?
  
- Características integradas de SharePoint
    
- El corpus de datos de gran tamaño (como un archivo de archivos)
    
- Disponibilidad
    
- Aplicaciones críticas, elementos web o documentos de la granja de servidores (granja crítica)
    
- Se cumplen los estándares de cumplimiento
    
- Personalizaciones
    
Si ejecuta algo esencial para su empresa desde la granja de servidores de SharePoint, diga que actúa como un gran catálogo de datos críticos sobre los requisitos de servicio de cliente, puede poner una marca de graduación junto a "Aplicaciones críticas", pero también "Disponibilidad", es decir, su negocio se vería afectado si no pudiera usar SharePoint durante un tiempo. Del mismo modo, puede comprobar "Personalizaciones" porque los servicios críticos que ofrece la granja de servidores se basan en código personalizado, definiciones de sitio o una serie de personalizaciones que funcionan conjuntamente.
  
Si SharePoint ha cumplido esas necesidades sin tener que hacer nada más allá de usar lo que está integrado en el software y, por lo general, lo actualiza y realiza una administración y mantenimiento normales, es posible que haya elegido "SharePoint integrado". Este también puede ser su motivo para estar sentado en una versión anterior de SharePoint. En otras palabras, ya hace lo que necesita y no ha necesitado actualizar hasta ahora, en Microsoft Office final de soporte técnico de SharePoint Server 2007.
  
Al enumerar con viñetas estas cosas, se crean criterios para la actualización. En otras palabras, cualquier actualización tendría que cumplir esta barra para ser considerada. Esto le ofrece una forma de descartar los métodos que actualmente no se ajustan a sus necesidades.
  
### <a name="a-simple-sample-plan"></a>Un plan de ejemplo simple

Es posible que deba haber un mayor consenso con el liderazgo y otros administradores en la ruta que llevará la actualización de SharePoint. Los administradores de SharePoint Server suelen colaborar con Microsoft SQL Server administradores, trabajar con equipos de redes y seguridad, etc. Si hay muchas partes interesadas, es posible que deba crear un acuerdo para el plan de actualización y migración o ajustarlo. Por ejemplo, si migra datos para que parte de su empresa use SharePoint Online en Microsoft 365, es probable que deba realizar pruebas o ajustes de rendimiento dentro de la red. Los equipos afectados deben estar informados con antelación.
  
En mi ejemplo simple, se muestra la propuesta de un administrador de SharePoint y, a continuación, se muestra el plan en el que coincidieron todas las partes interesadas. Para mayor claridad, documente sus acuerdos y decisiones.
  
El plan se inicia después de un análisis detallado de una granja de servidores e intenta identificar el rol de la granja de servidores, los puntos de problemas y otra información importante que llevará a restringir algunas opciones de actualización. Después, el administrador de SharePoint realiza una propuesta de actualización y las partes interesadas aceptan un plan de acción.
  
Mi lista de viñetas "más importante":
  
- Disponibilidad, características integradas en SharePoint y estándares de cumplimiento.
    
- La mayoría de los datos se encuentra en tres colecciones de sitios, con un área de reuniones usada por un equipo de desarrollo especialmente importante y en uso intenso en varias zonas horarias de todo el mundo.
    
- Hay muchos otros sitios que se usan ampliamente.
    
- Dos bibliotecas de documentos (Área de reuniones y Documentos en la colección de sitios raíz) son más grandes (más de 8000 documentos cada una). Tenemos un gran número de documentos archivados y una lista con datos adjuntos de hojas de cálculo.
    
- Hay 14 listas de bibliotecas que tienen datos confidenciales que DEBEN permanecer en cumplimiento.
    
- Debemos tener la capacidad de realizar retenciones y e-discovery dondequiera que vaya.
    
- Algunos de estos datos DEBEN permanecer locales, debido a las reglas de InfoSec.
    
 **Mis opciones de actualización y migración:**
  
| Sí | No |
|:-----|:-----|
|Actualización de bases de datos con base de datos adjunta  <br/> |Actualización local  <br/> |
|Actualización con granjas de servidores en paralelo  <br/> |Actualización híbrida  <br/> |
|API de migración a SPO en Microsoft 365 (para datos de sitios personales)  <br/> |Entorno híbrido de SharePoint (aún no es necesario)  <br/> |
|Algunas migraciones de datos manuales a SharePoint Online para datos críticos  <br/> |Actualización del asistente de FastTrack a Microsoft 365  <br/> |
   
 **Mi plan propuesto:**
  
Actualice localmente, con versiones de SharePoint en paralelo, algunas virtualizadas, para que podamos actualizar primero las bases de datos. Vaya de SharePoint 2007 a SharePoint 2010. Los administradores y los desarrolladores prueban la granja de servidores resultante. Los usuarios prueban la granja de servidores resultante. Se solucionan los problemas de detención de la presentación durante este tiempo. Una vez más, en paralelo, actualice las bases de datos de SharePoint 2010 a SharePoint 2013. Prueba. Prueba de usuario/piloto. Se solucionan los problemas de detención de la presentación durante este tiempo.
  
- Tenga en cuenta si una búsqueda híbrida federada con SPO satisface sus necesidades.
    
- Considere [la asistencia de FastTrack](https://fasttrack.microsoft.com) si desea actualizar a SharePoint Online desde aquí. 
    
- Determinar si se pueden descargar colecciones de sitios a una suscripción de Microsoft 365. (Microsoft 365 cumple muchos [estándares de cumplimiento.](https://technet.microsoft.com/library/office-365-compliance.aspx) Microsoft 365 tiene [eDiscovery](https://support.office.com/article/edea80d6-20a7-40fb-b8c4-5e8c8395f6da) y puede realizar [retenciones a](https://support.office.com/article/A18F8975-AA7F-43B4-A7D6-001D14744D8E) través del Centro de cumplimiento. 
    
De lo contrario, continúe con una actualización en paralelo a SharePoint Server 2016.
  
> [!NOTE]
> Entre las recomendaciones realizadas por los administradores que planean la actualización y el proceso real se encuentran las conversaciones que se realizan con otras partes interesadas en las que depende la actualización. Por ejemplo, a veces la económica obliga a los administradores a cambiar sus planes. Independientemente de cuál sea la decisión final, debe documentar cuál es el plan aceptado en el futuro. Podría tener un aspecto parecido al siguiente: 
  
 **Mi plan de acción:**
  
Localmente, usamos un entorno virtual para crear SharePoint Server 2010 y 2013 predeterminados. SharePoint Server 2016 se basará en un nuevo hardware que cumpla los requisitos del sistema para 2016. Se adjuntarán bases de datos a las bases de datos de actualización de SharePoint 2007 a través de todas las versiones entre ella y SharePoint Server 2016. Las personalizaciones principales se vuelven a crear y probar en el entorno de SharePoint Server 2016 en este momento, si las características nativas aún no satisfacen nuestras necesidades. Si se realiza correctamente, tendremos una granja de servidores local en nuevo hardware con bases de datos actualizadas y menos personalizaciones. Adjuntaremos las bases de datos de contenido actualizadas a nuevas colecciones de sitios en SharePoint Server 2013, realizaremos pruebas, pruebas de usuario y pruebas piloto y, a continuación, realizaremos un recorte de DNS al nuevo entorno de SharePoint Server 2016 para su uso en directo.
  
- No consideraremos la implementación híbrida federada entre SharePoint Server 2016 y SharePoint Online en este momento.
    
- Se calcula que el 35 % de nuestros sitios se puede convertir en nuevos sitios de SPO con dominios vangos o, en última instancia, convertirse en almacenamiento de OneDrive para la Empresa. Busca otras oportunidades para convertir sitios o enrutar sitios nuevos a SPO.
    
- Parte de esta parte de la migración será manual, mediante arrastrar y colocar a sitios personales de OneDrive para la Empresa y otras mediante la API de migración.
    
Los pasos más detallados o varios vínculos a instrucciones de actualización específicas deben seguir un plan. El equipo MOSS 2007 no debe retirarse y los entornos virtuales deben mantenerse para poder compararse; sin embargo, la actualización se completará cuando se redirija a los usuarios a SharePoint Server 2016.
  
A menudo, los factores principales a la hora de elegir un método son el costo total de la actualización y el costo en el tiempo (verá más información en el artículo mapa de ruta de migración de SharePoint). Sin embargo, la planeación con antelación le beneficiará en gran parte al establecer las expectativas, elegir de forma inteligente y definir el aspecto que tendrá el éxito.
  
## <a name="related-links"></a>Vínculos relacionados

[Recursos para ayudarle a actualizar desde clientes y servidores de Office 2007](upgrade-from-office-2007-servers-and-products.md)
  
[Búsqueda de ciclo de vida y directiva de ciclo de vida de Microsoft](https://support.microsoft.com/lifecycle)
  
[Buscar partners de Microsoft que puedan ayudarle con la actualización o migración](https://partnercenter.microsoft.com/pcv/search)
  

