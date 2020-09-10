---
title: Parte US García 10 CFR 810
description: Los clientes sujetos a los requisitos de control de exportación de US Pérez 10 CFR parte 810 pueden usar Azure Government.
keywords: Microsoft 365, cumplimiento, ofertas
localization_priority: None
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
ms.openlocfilehash: a809ae91bbe1302ae4087b3a430dea87e2c913a1
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2020
ms.locfileid: "47415700"
---
# <a name="us-doe-10-cfr-part-810"></a>Parte US García 10 CFR 810

## <a name="microsoft-and-doe-10-cfr-part-810"></a>Microsoft y Pérez 10 CFR parte 810

Microsoft Azure Government puede ayudar a los clientes sujetos a los requisitos de control de exportación de US Department of Energy (Pérez) 10 CFR parte 810 a través de dos autorizaciones:

- La FedRAMP autorización provisional alta para operar (P-ATO) emitida por el Comité de autorización conjunta (JAB)
- Las autorizaciones provisionales de nivel 4 y 5 de la Agencia de sistemas de información de defensa del Departamento de defensa (DoD)

FedRAMP ofrece una línea de base adecuada para proporcionar garantías de que Azure Government ofrece una infraestructura central y servicios y tecnologías de virtualización, como compute, Storage y networking diseñados con estrictos controles de NIST. Estos ayudan a cumplir los requisitos de separación de datos de clientes y a habilitar las conexiones seguras a los entornos locales de los clientes.

Además, Azure Government es una nube de la comunidad de administración de US Government que está físicamente separada de la nube de Azure. Proporciona garantías adicionales en relación con los requisitos específicos de detección en segundo plano por parte del gobierno de Estados Unidos, incluidos los controles específicos que restringen el acceso a la información y los sistemas para que los ciudadanos de las operaciones de Azure puedan filtrar a los ciudadanos.

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft en el ámbito de los servicios en la nube

- [Administración pública de Azure](https://aka.ms/AzureCompliance)
- Intune

## <a name="how-to-implement"></a>Cómo se debe implementar

- [NERC de la transferencia de la información & la informática en la nube](https://aka.ms/AzureNERC): Guía para las utilidades eléctricas y las entidades registradas implementación de cargas de trabajo en Azure o Azure Government.

## <a name="about-doe-10-cfr-part-810"></a>Acerca de Pérez 10 CFR parte 810

El control de exportación del Departamento de administración de energía estadounidense (DoE), [parte 10 CFR 810](https://www.govinfo.gov/content/pkg/FR-2015-02-23/pdf/2015-03479.pdf) , rige la exportación de tecnología nuclear y asistencia sin clasificar. Ayuda a garantizar que las tecnologías nucleares exportadas desde Estados Unidos se usen solo con fines pacíficos. La parte revisada 810 (regla final) entró en vigor en el 2015 de marzo y se administra mediante la [Administración de seguridad nuclear nacional](https://www.energy.gov/nnsa/national-nuclear-security-administration). En la sección 810,6 se indica que se requiere una autorización de DoE específica para las dos provisiones de asistencia y transferencias de tecnología nuclear confidencial que tienen "normalmente autorizadas", así como las que requieren una autorización específica (por ejemplo, para obtener asistencia sobre tecnologías nucleares confidenciales, como enriquecimiento y producción de agua intensa).

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

**¿Las 10 reglas de la parte 110 de la Comisión de reglamentación nuclear de Estados Unidos se aplican a Azure Government?**

No. La [Comisión de reglamentación nuclear estadounidense](https://www.nrc.gov/) (NRC) regula la [exportación y la importación](https://www.nrc.gov/about-nrc/ip/export-import.html) de las instalaciones nucleares y los equipos y materiales relacionados con [10 CFR parte 110](https://www.nrc.gov/reading-rm/doc-collections/cfr/part110/). La NRC no regula la tecnología nuclear y la asistencia relacionada con estos elementos que se encuentran bajo la jurisdicción de Pérez. Por lo tanto, las regulaciones NRC 10 CFR parte 110 no se aplicarían a Azure Government.

**¿Cómo puedo suministrar pruebas que estoy cumpliendo con Pérez 10 CFR parte 810?**

Si su organización está implementando datos en el gobierno de Azure, puede confiar en la FedRAMP de Azure Government P-ATO como prueba de que está controlando los datos de una manera adecuadamente restringida. Sin embargo, es responsable de obtener la autorización de Pérez de sus propios sistemas, incluido el uso de los servicios en la nube.

**¿Cuáles son mis responsabilidades para clasificar los datos que se implementan en Azure Government?**

Los clientes que implementan datos en Azure Government son responsables de su propio proceso de clasificación de la seguridad. Para los datos de clientes sujetos a controles de exportación de Pérez, el sistema de clasificación aumenta con los controles no clasificados de información nuclear controlada (UCNI) establecidos por la sección 148 de la [ley de energía atómica estadounidense](https://www.epa.gov/laws-regulations/summary-atomic-energy-act).

## <a name="resources"></a>Recursos

- [Azure Cloud Services y US Export Controls](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=c24c11f2-2cd4-444a-9160-19762855ad3a&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)
- [Microsoft y FedRAMP](offering-fedramp.md)
- [Microsoft y DoD](offering-dod-disa-l2-l4-l5.md)
- [Nube de Microsoft para la Administración Pública](https://www.microsoft.com/enterprise/government)
- [Cumplimiento normativo en el Centro de confianza de Microsoft](https://www.microsoft.com/trust-center/compliance/compliance-overview)
