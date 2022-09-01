---
title: Administrar cargas de archivos de automatización
description: Habilitar el análisis de contenido y configurar la extensión de archivo y las extensiones de datos adjuntos de correo electrónico que se enviarán para su análisis
keywords: automation, file, uploads, content, analysis, file, extension, email, attachment
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
ms.openlocfilehash: 67c5e6bfb03fd38a8f55482c4debd69dd25e8000
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67521189"
---
# <a name="manage-automation-file-uploads"></a>Administrar cargas de archivos de automatización

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-automationefileuploads-abovefoldlink)

Habilite la funcionalidad de análisis de contenido para que determinados archivos y datos adjuntos de correo electrónico se puedan cargar automáticamente en la nube para una inspección adicional en la investigación automatizada.

Identifique los archivos y los datos adjuntos de correo electrónico especificando los nombres de extensión de archivo y los nombres de extensión de datos adjuntos de correo electrónico.

Por ejemplo, si agrega *exe* y *bat* como nombres de extensión de archivo o datos adjuntos, todos los archivos o datos adjuntos con esas extensiones se enviarán automáticamente a la nube para una inspección adicional durante la investigación automatizada.

## <a name="add-file-extension-names-and-attachment-extension-names"></a>Agregue nombres de extensión de archivo y nombres de extensión de datos adjuntos.

1. En el panel de navegación, seleccione Settings **Endpoints** \> Rules **Automation uploads** (Cargas de Automatización de **reglas** \> de puntos de conexión **de configuración**\>).

2. Alterne la configuración de análisis de contenido entre **Activado** y **Desactivado**.

3. Configure los siguientes nombres de extensión y los nombres de extensión independientes con una coma:
   - **Nombres de extensión de** archivo: los archivos sospechosos excepto los datos adjuntos de correo electrónico se enviarán para una inspección adicional.

## <a name="related-topics"></a>Temas relacionados

- [Administrar las exclusiones de carpeta de automatización](manage-automation-folder-exclusions.md)
