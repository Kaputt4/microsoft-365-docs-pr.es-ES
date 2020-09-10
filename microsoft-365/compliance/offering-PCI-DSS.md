---
title: Estándar de seguridad de los datos (DSS) de la industria de tarjetas de pago (PCI)
description: Azure, SharePoint Online y OneDrive para la Empresa cumplen con los estándares de seguridad de los datos de la industria de tarjetas de pago Nivel 1, versión 3.2.
keywords: Microsoft 365, cumplimiento, ofertas
localization_priority: Priority
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: ad755398afc80f829561854217f1295ce8fff6f5
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2020
ms.locfileid: "47417864"
---
# <a name="payment-card-industry-pci-data-security-standard-dss"></a>Estándar de seguridad de los datos (DSS) de la industria de tarjetas de pago (PCI)

## <a name="pci-dss-overview"></a>Información general del DSS PCI 

Los estándares de seguridad de datos (DSS) de la industria de tarjetas de pago (PCI) son un estándar global de seguridad de la información diseñado para evitar el fraude mediante un aumento en el control de datos de las tarjetas de crédito. Organizaciones de todos los tamaños deben seguir las normativas del DSS PCI si aceptan tarjetas de pago de las cinco marcas de tarjetas de crédito más grandes: Visa, MasterCard, American Express, Discover y Japan Credit Bureau (JCB). El cumplimiento con el DSS PCI es necesario para cualquier organización que almacene, procese o transmita datos de pago y de titulares de tarjetas.

## <a name="microsoft-and-pci-dss"></a>Microsoft y el DSS PCI 

Microsoft ha completado una evaluación anual del DSS PCI mediante un asesor de seguridad certificado aprobado (QSA). Los auditores revisaron entornos de Microsoft Azure, Microsoft OneDrive para la Empresa y Microsoft SharePoint Online, lo que abarcó la validación de la infraestructura, el desarrollo, las operaciones, la administración, el soporte técnico y los servicios en el ámbito. El DSS PCI designa cuatro niveles de cumplimiento basados en el volumen de transacciones. Azure, OneDrive para la Empresa y SharePoint Online están certificados como compatibles con la versión 3.2 del DSS PCI en el Nivel 1 de proveedor de servicios (el mayor volumen de transacciones: más de 6 millones al año).

La evaluación da como resultado una Atestación de Cumplimiento (AoC), que está disponible para los clientes y el Informe sobre el Cumplimiento (RoC) emitido por el QSA. El período de vigencia para el cumplimiento empieza al pasar la auditoría y recibir el AoC del asesor y finaliza un año después de la fecha en la que se firmó el AoC. 

Los clientes que quieran desarrollar un entorno de titulares de tarjetas o un servicio de procesamiento de tarjetas pueden usar estas validaciones en muchas de las partes subyacentes y, por lo tanto, reducir el esfuerzo y los costos asociados a la obtención de su propia certificación del DSS PCI.

Es importante entender que el estado de cumplimiento del DSS PCI para Azure, OneDrive para la Empresa y SharePoint Online no se traduce automáticamente en la certificación PCI DSS para los servicios que los clientes crean u hospedan en estas plataformas. Los clientes son responsables de garantizar que se logre cumplir con los requisitos del DSS PCI.

## <a name="microsoft-in-scope-cloud-services"></a>Servicios en la nube de Microsoft en el ámbito

