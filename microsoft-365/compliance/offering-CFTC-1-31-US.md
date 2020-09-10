---
title: 1.31 de reglas de la Comisión comercial de ventas de futuros (CFTC) (c-d) Estados Unidos
description: Una empresa de evaluación independiente ha validado que Azure y Office 365 pueden ayudar a las empresas financieras a cumplir con los requisitos de retención de CFTC reglas 1,31 registros y de almacenamiento inmutable.
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
ms.openlocfilehash: 73d52a91620bc0bd50a310c4085fa821fab80da2
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2020
ms.locfileid: "47416360"
---
# <a name="commodity-futures-trading-commission-cftc-rule-131c-d-united-states"></a>1.31 de reglas de la Comisión comercial de ventas de futuros (CFTC) (c-d) Estados Unidos

## <a name="about-cftc-rule-13c-d"></a>Acerca de la regla 1.3 de CFTC (c-d)

La [Comisión comercial de Futures](https://www.cftc.gov/) de la mercancía (CFTC), una Agencia Federal estadounidense independiente, regula los mercados de opciones y futuros de la mercancía y, más recientemente, el mercado de swaps.  
  
La regla CFTC de larga duración 1,31 define los requisitos de retención de registros establecidos por la regla de la SEC 17a-4 (f). Además, especifica que los registros electrónicos deben mantenerse durante cinco años y que los originales deben mantenerse "fácilmente accesibles" durante los dos primeros años y puestos a disposición de la Comisión o del Departamento de Justicia de Estados Unidos durante todo el período de retención.  
  
En 2017, el [CFTC revisó su regla](https://www.cftc.gov/sites/default/files/idc/groups/public/@lrfederalregister/documents/file/2017-11014a.pdf), modificando y modernizando el Reglamento de conservación de registros para adoptar estándares menos preceptivos y normativos basados en principios que proporcionan mayor flexibilidad en la forma en que se pueden mantener los registros. Esto hace que la regla sea más neutral en cuanto a tecnología, lo que permite a las entidades reguladas elegir la tecnología más adecuada para su negocio y mantener al mismo tiempo las medidas de seguridad que "aseguran la confiabilidad del proceso de conservación de la información". La regla revisada quita el requisito de que las organizaciones mantengan los registros originales durante dos años, pero conserva el período de mantenimiento de cinco años, que armoniza los procedimientos para las empresas reguladas por el CFTC y la SEC.

## <a name="microsoft-and-cftc-rule-131c-d"></a>1.31 de reglas de Microsoft y CFTC (c-d)

Los clientes de servicios financieros, que representan una de las industrias reguladas más intensamente del mundo, están sujetos a complejas provisiones como la retención de transacciones financieras y la comunicación relacionada en un estado no modificable y que no se puede borrar. Entre la regla más preceptiva se encuentra 1,31 de la Comisión comercial de transacciones de futuro (CFTC) de Estados Unidos, que estipula estrictos requisitos para las entidades reguladas que eligen conservar libros y registros en medios de almacenamiento electrónicos. Los registros almacenados deben ser inalterables sin capacidad para modificarlos o eliminarlos hasta después del período de retención designado. El almacenamiento de blobs inmutable de Microsoft Azure con bloqueo de directivas y Microsoft Office 365 con bloqueo de preservación puede ayudar a las instituciones financieras a cumplir los requisitos de almacenamiento de la regla de CFTC 1.31 (c-d).

### <a name="microsoft-azure"></a>Microsoft Azure

Para evaluar el cumplimiento de Azure con CFTC regla 1.31 (c-d), Microsoft reservó una empresa de evaluación independiente que se especializa en la administración de registros y el gobierno de la información, Cohasset Associates. En el informe resultante, [CFTC 1,31 (c) – (d) Compliance Assessment: Microsoft Azure Storage](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=19b08fd4-d276-43e8-9461-715981d0ea20&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_GRC_Assessment_Reports), Cohasset validó que [Azure inmutable Storage BLOB](https://docs.microsoft.com/azure/storage/blobs/storage-blob-immutable-storage) con la opción de bloqueo de Directiva, cuando se usa para conservar los blobs basados en tiempo en un formato de no reescritura y no regrabable (Worm), cumple con los requisitos basados en los principios de la regla CFTC. Cada BLOB (registro) está protegido contra modificaciones, sobrescritos o eliminaciones hasta que haya expirado el período de retención requerido y se hayan lanzado todas las retenciones legales asociadas. Los proveedores de software y los asociados con cargas de trabajo confidenciales ahora pueden confiar en Azure inmutable BLOB Storage como una solución de nube de tienda de un solo punto para la retención de registros. Las instituciones financieras ahora pueden crear sus propias aplicaciones aprovechando estas características a la vez que cumplen con los requisitos restantes.

### <a name="microsoft-office-365"></a>Microsoft Office 365

Para evaluar el cumplimiento de Office 365 con la regla de CFTC 1.31 (c-d), Microsoft contrató a un bufete de derecho independiente y líder que se especializa en problemas normativos, Covington & Burling, LLP. En el informe resultante, el [archivado en Microsoft Office 365, la retención de datos y el cumplimiento de reglas 17a-4](https://go.microsoft.com/fwlink/?linkid=830440), Covington valida que [Office 365 con bloqueo de preservación](retention.md#use-preservation-lock-to-comply-with-regulatory-requirements) incluye características de archivado que permiten a los clientes regulados almacenar datos de una manera que les ayude a cumplir con los requisitos de CFTC para la retención de registros.

El archivado en Office 365 ayuda a preservar una amplia gama de datos, incluidos el correo electrónico, el correo de voz, los documentos compartidos, los mensajes instantáneos y los datos de terceros. En concreto, el archivado en Office 365 permite a los clientes establecer directivas de retención de mensajería globales o granulares para almacenar datos durante un período definido y más adelante en un formato no regrabable y no borrable.

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft en el ámbito de los servicios en la nube

- [Azure](https://aka.ms/AzureCompliance)
- [Office 365](https://aka.ms/o365-compliance-framework)

## <a name="audits-reports-and-certificates"></a>Auditorías, informes y certificados

[Regla 1,31 de Azure & CFTC-SEC 17a-4 (f) & CFTC 1.31 (c-d) evaluación de cumplimiento de Azure Storage

[Office 365 & CFTC 1,31: archivado en Office 365, retención de datos y cumplimiento de la norma 17a-4 de la SEC

## <a name="how-to-implement"></a>Cómo se debe implementar

- [Reglamento de servicios financieros](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5b483567-00b0-4d86-96ae-ee887dadb61c&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_Compliance_Guides): mapa de cumplimiento de los principios clave de los Estados Unidos para la informática en la nube y los servicios en línea de Microsoft.
- [Guía de cumplimiento y evaluación de riesgos](https://aka.ms/RiskGovernanceGuide): Cree un modelo de gobierno para la evaluación de riesgos de los servicios en la nube de Microsoft y las notificaciones reglamentarias.
- [Casos de uso financiero](https://docs.microsoft.com/azure/industry/financial/): información general de casos de uso, tutoriales y otros recursos para crear soluciones de Azure para servicios financieros.

## <a name="resources"></a>Recursos

- [Programa de cumplimiento de servicios financieros de Microsoft](https://aka.ms/FSCP-Print)
- [Servicios financieros y servicios empresariales en la nube de Microsoft](https://www.microsoft.com/trustcenter/cloudservices/financialservices)
- [Cumplimiento de los servicios financieros en Azure](https://azure.microsoft.com/resources/videos/azurecon-2015-financial-services-compliance-in-azure/)
- [Herramienta de evaluación de riesgos en la nube para servicios financieros de Azure](https://aka.ms/FFIEC-CSDT)
- [Directivas de retención de Microsoft Office 365](https://docs.microsoft.com/office365/securitycompliance/retention-policies)
- [Blog de servicios financieros de Microsoft](https://techcommunity.microsoft.com/t5/Financial-Services-Blog/bg-p/FinancialServicesBlog)
- [Cumplimiento en el Centro de Confianza de Microsoft](https://www.microsoft.com/trust-center/compliance/compliance-overview)
