---
title: opciones de migración de SharePoint 2007 que se deben tener en cuenta
ms.author: tracyp
author: MSFTTracyP
manager: scotv
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
ms.openlocfilehash: 044bfce8ea64233950fa291c72896f36531d206e
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65090759"
---
# <a name="sharepoint-2007-migration-options-to-consider"></a>opciones de migración de SharePoint 2007 que se deben tener en cuenta

*Este artículo se aplica tanto a Microsoft 365 Enterprise como a Office 365 Enterprise.*

Microsoft SharePoint 2007 y SharePoint Server 2007 han llegado al final del soporte técnico. ¡Es el momento de actualizar! En este artículo se proporciona información sobre las opciones de migración.
  
## <a name="common-upgrade-strategies-for-sharepoint"></a>Estrategias de actualización comunes para SharePoint

Hay varios métodos para actualizar un entorno de SharePoint Server. Si tiene una granja de Microsoft Office SharePoint Server 2007, estos son algunos ejemplos de los métodos de actualización:
  
- Base de datos adjunta
    
- Actualización en paralelo
    
- Actualización local
    
- Actualización híbrida (en contexto con bases de datos desasociadas o conexión de base de datos independiente)
    
- SharePoint híbridos (conectarse en línea a SharePoint locales)
    
- Movimiento manual de datos entre colecciones de sitios o bibliotecas
    
