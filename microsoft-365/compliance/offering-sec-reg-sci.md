---
title: Securities and Exchange Commission-Commission Compliance and Integrity Systems (SCI)
description: Las reglas de SCI se aplican a las entidades de SCI, que incluyen organizaciones de autoreglamentación (SROs) como intercambios de valores y opciones, agencias de compensación registradas y sistemas comerciales alternativos (ATSs).
keywords: Microsoft 365, cumplimiento, ofertas
localization_priority: None
ms.prod: Microsoft-365-enterprise
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
ms.openlocfilehash: e2b314934a51c16ab4e907b7d9f6208e7de21641
ms.sourcegitcommit: 7f307b4f583b602f11f69adae46d7f3bf6982c65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2020
ms.locfileid: "44065715"
---
# <a name="securities-and-exchange-commission-regulation-systems-compliance-and-integrity-sci"></a>Securities and Exchange Commission: el Reglamento de cumplimiento e integridad de sistemas (SCI)

## <a name="about-regulation-sci"></a>Acerca de la reglamentación SCI

La Comisión US Securities and Exchange Commission (SEC) es una agencia independiente del gobierno federal de Estados Unidos y el supervisor principal y el regulador de los mercados de valores de los Estados Unidos. Maneja la autoridad de cumplimiento sobre las leyes federales de valores, propone nuevas reglas de valores y supervisa la reglamentación del mercado de la industria de valores.

