---
title: Administrar cargas de archivos de automatización
description: Habilitar el análisis de contenido y configurar las extensiones de archivo y datos adjuntos de correo electrónico que se enviarán para su análisis
keywords: automatización, archivo, cargas, contenido, análisis, archivo, extensión, correo electrónico, datos adjuntos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c8935368e4439221f2ce21cfa620e540c02165f8
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185854"
---
# <a name="manage-automation-file-uploads"></a>Administrar cargas de archivos de automatización

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automationefileuploads-abovefoldlink)

Habilite la funcionalidad de análisis de contenido para que determinados archivos y datos adjuntos de correo electrónico se puedan cargar automáticamente en la nube para una inspección adicional en la investigación automatizada.

Identifique los archivos y los datos adjuntos de correo electrónico especificando los nombres de extensión de archivo y los nombres de extensión de datos adjuntos de correo electrónico. 

Por ejemplo, si agrega *exe* y *bat* como nombres de extensión de archivo o datos adjuntos, todos los archivos o datos adjuntos con esas extensiones se enviarán automáticamente a la nube para una inspección adicional durante la investigación automatizada. 

## <a name="add-file-extension-names-and-attachment-extension-names"></a>Agregue nombres de extensión de archivo y nombres de extensión de datos adjuntos.

1. En el panel de navegación, seleccione **Settings**  >  **Automation file uploads**. 

2. Alterna la configuración del análisis de contenido **entre On** y **Off**.

3. Configure los siguientes nombres de extensión y separe los nombres de extensión con una coma:
   - **Nombres de extensión de archivo:** los archivos sospechosos, excepto los datos adjuntos de correo electrónico, se enviarán para inspección adicional
  

## <a name="related-topics"></a>Temas relacionados
- [Administrar exclusiones de carpetas de automatización](manage-automation-folder-exclusions.md)
