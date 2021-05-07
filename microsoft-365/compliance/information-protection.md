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
ms.openlocfilehash: 36e8e917349edd5523677112818cd39514710583
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114366"
---
# <a name="microsoft-information-protection-in-microsoft-365"></a>Microsoft Information Protection en Microsoft 365.

>*[Licencias para el Centro de seguridad y cumplimiento de Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

Implemente Microsoft Information Protection (MIP) para descubrir, clasificar y proteger la información confidencial donde esta resida o hacia donde se transfiera.

Las características de MIP se incluyen con el Centro de cumplimiento de Microsoft 365 y proporcionan las herramientas necesarias para [conocer](#know-your-data), [proteger](#protect-your-data) y [evitar la pérdida](#prevent-data-loss) de sus datos.

![Imagen de cómo MIP le ayuda a descubrir, clasificar y proteger los datos confidenciales](../media/powered-by-intelligent-platform.png)

Para obtener información sobre la gobernanza de los datos, consulte [Gobernanza de información de Microsoft en Microsoft 365](manage-Information-governance.md).

## <a name="know-your-data"></a>Conocer los datos

> [!NOTE]
> Para información sobre cómo clasificar y etiquetar datos en Azure Purview, actualmente en versión preliminar, consulte [Etiquetar automáticamente su contenido en Azure Purview](/azure/purview/create-sensitivity-label)
> 
> Para ver los anuncios de publicación de versiones de Azure Purview, consulte las siguientes entradas de blog: [Microsoft Information Protection y Microsoft Azure Purview: mejor juntos](https://techcommunity.microsoft.com/t5/microsoft-security-and/microsoft-information-protection-and-microsoft-azure-purview/ba-p/1957481) y [Azure Purview en Spring Ignite 2021](https://techcommunity.microsoft.com/t5/azure-purview/azure-purview-at-spring-ignite-2021/ba-p/2175919).


Para tener una visión general de sus datos e identificar aquellos más importantes en todo su entorno híbrido, utilice las funciones siguientes:
 
|Funcionalidad|¿Qué problemas se solucionan?|Introducción|
|:------|:------------|:--------------------|
|[Tipos de información confidencial](sensitive-information-type-learn-about.md)| Identifica datos confidenciales mediante expresiones regulares integradas o personalizadas, o con una función. Las pruebas confirmatorias incluyen palabras clave, niveles de confianza y proximidad.| [Personalizar un tipo de información confidencial integrado](customize-a-built-in-sensitive-information-type.md)|
|[Clasificadores que se pueden entrenar](classifier-learn-about.md)| Identifica datos confidenciales mediante ejemplos de los datos que le interesan, en lugar de identificar elementos dentro del elemento (coincidencia de patrones). Puede usar clasificadores predefinidos o entrenar un clasificador con su propio contenido.| [Introducción a los clasificadores que se pueden entrenar](classifier-get-started-with.md) |
|[Clasificación de datos](data-classification-overview.md) | Una identificación gráfica de los elementos de la organización que tienen una etiqueta de confidencialidad, una etiqueta de retención o que se han clasificado. También puede usar esta información para obtener información sobre las acciones que los usuarios están llevando a cabo en estos elementos. | [Introducción al explorador de contenido](data-classification-content-explorer.md)<br /><br /> [Introducción al explorador de actividad](data-classification-activity-explorer.md) |

## <a name="protect-your-data"></a>Proteger los datos

Para aplicar acciones de protección flexibles entre las que se incluyen el cifrado, las restricciones de acceso y las marcas visuales, utilice las funcionalidades siguientes:

|Funcionalidad|¿Qué problemas se solucionan?|Introducción|
|:------|:------------|---------------------|
|[Etiquetas de confidencialidad](sensitivity-labels.md)| Una solución única para todas aplicaciones, servicios y dispositivos con el fin de etiquetar y proteger los datos cuando se transfieren dentro y fuera de la organización. <br /><br />Escenarios de ejemplo: <br /> [Administrar etiquetas confidenciales para aplicaciones de Office](sensitivity-labels-office-apps.md)<br /> [Cifrar documentos y correos electrónicos](encryption-sensitivity-labels.md )<br /> [Aplicar y ver etiquetas en Power BI](/power-bi/admin/service-security-apply-data-sensitivity-labels) <br /><br /> Para obtener una lista completa de escenarios de etiquetas de confidencialidad, vea la documentación de Introducción.|[Empezar a usar las etiquetas de confidencialidad](get-started-with-sensitivity-labels.md) |
|[Cliente de etiquetado unificado de Azure Information Protection](/azure/information-protection/rms-client/aip-clientv2)| En el caso de los equipos con Windows, amplía las etiquetas de confidencialidad a otras características y funciones que incluyen etiquetar y proteger todos los tipos de archivos, desde el explorador de archivos a PowerShell<br /><br /> Ejemplo de características adicionales: [Configuración personalizada para el cliente de etiquetas unificado de Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide-customizations)| [Guía del administrador para cliente de etiquetado unificado de Azure Information Protection ](/azure/information-protection/rms-client/clientv2-admin-guide)|
|[Cifrado de doble clave](double-key-encryption.md)| Bajo cualquier circunstancia, solo su organización podrá descifrar el contenido protegido o para requisitos normativos, debe mantener las claves de cifrado en un límite geográfico. | [Implementar el cifrado de doble clave](double-key-encryption.md#deploy-dke)|
|[Cifrado de mensajes de Office 365 (OME)](ome.md)| Cifra los mensajes de correo electrónico y los documentos adjuntos que se envían a cualquier usuario en cualquier dispositivo, de modo que solo los destinatarios autorizados puedan leer la información de correo electrónico.  <br /><br />Escenario de ejemplo: [Revocar el correo electrónico cifrado mediante el Cifrado de mensajes avanzado](revoke-ome-encrypted-mail.md) | [Configurar las nuevas capacidades de cifrado de mensajes](set-up-new-message-encryption-capabilities.md)|
|[Cifrado de servicio con clave de cliente](customer-key-overview.md) | Protege frente a la visualización de los datos por parte de sistemas o personal no autorizado y complementa el cifrado de disco BitLocker en centros de datos de Microsoft. | [Configurar clave de cliente de Office 365](customer-key-set-up.md)|
|[Information Rights Management (IRM) de SharePoint](set-up-irm-in-sp-admin-center.md#irm-enable-sharepoint-document-libraries-and-lists)|Protege las listas y bibliotecas de SharePoint para que, cuando un usuario desproteja un documento, el archivo descargado esté protegido, de modo que solo los usuarios autorizados puedan ver y usar el archivo en función de las directivas que usted especifique. | [Configurar Information Rights Management (IRM) en el Centro de administración de SharePoint](set-up-irm-in-sp-admin-center.md)|
[Conector de administración de derechos](/azure/information-protection/deploy-rms-connector) |Modo de solo protección para implementaciones locales existentes que usan Exchange o SharePoint Server, o servidores de archivos que ejecutan Windows Server y la Infraestructura de Clasificación de Archivos (FCI). | [Pasos para implementar el conector RMS](/azure/information-protection/deploy-rms-connector#steps-to-deploy-the-rms-connector)
|[Escáner de etiquetas unificadas de Azure Information Protection](/azure/information-protection/deploy-aip-scanner)| Descubre, etiqueta y protege la información confidencial que reside en almacenes de datos locales. | [Configuración e instalación del escáner de etiquetas unificado de Azure Information Protection](/azure/information-protection/deploy-aip-scanner-configure-install)|
|[Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)| Descubre, etiqueta y protege la información confidencial que reside en almacenes de datos en la nube. | [Descubrir, clasificar, etiquetar y proteger la información regulada y confidencial almacenada en la nube](/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|[SDK de Microsoft Information Protection](/information-protection/develop/overview#microsoft-information-protection-sdk)|Amplía las etiquetas de confidencialidad a los servicios y aplicaciones de terceros.  <br /><br /> Escenario de ejemplo: [Establecer y obtener una etiqueta de confidencialidad (C++)](/information-protection/develop/quick-file-set-get-label-cpp) |[Instalación y configuración del SDK de Microsoft Information Protection (MIP)](/information-protection/develop/setup-configure-mip)|


## <a name="prevent-data-loss"></a>Prevenir la pérdida de datos

Para ayudar a evitar el uso compartido accidental de información confidencial, utilice las funciones siguientes:


|Funcionalidad|¿Qué problemas se solucionan?|Introducción|
|:------|:------------|:---------------------|
|[Obtenga más información acerca de la prevención de pérdida de datos](dlp-learn-about-dlp.md)| Permite evitar el uso compartido no intencionado de elementos confidenciales. | [Introducción a la directiva predeterminada de DLP](get-started-with-the-default-dlp-policy.md)|
|[Obtenga más información sobre la prevención de pérdida de datos en punto de conexión](endpoint-dlp-learn-about.md)| Amplía las capacidades de DLP a los elementos que se usan y comparten en equipos con Windows 10. | [Introducción a la prevención de pérdida de datos en punto de conexión](endpoint-dlp-getting-started.md)|
|[Obtenga información sobre la extensión de cumplimiento de Microsoft (versión preliminar)](dlp-chrome-learn-about.md) | Amplía las capacidades de DLP al explorador Chrome. | [Introducción a la extensión de cumplimiento de Microsoft (versión preliminar)](dlp-chrome-get-started.md)|
|[Obtenga más información sobre el examen de prevención de pérdida de datos locales de Microsoft 365 (versión preliminar)](dlp-on-premises-scanner-learn.md)|Extiende la supervisión de DLP de las actividades de archivos y las acciones de protección de esos archivos a recursos compartidos de archivos locales y bibliotecas de documentos y carpetas de SharePoint.|[Introducción al examen de prevención de pérdida de datos de Microsoft 365 en entorno local (versión preliminar)](dlp-on-premises-scanner-get-started.md)|
|[Proteger la información confidencial en mensajes de chat y canales de Microsoft Teams](dlp-microsoft-teams.md) | Amplía algunas funciones de DLP a los mensajes de canal y chat de Teams | [Obtenga información sobre la directiva de prevención de pérdida de datos predeterminada en Microsoft Teams (versión preliminar)](dlp-teams-default-policy.md)| 


## <a name="additional-resources"></a>Recursos adicionales

Muchas organizaciones usan estas funciones de protección de información para cumplir con las normativas de privacidad de datos. Para ayudarle, hemos diseñado un flujo de trabajo para guiarlo a través de un proceso de un extremo a otro para planear e implementar funcionalidades en Microsoft 365, incluido el acceso seguro, la protección contra amenazas, la protección de la información y el gobierno de datos. Para obtener más información, consulte [Implementar la protección de la información para normativas de privacidad de datos con Microsoft 365](../solutions/information-protection-deploy.md) (aka.ms/m365dataprivacy). 

Además, para ayudarle a planear una estrategia integrada para implementar funcionalidades de protección de la información, descargue el conjunto de ilustraciones de *Funcionalidades de protección de la información y cumplimiento de Microsoft 365*.  Siéntase libre de adaptar estas ilustraciones para su propio uso.

| Elemento | Descripción |
|:-----|:------------|
|[![Póster modelo: capacidades de protección y cumplimiento de la información de Microsoft 365](../media/solutions-architecture-center/m365-compliance-illustrations-thumb.png)](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.pdf) <br/> [Descargar como PDF](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.pdf)  \| [Descargar como Visio](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.vsdx) <br/> Japonés: [Descargar como PDF](https://download.microsoft.com/download/6/f/1/6f1a7d0e-dd8e-442e-b073-8e94327ae4f8/m365-compliance-illustrations.pdf)  \| [Descargar como Visio](https://download.microsoft.com/download/6/f/1/6f1a7d0e-dd8e-442e-b073-8e94327ae4f8/m365-compliance-illustrations.vsdx) <br/> Actualizado en octubre de 2020|Incluye: <ul><li>  Protección de la información y prevención de la pérdida de datos de Microsoft</li><li>Directivas y etiquetas de retención </li><li>Barreras de información</li><li>Cumplimiento de comunicaciones</li><li>Administración de riesgos internos</li><li>Ingesta de datos de terceros</li>|