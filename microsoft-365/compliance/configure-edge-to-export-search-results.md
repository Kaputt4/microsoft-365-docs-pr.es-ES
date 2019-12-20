---
title: Usar la herramienta de exportación de exhibición de documentos electrónicos de Office 365 en Microsoft Edge
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Tiene que habilitar la compatibilidad de ClickOnce para usar Microsoft Edge para exportar los resultados de búsqueda de la búsqueda de contenido y la exhibición de documentos electrónicos en el centro de seguridad y cumplimiento.
ms.openlocfilehash: f3e0442fe349aa3364594e07873b229f3205fb5e
ms.sourcegitcommit: d656fd58e5491cfb7fee16b55dc7a58904ed128d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2019
ms.locfileid: "39891131"
---
# <a name="use-the-office-365-ediscovery-export-tool-in-microsoft-edge"></a>Usar la herramienta de exportación de exhibición de documentos electrónicos de Office 365 en Microsoft Edge

Como resultado de los últimos cambios realizados en Microsoft Edge, la compatibilidad con ClickOnce ya no está habilitada de forma predeterminada. Para seguir usando la herramienta de exportación de exhibición de documentos electrónicos 365 de Microsoft Office para descargar los resultados de búsqueda de contenido o de exhibición de documentos electrónicos, debe usar [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) o habilitar la compatibilidad con ClickOnce en Microsoft Edge.

## <a name="how-to-enable-clickonce-support-in-microsoft-edge"></a>Cómo habilitar la compatibilidad con ClickOnce en Microsoft Edge

1. En Microsoft Edge, navegue a **edge://flags/#edge clic una vez**.

2. Si el valor existente se establece en **predeterminado** o está **deshabilitado** en la lista desplegable, cámbielo a **habilitado**.
    
   ![](media/ClickOnceimage1.png)

3. Desplácese hacia abajo hasta la parte inferior de la ventana del explorador y haga clic en **reiniciar** para reiniciar el perímetro.

   ![](media/ClickOnceimage2.png)

**Nota:** Las organizaciones pueden usar la Directiva de grupo para deshabilitar la compatibilidad con ClickOnce. Para comprobar si existe una directiva de la organización para la compatibilidad con ClickOnce, vaya a **Edge://Policy**. En la siguiente captura de pantalla se muestra que ClickOnce está habilitado en toda la organización. Si el valor de esta Directiva se establece en **false**, deberá ponerse en contacto con un administrador de la organización.

![](media/ClickOnceimage3.png)

## <a name="install-and-run-the-office-365-ediscovery-export-tool"></a>Instalar y ejecutar la herramienta de exportación de Office 365 eDiscovery

1. Haga clic en **Descargar resultados** en la página de flotante de una exportación en una búsqueda de contenido o un caso de exhibición de documentos electrónicos.

   ![Haga clic en descargar resultados en la página de flotante para descargar los resultados de la búsqueda](media/ClickOnceExport1.png)

2. Se le pedirá que confirme que desea iniciar la herramienta; para ello, haga clic en **abrir**.

   ![Haga clic en abrir para iniciar la herramienta de exportación de exhibición de documentos electrónicos](media/ClickOnceimage4.png)

   Si la herramienta de exportación de exhibición de documentos electrónicos 365 de Microsoft Office no está instalada, se le mostrará una advertencia de seguridad. 

   ![Haga clic en instalar para instalar la herramienta de exportación de exhibición de documentos electrónicos](media/ClickOnceimage5.png)

3. Haga clic en **Instalar**. Una vez instalada, la herramienta de exportación se iniciará automáticamente.

Para obtener más información, vea los siguientes temas:

- [Exportar resultados de la búsqueda de contenido](export-search-results.md)

- [Cómo habilitar las marcas de experimento en Microsoft Edge](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