En noviembre de 2014, la SEC adoptó el [Reglamento de cumplimiento e integridad de sistemas (SCI)](https://www.sec.gov/rules/final/2014/34-73639.pdf) (y el formulario SCI para informar de eventos SCI) para reforzar la infraestructura tecnológica en los mercados de valores de los Estados Unidos. El Reglamento está diseñado para reducir la frecuencia de las interrupciones del sistema, mejorar la resistencia cuando se produzcan dichos incidentes y aumentar la supervisión de la SEC de la tecnología del mercado de los valores y la aplicación de sus regulaciones.

Las reglas de SCI se aplican a las entidades de SCI, que incluyen organizaciones de autoreglamentación (SROs) como intercambios de valores y opciones, agencias de compensación registradas y sistemas comerciales alternativos (ATSs). Las reglas principalmente regulan los sistemas que admiten directamente las funciones clave del mercado de valores: comercio, holgura y liquidación, enrutamiento de pedidos, datos de mercado, Reglamento de mercado y vigilancia del mercado.

## <a name="microsoft-and-sec-regulation-sci"></a>Microsoft y la SEC normativa SCI

La Comisión US Securities and Exchange Commission (SEC) adoptó la regla SCI para fortalecer la infraestructura tecnológica de las organizaciones financieras que operan y respaldan los mercados de valores de los Estados Unidos. En supervisión de la SEC, sus requisitos están diseñados para garantizar que estos sistemas tienen alta disponibilidad, resistencia segura y baja latencia (gran volumen de mensajes con poco retraso).

Para ayudar a los clientes de servicios financieros de Estados Unidos que deben cumplir con el presente Reglamento, Microsoft ha publicado la guía de implementación de la [nube de integridad y cumplimiento de sistemas de Microsoft Azure en el cumplimiento normativo](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=a69ce0c1-7b7e-44e9-9143-867241e6b2f9&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_FAQ_and_White_Papers). La guía de este documento:

- Proporciona una introducción a las funciones generales de Azure que admiten una resistencia sólida, alta disponibilidad y baja latencia.
- Deja claro qué áreas de control y aspectos normativos de Azure se redirigen. Esta asignación punto a punto de las características y los servicios de Azure a los requisitos de SCI mide el cumplimiento de Azure frente al marco normativo. También ayuda a los clientes a comprender dónde pueden cambiar las responsabilidades de seguridad a Azure y que tienen una propiedad completa cuando se operaban de forma local. Estas funcionalidades están respaldadas por las promesas que Microsoft realiza en los SLAs de Azure.
- Especifica cada requisito de solución de la ciencia que es la responsabilidad del cliente de afrontar y ofrece documentación y servicios de Azure para ayudarlos a abordar estas responsabilidades.

En este documento se proporciona una lista de comprobación completa de las áreas de enfoque de la ciencia de la reglamentación crítica. Esta lista de comprobación ayuda a las organizaciones financieras a adoptar Azure para garantizar que sus reguladores, clientes y liderazgo puedan cumplir con los requisitos normativos aplicables.

## <a name="microsoft-in-scope-cloud-services"></a>Servicios de la nube dentro del alcance de Microsoft

- [Azure](https://aka.ms/AzureCompliance)

## <a name="how-to-implement"></a>Cómo implementar

- [Guía de implementación](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=a69ce0c1-7b7e-44e9-9143-867241e6b2f9&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_FAQ_and_White_Papers)de la regla de SCI: asigna las capacidades de Azure en comparación con el Reglamento y detalla la responsabilidad compartida del cumplimiento.
- [Diseño de aplicaciones confiables de Azure](https://docs.microsoft.com/azure/architecture/resiliency/): breve introducción sobre cómo crear confiabilidad en cada paso del diseño de la aplicación de Azure.
- [Diseño de aplicaciones de alta disponibilidad](https://docs.microsoft.com/azure/storage/common/storage-designing-ha-apps-with-ragrs): cómo los desarrolladores pueden ayudar a garantizar que sus aplicaciones de almacenamiento de Azure estén altamente disponibles.
- [Guía de cumplimiento y evaluación de riesgos](https://aka.ms/RiskGovernanceGuide): Cree un modelo de gobierno para la evaluación de riesgos de los servicios en la nube de Microsoft y las notificaciones reglamentarias.

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

**¿Qué significa la responsabilidad compartida cuando se usa la tecnología de nube?**

A medida que los entornos informáticos se mueven de los centros de trabajo locales a los de la nube, la responsabilidad de la seguridad también cambia: el proveedor de servicios en la nube (CSP) y el cliente ahora comparten esa responsabilidad. Para cada aplicación y solución, qué parte de esa responsabilidad recae en el cliente y qué parte del CSP depende del modelo de Azure que implementa un cliente (IaaS, SaaS o PaaS). Es el derecho del cliente comprender en qué grado son responsables de implementar los controles de seguridad necesarios. Sin embargo, Microsoft proporciona instrucciones para ayudar a los clientes a navegar por esta compleja compleja. Para obtener más información, vea [responsabilidades compartidas para la informática en la nube](https://gallery.technet.microsoft.com/Shared-Responsibilities-81d0ff91).

**¿Qué instituciones financieras pueden aprovechar Azure para cumplir con los requisitos de la regla SCI?**

Las organizaciones financieras o las entidades de SCI que están sujetas a este Reglamento pueden implementar Azure. La SEC indica que su reglamentación se aplica a las organizaciones que se aplican a sí mismas (SROs), incluidos los intercambios de cotizaciones y opciones, las agencias de compensación registradas, el FINRA y el MSRB, los sistemas comerciales alternativos (ATSs), que son de las poblaciones comerciales y las poblaciones no NMS que superan los umbrales de volumen especificados, así

## <a name="resources"></a>Recursos

- [Respuestas de la SEC a preguntas más frecuentes referentes a la reglamentación SCI](https://www.sec.gov/divisions/marketreg/regulation-sci-faq.shtml)
- [Continuidad empresarial y recuperación ante desastres (BCDR): regiones emparejadas de Azure](https://docs.microsoft.com/azure/best-practices-availability-paired-regions)
- [Mapa de cumplimiento de los principios normativos de informática en la nube y Microsoft Online Services](https://aka.ms/FinServ-Guide-US)
- [Programa de cumplimiento de servicios financieros en la nube de Microsoft](https://aka.ms/FSCP-Print)
- [Cumplimiento de los servicios financieros en Azure](https://aka.ms/FinServ-Compliance-Azure)
- [Servicios financieros de Microsoft](https://aka.ms/FinServ-Compliance)
- [Microsoft y reglas de la SEC 17a-4](offering-SEC-17a-4.md)
- [Cumplimiento en el Centro de Confianza de Microsoft](https://www.microsoft.com/trust-center/compliance/compliance-overview)
