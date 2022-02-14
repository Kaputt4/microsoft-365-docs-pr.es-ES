---
title: SharePoint opciones de migración de 2007 a tener en cuenta
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
ms.localizationpriority: medium
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
ms.openlocfilehash: 9c1c4c90443b632b490ac7a510394f367f688fca
ms.sourcegitcommit: 355ab75eb7b604c6afbe9a5a1b97ef16a1dec4fc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2022
ms.locfileid: "62805825"
---
# <a name="sharepoint-2007-migration-options-to-consider"></a>SharePoint opciones de migración de 2007 a tener en cuenta

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Microsoft SharePoint 2007 y SharePoint Server 2007 han llegado al final de la compatibilidad. Es hora de actualizar. En este artículo se proporciona información sobre las opciones de migración.
  
## <a name="common-upgrade-strategies-for-sharepoint"></a>Estrategias de actualización comunes para SharePoint

Existen varios métodos para actualizar un SharePoint de servidor. Si tiene una granja Microsoft Office SharePoint Server 2007, estos son algunos ejemplos de los métodos de actualización:
  
- Base de datos adjunta
    
- Actualización en paralelo
    
- Actualización local
    
- Actualización híbrida (local con bases de datos separadas/ base de datos adjunta independiente)
    
- SharePoint híbridos (conectarse en línea a servidores locales SharePoint)
    
- Mover manualmente datos entre colecciones de sitios o bibliotecas
    
