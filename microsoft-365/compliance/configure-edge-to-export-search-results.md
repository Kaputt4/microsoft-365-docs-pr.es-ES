---
title: Use la herramienta de exportación de exhibición de documentos electrónicos en Microsoft Edge
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
description: Debe habilitar la compatibilidad ClickOnce para usar la versión más reciente de Microsoft Edge para descargar los resultados de búsqueda de la búsqueda de contenido y la exhibición de documentos electrónicos en el centro de seguridad y cumplimiento.
ms.openlocfilehash: ec241d36bc24d72e4c0ea3e30e622e42eb9546bfb4b548220e98a0d9ea1c0334
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53830952"
---
# <a name="use-the-ediscovery-export-tool-in-microsoft-edge"></a>Use la herramienta de exportación de exhibición de documentos electrónicos en Microsoft Edge

Como resultado de los cambios recientes en la versión más reciente de Microsoft Edge, ClickOnce soporte técnico ya no está habilitado de forma predeterminada. Para seguir usando la herramienta de exportación de exhibición de documentos electrónicos para descargar resultados de búsqueda de búsqueda de contenido o exhibición de documentos electrónicos, debe usar [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) o habilitar la compatibilidad ClickOnce en la versión más reciente de Microsoft Edge.

## <a name="enable-clickonce-support-in-microsoft-edge"></a>Habilitar ClickOnce soporte técnico en Microsoft Edge

1. En Microsoft Edge, vaya **a edge://flags/#edge-click-once**.

2. Si el valor existente se establece en **Predeterminado** o Deshabilitado **en** la lista desplegable, cámbilo a **Habilitado**.

   ![Seleccionar habilitado en la lista desplegable](../media/ClickOnceimage1.png)

3. Desplácese hacia abajo hasta la parte inferior de la ventana del explorador y haga clic **en Reiniciar** para reiniciar Edge.

   ![Haga clic en Reiniciar](../media/ClickOnceimage2.png)

**Nota:** Las organizaciones pueden usar la directiva de grupo para deshabilitar ClickOnce compatibilidad. Para comprobar si hay una directiva organizativa para la ClickOnce, vaya a **edge://policy**. La siguiente captura de pantalla muestra ClickOnce está habilitada en toda la organización. Si este valor de directiva se establece en **false,** deberá ponerse en contacto con un administrador de la organización.

![Lista de directivas organizativas perimetrales](../media/ClickOnceimage3.png)

## <a name="install-and-run-the-ediscovery-export-tool"></a>Instalar y ejecutar la herramienta de exportación de exhibición de documentos electrónicos

1. Haga clic en Descargar **resultados** en la página desplegable de una exportación en Búsqueda de contenido o en un caso de exhibición de documentos electrónicos.

   ![Haga clic en Descargar resultados en la página desplegable para descargar los resultados de búsqueda](../media/ClickOnceExport1.png)

2. Se le pedirá una confirmación para iniciar la herramienta, Haga clic **en Abrir**.

   ![Haga clic en Abrir para iniciar la herramienta de exportación de exhibición de documentos electrónicos](../media/ClickOnceimage4.png)

   Si la herramienta de exportación de exhibición de documentos electrónicos no está instalada, se le pedirá una advertencia de seguridad, 

   ![Haga clic en Instalar para instalar la herramienta de exportación de exhibición de documentos electrónicos](../media/ClickOnceimage5.png)

3. Haga clic en **Instalar**. Una vez instalada, la herramienta de exportación se iniciará automáticamente.

Para obtener más información, consulte los siguientes temas:

- [Exportar resultados de la búsqueda de contenido](export-search-results.md)

- [Cómo habilitar las marcas de experimento en Microsoft Edge](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