- Actualización del Asistente para FastTrack a Microsoft 365 ([SharePoint Asesor de implementación en línea](https://aka.ms/spoguidance))
    
- Api de migración a SharePoint Online (SPO) en Microsoft 365
    
¿Qué funciona mejor para ti?
  
Su conocimiento de lo que hace y se usa para su granja es una fuerza táctica a la hora de actualizar. La forma en que los usuarios usan SharePoint Farm le ayudará a elegir entre sus opciones.
  
> [!TIP]
> Microsoft Office SharePoint Server 2007 también tiene una actualización gradual que no se cubre aquí. Para ver una lista de artículos de actualización específicos del paso, consulte la hoja de ruta de [finalización del soporte técnico de SharePoint Server 2007](sharepoint-2007-end-of-support.md). 
  
No olvide comprobar el [ciclo de vida del producto](https://support.microsoft.com/lifecycle/search) y los requisitos del sistema para ver la versión de SharePoint a la que va a actualizar. Esto es así que tendrá en cuenta cuándo será necesaria la siguiente actualización (por ejemplo, si se detiene en un producto heredado como SharePoint Server 2010 para planear más actualizaciones, asegúrese de que conoce la fecha de finalización del soporte técnico) y para asegurarse de que tiene hardware compatible con el plan. 
  
Si tiene previsto realizar la transición de algunos o todos los sitios de SharePoint a Microsoft 365 en la nube, este es un momento para marcar un vínculo a las [descripciones del servicio Microsoft 365 y Office 365](/office365/servicedescriptions/office-365-service-descriptions-technet-library). Necesitará las descripciones de servicio para obtener información sobre las características de SharePoint Online y cómo pueden diferir de SharePoint Server local. Actualice las granjas de servidores funcionales Microsoft Office SharePoint Server 2007. Si la instalación tiene sitios que están rotos, corrija los sitios antes de la actualización.
  
## <a name="a-note-about-managing-risk"></a>Una nota sobre la administración del riesgo

Los métodos como "en paralelo" son importantes en el esquema de la lógica de actualización. Al actualizar en paralelo, se mantiene la granja de servidores de Microsoft Office SharePoint Server 2007, pero se crea una granja de servidores a partir de ella (SharePoint Server 2010) en hardware nuevo. Esto ayuda de tres maneras:
  
1. Tiene un lugar para realizar copias de seguridad de las bases de datos de Microsoft Office SharePoint Server 2007 para actualizarlas por separado, mediante la asociación de bases de datos.
    
2. Si descubre que solo hay algunas bibliotecas de documentos críticas y otra información en uso en la granja de servidores de Microsoft Office SharePoint Server 2007, puede elegir mover manualmente los datos de Microsoft Office SharePoint Server 2007 a SharePoint  Server 2010 o lleve solo sitios y webs específicos a la siguiente versión (lo que puede facilitar el trabajo).
    
3. Cuanto menos se haga en la granja de servidores de Microsoft Office SharePoint Server 2007, directamente, más seguros son los datos que contiene la granja de servidores al actualizar.
    
Métodos como In-Place actualización actuarán directamente en la granja de servidores de Microsoft Office SharePoint Server 2007, lo que le proporcionará menos opciones sencillas para abandonar una ruta de acceso y comenzar de nuevo con su entorno impecable. En la medida de lo posible, cree algunas medidas de seguridad (como tomar y probar copias de seguridad del entorno original). Por ejemplo, si la granja de servidores de Microsoft Office SharePoint Server 2007 es virtual y se duplica con fines de copia de seguridad y restauración, haga una copia de seguridad y restaure las bases de datos más actuales antes de la ventana de servicio para la actualización. Saber que tiene la opción de restaurar las copias de seguridad de la base de datos no solo le dará una conmutación por error, sino que le puede dar tranquilidad.
  
> [!TIP]
> Existen documentos de procedimientos recomendados para la actualización para [Microsoft Office SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc261992(v=office.12)), [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc261992(v=office.14)), [SharePoint Server 2013](/SharePoint/upgrade-and-update/best-practices-for-upgrading-from-sharepoint-2010-to-sharepoint-2013) y [SharePoint Server 2016](/SharePoint/upgrade-and-update/best-practices-for-upgrade). También puede buscar [asociados de Microsoft](https://partnercenter.microsoft.com/pcv/search) que tengan experiencia con actualizaciones o migraciones Microsoft 365. 
  
## <a name="make-your-plan"></a>Hacer el plan

Si necesita actualizar, necesita un plan y un tamaño no se ajusta a todos en estos casos. El plan puede ser tan sencillo como "Crear una suscripción Microsoft 365 con SharePoint Online, registrar un dominio y redirigir a las personas para guardar sus archivos allí". Y puede que no lo sea. Esa decisión es suya y depende de lo que usted y sus usuarios realmente necesitan.
  
> [!NOTE]
> Es arriesgado ejecutarse en software cuyo ciclo de vida ha finalizado. Los productos que no son compatibles ya no se aplican cuando se encuentran problemas. Esto también significa que si surgen nuevas amenazas de seguridad, no habrá revisiones ni correcciones de seguridad porque ya no se admiten los productos de fin de ciclo de vida. ¡Por favor, evite esa situación! 
  
### <a name="first-know-your-farm"></a>En primer lugar, conozca su granja.

Al actualizar, la toma de decisiones debe basarse en lo que hace la granja de servidores para su organización. ¿Qué necesidad satisface? ¿Cuál es su rol? Cada granja de servidores de la empresa puede tener un rol diferente. Algunas de las granjas de SharePoint pueden ser *críticas*, algunas pueden ser archivos de archivos, allí para mantener la seguridad. O bien, si la granja de servidores rellena muchos roles a la vez, es posible que tenga que saber qué hacen las colecciones de sitios, las webs o incluso las bibliotecas de documentos, las personalizaciones y lo importantes que son. Analizar los datos en este nivel puede parecer mucho trabajo, pero ahorra tiempo y esfuerzo para dominar el dominio antes de actualizarlo o migrarlo. Una vez que conozca todas las partes móviles y los bits más importantes, también sabrá lo que ha superado y puede dejar atrás. Ese conocimiento solo le beneficiará en el futuro. 
  
Por lo tanto, ¿qué dicen los usuarios es más importante sobre la granja de servidores de SharePoint Server?
  
- Características de SharePoint integradas
    
- El corpus de datos de gran tamaño (como un archivo de archivos)
    
- Disponibilidad
    
- Aplicaciones críticas, elementos web o documentos de la granja de servidores (granja de servidores crítica)
    
- Los estándares de cumplimiento se cumplieron
    
- Personalizaciones
    
Si ejecuta algo esencial para su empresa desde la granja de SharePoint, supongamos que actúa como un gran catálogo de datos críticos sobre los requisitos del servicio cliente, puede colocar una marca junto a "Aplicaciones críticas", pero también "Disponibilidad", es decir, que su negocio se vería afectado si no pudiera usar SharePoint durante un tiempo. Del mismo modo, puede comprobar "Personalizaciones" porque los servicios críticos que ofrece la granja se basan en código personalizado, definiciones de sitio o muchas personalizaciones que funcionan conjuntamente.
  
Si SharePoint satisfacer esas necesidades sin su participación fuera del uso de lo que está integrado en el software, y por lo general lo actualiza y lleva a cabo la administración y el mantenimiento normales, es posible que haya elegido "SharePoint integrados", esta también puede ser su razón para sentarse en una versión anterior de SharePoint. En otras palabras, ya hace lo que necesita y no ha necesitado actualizar hasta ahora, en Microsoft Office SharePoint Server 2007 fin de soporte técnico.
  
Al enumerar estas cosas con viñetas, se crean criterios para la actualización. En otras palabras, cualquier actualización tendría que cumplir con esta barra para que se tenga en cuenta. Esto le ofrece una manera de descartar métodos que no se ajusten actualmente a sus necesidades.
  
### <a name="a-simple-sample-plan"></a>Un plan de ejemplo simple

Es posible que sea necesario un consenso más amplio con el liderazgo y otros administradores sobre el camino que tomará la actualización de SharePoint. SharePoint Los administradores del servidor suelen cooperar con Microsoft SQL Server administradores, trabajar con equipos de redes y seguridad, etc. Si hay muchas partes interesadas, es posible que tenga que crear un acuerdo para el plan de actualización y migración o ajustarlo. Por ejemplo, si migra datos para que parte de su empresa use SharePoint Online en Microsoft 365, es probable que tenga que realizar pruebas o optimización del rendimiento dentro de la red. Los equipos afectados deben informarse con antelación.
  
En mi ejemplo simple, muestro una propuesta de administrador de SharePoint y, a continuación, enumere el plan que acordaron todas las partes interesadas. Para mayor claridad, documente sus acuerdos y decisiones.
  
El plan comienza después de un análisis en profundidad de una granja de servidores e intenta identificar el rol de la granja, los puntos de dolor y otra información importante que llevará a restringir algunas opciones de actualización. Después, SharePoint administrador realiza una propuesta de actualización y las partes interesadas acuerdan un plan de acción.
  
Mi lista de viñetas "más importante":
  
- Disponibilidad, características integradas en SharePoint y estándares de cumplimiento.
    
- La mayoría de los datos se encuentra en tres colecciones de sitios, con un área de trabajo de reunión utilizada por un equipo de desarrollo importante y en uso intensivo en varias zonas horarias de todo el mundo.
    
- Hay otros 17 sitios que se usan ampliamente.
    
- Dos bibliotecas de documentos (Área de trabajo de reuniones y Documentos en la colección de sitios raíz) son más grandes (más de 8000 documentos cada una). Tenemos un gran número de documentos archivados y una lista con datos adjuntos de hoja de cálculo.
    
- Hay 14 listas de bibliotecas que tienen datos confidenciales que deben permanecer en cumplimiento.
    
- Debemos tener la capacidad de hacer retenciones y e-discovery dondequiera que vayamos.
    
- Algunos de estos datos DEBEN permanecer en el entorno local, debido a las reglas de InfoSec.
    
 **Mis opciones de actualización y migración:**
  
| Sí | No |
|:-----|:-----|
|Actualización de bases de datos con conexión de base de datos  <br/> |Actualización local  <br/> |
|Actualización con granjas en paralelo  <br/> |Actualización híbrida  <br/> |
|Api de migración a SPO en Microsoft 365 (para datos de sitio personales)  <br/> |SharePoint híbrido (aún no es necesario)  <br/> |
|Algunas migraciones manuales de datos a SharePoint Online para datos críticos  <br/> |actualización del asistente de FastTrack a Microsoft 365  <br/> |
   
 **Mi plan propuesto:**
  
Actualice localmente, con versiones de SharePoint en paralelo, algunas virtualizadas, para que podamos actualizar primero las bases de datos. Vaya de SharePoint 2007 a SharePoint 2010. Los administradores y desarrolladores prueban la granja resultante. Los usuarios prueban la granja resultante. Corrija los problemas de detención de espectáculos durante este tiempo. Una vez más, en paralelo, actualice SharePoint bases de datos de 2010 a SharePoint 2013. Probar. Prueba o prueba piloto del usuario. Corrija los problemas de detención de espectáculos durante este tiempo.
  
- Considere si un híbrido federado de búsqueda con SPO satisface sus necesidades.
    
- Considere [FastTrack ayuda](https://fasttrack.microsoft.com) si desea actualizar a SharePoint Online desde aquí. 
    
- Determine si se puede descargar alguna colección de sitios en una suscripción de Microsoft 365. (Microsoft 365 cumple muchos [estándares de cumplimiento](/compliance/regulatory/offering-home). Microsoft 365 tiene [eDiscovery](https://support.office.com/article/edea80d6-20a7-40fb-b8c4-5e8c8395f6da) y puede realizar [retenciones](https://support.office.com/article/A18F8975-AA7F-43B4-A7D6-001D14744D8E) a través del Centro de cumplimiento). 
    
De lo contrario, continúe con una actualización en paralelo a SharePoint Server 2016.
  
> [!NOTE]
> Entre las recomendaciones realizadas por los administradores que planean la actualización y el proceso real se encuentran las conversaciones que se producen con otras partes interesadas en las que se basa la actualización. Por ejemplo, a veces la economía obliga a los administradores a cambiar sus planes. Sea cual sea la decisión final, debe documentar cuál es el plan acordado, en el futuro. Podría tener un aspecto similar al siguiente: 
  
 **Mi plan de acción:**
  
En el entorno local, usamos un entorno virtual para compilar SharePoint Server 2010 y 2013 predeterminados. SharePoint Server 2016 se basará en un nuevo hardware que cumpla los requisitos del sistema para 2016. Realizaremos la asociación de bases de datos para actualizar las bases de datos de SharePoint 2007 a todas las versiones entre ella y SharePoint Server 2016. Las personalizaciones principales se vuelven a crear y probar en el entorno de SharePoint Server 2016 en este momento, si las características nativas aún no satisfacen nuestras necesidades. Si se realiza correctamente, tendremos una granja local en un nuevo hardware con bases de datos actualizadas y menos personalizaciones. Adjuntaremos las bases de datos de contenido actualizadas a nuevas colecciones de sitios en SharePoint Server 2013, probaremos, probaremos o probaremos el usuario y, a continuación, realizaremos un corte de DNS al nuevo entorno de SharePoint Server 2016 para su uso activo.
  
- En este momento, no consideraremos la implementación híbrida federada entre SharePoint Server 2016 y SharePoint Online.
    
- Se estima que el 35 % de nuestros sitios se pueden convertir en nuevos sitios de SPO con dominios de vanidad o, en última instancia, convertirse en OneDrive para la Empresa almacenamiento. Busca otras oportunidades para convertir sitios o enrutar sitios nuevos a SPO.
    
- Parte de esta parte de la migración será manual, al arrastrar y colocar en OneDrive para la Empresa sitios personales y otros mediante la API de migración.
    
Los pasos más detallados o una serie de vínculos a instrucciones de actualización específicas deben seguir un plan. El equipo MOSS 2007 no debe retirarse y los entornos virtuales deben mantenerse en aras de la comparación; sin embargo, la actualización se completará cuando se redirija a los usuarios a SharePoint Server 2016.
  
A menudo, los factores principales a la hora de elegir un método son el costo total de la actualización y el costo en el tiempo (verá más información al respecto en el artículo SharePoint Migration Roadmap). Sin embargo, planear con antelación le beneficiará en gran medida en la definición de expectativas, la elección sabia y la definición de qué aspecto tendrá el éxito.
  
## <a name="related-links"></a>Vínculos relacionados

[Recursos que le ayudarán a actualizar desde Office servidores y clientes de 2007](upgrade-from-office-2007-servers-and-products.md)
  
[Búsqueda de ciclo de vida y directiva de ciclo de vida de Microsoft](https://support.microsoft.com/lifecycle)
  
[Busque asociados de Microsoft que puedan ayudar con la actualización o la migración.](https://partnercenter.microsoft.com/pcv/search)
