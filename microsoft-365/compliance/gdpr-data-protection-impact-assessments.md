---
title: Evaluaciones de impacto en la protección de datos
description: Estos documentos proporcionan a los poseedores de los datos información que les permitirá determinar si se necesita un EIPD y, en ese caso, qué detalles incluir.
keywords: Evaluación de impacto en la protección de datos, EIPD, Dynamics 365, Servicios profesionales de Microsoft, Microsoft 365, documentación de Microsoft 365, RGPD
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 0a62cf2ef40bbf9da219309cf75eed27ea8739e4
ms.sourcegitcommit: 2498cd4af90c31771167a1be9f8f12a96dc6500f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2020
ms.locfileid: "41916905"
---
# <a name="data-protection-impact-assessment-for-the-gdpr"></a>Evaluación de impacto de la protección de datos para el RGPD

El Reglamento General de Protección de Datos (RGPD) añade nuevas normas para organizaciones que ofrecen bienes y servicios a los ciudadanos de la Unión Europea (UE) o que recopilan y analizan datos de los residentes de la UE, independientemente de donde estén ubicados usted o su empresa. Puede encontrar más información en el [tema de resumen del RGPD](gdpr.md). Este documento le guiará por la información relativa a la Evaluación de Impacto de Protección de Datos (EIPD) de conformidad con el RGPD al utilizar productos y servicios de Microsoft.

## <a name="terminology"></a>Terminología

Definiciones útiles de los términos del RGPD utilizados en este documento:

- *Controlador de datos (controlador)*: una persona jurídica, autoridad pública, agencia u otro organismo, que por sí solos o conjuntamente con otras personas, determinan el propósito y el medio del procesamiento de datos personales.  
- *Datos personales * e *interesado*: cualquier información relacionada con una persona física identificada o una persona natural identificable (interesado), una persona física identificable es la que puede identificarse, directa o indirectamente.  
- *Procesador*: una persona física o jurídica, entidad pública, agencia u otro organismo que procese datos personales en nombre del controlador.  
- *Datos de clientes*: datos producidos y almacenados en las operaciones diarias de su empresa.

## <a name="what-is-a-dpia"></a>¿Qué es una EIPD?

El Reglamento General de Protección de Datos (RGPD) exige a los controladores de datos que elaboren una evaluación de impacto de la protección de datos (EIPD) para las operaciones que sea "probable que resulten en un alto riesgo para los derechos y libertades de las personas físicas". No hay nada inherente a los productos y servicios de Microsoft que necesitan la creación de un evaluación de impacto de la protección de datos (EIPA). Sin embargo, dado que los productos y servicios de Microsoft son muy personalizables, es posible que se necesite una EIPD en función de las características de su configuración de Microsoft. Microsoft no controla esta información y tiene muy poco o ningún conocimiento sobre ella. Usted, como controlador de los datos, debe determinar los usos adecuados de sus datos.

## <a name="dpia-in-action"></a>La EIPD en acción

La guía de EIPD se aplica a los servicios profesionales y de soporte técnico de Office 365, Azure, Dynamics 365 y Microsoft. Esta guía presenta incluye consideraciones sobre:

**¿Cuándo se necesita una EIPD?**

Al considerar si se realiza una EIPD, se deben tratar los factores de riesgo que aparecen a continuación. En la primera parte de cada una de las instrucciones se encuentran otros factores potenciales y detalles adicionales.  

- Una evaluación sistemática y extensa de los datos basada en el procesamiento automatizado.  
- Procesamiento a gran escala de categorías especiales de datos (datos que revelan información unívoca para la identificación de una persona física) o de datos personales relativos a delitos y condenas penales.
- Supervisión sistemática a gran escala de un área de acceso público.

El RGPD aclara que: "El tratamiento de datos personales no debe considerarse a gran escala si lo realiza, respecto de datos personales de pacientes o clientes, un solo médico, otro profesional de la salud o abogado. En estos casos, la evaluación de impacto de la protección de datos no debe ser obligatoria".

**¿Qué se necesita para elaborar una EIPD?**

Una EIPD debe proporcionar información específica sobre el procesamiento previsto, que se detalla en la segunda parte de las instrucciones. Esta información incluye:

- Una evaluación de la necesidad y proporcionalidad del procesamiento de datos en relación con el propósito de EIPD.  
- Una evaluación de los riesgos para los derechos y libertades de las personas físicas.
- Las medidas previstas para abordar los riesgos, las protecciones, las medidas de seguridad y los mecanismos para asegurar la protección de los datos personales y demostrar el cumplimiento del RGPD.
- Finalidades del procesamiento  
- Categorías de datos personales procesados  
- Retención de datos  
- Ubicación y transferencias de datos personales  
- Uso compartido de datos con subprocesadores terceros  
- Uso compartido de datos con terceros independientes  
- Derechos del titular de los datos

## <a name="additional-considerations"></a>Consideraciones adicionales

A continuación, se muestran detalles específicos que pueden ser relevantes para su implementación de Microsoft.

- [Office 365](gdpr-dpia-office365.md): este documento se aplica a aplicaciones y servicios de Office 365, entre los que se incluyen, entre otros, Exchange Online, SharePoint Online, Yammer, Skype Empresarial y Power BI. Consulte las tablas [1](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365#part-1--determining-whether-a-dpia-is-needed) y [2](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365#part-2--contents-of-a-dpia) para obtener más información.  
- [Azure](gdpr-dpia-azure.md): Se recomienda a los clientes que trabajen con sus responsables de privacidad y asesores legales para determinar la necesidad y el contenido de cualquier EIPD relacionada con su uso de Microsoft Azure.  
- [Dynamics 365](gdpr-dpia-dynamics.md): el contenido de una EIPD puede variar en función de las herramientas de Dynamics 365 que utilice. Para obtener detalles específicos, consulte el [contenido de la segunda parte de una EIPD](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-dynamics#part-2--contents-of-a-dpia).
- [Professional Services y Soporte Técnico de Microsoft](gdpr-dpia-prof-services.md): Professional Services no lleva a cabo ciertos procesos de procesamiento de datos y rutinas automatizadas, ni tampoco está diseñado para procesar categorías especiales ni realizar tareas que faciliten o requieran la monitorización de datos de acceso público. Para más detalles, consultar [Parte 1: determinar si se necesita una EIPD](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-prof-services#part-1--determining-whether-a-dpia-is-needed) Los controladores deben tener en cuenta los elementos de la EIPD descritos arriba, además de cualquier otro factor relevante, en el contexto de las implementaciones específicas del controlador y el uso de Professional Services. Para obtener información sobre Professional Services, consulte [Parte 2: contenido de una EIPD](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-prof-services#part-2--contents-of-a-dpia).

## <a name="learn-more"></a>Más información

- [Centro de confianza de Microsoft](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
