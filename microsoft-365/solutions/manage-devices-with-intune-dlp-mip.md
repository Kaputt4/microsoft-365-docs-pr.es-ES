---
title: Step 7. Implement data loss prevention (DLP) with information protection capabilities
ms.author: bcarter
author: brendacarter
f1.keywords:
- Endpoint dlp
- data loss prevention
- dlp policies
manager: dougeby
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: high
ms.collection:
- highpri
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
ms.openlocfilehash: 0208f236e477affaebbea7c32c2cadf769128014
ms.sourcegitcommit: fce27da5140691b013a6f7c0ea9c88b4ea4b7c10
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2022
ms.locfileid: "67986628"
---
# <a name="step-7-implement-data-loss-prevention-dlp-with-information-protection-capabilities"></a>Step 7. Implement data loss prevention (DLP) with information protection capabilities


Si su organización ya ha puesto el tiempo en comprender los datos, desarrollar un esquema de confidencialidad de datos y aplicar el esquema, es posible que esté listo para extender elementos de este esquema a los puntos de conexión mediante directivas de prevención de pérdida de datos (DLP) de Microsoft Purview. 

La prevención de pérdida de datos en punto de conexión (DLP de punto de conexión) se aplica actualmente a:
- Windows 10, Windows 11
- macOS

DLP policies are created by your information protection and governance team. Each DLP policy defines what elements within a data set to look for, like sensitive information types or labels, and how to protect this data. 

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
