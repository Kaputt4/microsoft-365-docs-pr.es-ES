---
title: Usar la herramienta de exportación de exhibición de documentos electrónicos en Microsoft Edge
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Debe habilitar la compatibilidad de ClickOnce para usar la versión más reciente de Microsoft Edge para descargar los resultados de búsqueda de la búsqueda de contenido y la exhibición de documentos electrónicos en el centro de seguridad y cumplimiento.
ms.openlocfilehash: 317e19c81a606565fcb18f3256fd5bac007747e1
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357580"
---
# <a name="use-the-ediscovery-export-tool-in-microsoft-edge"></a>Usar la herramienta de exportación de exhibición de documentos electrónicos en Microsoft Edge

Como resultado de los últimos cambios en la versión más reciente de Microsoft Edge, la compatibilidad con ClickOnce ya no está habilitada de forma predeterminada. Para seguir usando la herramienta de exportación de exhibición de documentos electrónicos para descargar los resultados de búsqueda de contenido o de exhibición de documentos electrónicos, debe usar [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) o habilitar la compatibilidad con ClickOnce en la versión más reciente de Microsoft Edge.

## <a name="enable-clickonce-support-in-microsoft-edge"></a>Habilitar la compatibilidad con ClickOnce en Microsoft Edge

1. En Microsoft Edge, ve a **edge://flags/#edge clic una vez**.

2. Si el valor existente se establece en **predeterminado** o está **deshabilitado** en la lista desplegable, cámbielo a **habilitado**.

   ![Seleccionar habilitado en la lista desplegable](../media/ClickOnceimage1.png)

3. Desplácese hacia abajo hasta la parte inferior de la ventana del explorador y haga clic en **reiniciar** para reiniciar el perímetro.

   ![Haga clic en reiniciar](../media/ClickOnceimage2.png)

**Nota:** Las organizaciones pueden usar la Directiva de grupo para deshabilitar la compatibilidad con ClickOnce. Para comprobar si hay una directiva de la organización para la compatibilidad con ClickOnce, vaya a **Edge://Policy**. En la siguiente captura de pantalla se muestra que ClickOnce está habilitado en toda la organización. Si el valor de esta Directiva se establece en **false**, deberá ponerse en contacto con un administrador de la organización.

![Lista de directivas de organización perimetral](../media/ClickOnceimage3.png)

## <a name="install-and-run-the-ediscovery-export-tool"></a>Instalar y ejecutar la herramienta de exportación de exhibición de documentos electrónicos

1. Haga clic en **Descargar resultados** en la página de flotante de una exportación en una búsqueda de contenido o un caso de exhibición de documentos electrónicos.

   ![Haga clic en descargar resultados en la página de flotante para descargar los resultados de la búsqueda](../media/ClickOnceExport1.png)

2. Se le pedirá que confirme que desea iniciar la herramienta; para ello, haga clic en **abrir**.

   ![Haga clic en abrir para iniciar la herramienta de exportación de exhibición de documentos electrónicos](../media/ClickOnceimage4.png)

   Si la herramienta de exportación de exhibición de documentos electrónicos no está instalada, se le mostrará una advertencia de seguridad. 

   ![Haga clic en instalar para instalar la herramienta de exportación de exhibición de documentos electrónicos](../media/ClickOnceimage5.png)

3. Haga clic en **Instalar**. Una vez instalada, la herramienta de exportación se iniciará automáticamente.

Para obtener más información, consulte los siguientes temas:

- [Exportar resultados del Contenido de búsqueda](export-search-results.md)

- [Cómo habilitar las marcas de experimento en Microsoft Edge](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