- FastTrack actualización del Asistente para Microsoft 365 ([SharePoint de implementación en línea](https://aka.ms/spoguidance))
    
- API de migración a SharePoint Online (SPO) en Microsoft 365
    
¿Qué funciona mejor para usted?
  
El conocimiento de lo que hace y se usa en la granja de servidores es una fuerza táctica a la hora de actualizar. La forma en que las personas usan SharePoint granja de servidores le ayudará a elegir entre sus opciones.
  
> [!TIP]
> Microsoft Office SharePoint Server 2007 también tiene una actualización gradual no cubierta aquí. Para ver una lista de artículos de actualización específicos de pasos, vea [SharePoint Server 2007 end of support Roadmap](sharepoint-2007-end-of-support.md). 
  
Recuerda comprobar el ciclo de [vida del](https://support.microsoft.com/lifecycle/search) producto y los requisitos del sistema para cualquier versión SharePoint a la que estés actualizando. Esto es para que tenga en cuenta cuándo será necesaria la siguiente actualización (por ejemplo, si hace una pausa en un producto heredado como SharePoint Server 2010 para planear más actualizaciones, asegúrese de conocer su fecha de finalización de soporte técnico) y de estar seguro de que tiene hardware compatible con el plan. 
  
Si está planeando realizar la transición de algunos sitios de SharePoint a Microsoft 365 en la nube, este es un momento para marcar un vínculo a las descripciones del servicio Microsoft 365 y [Office 365](/office365/servicedescriptions/office-365-service-descriptions-technet-library). Necesitará las descripciones de servicio para obtener información sobre las características de SharePoint Online y cómo pueden diferir de las características locales SharePoint Server. Actualizar granjas Microsoft Office SharePoint server 2007 funcionales. Si la instalación tiene sitios rotos, arréstelos antes de la actualización.
  
## <a name="a-note-about-managing-risk"></a>Una nota sobre la administración de riesgos

Los métodos como "en paralelo" son importantes en el esquema de lógica de actualización. Al actualizar en paralelo, se mantiene la granja de servidores de Microsoft Office SharePoint Server 2007, pero se compila una granja de servidores a partir de la siguiente versión (SharePoint Server 2010) en el nuevo hardware. Esto ayuda de tres maneras:
  
1. Tiene un lugar para realizar copias de seguridad de las bases de datos de Microsoft Office SharePoint Server 2007 para actualizarlas por separado, mediante la base de datos adjunta.
    
2. Si se sabe que solo se usan algunas bibliotecas de documentos críticas y otra información en la granja de servidores de Microsoft Office SharePoint Server 2007, puede elegir mover manualmente datos de Microsoft Office SharePoint Server 2007 a SharePoint  Server 2010 o llevar solo sitios y webs específicos a la siguiente versión (lo que puede facilitar el trabajo).
    
3. Cuanto menos haga en la granja de servidores de Microsoft Office SharePoint Server 2007, más seguros son los datos que contiene la granja de servidores al actualizar.
    
Métodos como In-Place actualización actuarán directamente en la granja de servidores de Microsoft Office SharePoint Server 2007, lo que le dará menos opciones fáciles para abandonar una ruta de acceso y empezar de nuevo con su entorno prístina. En la medida de lo posible, cree algunas medidas de seguridad (como realizar y probar copias de seguridad del entorno original). Por ejemplo, si la granja de servidores de Microsoft Office SharePoint Server 2007 es virtual y se duplica con fines de copia de seguridad y restauración, haga una copia de seguridad y restaure las bases de datos más actuales antes de la ventana de servicio para la actualización. Saber que tiene la opción de restaurar copias de seguridad de bases de datos no solo le dará un error seguro, sino que puede darle tranquilidad.
  
> [!TIP]
> Existen documentos de procedimientos recomendados para la actualización de [Microsoft Office SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc261992(v=office.12)), [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc261992(v=office.14)), [SharePoint Server 2013](/SharePoint/upgrade-and-update/best-practices-for-upgrading-from-sharepoint-2010-to-sharepoint-2013) y [SharePoint Server 2016](/SharePoint/upgrade-and-update/best-practices-for-upgrade). También puede buscar socios de [Microsoft](https://partnercenter.microsoft.com/pcv/search) que tengan experiencia con actualizaciones o Microsoft 365 migración. 
  
## <a name="make-your-plan"></a>Hacer su plan

Si necesita actualizar, necesita un plan y un tamaño no se ajusta a todos en estos casos. El plan puede ser tan sencillo como "Crear una suscripción Microsoft 365 con SharePoint Online, registrar un dominio y redirigir a las personas para guardar sus archivos allí". Y puede que no lo sea. Esa decisión es tuyo y se debe a lo que tú y tus usuarios realmente necesitan.
  
> [!NOTE]
> Es arriesgado ejecutarse en software cuyo ciclo de vida ha finalizado. Los productos que no son compatibles ya no se parchea cuando se encuentran problemas. Esto también significa que si surgen nuevas amenazas de seguridad, no habrá revisiones de seguridad ni correcciones porque los productos de fin de ciclo de vida ya no son compatibles. Por favor, evite esa situación. 
  
### <a name="first-know-your-farm"></a>En primer lugar, conozca la granja de servidores

Al actualizar, la toma de decisiones debe basarse en lo que la granja de servidores hace para su organización. ¿Qué necesidad satisface? ¿Cuál es su función? Cada granja de servidores de la empresa puede tener un rol diferente. Algunas de las SharePoint granjas de servidores pueden ser *críticas*, otras pueden ser archivos de archivos, ya que existen para el mantenimiento seguro. O bien, si la granja de servidores rellena muchos roles a la vez, es posible que necesite saber qué hacen las colecciones de sitios, webs o incluso bibliotecas de documentos, las personalizaciones y lo importantes que son. Analizar los datos en este nivel puede parecer mucho trabajo, pero ahorra tiempo y esfuerzo para dominar el dominio antes de actualizarlo o migrarlo. Una vez que conozca todas las partes en movimiento y los bits más importantes, también sabrá lo que ha superado y puede dejar atrás. Ese conocimiento solo le beneficiará en el futuro. 
  
Por lo tanto, ¿qué dicen los usuarios que es lo más importante SharePoint granja de servidores?
  
- Características de SharePoint integradas
    
- El corpus de datos grande (como un archivo de archivos)
    
- Disponibilidad
    
- Aplicaciones críticas, elementos web o documentos de la granja de servidores (granja de servidores de misión crítica)
    
- Se cumplen los estándares de cumplimiento
    
- Personalizaciones
    
Si ejecuta algo esencial para su empresa desde la granja de servidores de SharePoint, diga que actúa como un gran catálogo de datos críticos sobre los requisitos de servicio de cliente, puede poner una marca de graduación junto a "Aplicaciones críticas", pero también "Disponibilidad", es decir, su empresa se vería afectada si no pudiera usar SharePoint durante un tiempo. Del mismo modo, puede comprobar "Personalizaciones" porque los servicios críticos que ofrece la granja de servidores se basan en código personalizado, definiciones de sitio o muchas personalizaciones que funcionan juntas.
  
Si SharePoint satisfacer esas necesidades sin su implicación fuera del uso de lo que está integrado en el software y, por lo general, lo actualiza y lleva a cabo una administración y mantenimiento normales, puede que haya elegido "SharePoint integrado", esto también puede ser su motivo para sentarse en una versión anterior de SharePoint. En otras palabras, ya hace lo que necesita y no ha necesitado actualizar hasta ahora, en Microsoft Office SharePoint Server 2007 final de soporte técnico.
  
Al enumerar estas cosas con viñetas, se crean criterios para la actualización. En otras palabras, cualquier actualización tendría que cumplir esta barra para ser considerada. Esto le ofrece una forma de descartar métodos que actualmente no se ajustan a sus necesidades.
  
### <a name="a-simple-sample-plan"></a>Un plan de ejemplo simple

Es posible que deba haber un mayor consenso con el liderazgo y otros administradores en la ruta que tomará SharePoint actualización. SharePoint administradores de servidor a menudo colaboran con Microsoft SQL Server administradores, trabajan con equipos de redes y seguridad, etc. Cuando hay muchas partes interesadas, es posible que deba crear un acuerdo para el plan de actualización y migración o ajustarlo. Por ejemplo, si migra datos para que parte de su empresa use SharePoint Online en Microsoft 365, es probable que deba realizarse una optimización del rendimiento o pruebas dentro de la red. Los equipos afectados deben estar informados con antelación.
  
En mi ejemplo simple, mostro una SharePoint de administrador y, a continuación, enumero el plan que todas las partes interesadas acordaron. Para mayor claridad, documente sus acuerdos y decisiones.
  
El plan comienza después de un análisis en profundidad de una granja de servidores e intenta identificar el rol de la granja de servidores, los puntos de dolor y otra información importante que llevará a restringir algunas opciones de actualización. Después, el administrador SharePoint una propuesta de actualización y las partes interesadas acuerdan un plan de acción.
  
Mi lista de viñetas "más importante":
  
- Disponibilidad, características integradas para SharePoint y estándares de cumplimiento.
    
- La mayoría de los datos se encuentra en tres colecciones de sitios, con un área de reuniones usada por un equipo de desarrollo importante y en uso intenso en varias zonas horarias de todo el mundo.
    
- Hay otros 17 sitios que se usan ampliamente.
    
- Dos bibliotecas de documentos (Área de reuniones y Documentos en la colección de sitios raíz) son más grandes (más de 8000 documentos cada una). Tenemos un gran número de documentos archivados y una lista con datos adjuntos de hoja de cálculo.
    
- Hay 14 listas de bibliotecas que tienen datos confidenciales que DEBEN permanecer en cumplimiento.
    
- Debemos tener la capacidad de realizar retenciones y e-discovery allá donde vayamos.
    
- Algunos de estos datos DEBEN permanecer locales, debido a las reglas de InfoSec.
    
 **Mis opciones de actualización y migración:**
  
| Sí | No |
|:-----|:-----|
|Actualizar bases de datos con base de datos adjunta  <br/> |Actualización local  <br/> |
|Actualizar con granjas de servidores en paralelo  <br/> |Actualización híbrida  <br/> |
|API de migración a SPO en Microsoft 365 (para datos de sitio personales)  <br/> |SharePoint híbrido (aún no es necesario)  <br/> |
|Algunas migraciones de datos manuales a SharePoint Online para datos críticos  <br/> |FastTrack actualización del asistente a Microsoft 365  <br/> |
   
 **Mi plan propuesto:**
  
Actualice localmente, con versiones de SharePoint en paralelo, algunas virtualizadas, para que podamos actualizar primero las bases de datos. Vaya de SharePoint 2007 a SharePoint 2010. Los administradores y desarrolladores prueban la granja de servidores resultante. Los usuarios prueban la granja de servidores resultante. Se solucionan los problemas de detención de la presentación durante este tiempo. De nuevo, en paralelo, actualice SharePoint bases de datos de 2010 a SharePoint 2013. Probar. Prueba/piloto del usuario. Se solucionan los problemas de detención de la presentación durante este tiempo.
  
- Considere si un híbrido federado de búsqueda con SPO satisface sus necesidades.
    
- Considere [FastTrack ayuda](https://fasttrack.microsoft.com) si desea actualizar a SharePoint Online desde aquí. 
    
- Determine si las colecciones de sitios se pueden descargar en una Microsoft 365 suscripción. (Microsoft 365 cumple muchos [estándares de cumplimiento](/compliance/regulatory/offering-home). Microsoft 365 [exhibición de documentos electrónicos](https://support.office.com/article/edea80d6-20a7-40fb-b8c4-5e8c8395f6da) y puede realizar [retenciones](https://support.office.com/article/A18F8975-AA7F-43B4-A7D6-001D14744D8E) a través del Centro de cumplimiento). 
    
De lo contrario, continúe con una actualización en paralelo a SharePoint Server 2016.
  
> [!NOTE]
> Entre las recomendaciones realizadas por los administradores que planean la actualización y el proceso real se encuentran las conversaciones que se realizan con otras partes interesadas en las que se basa la actualización. Por ejemplo, a veces la economía obliga a los administradores a cambiar sus planes. Cualquiera que sea la decisión final, debe documentar cuál es el plan de acuerdo, en adelante. Podría tener un aspecto parecido a este: 
  
 **Mi plan de acción:**
  
Localmente, usamos un entorno virtual para crear un servidor SharePoint Server 2010 y 2013. SharePoint Server 2016 se basará en un nuevo hardware que cumpla los requisitos del sistema para 2016. Realizaremos las bases de datos adjuntas para actualizar bases de datos desde SharePoint 2007 a través de todas las versiones entre ella y SharePoint Server 2016. Las personalizaciones principales se vuelven a crear y probar en el entorno de SharePoint Server 2016 en este momento, si las características nativas aún no satisfacen nuestras necesidades. Si se ejecuta correctamente, tendremos una granja de servidores local en un nuevo hardware con bases de datos actualizadas y menos personalizaciones. Adjuntaremos las bases de datos de contenido actualizadas a nuevas colecciones de sitios en SharePoint Server 2013, probaremos, probaremos y probaremos el usuario y, a continuación, realizaremos un recorte de DNS en el nuevo entorno de SharePoint Server 2016 para su uso en directo.
  
- No consideraremos Federated Hybrid entre SharePoint Server 2016 y SharePoint Online en este momento.
    
- Se calcula que un 35 % de nuestros sitios se pueden convertir en nuevos sitios de SPO con dominios de vanidad o, en última instancia, convertirse en OneDrive para la Empresa almacenamiento. Buscar otras oportunidades para convertir sitios o enrutar nuevos sitios a SPO.
    
- Parte de esta parte de la migración será manual, arrastrando y colocando a OneDrive para la Empresa sitios personales, y otras por la API de migración.
    
Los pasos más detallados o una serie de vínculos a instrucciones de actualización específicas deben seguir un plan. El equipo de MOSS 2007 no debe retirarse y los entornos virtuales deben mantenerse en aras de la comparación; sin embargo, la actualización se completará cuando los usuarios sean redirigidos a SharePoint Server 2016.
  
A menudo, los factores principales a la hora de elegir un método son el costo total de la actualización y el costo en el tiempo (verá más información sobre esto en el artículo SharePoint Plan de migración). Sin embargo, planear con antelación le beneficiará en gran parte al establecer expectativas, elegir con prudencia y enmarcar cómo será el éxito.
  
## <a name="related-links"></a>Vínculos relacionados

[Recursos para ayudarle a actualizar desde Office servidores y clientes de 2007](upgrade-from-office-2007-servers-and-products.md)
  
[Búsqueda de ciclo de vida y directiva de ciclo de vida de Microsoft](https://support.microsoft.com/lifecycle)
  
[Buscar socios de Microsoft que puedan ayudar con la actualización o migración](https://partnercenter.microsoft.com/pcv/search)
