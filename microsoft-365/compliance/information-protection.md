---
title: Microsoft Purview Information Protection
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
description: Implemente las funcionalidades de Information Protection de Microsoft Purview para ayudarle a proteger la información confidencial dondequiera que resida o viaje.
ms.openlocfilehash: ac6627d620169aca962f85f30c98d830b4a34a9f
ms.sourcegitcommit: caedcf7f16eed23596487d97c375d4bc4c8f3566
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2022
ms.locfileid: "64999880"
---
# <a name="protect-your-sensitive-data-with-microsoft-purview"></a>Proteja sus datos confidenciales con Microsoft Purview

> [!TIP]
> *¿Sabía que puede probar las versiones premium de las nueve soluciones de Microsoft Purview de forma gratuita?* Utilice la prueba de 90 días de las soluciones Purview para explorar cómo las sólidas capacidades de Purview pueden ayudar a su organización a satisfacer sus necesidades de cumplimiento. Los clientes Microsoft 365 E3 y Office 365 E3 pueden empezar ahora en el [Centro de pruebas del portal de cumplimiento de Microsoft Purview](https://compliance.microsoft.com/trialHorizontalHub?sku=ComplianceE5&ref=DocsRef). Obtenga información sobre [las personas que pueden registrarse y los términos de la prueba](compliance-easy-trials.md).

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

>*[Licencias para el Centro de seguridad y cumplimiento de Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

Implemente funcionalidades de **Microsoft Purview Information Protection** (anteriormente Microsoft Information Protection) para ayudarle a descubrir, clasificar y proteger la información confidencial dondequiera que resida o viaje.

Estas funcionalidades de protección de la información proporcionan las herramientas necesarias para [conocer los de datos](#know-your-data), [proteger los datos](#protect-your-data)y [evitar la pérdida de datos](#prevent-data-loss).

![Imagen de cómo Microsoft Purview Information Protection ayuda a detectar, clasificar y proteger datos confidenciales.](../media/powered-by-intelligent-platform.png)

Para obtener instrucciones prescriptivas para implementar una solución de Information Protection de Microsoft Purview para su organización, consulte [Implementar una solución de protección de la información con Microsoft Purview](information-protection-solution.md).

Para obtener información sobre cómo controlar los datos, consulte [Controlar los datos con Microsoft Purview](manage-Information-governance.md).

## <a name="know-your-data"></a>Conocer los datos

Para tener una visión general de sus datos e identificar aquellos confidenciales en todo su entorno híbrido, utilice las funciones siguientes:

|Funcionalidad|¿Qué problemas se solucionan?|Introducción|
|:------|:------------|:--------------------|
|[Tipos de información confidencial](sensitive-information-type-learn-about.md)| Identifica datos confidenciales mediante expresiones regulares integradas o personalizadas, o con una función. Las pruebas confirmatorias incluyen palabras clave, niveles de confianza y proximidad.| [Personalizar un tipo de información confidencial integrado](customize-a-built-in-sensitive-information-type.md)|
|[Clasificadores que se pueden entrenar](classifier-learn-about.md)| Identifica datos confidenciales mediante ejemplos de los datos que le interesan, en lugar de identificar elementos dentro del elemento (coincidencia de patrones). Puede usar clasificadores predefinidos o entrenar un clasificador con su propio contenido.| [Introducción a los clasificadores que se pueden entrenar](classifier-get-started-with.md) |
|[Clasificación de datos](data-classification-overview.md) | Una identificación gráfica de los elementos de la organización que tienen una etiqueta de confidencialidad, una etiqueta de retención o que se han clasificado. También puede usar esta información para obtener información sobre las acciones que los usuarios están llevando a cabo en estos elementos. | [Introducción al explorador de contenido](data-classification-content-explorer.md) <p> [Introducción al explorador de actividad](data-classification-activity-explorer.md) |

## <a name="protect-your-data"></a>Proteger los datos

Para aplicar acciones de protección flexibles entre las que se incluyen el cifrado, las restricciones de acceso y las marcas visuales, utilice las funcionalidades siguientes:

|Funcionalidad|¿Qué problemas se solucionan?|Introducción|
|:------|:------------|---------------------|
|[Etiquetas de confidencialidad](sensitivity-labels.md)| Una solución única para todas aplicaciones, servicios y dispositivos con el fin de etiquetar y proteger los datos cuando se transfieren dentro y fuera de la organización. <br /><br /> Escenarios de ejemplo: <br />- [Administrar etiquetas de confidencialidad para aplicaciones de Office](sensitivity-labels-office-apps.md) <br />- [Cifrar documentos y correos electrónicos](encryption-sensitivity-labels.md) <br />-  [Aplicar y ver etiquetas en Power BI](/power-bi/admin/service-security-apply-data-sensitivity-labels) <br /><br /> Para obtener una lista completa de escenarios de etiquetas de confidencialidad, vea la documentación de Introducción.|[Introducción a las etiquetas de confidencialidad](get-started-with-sensitivity-labels.md) |
|[Cliente de etiquetado unificado de Azure Information Protection](/azure/information-protection/rms-client/aip-clientv2)| Para equipos Windows, amplía el etiquetado a Explorador de archivos y PowerShell, con características adicionales para las aplicaciones de Office si es necesario| [Guía del administrador para cliente de etiquetado unificado de Azure Information Protection ](/azure/information-protection/rms-client/clientv2-admin-guide)|
|[Cifrado de doble clave](double-key-encryption.md)| Bajo cualquier circunstancia, solo su organización podrá descifrar el contenido protegido o para requisitos normativos, debe mantener las claves de cifrado en un límite geográfico. | [Implementar el cifrado de doble clave](double-key-encryption.md#deploy-dke)|
|[Cifrado de mensajes de Office 365 (OME)](ome.md)| Cifra los mensajes de correo electrónico y los documentos adjuntos que se envían a cualquier usuario en cualquier dispositivo, de modo que solo los destinatarios autorizados puedan leer la información de correo electrónico. <br /><br />  Escenario de ejemplo: [Revocar el correo electrónico cifrado mediante el Cifrado de mensajes avanzado](revoke-ome-encrypted-mail.md) | [Configurar las nuevas capacidades de cifrado de mensajes](set-up-new-message-encryption-capabilities.md)|
|[Cifrado de servicio con clave de cliente](customer-key-overview.md) | Protege frente a la visualización de los datos por parte de sistemas o personal no autorizado y complementa el cifrado de disco BitLocker en centros de datos de Microsoft. | [Configurar clave de cliente de Office 365](customer-key-set-up.md)|
|[Information Rights Management (IRM) de SharePoint](set-up-irm-in-sp-admin-center.md#irm-enable-sharepoint-document-libraries-and-lists)|Protege las listas y bibliotecas de SharePoint para que, cuando un usuario desproteja un documento, el archivo descargado esté protegido, de modo que solo los usuarios autorizados puedan ver y usar el archivo en función de las directivas que usted especifique. | [Configurar Information Rights Management (IRM) en el Centro de administración de SharePoint](set-up-irm-in-sp-admin-center.md)|
[Conector de administración de derechos](/azure/information-protection/deploy-rms-connector) |Modo de solo protección para implementaciones locales existentes que usan Exchange o SharePoint Server, o servidores de archivos que ejecutan Windows Server y la Infraestructura de Clasificación de Archivos (FCI). | [Pasos para implementar el conector RMS](/azure/information-protection/deploy-rms-connector#steps-to-deploy-the-rms-connector)
|[Escáner de etiquetas unificadas de Azure Information Protection](/azure/information-protection/deploy-aip-scanner)| Descubre, etiqueta y protege la información confidencial que reside en almacenes de datos locales. | [Configuración e instalación del escáner de etiquetas unificado de Azure Information Protection](/azure/information-protection/deploy-aip-scanner-configure-install)|
|[Microsoft Defender for Cloud Apps](/cloud-app-security/what-is-cloud-app-security)| Descubre, etiqueta y protege la información confidencial que reside en almacenes de datos en la nube. | [Descubrir, clasificar, etiquetar y proteger la información regulada y confidencial almacenada en la nube](/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|[Mapa de datos de Microsoft Purview](/azure/purview/overview) |Identifica los datos confidenciales y aplica el etiquetado automático al contenido de los recursos de Mapa de datos de Microsoft Purview. Estos incluyen archivos en el almacenamiento, como Azure Data Lake y Azure Files, y datos esquematizados como columnas en Azure SQL DB y Cosmos DB. |[Etiquetado en el mapa de datos de Microsoft Purview](/azure/purview/create-sensitivity-label) |
|[SDK de Microsoft Information Protection](/information-protection/develop/overview#microsoft-information-protection-sdk)|Amplía las etiquetas de confidencialidad a los servicios y aplicaciones de terceros. <br /><br />  Escenario de ejemplo: [Establecer y obtener una etiqueta de confidencialidad (C++)](/information-protection/develop/quick-file-set-get-label-cpp) |[Instalación y configuración del SDK de Microsoft Information Protection (MIP)](/information-protection/develop/setup-configure-mip)|


## <a name="prevent-data-loss"></a>Prevenir la pérdida de datos

Para ayudar a evitar el uso compartido accidental de información confidencial, utilice las funciones siguientes:


|Funcionalidad|¿Qué problemas se solucionan?|Introducción|
|:------|:------------|:---------------------|
|[Prevención de pérdida de datos de Microsoft Purview](dlp-learn-about-dlp.md)| Permite evitar el uso compartido no intencionado de elementos confidenciales. | [Introducción a la directiva predeterminada de DLP](get-started-with-the-default-dlp-policy.md)|
|[Prevención de perdida de datos en el punto de conexión](endpoint-dlp-learn-about.md)| Amplía las capacidades de DLP a los elementos que se usan y comparten en equipos con Windows 10. | [Introducción a la prevención de pérdida de datos en punto de conexión](endpoint-dlp-getting-started.md)|
|[Extensión de cumplimiento de Microsoft](dlp-chrome-learn-about.md) | Amplía las capacidades de DLP al explorador Chrome. | [Introducción a la extensión de cumplimiento de Microsoft](dlp-chrome-get-started.md)|
|[Examinador de prevención de pérdida de datos local de Microsoft Purview (versión preliminar)](dlp-on-premises-scanner-learn.md)|Extiende la supervisión de DLP de las actividades de archivos y las acciones de protección de esos archivos a recursos compartidos de archivos locales y bibliotecas de documentos y carpetas de SharePoint.|[Introducción al examinador de prevención de pérdida de datos locales de Microsoft Purview (versión preliminar)](dlp-on-premises-scanner-get-started.md)|
|[Proteger la información confidencial en mensajes de chat y canales de Microsoft Teams](dlp-microsoft-teams.md) | Amplía algunas funciones de DLP a los mensajes de canal y chat de Teams | [Obtenga información sobre la directiva de prevención de pérdida de datos predeterminada en Microsoft Teams (versión preliminar)](dlp-teams-default-policy.md)|

## <a name="licensing-requirements"></a>Requisitos de licencias

Los requisitos de licencia de Microsoft Purview Information Protection dependen de los escenarios y características que use, en lugar de establecer los requisitos de licencia para cada funcionalidad que se muestra en esta página. Para comprender los requisitos de licencia y las opciones de Microsoft Purview Information Protection, consulte las secciones **Information Protection** de la [Guía de seguridad y cumplimiento de Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance) y las [descargas de PDF](https://go.microsoft.com/fwlink/?linkid=2139145) relacionados para los requisitos de licencia de nivel de característica.
