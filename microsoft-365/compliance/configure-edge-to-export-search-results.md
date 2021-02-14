---
title: Usar la herramienta de exportación de exhibición de documentos electrónicos en Microsoft Edge
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Debe habilitar la compatibilidad ClickOnce para usar la versión más reciente de Microsoft Edge para descargar los resultados de la búsqueda de contenido y la exhibición de documentos electrónicos en el centro de seguridad y cumplimiento.
ms.openlocfilehash: 60f42d2884c56aaff40bc0a6a979e99698a3cd2e
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546824"
---
# <a name="use-the-ediscovery-export-tool-in-microsoft-edge"></a>Usar la herramienta de exportación de exhibición de documentos electrónicos en Microsoft Edge

Como resultado de los cambios recientes en la versión más reciente de Microsoft Edge, ClickOnce soporte técnico ya no está habilitado de forma predeterminada. Para seguir usando la herramienta de exportación de exhibición de documentos electrónicos para descargar resultados de búsqueda de contenido o de exhibición de documentos electrónicos, debe usar [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) o habilitar la compatibilidad con ClickOnce en la versión más reciente de Microsoft Edge.

## <a name="enable-clickonce-support-in-microsoft-edge"></a>Habilitar ClickOnce en Microsoft Edge

1. En Microsoft Edge, vaya a **edge://flags/#edge-click-once**.

2. Si el valor existente se establece en **Predeterminado** o **Deshabilitado en** la lista desplegable, cámbielo a **Habilitado**.

   ![Seleccionar habilitado en la lista desplegable](../media/ClickOnceimage1.png)

3. Desplácese hacia abajo hasta la parte inferior de la ventana del explorador y haga clic **en Reiniciar** para reiniciar Edge.

   ![Haga clic en Reiniciar](../media/ClickOnceimage2.png)

**Nota:** Las organizaciones pueden usar la directiva de grupo para deshabilitar ClickOnce compatibilidad. Para comprobar si hay una directiva organizativa para ClickOnce soporte técnico, vaya **a edge://policy**. La siguiente captura de pantalla muestra que ClickOnce está habilitada en toda la organización. Si este valor de directiva se establece en **false,** deberá ponerse en contacto con un administrador de su organización.

![Lista de directivas de organización perimetral](../media/ClickOnceimage3.png)

## <a name="install-and-run-the-ediscovery-export-tool"></a>Instalar y ejecutar la herramienta de exportación de exhibición de documentos electrónicos

1. Haga **clic en Descargar resultados** en la página desplegable de una exportación en búsqueda de contenido o en un caso de exhibición de documentos electrónicos.

   ![Haga clic en Descargar resultados en la página desplegable para descargar los resultados de la búsqueda](../media/ClickOnceExport1.png)

2. Se le pedirá una confirmación para iniciar la herramienta, Haga clic **en Abrir.**

   ![Haga clic en Abrir para iniciar la herramienta de exportación de exhibición de documentos electrónicos](../media/ClickOnceimage4.png)

   Si la herramienta de exportación de exhibición de documentos electrónicos no está instalada, se le pedirá una advertencia de seguridad. 

   ![Haga clic en Instalar para instalar la herramienta de exportación de exhibición de documentos electrónicos](../media/ClickOnceimage5.png)

3. Haga clic en **Instalar**. Después de instalarla, la herramienta de exportación se iniciará automáticamente.

Para obtener más información, consulte los siguientes temas:

- [Exportar resultados de la búsqueda de contenido](export-search-results.md)

- [Cómo habilitar las marcas de experimento en Microsoft Edge](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
