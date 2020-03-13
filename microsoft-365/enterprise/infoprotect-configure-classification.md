---
title: 'Paso 2: Configurar la clasificación para el entorno'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda y configure varias formas de clasificar los datos de su organización.
ms.openlocfilehash: e8c40ca4c419edc2d59a060dfd4fe8918cf4e784
ms.sourcegitcommit: 6c8edbc54b193e964cf93aec48c51cb79231f1d9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2020
ms.locfileid: "42544189"
---
# <a name="step-2-configure-classification-for-your-environment"></a>Paso 2: Configurar la clasificación para el entorno

*Este paso es opcional y es válido para las versiones E3 y E5 de Microsoft 365 Enterprise*

![Fase 6: Protección de la información](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

En este paso, trabajará con los equipos legales y de cumplimiento para definir un esquema de clasificación para los datos de su organización.

## <a name="microsoft-365-classification-types"></a>Tipos de clasificación de Microsoft 365

Microsoft 365 incluye cuatro tipos de clasificación:

- Tipos de información confidencial
- Etiquetas de retención
- Etiquetas de confidencialidad
- Etiquetas y protección de Azure Information Protection

### <a name="sensitive-information-types"></a>Tipos de información confidencial

Los tipos de información confidencial de Microsoft 365 definen cómo procesos automatizados como la búsqueda reconocen tipos específicos de información. Estos incluyen datos confidenciales de empleados o clientes, como números de tarjeta de crédito y de servicio de salud. Se usan los tipos de información confidencial para buscar información confidencial y aplicar reglas y directivas de prevención de pérdida de datos (DLP) para proteger estos datos. Para obtener más información, vea [what a DLP policy contains](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies#what-a-dlp-policy-contains) (qué contiene una directiva DLP). 

Los tipos de información confidencial son especialmente útiles para cumplir los requisitos de cumplimiento y normativa, como en el caso del Reglamento general de protección de datos (RGPD).

### <a name="retention-labels"></a>Etiquetas de retención

Parte de la definición de una estrategia de gobierno de datos es decidir durante cuánto tiempo deben conservarse determinados tipos de documentos o documentos con contenido específico de acuerdo con las directivas de la organización y los reglamentos regionales. Por ejemplo, algunos tipos de documentos se deben conservar durante un tiempo determinado y eliminarse después, mientras que otros deben conservarse indefinidamente.

En el caso de los documentos almacenados en Microsoft 365, puede definir y aplicar etiquetas de retención a los documentos y datos almacenados en el correo electrónico de Exchange, SharePoint Online, OneDrive para la Empresa, y mensajes de canal y de chat de Teams. 

Si usa etiquetas de retención, debe configurar una etiqueta para cada categoría de archivo que deba tener una directiva de retención aplicada. En la etiqueta de retención, puede especificar:

- Un conjunto de descriptores para los archivos (por ejemplo, por departamento de empresa, categoría de archivo o reglamento).
- La configuración de retención de los archivos que tengan la etiqueta de retención asociada, como el tiempo de conservación y el comportamiento tras haberse superado el tiempo de conservación.

También puede aplicar una etiqueta de retención a los archivos automáticamente si configura un sitio de SharePoint Online para aplicar una etiqueta de retención predeterminada a todos los documentos nuevos en el sitio. 

Para obtener más información, vea la [Introducción a las etiquetas de retención](https://docs.microsoft.com/office365/securitycompliance/labels).

### <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

Parte de la protección y la implementación de seguridad para determinados tipos de documentos o documentos con contenido específico consiste en marcarlos con una etiqueta para que pueda aplicar la seguridad adicional. Con las etiquetas de confidencialidad de Microsoft 365, puede:

- Aplicar la configuración de protección como el cifrado, los permisos o la agregación de una marca de agua.
- Usar Endpoint Protection de Windows Information Protection (WIP) para impedir que el contenido se copie en una aplicación de terceros, como Twitter o Gmail, o se copie en unidades de almacenamiento extraíbles, como una unidad USB.
- Proteger el contenido en los servicios y aplicaciones de terceros con Microsoft Cloud App Security (CAS). 
- Clasificar contenido sin usar configuración de protección.

Si usa etiquetas de confidencialidad, debe configurar una etiqueta para cada nivel de protección de información y seguridad. Por ejemplo, cree tres etiquetas de confidencialidad para:

- Línea base
- Confidencial
- Extremadamente regulado

Si almacena archivos con datos altamente regulados en un sitio de SharePoint Online y desea que estos archivos tengan los mismos permisos que el sitio incluso si los archivos abandonan el sitio, debe crear una etiqueta de sensibilidad adicional que tenga los mismos permisos que el sitio.

Para obtener más información, vea [Información general de etiquetas de confidencialidad](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels).

### <a name="azure-information-protection-labels-and-protection"></a>Etiquetas y protección de Azure Information Protection

Puede usar etiquetas de Azure Information Protection para clasificar correos electrónicos y documentos de su organización, y opcionalmente protegerlos. Estas etiquetas se pueden aplicar a los documentos almacenados fuera de Microsoft 365. Las etiquetas pueden aplicarse automáticamente por administradores que definen reglas y condiciones, manualmente por los usuarios o mediante una combinación en la que los usuarios reciben recomendaciones.

Para planear e implementar etiquetas y protección de Azure Information Protection, siga este procedimiento:

1. Revise los [requisitos de Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/requirements).
2. Siga el [mapa de ruta de implementación para clasificación, etiquetado y protección](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).

Para obtener más información, vea la [biblioteca de documentación de Azure Information Protection](https://docs.microsoft.com/information-protection/).

Las etiquetas de confidencialidad funcionan a la perfección con las etiquetas existentes de Azure Information Protection. Por ejemplo, puede mantener sus etiquetas existentes de Azure Information Protection y las etiquetas que se aplican a los documentos y correos electrónicos.

Si tiene etiquetas de confidencialidad y de Azure Information Protection, debe [migrar las etiquetas de Azure Information Protection a las etiquetas de confidencialidad](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels#how-sensitivity-labels-work-with-existing-azure-information-protection-labels).

## <a name="example-classification-for-gdpr"></a>Ejemplo: clasificación para el RGPD

Para obtener un esquema de clasificación de ejemplo que incluye datos personales para el RGPD, consulte [Diseño de un esquema de clasificación de datos personales](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data).

## <a name="take-it-for-a-test-drive"></a>Pruébelo

|||
|:-------|:-----|
|![Guías de laboratorio de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guía del entorno de pruebas: clasificación de datos](data-classification-microsoft-365-enterprise-dev-test-environment.md) |
|||

Como punto de control provisional, vea los [criterios de salida](infoprotect-exit-criteria.md#crit-infoprotect-step2) correspondientes a este paso.

## <a name="next-step"></a>Siguiente paso

|||
|:-------|:-----|
|![Paso 3](../media/stepnumbers/Step3.png)|[Configurar una mayor seguridad para Office 365](infoprotect-configure-increased-security-office-365.md)|

