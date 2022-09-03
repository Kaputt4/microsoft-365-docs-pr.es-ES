---
title: Paso 7. Implementar la prevención de pérdida de datos (DLP) con funcionalidades de protección de la información
ms.author: bcarter
author: brendacarter
f1.keywords:
- Endpoint dlp
- data loss prevention
- dlp policies
manager: dougeby
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- endpoint dlp
- data loss prevention
- dlp policies
- M365-security-compliance
- m365solution-managedevices
- m365solution-scenario
- zerotrust-solution
ms.custom: ''
keywords: ''
description: Implemente DLP para punto de conexión trabajando con el equipo de gobernanza y protección de la información para crear directivas DLP para su organización.
ms.openlocfilehash: 5a20f7e128890d75ec051667c41d3251639fadab
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2022
ms.locfileid: "67585474"
---
# <a name="step-7-implement-data-loss-prevention-dlp-with-information-protection-capabilities"></a>Paso 7. Implementar la prevención de pérdida de datos (DLP) con funcionalidades de protección de la información


Si su organización ya ha puesto el tiempo en comprender los datos, desarrollar un esquema de confidencialidad de datos y aplicar el esquema, es posible que esté listo para extender elementos de este esquema a los puntos de conexión mediante directivas de prevención de pérdida de datos (DLP) de Microsoft Purview. 

La prevención de pérdida de datos en punto de conexión (DLP de punto de conexión) se aplica actualmente a:
- Windows 10, Windows 11
- macOS

El equipo de gobierno y protección de la información crea directivas DLP. Cada directiva DLP define qué elementos de un conjunto de datos se deben buscar, como etiquetas o tipos de información confidencial, y cómo proteger estos datos. 

Por ejemplo, una directiva DLP puede buscar datos personales como un número de pasaporte. La directiva DLP incluirá una condición que desencadena que la directiva tome medidas, como cuando se comparte un número de pasaporte con personas de fuera de la organización. La acción que realiza la directiva también se puede configurar. Las opciones van desde simplemente informar de la acción a los administradores, advertir a los usuarios o incluso impedir que se compartan los datos.

La directiva DLP también especifica la ubicación a la que se aplicará la directiva, por ejemplo, Exchange correo electrónico y SharePoint sitios. Una de las ubicaciones disponibles para los administradores son los dispositivos. Si los dispositivos están seleccionados, puedes especificar a qué usuarios y grupos de usuarios aplicar la directiva. También puede especificar usuarios y grupos de usuarios que se excluirán de la directiva.

Si el equipo de gobierno y protección de la información está listo para extender las directivas DLP a los puntos de conexión, deberá coordinarse con ellos para habilitar dispositivos para DLP de punto de conexión, probar y ajustar directivas DLP, entrenar a los usuarios y supervisar los resultados. 

![Pasos de DLP de punto de conexión para el administrador de dispositivos](../media/devices/endpoint-dlp-steps.png#lightbox)


Siga estos pasos para trabajar con el equipo de protección de la información.


|Paso  |Descripción  |
|---------|---------|
|1     |  [Obtener información sobre la Prevención de pérdida de datos en punto de conexión](../compliance/endpoint-dlp-learn-about.md).        |
|2     | Habilitar dispositivos para DLP de punto de conexión. Si ha incorporado dispositivos a Microsoft Defender para punto de conexión, los dispositivos ya están habilitados para DLP de punto de conexión. Si los dispositivos no están incorporados a Defender para punto de conexión, consulte [Introducción a la prevención de pérdida de datos en punto de conexión](../compliance/endpoint-dlp-getting-started.md) para obtener instrucciones.|
|3     |   Trabaje con su equipo de gobernanza y protección de la información para definir, probar y ajustar directivas. Esto incluye la supervisión de los resultados. Consulte estos recursos:<br>- [Uso de la prevención de pérdida de datos de punto de conexión](../compliance/endpoint-dlp-using.md)<br>- [Ver los informes para la prevención de pérdida de datos](../compliance/view-the-dlp-reports.md)      |
