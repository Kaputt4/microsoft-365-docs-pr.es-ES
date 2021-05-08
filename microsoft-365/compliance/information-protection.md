---
title: Microsoft Information Protection en Microsoft 365.
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.collection:
- m365solution-mip
- m365initiative-compliance
recommendations: false
description: Implemente Microsoft Information Protection (MIP) para proteger la información confidencial donde esta resida o hacia donde se transfiera.
ms.openlocfilehash: 5b9484826f0d3a297dae47c7d140d93297473023
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259303"
---
# <a name="microsoft-information-protection-in-microsoft-365"></a>Microsoft Information Protection en Microsoft 365.

>*[Licencias para el Centro de seguridad y cumplimiento de Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

Implemente Microsoft Information Protection (MIP) para descubrir, clasificar y proteger la información confidencial donde esta resida o hacia donde se transfiera.

Las características de MIP se incluyen con el Centro de cumplimiento de Microsoft 365 y proporcionan las herramientas necesarias para [conocer](#know-your-data), [proteger](#protect-your-data) y [evitar la pérdida](#prevent-data-loss) de sus datos.

![Imagen de cómo MIP le ayuda a descubrir, clasificar y proteger los datos confidenciales](../media/powered-by-intelligent-platform.png)

:::image type="content" source="../media/data-table1-4638524-new.png" alt-text="Conocer los datos":::

Para obtener información sobre la gobernanza de los datos, consulte [Gobernanza de información de Microsoft en Microsoft 365](manage-Information-governance.md).

## <a name="know-your-data"></a>Conocer los datos

> [!NOTE]
> Para información sobre cómo clasificar y etiquetar datos en Azure Purview, actualmente en versión preliminar, consulte [Etiquetar automáticamente su contenido en Azure Purview](/azure/purview/create-sensitivity-label)
> 
> Para ver los anuncios de publicación de versiones de Azure Purview, consulte las siguientes entradas de blog: [Microsoft Information Protection y Microsoft Azure Purview: mejor juntos](https://techcommunity.microsoft.com/t5/microsoft-security-and/microsoft-information-protection-and-microsoft-azure-purview/ba-p/1957481) y [Azure Purview en Spring Ignite 2021](https://techcommunity.microsoft.com/t5/azure-purview/azure-purview-at-spring-ignite-2021/ba-p/2175919).

Para tener una visión general de sus datos e identificar aquellos más importantes en todo su entorno híbrido, utilice las funciones siguientes:

:::image type="content" source="../media/knowyourdata-new.png" alt-text="Conocer los datos"::: 


|**Función**|**¿Qué problemas soluciona?**|**Introducción**|**Licencias**|
|--|--|--|--|
|[Tipos de información confidencial](sensitive-information-type-entity-definitions.md)| Identifica datos confidenciales mediante expresiones regulares integradas o personalizadas, o con una función, junto con pruebas confirmatorias que incluyen palabras clave, niveles de confianza y proximidad. Use tipos de información confidencial para identificar tipos de datos específicos de su organización. Use los tipos de información confidencial predefinidos para buscar tipos de datos estándar, como números de pasaporte. Cree un tipo de información personalizado para identificar información exclusiva de su entorno, como números de pieza. | [Personalizar un tipo de información confidencial integrado](customize-a-built-in-sensitive-information-type.md)| |
|[Clasificadores que se pueden entrenar (versión preliminar)](classifier-learn-about.md)| Clasifica datos con uno de los clasificadores predefinidos o entrena un clasificador con el contenido que usted posea. | [Introducción a los clasificadores que se pueden entrenar (versión preliminar)](classifier-get-started-with.md)| |
|[Clasificación de datos](data-classification-overview.md) | Identifica elementos que tienen una etiqueta de confidencialidad, una etiqueta de retención o que se han clasificado como un tipo de información confidencial en la organización y las acciones que sus usuarios realizan con ellos.  | [Introducción al explorador de contenido](data-classification-content-explorer.md)<br /><br /> [Introducción al explorador de actividad](data-classification-activity-explorer.md)| |



## <a name="protect-your-data"></a>Proteger los datos

Para aplicar acciones de protección flexibles entre las que se incluyen el cifrado, las restricciones de acceso y las marcas visuales, utilice las funcionalidades siguientes:


:::image type="content" source="../media/protectyourdata-4638524-new.png" alt-text="Proteger los datos":::

|**Función**|**¿Qué problemas soluciona?**|**Introducción**|**Licencias**|
|--|--|--|--|
|[Etiquetas de confidencialidad](sensitivity-labels.md)| Una solución única para todas aplicaciones, servicios y dispositivos con el fin de etiquetar y proteger los datos cuando se transfieren dentro y fuera de la organización. <br /><br />Situación de ejemplo: [Aplicar y ver las etiquetas de confidencialidad en Power BI y proteger los datos cuando se exportan](/power-bi/admin/service-security-apply-data-sensitivity-labels)|[Empezar a usar las etiquetas de confidencialidad](get-started-with-sensitivity-labels.md) |
|[Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)| Descubre, etiqueta y protege la información confidencial que reside en almacenes de datos en la nube. | [Descubrir, clasificar, etiquetar y proteger la información regulada y confidencial almacenada en la nube](/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|[Escáner de etiquetas unificadas de Azure Information Protection](/azure/information-protection/deploy-aip-scanner)| Descubre, etiqueta y protege la información confidencial que reside en almacenes de datos locales. | [Configuración e instalación del escáner de etiquetas unificado de Azure Information Protection](/azure/information-protection/deploy-aip-scanner-configure-install)|
|[Explorador de actividades]()||||


## <a name="transition-from-aip-to-mip"></a>Transición de AIP a MIP
La experiencia de administración y el cliente clásico de Azure Information Protection dejarán de estar disponibles a principios del año que viene. Le recomendamos que cambie a Microsoft Information Protection. Esto implica migrar todas las etiquetas y directivas existentes. 

:::image type="content" source="../media/transition-aip2mip-4638524-new.png" alt-text="Transición de AIP a MIP":::

## <a name="additional-capabilities"></a>Capacidades adicionales
Microsoft 365 incluye estas funciones para ayudar a proteger los datos:

|**Función**|**¿Qué problemas soluciona?**|**Introducción**|
|--|--|--|
| Cifrado de mensajes de Office 365 (OME) | Cifra los mensajes de correo electrónico y los documentos adjuntos que se envían a cualquier usuario en cualquier dispositivo, de modo que solo los destinatarios autorizados puedan leer la información de correo electrónico. <br /><br /> Escenario de ejemplo: Revocar el correo electrónico cifrado mediante el Cifrado de mensajes avanzado | Configurar las nuevas capacidades de cifrado de mensajes |
| Cifrado de claves doble | Bajo cualquier circunstancia, solo usted podrá descifrar el contenido protegido, si bien, para requisitos normativos, puede que deba mantener las claves de cifrado en un límite geográfico | Implementar el cifrado de doble clave |  
| Cifrado de servicio con clave de cliente | Protege frente a la visualización de los datos por parte de sistemas o personal no autorizado y complementa el cifrado de disco de bitlocker en centros de datos de Microsoft. | Configurar Clave de cliente de Office 365 |
| Information Rights Management (IRM) de SharePoint | Protege las listas y bibliotecas de SharePoint para que, cuando un usuario desproteja un documento, el archivo descargado esté protegido, de modo que solo los usuarios autorizados puedan ver y usar el archivo en función de las directivas que usted especifique. | Configurar Information Rights Management (IRM) en el Centro de administración de SharePoint |
| Conector de administración de derechos | Modo de solo protección para implementaciones locales existentes que usan Exchange o SharePoint Server y la Infraestructura de Clasificación de Archivos (FCI). | Pasos para implementar el conector RMS |



## <a name="prevent-data-loss"></a>Prevenir la pérdida de datos

Para ayudar a evitar el uso compartido accidental de información confidencial, utilice las funciones siguientes:

:::image type="content" source="../media/dlp-4638524-new.png" alt-text="Evitar la pérdida de datos":::

|**Paso**|**Descripción**|**Más información**|
|--|--|--|
|[Diseñar directivas DLP](data-loss-prevention-policies.md)| Planear el modo de identificar información (tipo de información confidencial, etiqueta, otro) <br /><br /> Planear dónde los objetivos de las directivas (servicios, cliente, aplicaciones de terceros). <br /><br /> Planear sugerencias de directiva, otros||
||||




|**Función**|**¿Qué problemas soluciona?**|**Introducción**|
|--|--|--|
|[Obtenga más información acerca de la prevención de pérdida de datos](dlp-learn-about-dlp.md)| Permite evitar el uso compartido no intencionado de elementos confidenciales. | [Introducción a la directiva predeterminada de DLP](get-started-with-the-default-dlp-policy.md)|
|[Obtenga más información sobre la prevención de pérdida de datos en punto de conexión](endpoint-dlp-learn-about.md)| Amplía las capacidades de DLP a los elementos que se usan y comparten en equipos con Windows 10. | [Introducción a la prevención de pérdida de datos en punto de conexión](endpoint-dlp-getting-started.md)|
|[Obtenga información sobre la extensión de cumplimiento de Microsoft (versión preliminar)](dlp-chrome-learn-about.md) | Amplía las capacidades de DLP al explorador Chrome. | [Introducción a la extensión de cumplimiento de Microsoft (versión preliminar)](dlp-chrome-get-started.md)|
|[Obtenga más información sobre el examen de prevención de pérdida de datos locales de Microsoft 365 (versión preliminar)](dlp-on-premises-scanner-learn.md)|Extiende la supervisión de DLP de las actividades de archivos y las acciones de protección de esos archivos a recursos compartidos de archivos locales y bibliotecas de documentos y carpetas de SharePoint.|[Introducción al examen de prevención de pérdida de datos de Microsoft 365 en entorno local (versión preliminar)](dlp-on-premises-scanner-get-started.md)|
|[Proteger la información confidencial en mensajes de chat y canales de Microsoft Teams](dlp-microsoft-teams.md) | Amplía algunas funciones de DLP a los mensajes de canal y chat de Teams | [Obtenga información sobre la directiva de prevención de pérdida de datos predeterminada en Microsoft Teams (versión preliminar)](dlp-teams-default-policy.md)| 


## <a name="additional-resources"></a>Recursos adicionales

Muchas organizaciones usan estas funciones de protección de información para cumplir con las normativas de privacidad de datos. Para ayudarle, hemos diseñado un flujo de trabajo para guiarlo a través de un proceso de un extremo a otro para planear e implementar funcionalidades en Microsoft 365, incluido el acceso seguro, la protección contra amenazas, la protección de la información y el gobierno de datos. Para obtener más información, consulte [Implementar la protección de la información para normativas de privacidad de datos con Microsoft 365](../solutions/information-protection-deploy.md) (aka.ms/m365dataprivacy). 

Además, puede descargar el conjunto de ilustraciones de *Information Protection y funcionalidades de cumplimiento de Microsoft 365* para planificar una estrategia integrada para implementar las funcionalidades de protección de la información.  Siéntase libre de adaptar estas ilustraciones para su propio uso.

| Elemento | Descripción |
|:-----|:------------|
|[![Póster modelo: capacidades de protección y cumplimiento de la información de Microsoft 365](../media/solutions-architecture-center/m365-compliance-illustrations-thumb.png)](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.pdf) <br/> [Descargar como PDF](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.pdf)  \| [Descargar como Visio](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.vsdx) <br/> Japonés: [Descargar como PDF](https://download.microsoft.com/download/6/f/1/6f1a7d0e-dd8e-442e-b073-8e94327ae4f8/m365-compliance-illustrations.pdf)  \| [Descargar como Visio](https://download.microsoft.com/download/6/f/1/6f1a7d0e-dd8e-442e-b073-8e94327ae4f8/m365-compliance-illustrations.vsdx) <br/> Actualizado en octubre de 2020|Incluye: <ul><li>  Protección de la información y prevención de la pérdida de datos de Microsoft</li><li>Directivas y etiquetas de retención </li><li>Barreras de información</li><li>Cumplimiento de comunicaciones</li><li>Administración de riesgos internos</li><li>Ingesta de datos de terceros</li>|

