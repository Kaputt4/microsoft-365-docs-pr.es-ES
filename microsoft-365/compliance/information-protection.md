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
ms.localizationpriority: high
search.appverid:
- MOE150
- MET150
ms.collection:
- m365solution-mip
- m365initiative-compliance
recommendations: false
description: Implemente Microsoft Information Protection (MIP) para proteger la información confidencial donde esta resida o hacia donde se transfiera.
ms.openlocfilehash: 45448ee509b580a5fbd35388b95f130b684325d4
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2021
ms.locfileid: "61369689"
---
# <a name="microsoft-information-protection-in-microsoft-365"></a>Microsoft Information Protection en Microsoft 365.

>*[Licencias para el Centro de seguridad y cumplimiento de Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

Implemente Microsoft Information Protection (MIP) para descubrir, clasificar y proteger la información confidencial donde esta resida o hacia donde se transfiera.

Las características de MIP se incluyen con el Centro de cumplimiento de Microsoft 365 y proporcionan las herramientas necesarias para [conocer](#know-your-data), [proteger](#protect-your-data) y [evitar la pérdida](#prevent-data-loss) de sus datos.

![Imagen de cómo MIP le ayuda a descubrir, clasificar y proteger los datos confidenciales.](../media/powered-by-intelligent-platform.png)

Para obtener información sobre la gobernanza de los datos, consulte [Gobernanza de información de Microsoft en Microsoft 365](manage-Information-governance.md).

## <a name="know-your-data"></a>Conocer los datos

Para tener una visión general de sus datos e identificar aquellos más importantes en todo su entorno híbrido, utilice las funciones siguientes:

|Funcionalidad|¿Qué problemas se solucionan?|Introducción|
|:------|:------------|:--------------------|
|[Tipos de información confidencial](sensitive-information-type-learn-about.md)| Identifica datos confidenciales mediante expresiones regulares integradas o personalizadas, o con una función. Las pruebas confirmatorias incluyen palabras clave, niveles de confianza y proximidad.| [Personalizar un tipo de información confidencial integrado](customize-a-built-in-sensitive-information-type.md)|
|[Clasificadores que se pueden entrenar](classifier-learn-about.md)| Identifica datos confidenciales mediante ejemplos de los datos que le interesan, en lugar de identificar elementos dentro del elemento (coincidencia de patrones). Puede usar clasificadores predefinidos o entrenar un clasificador con su propio contenido.| [Introducción a los clasificadores que se pueden entrenar](classifier-get-started-with.md) |
|[Clasificación de datos](data-classification-overview.md) | Una identificación gráfica de los elementos de la organización que tienen una etiqueta de confidencialidad, una etiqueta de retención o que se han clasificado. También puede usar esta información para obtener información sobre las acciones que los usuarios están llevando a cabo en estos elementos. | [Introducción al explorador de contenido](data-classification-content-explorer.md) <p> [Introducción al explorador de actividad](data-classification-activity-explorer.md) |
|[Azure Purview](/azure/purview/overview) |Identifica datos confidenciales y aplica el etiquetado automático a cualquier contenido de los recursos de Azure Purview tales como Azure Blob Storage, Azure Files, Azure Data Lake Storage y orígenes de datos de varias nubes. |[Etiquetado en Azure Purview](/azure/purview/create-sensitivity-label) |

## <a name="protect-your-data"></a>Proteger los datos

Para aplicar acciones de protección flexibles entre las que se incluyen el cifrado, las restricciones de acceso y las marcas visuales, utilice las funcionalidades siguientes:

|Funcionalidad|¿Qué problemas se solucionan?|Introducción|
|:------|:------------|---------------------|
|[Etiquetas de confidencialidad](sensitivity-labels.md)| Una solución única para todas aplicaciones, servicios y dispositivos con el fin de etiquetar y proteger los datos cuando se transfieren dentro y fuera de la organización. <p> Escenarios de ejemplo: <p> [Administrar etiquetas confidenciales para aplicaciones de Office](sensitivity-labels-office-apps.md) <p> [Cifrar documentos y correos electrónicos](encryption-sensitivity-labels.md) <p> [Aplicar y ver etiquetas en Power BI](/power-bi/admin/service-security-apply-data-sensitivity-labels) <p> Para obtener una lista completa de escenarios de etiquetas de confidencialidad, vea la documentación de Introducción.|[Introducción a las etiquetas de confidencialidad](get-started-with-sensitivity-labels.md) |
|[Cliente de etiquetado unificado de Azure Information Protection](/azure/information-protection/rms-client/aip-clientv2)| En el caso de los equipos con Windows, amplía las etiquetas de confidencialidad a otras características y funciones que incluyen etiquetar y proteger todos los tipos de archivos, desde el explorador de archivos a PowerShell <p> Ejemplo de características adicionales: [Configuración personalizada para el cliente de etiquetas unificado de Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide-customizations)| [Guía del administrador para cliente de etiquetado unificado de Azure Information Protection ](/azure/information-protection/rms-client/clientv2-admin-guide)|
|[Cifrado de doble clave](double-key-encryption.md)| Bajo cualquier circunstancia, solo su organización podrá descifrar el contenido protegido o para requisitos normativos, debe mantener las claves de cifrado en un límite geográfico. | [Implementar el cifrado de doble clave](double-key-encryption.md#deploy-dke)|
|[Cifrado de mensajes de Office 365 (OME)](ome.md)| Cifra los mensajes de correo electrónico y los documentos adjuntos que se envían a cualquier usuario en cualquier dispositivo, de modo que solo los destinatarios autorizados puedan leer la información de correo electrónico. <p> Escenario de ejemplo: [Revocar el correo electrónico cifrado mediante el Cifrado de mensajes avanzado](revoke-ome-encrypted-mail.md) | [Configurar las nuevas capacidades de cifrado de mensajes](set-up-new-message-encryption-capabilities.md)|
|[Cifrado de servicio con clave de cliente](customer-key-overview.md) | Protege frente a la visualización de los datos por parte de sistemas o personal no autorizado y complementa el cifrado de disco BitLocker en centros de datos de Microsoft. | [Configurar clave de cliente de Office 365](customer-key-set-up.md)|
|[Information Rights Management (IRM) de SharePoint](set-up-irm-in-sp-admin-center.md#irm-enable-sharepoint-document-libraries-and-lists)|Protege las listas y bibliotecas de SharePoint para que, cuando un usuario desproteja un documento, el archivo descargado esté protegido, de modo que solo los usuarios autorizados puedan ver y usar el archivo en función de las directivas que usted especifique. | [Configurar Information Rights Management (IRM) en el Centro de administración de SharePoint](set-up-irm-in-sp-admin-center.md)|
[Conector de administración de derechos](/azure/information-protection/deploy-rms-connector) |Modo de solo protección para implementaciones locales existentes que usan Exchange o SharePoint Server, o servidores de archivos que ejecutan Windows Server y la Infraestructura de Clasificación de Archivos (FCI). | [Pasos para implementar el conector RMS](/azure/information-protection/deploy-rms-connector#steps-to-deploy-the-rms-connector)
|[Escáner de etiquetas unificadas de Azure Information Protection](/azure/information-protection/deploy-aip-scanner)| Descubre, etiqueta y protege la información confidencial que reside en almacenes de datos locales. | [Configuración e instalación del escáner de etiquetas unificado de Azure Information Protection](/azure/information-protection/deploy-aip-scanner-configure-install)|
|[Microsoft Defender for Cloud Apps](/cloud-app-security/what-is-cloud-app-security)| Descubre, etiqueta y protege la información confidencial que reside en almacenes de datos en la nube. | [Descubrir, clasificar, etiquetar y proteger la información regulada y confidencial almacenada en la nube](/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|[SDK de Microsoft Information Protection](/information-protection/develop/overview#microsoft-information-protection-sdk)|Amplía las etiquetas de confidencialidad a los servicios y aplicaciones de terceros. <p> Escenario de ejemplo: [Establecer y obtener una etiqueta de confidencialidad (C++)](/information-protection/develop/quick-file-set-get-label-cpp) |[Instalación y configuración del SDK de Microsoft Information Protection (MIP)](/information-protection/develop/setup-configure-mip)|


## <a name="prevent-data-loss"></a>Prevenir la pérdida de datos

Para ayudar a evitar el uso compartido accidental de información confidencial, utilice las funciones siguientes:


|Funcionalidad|¿Qué problemas se solucionan?|Introducción|
|:------|:------------|:---------------------|
|[Prevención de pérdida de datos](dlp-learn-about-dlp.md)| Permite evitar el uso compartido no intencionado de elementos confidenciales. | [Introducción a la directiva predeterminada de DLP](get-started-with-the-default-dlp-policy.md)|
|[Prevención de perdida de datos en el punto de conexión](endpoint-dlp-learn-about.md)| Amplía las capacidades de DLP a los elementos que se usan y comparten en equipos con Windows 10. | [Introducción a la prevención de pérdida de datos en punto de conexión](endpoint-dlp-getting-started.md)|
|[Extensión de cumplimiento de Microsoft](dlp-chrome-learn-about.md) | Amplía las capacidades de DLP al explorador Chrome. | [Introducción a la extensión de cumplimiento de Microsoft](dlp-chrome-get-started.md)|
|[Examinador de prevención de pérdida de datos local de Microsoft 365 (versión preliminar)](dlp-on-premises-scanner-learn.md)|Extiende la supervisión de DLP de las actividades de archivos y las acciones de protección de esos archivos a recursos compartidos de archivos locales y bibliotecas de documentos y carpetas de SharePoint.|[Introducción al examen de prevención de pérdida de datos de Microsoft 365 en entorno local (versión preliminar)](dlp-on-premises-scanner-get-started.md)|
|[Proteger la información confidencial en mensajes de chat y canales de Microsoft Teams](dlp-microsoft-teams.md) | Amplía algunas funciones de DLP a los mensajes de canal y chat de Teams | [Obtenga información sobre la directiva de prevención de pérdida de datos predeterminada en Microsoft Teams (versión preliminar)](dlp-teams-default-policy.md)|

## <a name="licensing-requirements"></a>Requisitos de licencias

Los requisitos de licencia para MIP dependen de los escenarios y características que use, en lugar del establecimiento de requisitos de licencia para cada funcionalidad que se muestra en esta página. Para comprender los requisitos de licencia y las opciones de MIP, consulte la sección [Information Protection: Etiquetado de confidencialidad](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection-sensitivity-labeling) y descargue el [documento PDF relacionado](https://go.microsoft.com/fwlink/?linkid=2139145)para conocer los requisitos de licencia a nivel de características de la documentación de licencias de Microsoft 365.
