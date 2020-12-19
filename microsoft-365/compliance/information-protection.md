---
title: Microsoft Information Protection en Microsoft 365.
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.collection:
- m365solution-mip
- m365initiative-compliance
description: Implemente Microsoft Information Protection (MIP) para proteger la información confidencial donde esta resida o hacia donde se transfiera.
ms.openlocfilehash: 2a1ec47ce888dc6d31868d65f9c4c113fa9b968c
ms.sourcegitcommit: c0495e224f12c448bfc162ef2e4b33b82f064ac8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2020
ms.locfileid: "49709512"
---
# <a name="microsoft-information-protection-in-microsoft-365"></a>Microsoft Information Protection en Microsoft 365.

>*[Licencias para el Centro de seguridad y cumplimiento de Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

Implemente Microsoft Information Protection (MIP) para descubrir, clasificar y proteger la información confidencial donde esta resida o hacia donde se transfiera.

Las características de MIP se incluyen con el Centro de cumplimiento de Microsoft 365 y proporcionan las herramientas necesarias para [conocer](#know-your-data), [proteger](#protect-your-data) y [evitar la pérdida](#prevent-data-loss) de sus datos.

![Imagen de cómo MIP le ayuda a descubrir, clasificar y proteger los datos confidenciales](../media/powered-by-intelligent-platform.png)

Para obtener información sobre la gobernanza de los datos, consulte [Gobernanza de información de Microsoft en Microsoft 365](manage-Information-governance.md).

## <a name="know-your-data"></a>Conocer los datos

> [!NOTE]
> Para información sobre cómo clasificar y etiquetar datos en Azure Purview, actualmente en versión preliminar, consulte [Etiquetar automáticamente su contenido en Azure Purview](https://docs.microsoft.com/azure/purview/create-sensitivity-label)
> 
> Para obtener más información sobre esta nueva versión, consulte la entrada de blog [Microsoft Information Protection y Microsoft Azure Purview: mejor juntos](https://techcommunity.microsoft.com/t5/microsoft-security-and/microsoft-information-protection-and-microsoft-azure-purview/ba-p/1957481).



Para tener una visión general de sus datos e identificar aquellos más importantes en todo su entorno híbrido, utilice las funciones siguientes:
 
|Funcionalidad|¿Qué problemas se solucionan?|Introducción|
|:------|:------------|:--------------------|:-----------------------------|
|[Tipos de información confidencial](sensitive-information-type-entity-definitions.md)| Identifica datos confidenciales mediante expresiones regulares integradas o personalizadas, o con una función, junto con pruebas confirmatorias que incluyen palabras clave, niveles de confianza y proximidad.| [Personalizar un tipo de información confidencial integrado](customize-a-built-in-sensitive-information-type.md)|
|[Clasificadores que se pueden entrenar (versión preliminar)](classifier-learn-about.md)| Clasifica datos con uno de los clasificadores predefinidos o entrena un clasificador con el contenido que usted posea. | [Introducción a los clasificadores que se pueden entrenar (versión preliminar)](classifier-get-started-with.md) |
|[Clasificación de datos](data-classification-overview.md) | Identifica elementos que tienen una etiqueta de confidencialidad, una etiqueta de retención o que se han clasificado como un tipo de información confidencial en la organización y las acciones que sus usuarios realizan con ellos.  | [Introducción al explorador de contenido](data-classification-content-explorer.md)<br /><br /> [Introducción al explorador de actividad](data-classification-activity-explorer.md) |

## <a name="protect-your-data"></a>Proteger los datos

Para aplicar acciones de protección flexibles entre las que se incluyen el cifrado, las restricciones de acceso y las marcas visuales, utilice las funcionalidades siguientes:

|Funcionalidad|¿Qué problemas se solucionan?|Introducción|
|:------|:------------|---------------------|:----------------------------|
|[Etiquetas de confidencialidad](sensitivity-labels.md)| Una solución única para todas aplicaciones, servicios y dispositivos con el fin de etiquetar y proteger los datos cuando se transfieren dentro y fuera de la organización. <br /><br />Escenario de ejemplo: [Aplicar y ver las etiquetas en Power BI y proteger los datos cuando se exportan](https://docs.microsoft.com/power-bi/admin/service-security-apply-data-sensitivity-labels)|[Empezar a usar las etiquetas de confidencialidad](get-started-with-sensitivity-labels.md) |
|[Cliente de etiquetado unificado de Azure Information Protection](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)| En el caso de los equipos con Windows, amplía las etiquetas de confidencialidad a otras características y funciones que incluyen etiquetar y proteger todos los tipos de archivos, desde el explorador de archivos a PowerShell<br /><br /> Ejemplo de características adicionales: [Configuración personalizada para el cliente de etiquetas unificado de Azure Information Protection](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)| [Guía del administrador para cliente de etiquetado unificado de Azure Information Protection ](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide)|
|[Cifrado de doble clave](double-key-encryption.md)| Bajo cualquier circunstancia, solo usted podrá descifrar el contenido protegido, si bien, para requisitos normativos, puede que deba mantener las claves de cifrado en un límite geográfico | [Implementar el cifrado de doble clave](double-key-encryption.md#deploy-dke)|
|[Cifrado de mensajes de Office 365 (OME)](ome.md)| Cifra los mensajes de correo electrónico y los documentos adjuntos que se envían a cualquier usuario en cualquier dispositivo, de modo que solo los destinatarios autorizados puedan leer la información de correo electrónico  <br /><br />Escenario de ejemplo: [Revocar el correo electrónico cifrado mediante el Cifrado de mensajes avanzado](revoke-ome-encrypted-mail.md) | [Configurar las nuevas capacidades de cifrado de mensajes](set-up-new-message-encryption-capabilities.md)|
|[Cifrado de servicio con clave de cliente](customer-key-overview.md) | Protege frente a la visualización de los datos por parte de sistemas o equipos no autorizados y complementa el cifrado de disco BitLocker en centros de datos de Microsoft. | [Configurar clave de cliente de Office 365](customer-key-set-up.md)|
|[Information Rights Management (IRM) de SharePoint](set-up-irm-in-sp-admin-center.md#irm-enable-sharepoint-document-libraries-and-lists)|Protege las listas y bibliotecas de SharePoint para que, cuando un usuario desproteja un documento (en el sentido de que solo lo pueda editar él), el archivo descargado esté protegido, de modo que solo los usuarios autorizados puedan ver y usar el archivo en función de las directivas que usted especifique. | [Configurar Information Rights Management (IRM) en el Centro de administración de SharePoint](set-up-irm-in-sp-admin-center.md)|
[Conector de administración de derechos](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector) |Modo de solo protección para implementaciones locales existentes que usan Exchange o SharePoint Server, o servidores de archivos que ejecutan Windows Server y la Infraestructura de Clasificación de Archivos (FCI). | [Pasos para implementar el conector RMS](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector#steps-to-deploy-the-rms-connector)
|[Escáner de etiquetas unificadas de Azure Information Protection](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)| Descubre, etiqueta y protege la información confidencial que reside en almacenes de datos locales. | [Configuración e instalación del escáner de etiquetas unificado de Azure Information Protection](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner-configure-install)|
|[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)| Descubre, etiqueta y protege la información confidencial que reside en almacenes de datos en la nube. | [Descubrir, clasificar, etiquetar y proteger la información regulada y confidencial almacenada en la nube](https://docs.microsoft.com/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|[SDK de Microsoft Information Protection](https://docs.microsoft.com/information-protection/develop/overview#microsoft-information-protection-sdk)|Amplía las etiquetas de confidencialidad a los servicios y aplicaciones de terceros.  <br /><br /> Escenario de ejemplo: [Establecer y obtener una etiqueta de confidencialidad (C++)](https://docs.microsoft.com/information-protection/develop/quick-file-set-get-label-cpp) |[Instalación y configuración del SDK de Microsoft Information Protection (MIP)](https://docs.microsoft.com/information-protection/develop/setup-configure-mip)|


## <a name="prevent-data-loss"></a>Prevenir la pérdida de datos

Para ayudar a evitar el uso compartido accidental de información confidencial, utilice las funciones siguientes:


|Funcionalidad|¿Qué problemas se solucionan?|Introducción|
|:------|:------------|:---------------------|:-----------------------------|
|[Prevención de pérdida de datos (DLP)](data-loss-prevention-policies.md)| Permite evitar el uso compartido no intencionado de elementos confidenciales. <br /><br />Escenario de ejemplo: [Proteger la información confidencial en mensajes de chat y canales de Microsoft Teams](dlp-microsoft-teams.md) | [Introducción a la directiva predeterminada de DLP](get-started-with-the-default-dlp-policy.md)|
|[Obtenga más información sobre la prevención de pérdida de datos en punto de conexión](endpoint-dlp-learn-about.md)| Amplía las capacidades DLP a los elementos que se usan y comparten en equipos con Windows 10. | [Introducción a la prevención de pérdida de datos en punto de conexión](endpoint-dlp-getting-started.md)|
