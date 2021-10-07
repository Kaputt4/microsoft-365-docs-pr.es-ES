---
title: Information Protection en Introducción de Windows
ms.reviewer: ''
description: Obtenga información sobre cómo funciona la protección de la información Windows para identificar y proteger información confidencial
keywords: información, protección, dlp, datos, pérdida, prevención, protección
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 4a96296f09a82fe2b2c8d5c4d5d250c48f89ffc4
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60156299"
---
# <a name="information-protection-in-windows-overview"></a>Information Protection en Introducción de Windows

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

La protección de la información es una parte integral de Microsoft 365 Enterprise conjunto de aplicaciones, que proporciona protección inteligente para proteger los datos confidenciales y, al mismo tiempo, permitir la productividad en el lugar de trabajo.

> [!TIP]
> Lea nuestra entrada de blog sobre cómo Microsoft Defender para endpoint se integra con Microsoft Information Protection para descubrir, proteger y supervisar datos confidenciales en [Windows dispositivos](https://cloudblogs.microsoft.com/microsoftsecure/2019/01/17/windows-defender-atp-integrates-with-microsoft-information-protection-to-discover-protect-and-monitor-sensitive-data-on-windows-devices/).

Defender for Endpoint aplica los siguientes métodos para detectar, clasificar y proteger datos:

- **Detección de** datos: identificar datos confidenciales en Windows dispositivos en riesgo
- **Clasificación de datos:** clasificar automáticamente los datos en función de las directivas Microsoft Information Protection (MIP) comunes administradas en el Centro de Office 365 seguridad & cumplimiento. La clasificación automática le permite proteger datos confidenciales incluso si el usuario final no los ha clasificado manualmente.

## <a name="data-discovery-and-data-classification"></a>Detección de datos y clasificación de datos

Defender for Endpoint detecta automáticamente archivos con etiquetas de confidencialidad y archivos que contienen tipos de información confidencial.

Las etiquetas de confidencialidad clasifican y ayudan a proteger el contenido confidencial.

Los tipos de información confidencial en la Office 365 de prevención de pérdida de datos (DLP) se en dos categorías:

- Predeterminada
- Personalizado

Los tipos de información confidencial predeterminados incluyen información como números de cuenta bancaria, números de seguridad social o nacionales. Para obtener más información, vea [What the sensitive information type look for](/office365/securitycompliance/what-the-sensitive-information-types-look-for).

Los tipos personalizados son los que se definen y están diseñados para proteger un tipo diferente de información confidencial (por ejemplo, los datos de los empleados o los números de proyecto). Para obtener más información, [vea Create a custom sensitive information type](/office365/securitycompliance/create-a-custom-sensitive-information-type).

Cuando se crea o edita un archivo en un dispositivo Windows, Defender for Endpoint examina el contenido para evaluar si contiene información confidencial.

Active la integración de Azure Information Protection para que, cuando Defender for Endpoint detecta un archivo que contiene información confidencial a través de etiquetas o tipos de información, se reenvía automáticamente a Azure Information Protection desde el dispositivo.

![Imagen de la página de configuración con Azure Information Protection.](images/atp-settings-aip.png)

Las señales notificadas se pueden ver en el Panel de Azure Information Protection : detección de datos.

## <a name="azure-information-protection---data-discovery-dashboard"></a>Azure Information Protection: panel de detección de datos

Este panel presenta una información resumida de detección de datos detectados por Defender para Endpoint y Azure Information Protection. Los datos de Defender para endpoint se marcan con Tipo de ubicación: extremo.

![Imagen de Azure Information Protection: detección de datos.](images/azure-data-discovery.png)

Observe la columna Riesgo de dispositivo a la derecha, este riesgo de dispositivo se deriva directamente de Defender para endpoint, lo que indica el nivel de riesgo del dispositivo de seguridad donde se detectó el archivo, en función de las amenazas de seguridad activas detectadas por Defender para endpoint.

Haz clic en un dispositivo para ver una lista de archivos observados en este dispositivo, con sus etiquetas de confidencialidad y tipos de información.

> [!NOTE]
> Espere entre 15 y 20 minutos aproximadamente para que la detección del panel de Azure Information Protection refleje los archivos detectados.

## <a name="log-analytics"></a>Log Analytics

La detección de datos basada en Defender para endpoint también está disponible en [Azure Log Analytics,](/azure/log-analytics/log-analytics-overview)donde puede realizar consultas complejas sobre los datos sin procesar.

Para obtener más información sobre el análisis de Azure Information Protection, vea [Central reporting for Azure Information Protection](/azure/information-protection/reports-aip).

Abra Azure Log Analytics en Azure Portal y abra un generador de consultas (estándar o clásico).

Para ver los datos de Defender for Endpoint, realice una consulta que contenga:

```text
InformationProtectionLogs_CL
| where Workload_s == "Windows Defender"
```

### <a name="prerequisites"></a>Requisitos previos

- Los clientes deben tener una suscripción a Azure Information Protection.
- Habilitar la integración de Azure Information Protection en Centro de seguridad de Microsoft Defender:
  - Vaya a **Configuración** en Centro de seguridad de Microsoft Defender, haga clic en **Configuración** en **General**.
