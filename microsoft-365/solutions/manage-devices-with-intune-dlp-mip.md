---
title: Paso 7. Implementar la prevención de pérdida de datos (DLP) con funcionalidades de protección de la información
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: dougeby
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
ms.custom: ''
keywords: ''
description: ''
ms.openlocfilehash: 76c7f613ba6a859f843550e18baa78637858be46
ms.sourcegitcommit: 2ea2105d40b60a87fc9aa30f392a73a3a9db6d99
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2021
ms.locfileid: "61129526"
---
# <a name="step-7-implement-data-loss-prevention-dlp-with-information-protection-capabilities"></a>Paso 7. Implementar la prevención de pérdida de datos (DLP) con funcionalidades de protección de la información

Si su organización ya ha puesto el tiempo en comprender los datos, desarrollar un esquema de confidencialidad de datos y aplicar el esquema, es posible que esté listo para extender elementos de este esquema a los puntos de conexión mediante directivas de prevención de pérdida de datos (DLP). 

El equipo de gobierno y protección de la información crea directivas DLP. Cada directiva DLP define qué elementos de un conjunto de datos debe buscar, como etiquetas o tipos de información confidencial, y cómo proteger estos datos. 

Por ejemplo, una directiva DLP puede buscar datos personales como un número de pasaporte. La directiva DLP incluirá una condición que desencadena que la directiva tome medidas, como cuando se comparte un número de pasaporte con personas de fuera de la organización. La acción que realiza la directiva también se puede configurar. Las opciones van desde simplemente informar de la acción a los administradores, advertir a los usuarios o incluso impedir que se compartan los datos.

La directiva DLP también especifica la ubicación a la que se aplicará la directiva, por ejemplo, Exchange correo electrónico y SharePoint sitios. Una de las ubicaciones disponibles para los administradores son los dispositivos. Si los dispositivos están seleccionados, puedes especificar a qué usuarios y grupos de usuarios aplicar la directiva. También puede especificar usuarios y grupos de usuarios que se excluirán de la directiva.

Si el equipo de gobierno y protección de la información está listo para extender directivas DLP a los puntos de conexión, deberá coordinarse con ellos para incorporar dispositivos, probar y ajustar las directivas, entrenar a los usuarios y supervisar los resultados. 

Siga estos pasos para trabajar con el equipo de protección de la información.


|Paso  |Descripción  |
|---------|---------|
|1     |  [Obtenga información sobre Microsoft 365 prevención de pérdida de datos de punto de conexión](../compliance/endpoint-dlp-learn-about.md).        |
|2     | Incorporar dispositivos a las soluciones de cumplimiento de Microsoft 365. Consulte [Introducción a la prevención de pérdida de datos de extremo](../compliance/endpoint-dlp-getting-started.md) para obtener instrucciones sobre:<br>- Incorporación de Windows 10 y Windows 11<br>- Incorporación de MacOS       |
|3     |   Trabaje con su equipo de gobernanza y protección de la información para definir, probar y ajustar directivas. Esto incluye la supervisión de los resultados. Consulte estos recursos:<br>- [Uso de la prevención de pérdida de datos de punto de conexión](../compliance/endpoint-dlp-using.md)<br>- [Ver los informes para la prevención de pérdida de datos](../compliance/view-the-dlp-reports.md)      |
|     |         |
