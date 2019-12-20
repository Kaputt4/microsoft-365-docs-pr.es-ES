---
title: Commission Securities and Exchange Commission (SEC) Rule 17a-4 (f) Estados Unidos
description: Una empresa de evaluación independiente ha validado que Azure y Office 365 pueden ayudar a las empresas financieras a cumplir con las reglas de la SEC 17a-4 (f) retención de registros y los requisitos de almacenamiento inmutables.
keywords: Microsoft 365, cumplimiento, ofertas
localization_priority: None
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: 915e70065e6efb05424c710bb3e8a98902857c6c
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2019
ms.locfileid: "40804253"
---
# <a name="securities-and-exchange-commission-sec-rule-17a-4f-united-states"></a>Commission Securities and Exchange Commission (SEC) Rule 17a-4 (f) Estados Unidos

## <a name="microsoft-and-sec-rule-17a-4f"></a>Reglas de Microsoft y SEC 17a-4 (f)

La [Comisión US Securities and Exchange Commission (SEC)](https://www.sec.gov/) es una agencia independiente del gobierno federal de Estados Unidos y el supervisor principal y el regulador de los mercados de valores de los Estados Unidos. Maneja la autoridad de cumplimiento sobre las leyes federales de valores, propone nuevas reglas de valores y supervisa la reglamentación del mercado de la industria de valores.

La SEC define requisitos rigurosos y explícitos para las entidades reguladas que eligen retener libros y registros en medios de almacenamiento electrónicos. Se estableció [17 CFR 240.17 a-3](https://www.govinfo.gov/app/details/CFR-2012-title17-vol3/CFR-2012-title17-vol3-sec240-17a-3) y [17 CFR 240.17 a-4](https://www.ecfr.gov/cgi-bin/text-idx?mc=true&node=pt17.4.240&rgn=div5#se17.4.240_117a_64) para regularización de los tiempos de conservación, incluidos los períodos de retención, para los corredores de agentes de valores. Más adelante, la SEC [modificaba](https://www.sec.gov/rules/interp/34-47806.htm) 17 CFR 240.17 a-4 párrafo (f), emitiendo dos versiones interpretadoras expresamente para permitir que los libros y registros se retengan en medios de almacenamiento electrónicos siempre que se cumplieran determinadas condiciones.

Un sistema de almacenamiento electrónico cumple con las condiciones que impiden la alteración o eliminación de registros durante el período de retención requerido. Los períodos de retención varían de tres a seis años en función de los tipos de registro, con la accesibilidad inmediata que se ha actualizado para los primeros dos años. Además, una de las versiones interpretativas requiere que el sistema de almacenamiento sea capaz de retener los registros más allá del período de retención establecido en la SEC para cumplir con las citaciónes, la retención legal u otros requisitos de este tipo.

## <a name="microsoft-and-sec-rule-17a-4f"></a>Reglas de Microsoft y SEC 17a-4 (f)

Los clientes de servicios financieros, que representan una de las industrias reguladas más intensamente del mundo, están sujetos a complejas provisiones como la retención de transacciones financieras y la comunicación relacionada en un estado no modificable y que no se puede borrar. Entre la regla más preceptiva 17a-4 (f) de la seguridad estadounidense de la Comisión de Exchange (SEC), que estipula requisitos rigurosos para las entidades reguladas que eligen conservar libros y registros en medios de almacenamiento electrónicos. Los registros almacenados deben ser inalterables sin capacidad para modificarlos o eliminarlos hasta después del período de retención designado.

El almacenamiento de blobs inmutable de Microsoft Azure con bloqueo de directivas y Microsoft Office 365 con bloqueo de preservación puede ayudar a las instituciones financieras a cumplir los requisitos de almacenamiento inmutables de la regla de la SEC 17a-4 (f).

Para evaluar el cumplimiento de Azure y Office 365 con la regla SEC 17a-4 (f), Microsoft reservó una empresa de evaluación independiente que se especializa en la administración de registros y el gobierno de la información, Cohasset Associates. En el informe resultante para:

- **Azure**: [SEC 17a-4 (f) Compliance Assessment: Microsoft Azure Storage](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=19b08fd4-d276-43e8-9461-715981d0ea20&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_GRC_Assessment_Reports), Cohasset validó que [Azure inmutable Storage BLOB](https://docs.microsoft.com/azure/storage/blobs/storage-blob-immutable-storage) con la opción de bloqueo de Directiva, cuando se usa para conservar blobs basados en tiempo en un formato de no reescritura y no regrabable (Worm), cumple los requisitos de almacenamiento inmutables de la regla de la SEC. Cada BLOB (registro) está protegido contra modificaciones, sobrescritos o eliminaciones hasta que haya expirado el período de retención requerido y se hayan lanzado todas las retenciones legales asociadas. Los proveedores de software y los asociados con cargas de trabajo confidenciales ahora pueden confiar en Azure inmutable BLOB Storage como una solución de nube de OneStop-Shop para la retención de registros y el almacenamiento inmutable. Las instituciones financieras ahora pueden crear sus propias aplicaciones aprovechando estas características a la vez que cumplen con los requisitos restantes.
- **Office 365**: [usar Exchange Online para cumplir con la norma SEC 17a-4](https://docs.microsoft.com/office365/securitycompliance/use-exchange-online-to-comply-with-sec-rule-17a-4), Cohasset validó [que Office 365 con bloqueo de preservación](https://docs.microsoft.com/office365/securitycompliance/retention-policies#locking-a-retention-policy) incluye características de archivado que permiten a los clientes regulados, incluidos agentes de bolsa, almacenar datos de manera que les ayuden a cumplir con los requisitos de la SEC para la retención de registros. Las directivas de retención en Office 365 ayudan a conservar una amplia gama de datos, incluidos el correo electrónico, el correo de voz, los documentos compartidos, los mensajes instantáneos y los datos de terceros. En concreto, el archivado en Office 365 permite a los clientes establecer directivas de retención de mensajería globales o granulares para almacenar datos durante un período definido y más adelante en un formato no regrabable y no borrable.

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft en el ámbito de los servicios en la nube

- [Azure](https://gallery.technet.microsoft.com/Overview-of-Azure-c1be3942)
- [Office 365](https://aka.ms/Office365ComplianceOfferings)

## <a name="audits-reports-and-certificates"></a>Auditorías, informes y certificados

### <a name="azure--sec-rule-17"></a>Regla 17 de Azure & SEC

[Evaluación de cumplimiento de SEC 17a-4 (f) & CFTC 1,31 (c-d) de Azure Storage](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=19b08fd4-d276-43e8-9461-715981d0ea20&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_GRC_Assessment_Reports)

### <a name="office-365--sec-rule-17"></a>Regla 17 de Office 365 & SEC

[Evaluación de cumplimiento de SEC 17a-4 (f): Centro de cumplimiento de Microsoft Security & con Exchange Online](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9fa8349d-a0c9-47d9-93ad-472aa0fa44ec&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

## <a name="how-to-implement"></a>Cómo implementar

### <a name="financial-services-regulation"></a>Reglamento de servicios financieros

Mapa de cumplimiento de los principios clave de los Estados Unidos para la informática en la nube y Microsoft Online Services. [Más información](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5b483567-00b0-4d86-96ae-ee887dadb61c&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_Compliance_Guides)

### <a name="risk-assessment--compliance-guide"></a>Guía de cumplimiento de & de evaluación de riesgos

Cree un modelo de gobierno para la evaluación de riesgos de los servicios en la nube de Microsoft y la notificación del regulador. [Más información](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

### <a name="financial-use-cases"></a>Casos de uso financiero

Use introducciones de casos, tutoriales y otros recursos para crear soluciones de Azure para servicios financieros. [Más información](https://docs.microsoft.com/azure/industry/financial/)

## <a name="resources"></a>Recursos

- [Archivado en Microsoft Office 365, retención de datos y reglas 17a-4](https://www.microsoft.com/microsoft-365/blog/2015/11/10/office-365-exchange-online-archiving-now-meets-sec-rule-17a-4-requirements/)
- [Cumplimiento de servicios de Microsoft Financial Services](https://download.microsoft.com/download/6/4/7/64707E3E-6D3E-45D0-8207-A0EA3201B4A6/Microsoft%20Cloud%20-%20Financial%20Services%20Compliance%20Program%20\(Print\).pdf)
- [Programa de cumplimiento servicios de Microsoft Business Cloud y servicios financieros](https://servicetrust.microsoft.com/viewpage/financialservicesoverview)
- [Cumplimiento de los servicios financieros en Azure](https://azure.microsoft.com/resources/videos/azurecon-2015-financial-services-compliance-in-azure/)
- [Herramienta de evaluación de riesgos en la nube para servicios financieros de Azure](https://servicetrust.microsoft.com/ViewPage/FFIECBlueprint?command=Download&downloadType=Document&downloadId=079a1973-711a-428f-9312-9ddd290cff7b&docTab=c726d5c0-2d1e-11e8-a485-57140ec19669_PaaS)
- [Directivas de retención de Microsoft Office 365](https://docs.microsoft.com/office365/securitycompliance/retention-policies)
- [Blog de servicios financieros de Microsoft](https://techcommunity.microsoft.com/t5/Financial-Services-Blog/bg-p/FinancialServicesBlog)
- [Cumplimiento en el centro de confianza de Microsoft ](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a>Descargar el documento de información general de la oferta

¿Necesita el documento de información general de esta oferta? Descargue el [PDF](https://download.microsoft.com/download/E/5/2/E52103E7-C1BB-4118-9725-4452FEA931D8/SEC17a-4(f)-Compliance.pdf).
