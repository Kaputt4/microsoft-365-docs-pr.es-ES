---
title: Regla de la autoridad reguladora del sector financiero (FINRA) 4511 (c) Estados Unidos
description: Una empresa de evaluación independiente ha validado que Azure y Office 365 pueden ayudar a las empresas financieras a cumplir con los requisitos de retención de FINRA reglas 4511 registros y de almacenamiento inmutable.
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
ms.openlocfilehash: 80114436580e388afce0508f69dc892c0eaaf435
ms.sourcegitcommit: 4612c270867c148818eaa4008f45ca793f5d2a2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2019
ms.locfileid: "38691010"
---
# <a name="compliance-offering-financial-industry-regulatory-authority-finra-rule-4511c-united-states"></a>Oferta de cumplimiento: Estados Unidos de la regla de la autoridad de reglamentación del sector financiero (FINRA) de 4511 (c)

## <a name="about-finra-rule-4511"></a>Acerca de la regla 4511 de FINRA

La [autoridad reguladora del sector financiero (FINRA)](https://www.finra.org/#/) es el cuerpo independiente más grande que regula a las empresas de valores con supervisión de más de 4.500 de empresas de corretaje en los Estados Unidos. Fue autorizado por el Congreso estadounidense "para proteger a los inversores de America asegurándose de que la industria de agentes del agente opera de manera equitativa y honesta".

En 2011, la Comisión estadounidense Security and Exchange Commission (SEC) aprobó la FINRA adopción de reglas de la SEC que rigen la retención de libros y registros en medios de almacenamiento electrónicos. La [regla 4511 de FINRA](https://www.finra.org/sites/default/files/NoticeDocument/p123548.pdf) especifica que "todos los libros y los registros que deben realizarse con arreglo a las reglas de FINRA se conservarán en un formato y en un medio que cumpla con la norma" marítima (Ley de intercambio de valores) Rule 17a-4 ".

Además, la regla de FINRA 4511 (c) requiere que las empresas conserven durante un período de al menos seis años los libros y los registros para los que no haya un período de retención especificado en las reglas aplicables de FINRA o mar. De hecho, si los libros y los registros pertenecen a una cuenta, el período de retención debe ser seis años después del cierre de la cuenta. De lo contrario, el período de retención es de seis años tras la creación de estos libros y registros.

## <a name="microsoft-and-finra-rule-4511c"></a>4511 de reglas de Microsoft y FINRA (c)

Los clientes de servicios financieros, que representan una de las industrias reguladas más intensamente del mundo, están sujetos a complejas provisiones como la retención de transacciones financieras y la comunicación relacionada en un estado no modificable y que no se puede borrar. Entre ellas se encuentra la regla 4511 de la autoridad reguladora del sector financiero (FINRA) que estipula estrictos requisitos para las entidades reguladas que eligen conservar libros y registros en medios de almacenamiento electrónicos. Los registros almacenados deben ser inalterables sin capacidad para modificarlos o eliminarlos hasta después del período de retención designado.

El almacenamiento de blobs inmutable de Microsoft Azure con bloqueo de directivas y Microsoft Office 365 con bloqueo de preservación puede ayudar a las instituciones financieras a cumplir los requisitos de almacenamiento inmutables de la regla de FINRA 4511 (c).

## <a name="microsoft-azure"></a>Microsoft Azure

Para evaluar el cumplimiento de Azure con FINRA regla 4511 (c), Microsoft reservó una empresa de evaluación independiente que se especializa en la administración de registros y el gobierno de la información, Cohasset Associates. El informe resultante, la [SEC 17a-4 (f) & CFTC 1,31 (c-d) Compliance Assessment: Microsoft Azure Storage](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=19b08fd4-d276-43e8-9461-715981d0ea20&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_GRC_Assessment_Reports), engloba el cumplimiento de Azure con FINRA Rule 4511 (c), que se pospone al formato y los requisitos de medios de la regla SEC 17a-4 (f).

Cohasset validó que [Azure inmutable Storage BLOB](https://docs.microsoft.com/azure/storage/blobs/storage-blob-immutable-storage) con la opción de bloqueo de Directiva, cuando se usa para conservar los blobs basados en tiempo en un formato no regrabable y no regrabable (Worm), cumple los requisitos de almacenamiento de FINRA relevantes. Cada BLOB (registro) está protegido contra modificaciones, sobrescritos o eliminaciones hasta que haya expirado el período de retención requerido y se hayan lanzado todas las retenciones legales asociadas.

Los proveedores de software y los asociados con cargas de trabajo confidenciales ahora pueden confiar en Azure inmutable BLOB Storage como una solución de nube de tienda integrada para la retención de registros y el almacenamiento inmutable. Las instituciones financieras ahora pueden crear sus propias aplicaciones aprovechando estas características a la vez que cumplen con los requisitos restantes.

## <a name="microsoft-office-365"></a>Microsoft Office 365

Para evaluar el cumplimiento de Office 365 con la 4511 de la regla de FINRA (c), Microsoft ha mantenido una empresa líder de derecho independiente que se especializa en problemas normativos, Covington & Burling, LLP. En el informe resultante, el archivado en Microsoft Office 365, la retención de datos y el cumplimiento de reglas 17a-4, Covington valida que [Office 365 con bloqueo de preservación](https://docs.microsoft.com/office365/securitycompliance/retention-policies#locking-a-retention-policy) incluye características de archivado que permiten a los clientes regulados, incluidos agentes de mantenimiento, almacenar datos de una manera que les ayude a cumplir con los requisitos de FINRA para la retención de registros.

El archivado en Office 365 ayuda a conservar una amplia gama de datos, incluidos el correo electrónico, el correo de voz, los documentos compartidos, los mensajes instantáneos y los datos de terceros. En concreto, el archivado en Office 365 permite a los clientes establecer directivas de retención de mensajería globales o granulares para almacenar datos durante un período definido y más adelante en un formato no regrabable y no borrable.

## <a name="microsoft-in-scope-cloud-services"></a>Servicios en la nube de Microsoft en el ámbito

- [Azure](https://gallery.technet.microsoft.com/Overview-of-Azure-c1be3942)
- [Office 365](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9f756cce-b15d-45a9-94d7-6a583dee4401&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_Compliance_Guides)

## <a name="audits-reports-and-certificates"></a>Auditorías, informes y certificados

### <a name="azure--finra-rule-4511c"></a>4511 de reglas de Azure & FINRA (c)

[Evaluación de cumplimiento de SEC 17a-4 (f) & CFTC 1,31 (c-d) de Azure Storage](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=19b08fd4-d276-43e8-9461-715981d0ea20&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_GRC_Assessment_Reports)

### <a name="office-365--finra-rule-4511c"></a>Office 365 & FINRA de reglas de 4511 (c)

[Archivado en Office 365, retención de datos y cumplimiento de la norma 17a-4 de la SEC](https://www.microsoft.com/microsoft-365/blog/2015/11/10/office-365-exchange-online-archiving-now-meets-sec-rule-17a-4-requirements/)

## <a name="how-to-implement"></a>Cómo implementar

- **Reglamento de servicios financieros**: mapa de cumplimiento de los principios clave de los Estados Unidos para la informática en la nube y los servicios en línea de Microsoft. [Más información](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5b483567-00b0-4d86-96ae-ee887dadb61c&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_Compliance_Guides)
- **Guía de cumplimiento de & de evaluación de riesgos**: crear un modelo de gobierno para la evaluación de riesgos de los servicios en la nube de Microsoft y la notificación del regulador. [Más información](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)
- **Casos de uso financiero**: información general, tutoriales y otros recursos para crear soluciones de Azure para servicios financieros.

[Más información](https://docs.microsoft.com/azure/industry/financial/)

## <a name="resources"></a>Recursos

- [Programa de cumplimiento de servicios financieros de Microsoft](https://download.microsoft.com/download/6/4/7/64707E3E-6D3E-45D0-8207-A0EA3201B4A6/Microsoft%20Cloud%20-%20Financial%20Services%20Compliance%20Program%20\(Print\).pdf)
- [Servicios financieros y servicios de Microsoft Business Cloud](https://servicetrust.microsoft.com/viewpage/financialservicesoverview)
- [Cumplimiento de servicios financieros en Azure](https://azure.microsoft.com/resources/videos/azurecon-2015-financial-services-compliance-in-azure/)
- [Herramienta de evaluación de riesgos de la nube de servicios financieros de Azure](https://servicetrust.microsoft.com/ViewPage/FFIECBlueprint?command=Download&downloadType=Document&downloadId=079a1973-711a-428f-9312-9ddd290cff7b&docTab=c726d5c0-2d1e-11e8-a485-57140ec19669_PaaS)
- [Directivas de retención de Microsoft Office 365](https://docs.microsoft.com/office365/securitycompliance/retention-policies)
- [Blog de servicios financieros de Microsoft](https://techcommunity.microsoft.com/t5/Financial-Services-Blog/bg-p/FinancialServicesBlog)
- [Cumplimiento en el centro de confianza de Microsoft](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a>Descargar el fondo de la oferta

¿Necesita el documento de fondo para esta oferta? Descargue el [archivo PDF](https://download.microsoft.com/download/6/B/2/6B20520B-E264-4B58-9EE2-DD6C87D9E254/FINRA-Compliance.pdf).
