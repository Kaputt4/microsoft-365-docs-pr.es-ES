---
title: Protección de la información de Microsoft en Microsoft 365
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: High
search.appverid:
- MOE150
- MET150
- m365solution-mip
- m365initiative-compliance
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: Implemente las capacidades de Microsoft Information Protection (MIP) mediante el cumplimiento de Microsoft 365 para ayudarle a descubrir, clasificar y proteger información confidencial donde vive o se desplaza.
ms.openlocfilehash: b421cf0b81c5ad52282302626b93064f9cd83ce8
ms.sourcegitcommit: 0f48beaca3afa4df12d41847014975d50a4ebe7d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2020
ms.locfileid: "48338355"
---
# <a name="microsoft-information-protection-in-microsoft-365"></a>Protección de la información de Microsoft en Microsoft 365

>*[Licencias para el cumplimiento de & de seguridad de Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

Usar Microsoft Information Protection (MIP) para ayudarle a descubrir, clasificar y proteger información confidencial donde vive o se desplaza.

Las funcionalidades de MIP se incluyen con el cumplimiento de Microsoft 365 y le proporcionan las herramientas necesarias para [conocer sus datos](#know-your-data), [proteger sus datos](#protect-your-data)y [evitar la pérdida de datos](#prevent-data-loss).

![Conocer los datos, proteger los datos, evitar la pérdida de datos, regir los datos](../media/powered-by-intelligent-platform.png)

Para obtener información sobre el control de los datos, vea [Microsoft Information Governance en microsoft 365](manage-Information-governance.md).

## <a name="know-your-data"></a>Conocer los datos

Para comprender su panorama de datos e identificar datos importantes en todo el entorno híbrido, use las siguientes capacidades:
 
|Funcionalidad|¿Qué problemas soluciona?|Introducción|
|:------|:------------|:--------------------|:-----------------------------|
|[Tipos de información confidencial](sensitive-information-type-entity-definitions.md)| Identifica los datos confidenciales mediante expresiones regulares integradas o personalizadas o una función, junto con evidencias corroboradoras que incluyen palabras clave, niveles de confianza y proximidad.| [Personalizar un tipo de información confidencial integrado](customize-a-built-in-sensitive-information-type.md)|
|[Clasificadores capacitados (versión preliminar)](classifier-learn-about.md)| Clasifica datos para usted, usando uno de los clasificadores integrados o entrena un clasificador con su propio contenido | [Introducción a los clasificadores que se pueden entrenar (versión preliminar)](classifier-get-started-with.md) |
|[Clasificación de datos](data-classification-overview.md) | Identifica los elementos que tienen una etiqueta de confidencialidad, una etiqueta de retención o que se han clasificado como un tipo de información confidencial en la organización y las acciones que los usuarios están tomando en ellos.  | [Introducción al explorador de contenido](data-classification-content-explorer.md)<br /><br /> [Introducción al explorador de actividad](data-classification-activity-explorer.md) |

## <a name="protect-your-data"></a>Proteger los datos

Para aplicar acciones de protección flexibles que incluyan cifrado, restricciones de acceso y marcadores visuales, use las siguientes capacidades:

|Funcionalidad|¿Qué problemas soluciona?|Introducción|
|:------|:------------|---------------------|:----------------------------|
|[Etiquetas de confidencialidad](sensitivity-labels.md)| Una única solución en aplicaciones, servicios y dispositivos para etiquetar y proteger los datos a medida que viajan dentro y fuera de la organización. <br /><br />Escenario de ejemplo: [aplicar y ver las etiquetas de confidencialidad en Power BI y proteger los datos cuando se exportan](https://docs.microsoft.com/power-bi/admin/service-security-apply-data-sensitivity-labels)|[ Introducción a las etiquetas de confidencialidad](get-started-with-sensitivity-labels.md) |
|[Cliente de etiquetación unificada de Azure Information Protection](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)| Para los equipos Windows, extiende las etiquetas de confidencialidad para las características y funciones adicionales que incluyen el etiquetado y la protección de todos los tipos de archivo desde el explorador de archivos y PowerShell<br /><br /> Ejemplo de características adicionales: [configuraciones personalizadas para el cliente de etiquetado Unificado de Azure Information Protection](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)| [Guía del administrador del cliente de etiqueta unificada de Azure Information Protection](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide)|
|[Cifrado de claves doble](double-key-encryption.md)| En todos los casos, solo usted puede descifrar el contenido protegido o los requisitos normativos deben mantener las claves de cifrado dentro de un límite geográfico | [Implementar el cifrado de doble clave](double-key-encryption.md#deploy-dke)|
|[Office 365 cifrado de mensajes](ome.md) (OME)| Cifra los mensajes de correo electrónico y los documentos adjuntos que se envían a cualquier usuario en cualquier dispositivo, de modo que solo los destinatarios autorizados puedan leer la información de correo electrónico.  <br /><br />Escenario de ejemplo: [revocar correo electrónico cifrado por el cifrado de mensajes avanzado](revoke-ome-encrypted-mail.md) | [Configurar las nuevas capacidades de cifrado de mensajes](set-up-new-message-encryption-capabilities.md)|
|[Cifrado de servicio con clave de cliente](customer-key-overview.md) | Protege contra la visualización de datos por parte de sistemas o sistemas no autorizados y complementa el cifrado de disco de BitLocker en centros de datos de Microsoft. | [Configurar Clave de cliente de Office 365](customer-key-set-up.md)|
|[Administración de derechos de la información (IRM) de SharePoint](set-up-irm-in-sp-admin-center.md#irm-enable-sharepoint-document-libraries-and-lists)|Protege las listas y bibliotecas de SharePoint de modo que, cuando un usuario desproteja un documento, el archivo descargado esté protegido para que solo los usuarios autorizados puedan ver y usar el archivo de acuerdo con las directivas que especifique. | [Set up Information Rights Management (IRM) in SharePoint admin center](set-up-irm-in-sp-admin-center.md).|
[Conector Rights Management](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector) |Protección: solo para implementaciones locales existentes que usan Exchange o SharePoint Server, o servidores de archivos que ejecutan Windows Server y la infraestructura de clasificación de archivos (FCI). | [Pasos para implementar el conector RMS](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector#steps-to-deploy-the-rms-connector)
|[Escáner de etiquetación unificada de Azure Information Protection](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)| Detecta, etiqueta y protege información confidencial que reside en almacenes de datos que están en local | [Configuración e instalación del escáner de etiquetación unificada de Azure Information Protection](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner-configure-install)|
|[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)| Detecta, etiqueta y protege información confidencial que reside en almacenes de datos que están en la nube | [Descubrir, clasificar, etiquetar y proteger la información regulada y confidencialidad almacenada en la nube](https://docs.microsoft.com/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|[SDK de Microsoft Information Protection](https://docs.microsoft.com/information-protection/develop/overview#microsoft-information-protection-sdk)|Amplía las etiquetas de confidencialidad a servicios y aplicaciones de terceros  <br /><br /> Escenario de ejemplo: [establecer y obtener una etiqueta de confidencialidad (C++)](https://docs.microsoft.com/information-protection/develop/quick-file-set-get-label-cpp) |[Instalación y configuración del SDK de Microsoft Information Protection (MIP)](https://docs.microsoft.com/information-protection/develop/setup-configure-mip)|

## <a name="prevent-data-loss"></a>Prevenir la pérdida de datos

Para ayudar a evitar el reuso accidental de información confidencial, use las siguientes funciones:


|Funcionalidad|¿Qué problemas soluciona?|Introducción|
|:------|:------------|:---------------------|:-----------------------------|
|[Prevención de pérdida de datos](data-loss-prevention-policies.md) (DLP)| Ayuda a impedir el uso compartido involuntaria de elementos confidenciales <br /><br />Escenario de ejemplo: [proteger información confidencial en mensajes de chat y de canal de Microsoft Teams](dlp-microsoft-teams.md) | [Introducción a la directiva predeterminada de DLP](get-started-with-the-default-dlp-policy.md)|
|[Prevención de pérdida de datos de extremos (versión preliminar)](endpoint-dlp-learn-about.md)| Amplía las capacidades de DLP a los elementos que se usan y comparten en equipos con Windows 10 | [Introducción a la prevención de pérdida de datos de los puntos de conexión (versión preliminar)](endpoint-dlp-getting-started.md)|
