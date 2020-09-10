---
title: Corporación Norteamericana de Confiabilidad Eléctrica (NERC)
description: Azure y Azure Government son adecuados para entidades registradas que utilizan ciertas cargas de trabajo en la nube sujetas a los estándares de la NERC CIP.
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
ms.openlocfilehash: 7001a17af7932a7aafa7cceac207b772b42b55d9
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2020
ms.locfileid: "47417168"
---
# <a name="north-american-electric-reliability-corporation-nerc"></a>Corporación Norteamericana de Confiabilidad Eléctrica (NERC)

## <a name="about-the-nerc"></a>Acerca de NERC

La [Corporación Norteamericana de Confiabilidad Eléctrica](https://www.nerc.com/) (NERC) es una autoridad normativa sin fines de lucro, cuya misión es asegurar la fiabilidad del sistema de generación y transporte de los Estados Unidos. NERC está sujeto a la supervisión por parte de la Comisión Federal Reguladora de la Energía (FERC) de los Estados Unidos y autoridades gubernamentales en Canadá. En 2006, FERC otorgó la denominación de Organización de fiabilidad eléctrica (ERO) a NERC de conformidad con la Ley de política energética de 2005 (Derecho público de Estados Unidos 109-58). NERC desarrolla y aplica estándares de confiabilidad conocidos como[los estándares de Protección de infraestructura críticos (CIP)](https://www.nerc.com/pa/Stand/Pages/CIPStandards.aspx)de la NERC.

## <a name="microsoft-and-the-nerc-cip-standard"></a>Microsoft y el estándar NERC CIP

La Corporación Norteamericana de Confiabilidad Eléctrica (NERC) es una autoridad normativa sin fines de lucro, cuya misión es asegurar la fiabilidad del sistema de generación y transporte de los Estados Unidos. NERC está sujeto a la supervisión por parte de la Comisión Federal Reguladora de la Energía (FERC) de los Estados Unidos y autoridades gubernamentales en Canadá. En 2006, FERC otorgó la denominación de Organización de fiabilidad eléctrica (ERO) a NERC de conformidad con la Ley de política energética de 2005 (Derecho público de Estados Unidos 109-58). NERC desarrolla y aplica estándares de confiabilidad conocidos como[los estándares de Protección de infraestructura críticos (CIP)](https://www.nerc.com/pa/Stand/Pages/CIPStandards.aspx)de la NERC.

Todos los propietarios, operadores y usuarios de sistemas de generación y transporte deben [cumplir con los estándares de la NERC CIP](https://www.nerc.com/pa/comp/Pages/default.aspx). Estas entidades deben registrarse en NERC. Los proveedores de servicios en la nube y otros no se someten a los estándares NERC CIP; sin embargo, los estándares del CIP incluyen metas que se deben tener en cuenta cuando las[Entidades registradas](https://www.nerc.com/pa/comp/Pages/Registration.aspx) usen proveedores en la operación del Sistema de generación y transporte eléctrico (BES). Los clientes de Microsoft que operan los Sistemas de generación y transporte eléctrico son totalmente responsables de garantizar su propio cumplimiento con los estándares de NERC CIP. Ni Microsoft Azure o Microsoft Azure Government constituyen un BES o Activo cibernético del BES.

Como NERC indicó en el conjunto actual de [normas CIP](https://www.nerc.com/pa/Stand/Reliability%20Standards%20Complete%20Set/RSCompleteSet.pdf) y el [Glosario de los términos](https://www.nerc.com/pa/Stand/Glossary%20of%20Terms/Glossary_of_Terms.pdf) de NERC, los activos cibernéticos del BES realizan funciones en tiempo real para monitorear o controlar el BES, y afectarían al funcionamiento confiable del BES en un plazo de 15 minutos después de ser deteriorado. Para adecuar correctamente los Activos cibernéticos de BES y los Activos cibernéticos protegidos en la informática en la nube, es necesario que las definiciones existentes en los estándares NERC CIP[sean revisados](https://www.nerc.com/pa/Stand/Pages/Project%202016-02%20Modifications%20to%20CIP%20Standards.aspx). Sin embargo, hay una gran cantidad de cargas de trabajo que tratan con datos confidenciales del CIP y que no se encuentran dentro la regla de 15 minutos, incluida la amplia categoría de la Información del sistema cibernético BES (BCSI).

Azure y Azure Government son adecuados para entidades registradas que utilizan ciertas cargas de trabajo sujetas a los estándares NERC CIP, incluyendo cargas de trabajo del BCSI. Microsoft permite que los siguientes documentos estén disponibles para las Entidades registradas interesadas en implementar datos y cargas de trabajo sujetas a las obligaciones de cumplimiento de la CIP NERC en Azure o Azure Government:

- [Los estándares e Informática en la nube de NERC CIP ](https://aka.ms/AzureNERC)son informes técnicos que describen las consideraciones para el cumplimiento del NERC CIP en función a las auditorías establecidas por terceros y que son aplicables a los proveedores de servicios en la nube como FedRAMP. Cubre la detección en segundo plano para el personal de operaciones en la nube y responde preguntas comunes sobre aislamiento lógico y tenencia múltiple que son de interés para las Entidades registradas. También se tratan consideraciones de seguridad para la implementación local vs en la nube.
- [La Guía de implementación en la nube para las auditorías de NERC](https://aka.ms/AzureNERCGuide) es un documento de guía en el que se proporciona una asignación de controles entre el conjunto actual de requerimientos estándares de NERC CIP y el conjunto de control[NIST SP 800-53 Rev 4](https://nvd.nist.gov/800-53/Rev4)que constituye la base de FedRAMP. Se ha diseñado como guía de procedimientos técnicos para ayudar a las Entidades registradas a cumplir los requisitos de cumplimiento NERC CIP para los activos implementados en la nube. El documento contiene narraciones de[Hojas de cálculo de auditoria estándar de confiabilidad (RSAWs)](https://www.nerc.com/pa/comp/Pages/Reliability-Standard-Audit-Worksheets-\(RSAWs\).aspx) previamente rellenada(s) que ayudan a explicar cómo los controles de Azure resuelven los requisitos de NERC CIP, y son una guía para las Entidades registradas sobre cómo usar los servicios de Azure para implementar controles de su propiedad.

La Iniciativa NERC ERO[publicó](https://www.nerc.com/pa/comp/guidance/Pages/default.aspx)la [guía práctica](https://www.nerc.com/pa/comp/guidance/CMEPPracticeGuidesDL/ERO%20Enterprise%20CMEP%20Practice%20Guide%20_%20BCSI%20-%20v0.2%20CLEAN.pdf) Programa de control y cumplimiento normativo (CMEP) para proporcionar instrucciones al personal de la iniciativa ERO CMEP al momento de evaluar el proceso de una Entidad registrada para autorizar el acceso a ubicaciones de almacenamiento BCSI designadas y a cualquier control de acceso implementado por la Entidad registrada. Por otra parte, NERC revisó los detalles de la implementación de control de Azure y las pruebas de auditoría de FedRAMP relacionadas con los estándares NERC CIP-004-6 y CIP-011-2 que son aplicables a BCSI. Basándose en la guía práctica de ERO y los controles revisados de FedRAMP para asegurar que las entidades registradas cifren sus datos, no es necesario realizar ninguna guía o información adicional para que las entidades registradas implementen el BCSI y las cargas de trabajo asociadas en la nube. Sin embargo, las Entidades registradas son, en última instancia, responsables del cumplimiento normativo de los estándares NERC CIP de acuerdo con sus propios hechos y circunstancias. Las Entidades registradas deben revisar la [Guía de implementación en la nube para las auditorías de NERC](https://aka.ms/AzureNERCGuide) para obtener ayuda con la documentación de los procesos y la evidencia utilizados para autorizar el acceso electrónico a las ubicaciones de almacenamiento BCSI, incluyendo la administración de claves que se usa para el cifrado de BCSI en Azure y Azure Government.

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft en el ámbito de los servicios en la nube

- [Azure y Azure Government](https://aka.ms/AzureCompliance)

## <a name="audits-reports-and-certificates"></a>Auditorías, informes y certificados

Microsoft debe recertificar sus servicios en la nube cada año para mantener sus P-ATOs y ATOs. Para ello, Microsoft debe supervisar y evaluar sus controles de seguridad continuamente, y demostrar que permanece cumpliendo.

- [Autorizaciones de servicios en la nube de Microsoft](https://marketplace.fedramp.gov/?sort=productName&productNameSearch=azure#/product/azure-government)
- [Informes de auditoría de Microsoft FedRAMP](https://aka.ms/MicrosoftFedRAMPAuditDocuments)

## <a name="how-to-implement"></a>Cómo se debe implementar

### <a name="nerc-cip-standards-and-cloud-computing"></a>Estándares e Informática en la nube de NERC CIP 

Resuelve el cumplimiento para Entidades registradas considerando la adopción en la nube para cargas de trabajo sujetas a estándares NERC CIP.

[Más información](https://aka.ms/AzureNERC)

### <a name="cloud-implementation-guide-for-nerc-audits"></a>Guía de implementación en la nube para auditorías de NERC

Las instrucciones técnicas permiten a las Entidades registradas con NERC auditar los activos implementados en Azure o Azure Government. 

[Más información](https://aka.ms/AzureNERCGuide)

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

**¿Quién es el responsable de cumplimiento normativo de NERC CIP?**

Todos los propietarios, operadores y usuarios de sistemas de generación y transporte deben [cumplir con los estándares de la NERC CIP](https://www.nerc.com/pa/comp/Pages/default.aspx). Estas entidades deben registrarse en NERC. Los proveedores de servicios en la nube y otros no se someten a los estándares NERC CIP; sin embargo, los estándares del CIP incluyen metas que se deben tener en cuenta cuando las[Entidades registradas](https://www.nerc.com/pa/comp/Pages/Registration.aspx) usen proveedores en la operación del Sistema de generación y transporte eléctrico (BES). Los clientes de Microsoft que operan los Sistemas de generación y transporte eléctrico son totalmente responsables de garantizar su propio cumplimiento con los estándares de NERC CIP. Ni Azure o Microsoft Azure Government constituyen un BES o Activo cibernético del BES.

Para evaluar la idoneidad de Azure y Azure Government para los datos y las cargas de trabajo sujetos a los estándares de NERC CIP, las Entidades registradas deben consultar con sus propios responsables de cumplimiento normativo y auditores de NERC. Deben revisar la [Guía de implementación en la nube para auditorías de NERC](https://aka.ms/AzureNERCGuide)para obtener ayuda con la documentación de los procesos y pruebas para los activos implementados en la nube.

**¿Qué cargas de trabajo pueden realizarse en Entidades registradas en Azure y Azure Government?**

[Las normas CIP](https://www.nerc.com/pa/Stand/Reliability%20Standards%20Complete%20Set/RSCompleteSet.pdf) y el[Glosario de los términos](https://www.nerc.com/pa/Stand/Glossary%20of%20Terms/Glossary_of_Terms.pdf)de NERC, establece que los Activos cibernéticos del BES realizan funciones en tiempo real para monitorear o controlar el BES, y que si fueran afectados afectarían al funcionamiento confiable del BES en un plazo de 15 minutos. Para adecuar correctamente los Activos cibernéticos de BES y los Activos cibernéticos protegidos en la informática en la nube, es necesario que las definiciones existentes en los estándares NERC CIP[sean revisados](https://www.nerc.com/pa/Stand/Pages/Project%202016-02%20Modifications%20to%20CIP%20Standards.aspx). Sin embargo, hay una gran cantidad de cargas de trabajo que tratan con datos confidenciales del CIP y que no se encuentran dentro la regla de 15 minutos, incluida la amplia categoría de la Información del sistema cibernético BES (BCSI).

La Iniciativa NERC ERO[publicó](https://www.nerc.com/pa/comp/guidance/Pages/default.aspx)la [guía práctica](https://www.nerc.com/pa/comp/guidance/CMEPPracticeGuidesDL/ERO%20Enterprise%20CMEP%20Practice%20Guide%20_%20BCSI%20-%20v0.2%20CLEAN.pdf) Programa de control y cumplimiento normativo (CMEP) para proporcionar instrucciones al personal de la iniciativa ERO CMEP al momento de evaluar el proceso de una Entidad registrada para autorizar el acceso a ubicaciones de almacenamiento BCSI designadas y a cualquier control de acceso implementado por la Entidad registrada. Por otra parte, NERC revisó los detalles de la implementación de control de Azure y las pruebas de auditoría de FedRAMP relacionadas con los estándares NERC CIP-004-6 y CIP-011-2 que son aplicables a BCSI. Basándose en la guía práctica de ERO y los controles revisados de FedRAMP para asegurar que las Entidades registradas cifren sus datos, no es necesario realizar ninguna guía o información adicional para que las entidades registradas implementen el BCSI y las cargas de trabajo asociadas en la nube. Sin embargo, las Entidades registradas son, en última instancia, responsables del cumplimiento normativo de los estándares NERC CIP de acuerdo con sus propios hechos y circunstancias.

## <a name="resources"></a>Recursos

- [Guías de cumplimiento de NERC](https://www.nerc.com/pa/comp/guidance/)
- [Cumplimiento y aplicación de NERC](https://www.nerc.com/pa/comp/Pages/default.aspx)
- [Organización y certificación de NERC](https://www.nerc.com/pa/comp/Pages/Registration.aspx)
- [Microsoft y FedRAMP](offering-fedramp.md)
- [Atestación](offering-csa-star-attestation.md) y [Certificación](offering-csa-star-certification.md) de Microsoft y CSA STAR
- [Informes de Microsoft y SOC 2](offering-soc.md)
- [Cumplimiento normativo en el Centro de confianza de Microsoft](https://www.microsoft.com/trust-center/compliance/compliance-overview)