- [Azure y Azure Government](https://aka.ms/AzureCompliance)
- Microsoft Cloud App Security
- El servicio de nube de Flow como servicio independiente o incluido en un plan o conjunto de aplicaciones de Office 365 o Dynamics 365
- Microsoft Graph
- Intune
- [Protección contra amenazas avanzada de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- El servicio de nube de PowerApps como servicio independiente o incluido en un plan o conjunto de aplicaciones de Office 365 o Dynamics 365
- El servicio de nube de Power BI como servicio independiente o incluido en un plan o conjunto de aplicaciones de Office 365
- OneDrive para la Empresa y SharePoint Online (solo Estados Unidos)

## <a name="audit-reports-and-certificates"></a>Auditorías, informes y certificados

- [Atestación de Cumplimiento (AoC) del DSS PCI de Azure](https://aka.ms/azure-pci)
- [Atestación de Cumplimiento (AoC) del DSS PCI de OneDrive para la Empresa y SharePoint Online](https://aka.ms/spo-pci)

## <a name="get-your-pci-dss-solution-running-on-azure"></a>Obtenga la solución DSS PCI ejecutándose en Azure

Cree e implemente la solución DSS PCI en la nube de forma más rápida con el Plano técnico de seguridad y cumplimiento de Azure para DSS PCI. Obtenga arquitecturas de referencia, instrucciones de implementación, asignaciones de control de implementación, scripts automatizados y mucho más. [Empezar a usar el Plano técnico de Azure para el DSS PCI](https://aka.ms/pciblueprint).

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

**¿Por qué la Atestación de Cumplimiento normativo (AoC) dice "junio de 2018"?**

La fecha de junio de 2018 en la portada es de cuando se publicó la plantilla AoC. Consulte la sección 2 para ver la fecha de la evaluación.

**¿Por qué hay varias Atestaciones de Cumplimiento (AoCs) de Azure ?**

El paquete Azure AoC tiene AoCs correspondientes a Azure público, Alemania y la nube de administración pública. Los clientes deben usar el AoC que se corresponda sus entornos de Azure.  

**¿Cuál es la relación entre el DSS PA y el DSS PCI **

El Estándar de seguridad de datos para las aplicaciones de pago (DSS PA) es un conjunto de requerimientos que cumplen con el DSS PCI, que reemplaza a las Mejores prácticas para las aplicaciones de pagos de Visa y consolida los requerimientos de cumplimiento de los otros emisores principales de tarjetas. El PA DSS ayuda a los proveedores de software a desarrollar aplicaciones de terceros que almacenan, procesan o transmiten datos de pago del titular de la tarjeta como parte de un proceso de autorización o liquidación de tarjeta. Los distribuidores deben usar aplicaciones certificadas con el DSS PA para lograr el cumplimiento eficaz de su DSS PCI. El PA DSS no es aplicable a Azure.

**¿Qué es un adquiriente y Azure usa uno?**

Un adquirente es un banco u otra entidad que procesa transacciones con tarjetas de pago. Azure no ofrece el procesamiento de tarjetas de pago como servicio y, por lo tanto, no usa una empresa adquirente.

**¿A qué organizaciones y comerciantes se aplica el DSS PCI ?**

El DSS PCI se aplica a cualquier empresa, independientemente del tamaño o el número de transacciones, que acepte, transmita o almacene los datos de los titulares de la tarjeta. Es decir, si un cliente paga con una tarjeta de crédito o débito a una empresa en alguna ocasión, se aplicarán los requisitos del DSS PCI. Las empresas se validan en uno de los cuatro niveles, basándose en el volumen de transacciones totales durante un período de 12 meses. El nivel 1 es para las empresas que procesan más de 6 millones de transacciones al año; el nivel 2 para 1 millón a 6 millones de transacciones; el nivel 3 es para transacciones entre 20.000 a 1 millón y el nivel 4 es de menos de 20.000 transacciones.

**¿Dónde puedo empezar los esfuerzos de cumplimiento del DSS PCI de mi organización para una solución implementada en Azure?**

La información que proporciona el Consejo sobre Normas de Seguridad de la PCI es un buen punto de partida para obtener más información sobre los requisitos de cumplimiento específicos. El Consejo publica la [Guía de referencia rápida del DSS PCI](https://www.pcisecuritystandards.org/documents/PCISSC%20QRG%20August%202014%20-print.pdf) para comerciantes y otros involucrados en el procesamiento de tarjetas de pago. En la guía se explica cómo el DSS PCI puede ayudar a proteger un entorno de transacciones con tarjetas de pago y cómo aplicarlo.

El cumplimiento implica varios factores, entre los que se incluyen la evaluación de sistemas y procesos que no se hospedan en Azure. Los requisitos individuales varían en función de los servicios de Azure que se usan y de cómo se emplean dentro de la solución.

**¿Hay planes para que OneDrive para la Empresa y SharePoint Online sean compatibles con el DSS PCI fuera de Estados Unidos?**

Actualmente OneDrive para la Empresa y SharePoint Online solo son compatibles con PCI DSS dentro de Estados Unidos (US). Microsoft evaluará los requisitos y plazos para las regiones fuera de Estados Unidos y ofrecerá actualizaciones en caso de que se agreguen otras regiones al plan de desarrollo.

**¿Qué abarcan OneDrive para la Empresa y SharePoint Online?**

En la actualidad, solo los archivos y documentos cargados en OneDrive para la Empresa y SharePoint Online serán compatibles con el DSS PCI.

## <a name="resources"></a>Recursos

- [Consejo sobre Normas de Seguridad de la PCI](https://www.pcisecuritystandards.org/)
- [Estándar de seguridad de datos PCI](https://www.pcisecuritystandards.org/documents/PCI_DSS_v3-1.pdf)
- [Plano técnico de Azure para el DSS PCI 3.2.1](https://docs.microsoft.com/azure/governance/blueprints/samples/pci-dss-3.2.1/)
- [Guía de referencia rápida del DSS PCI](https://www.pcisecuritystandards.org/documents/PCISSC%20QRG%20August%202014%20-print.pdf)
- [Cumplimiento en el centro de confianza de Microsoft ](https://www.microsoft.com/trust-center/compliance/compliance-overview)
