---
title: Normas para la administración de la exportación de Estados Unidos (EAR)
description: Los servicios en la nube de Microsoft ayudan a los clientes sujetos a la normativa de administración de la exportación estadounidense (EAR) cumplen sus requisitos de cumplimiento y administran el riesgo de control de exportación.
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
ms.openlocfilehash: 4ad12f785a76f6ee733cb3b459ad58370a330f51
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2020
ms.locfileid: "47416066"
---
# <a name="us-export-administration-regulations-ear"></a>Normas para la administración de la exportación de Estados Unidos (EAR)

## <a name="about-the-ear"></a>Acerca de las EAR

El Departamento de comercio de Estados Unidos pone en vigor la normativa de administración de exportación (EAR) a través [de la oficina de la industria y la seguridad (bis)](https://www.bis.doc.gov/). El oído rige en general y impone los controles sobre la exportación y reexportación de la mayoría de los productos, el software y la tecnología comerciales, incluidos los elementos de "doble uso" que se pueden usar tanto para fines comerciales como militares y para determinados elementos de defensa.

La guía de BIS implica que, cuando los datos o el software se cargan en la nube o se transfieren entre nodos de usuario, el cliente, no el proveedor de la nube, es el "exportador" quien tiene la responsabilidad de garantizar que las transferencias, el almacenamiento y el acceso a esos datos o software cumplan con la lengüeta.

[Según el bis](https://www.bis.doc.gov/index.php/documents/regulation-docs/412-part-734-scope-of-the-export-administration-regulations/file), la *exportación* hace referencia a la transferencia de tecnología protegida o datos técnicos a un destino extranjero o su lanzamiento a una persona extranjera en los Estados Unidos (también conocido como una *exportación considerada*). El oído se rige en general:

- Exportaciones de los Estados Unidos.
- Reexporta o retransfiere los elementos de origen de Estados Unidos y determinados elementos de origen externo con más de una parte de *minimis* de contenido de origen de los Estados Unidos.
- Transferencias o divulgaciones a personas de otros países.

Los elementos sujetos a las LENGÜETAs se encuentran en la lista de control de Comercio (CCL) donde cada elemento tiene asignado un [número de clasificación de control de exportación único (ECCN)](https://www.bis.doc.gov/index.php/licensing/commerce-control-list-classification/export-control-classification-number-eccn). Los elementos que no aparecen en la lista de CCL se designan como EAR99 y la mayoría de los productos comerciales de EAR99 no requerirán que se exporte una licencia. Sin embargo, según el destino, el usuario final o el uso final del elemento, incluso un elemento EAR99 puede requerir una licencia de exportación BIS.

La [regla final](https://www.federalregister.gov/documents/2016/06/03/2016-12734/revisions-to-definitions-in-the-export-administration-regulations), publicada en junio de 2016, aclaraba que los requisitos de licencia de oído tampoco se aplicaron a la transmisión y almacenamiento de datos técnicos sin clasificar si se cifraron de un extremo a otro mediante módulos criptográficos basados en FIPS 140-2 y no se almacenaron intencionadamente en un país con embargo militar o en la Federación rusa.

## <a name="microsoft-and-the-ear"></a>Microsoft y las EAR

Las tecnologías, productos y servicios de Microsoft están sujetos a la normativa para la administración de la exportación de Estados Unidos (EAR). Aunque no hay ninguna certificación de cumplimiento para las EAR, los Microsoft Azure, Microsoft Azure Government y Microsoft Office 365 Government (GCCHigh y DoD) ofrecen características y herramientas importantes para ayudar a los clientes elegibles que están sujetos a los oídos a administrar los riesgos de control de exportación y cumplir con los requisitos de cumplimiento.

El Departamento de comercio de Estados Unidos, que exige el oído, ha tomado la posición de que los clientes, no los proveedores de servicios de nube como Microsoft, sean exportadores de sus propios datos de clientes. Si bien la mayoría de los datos de los clientes no se consideran "tecnológicos" o "datos técnicos" sujetos a EAR controles de exportación, los servicios en la nube de Microsoft en el ámbito están estructurados para ayudar a los clientes a administrar y mitigar considerablemente los posibles riesgos de control de exportación a los que se enfrentan. Microsoft generalmente, pero no exclusivamente, recomienda el uso de los servicios de nube de administración pública para clientes elegibles. Con una planificación adecuada, los clientes pueden usar las siguientes herramientas y sus propios procedimientos internos para ayudar a garantizar el total cumplimiento con los controles de exportación de los Estados Unidos.

- **Controles en la ubicación de datos**. Los clientes tienen visibilidad sobre dónde se almacenan los datos y el acceso a herramientas sólidas para restringir su almacenamiento. Por lo tanto, pueden garantizar que sus datos se almacenan en los Estados Unidos y minimizar la transferencia de la tecnología controlada o datos técnicos fuera de los Estados Unidos. Además, los datos de los clientes no se almacenan en una ubicación que no sea conforme, de acuerdo con las prohibiciones de las personas en las que los datos se almacenan de forma intencionada: ningún centro de datos de Azure se encuentra en ninguno de los 25 países D:5 de grupo o en la Federación rusa.
- **Cifrado de un extremo a otro**. Al aprovechar el puerto seguro de cifrado de extremo a extremo para ubicaciones de almacenamiento físico especificadas en las EAR, los servicios de nube de Microsoft en el ámbito proporcionan características de cifrado que pueden ayudar a protegerse contra los riesgos de control de la exportación. También ofrecen a los clientes una [amplia variedad de opciones para cifrar datos](https://aka.ms/Azure-Encryption-Overview) en tránsito y en reposo, así como la flexibilidad para elegir entre las opciones de cifrado.
- **Herramientas y protocolos para impedir la exportación no autorizada considerada**. El uso de cifrado también ayuda a proteger contra una Exportación posible (o reexportación considerada) bajo el oído, porque incluso si una persona no estadounidense tiene acceso a datos cifrados, no se revela nada si no pueden leer o comprender los datos mientras están cifrados; por lo tanto, no hay una "versión" de datos controlados.

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft en el ámbito de los servicios en la nube

- [Azure y Azure Government](https://aka.ms/AzureCompliance)
- [Office 365 Government (GCC-High y DoD)](https://aka.ms/Office-365-Export-Controls)
- Intune

## <a name="how-to-implement"></a>Cómo se debe implementar

Overview of US Export Controls and Guidance for customers Evaluating The astinas The EAR.

- [Azure](https://aka.ms/Azure-Export-Controls)
- [Office 365](https://aka.ms/Office-365-Export-Controls)

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

**¿Qué debo hacer para cumplir con los controles de exportación al usar los servicios en la nube de Microsoft?**

En el oído, cuando los datos se cargan en un servidor en la nube, como la nube de Microsoft, el cliente propietario de los datos (no el proveedor de servicios en la nube) se considera el exportador. Por ese motivo, el propietario de los datos (es decir, el cliente de Microsoft) debe valorar cuidadosamente cómo su uso de la nube de Microsoft puede someterse a Implicate de exportación de los Estados Unidos y determinar si alguno de los datos que desean usar o almacenar puede estar sujeto a controles EAR y, si es así, qué controles se aplican. Obtenga más información sobre cómo [Azure](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=c24c11f2-2cd4-444a-9160-19762855ad3a&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers) y [Office 365](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE1s5kI) Cloud Services pueden ayudar a los clientes a garantizar su total cumplimiento con los controles de exportación de los Estados Unidos.

**¿Las tecnologías, productos y servicios de Microsoft están sujetos a la lengüeta?**

La mayoría de las tecnologías, productos y servicios de Microsoft:

- No están sujetos a las EAR y, por lo tanto, no están en la lista de control de Commerce y no tienen ECCN;
- O bien son EAR99 o 5D992 de peso en el mercado en masa, con derecho a la autoclasificación por parte de Microsoft y pueden exportarse a países no sujetos a embargo sin una licencia, ya que no se requiere ninguna licencia (NLR).

Dicho esto, a algunos productos de Microsoft se les ha asignado un ECCN que puede requerir o no una licencia. Consulte a los oídos o a los abogados para determinar el tipo de licencia adecuado y los países elegibles con fines de exportación.

**¿Cuál es la diferencia entre el tráfico de oído y el tráfico internacional en las regulaciones de brazos (ITAR)?**

Los principales controles de exportación de Estados Unidos con la aplicación más amplia son el oído, administrado por el Departamento de comercio de Estados Unidos. Las EAR se aplican a los elementos de doble uso que tienen aplicaciones comerciales y militares y a los elementos con aplicaciones puramente comerciales.

Los Estados Unidos también tienen normas de control de exportación distintas y especializadas, como ITAR, que gobiernan los elementos y la tecnología más confidenciales. Por el Departamento de Estados de los Estados Unidos, imponen los controles en la exportación, la importación temporal, la reexportación y la transferencia de muchos elementos militares, de defensa y de inteligencia (también conocidos como "artículos de defensa"), incluidos los datos técnicos relacionados.

## <a name="resources"></a>Recursos

- [Exportación de productos de Microsoft: información general](https://www.microsoft.com/exporting/overview.aspx)
- [Exportación de productos de Microsoft: preguntas más frecuentes](https://www.microsoft.com/exporting/faq.aspx)
- [Exportación de productos de Microsoft: búsqueda de productos](https://www.microsoft.com/exporting/exporting-information.aspx)
- [Restricciones de exportación en la criptografía](https://docs.microsoft.com/windows/uwp/security/export-restrictions-on-cryptography)
- [Microsoft y FIPS 140-2](offering-fips-140-2.md)
- [Microsoft y ITAR](offering-itar.md)
- [Cumplimiento en el Centro de Confianza de Microsoft](https://www.microsoft.com/trust-center/compliance/compliance-overview)
