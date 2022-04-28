---
title: Uso de la herramienta de exportación de eDiscovery en Microsoft Edge
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Debe habilitar la compatibilidad con ClickOnce para usar la versión más reciente de Microsoft Edge para descargar los resultados de la búsqueda de contenido y eDiscovery en el centro de seguridad y cumplimiento.
ms.openlocfilehash: 13556b08a0eaec5ed11bdaf09014a3988cd56829
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65092445"
---
# <a name="use-the-ediscovery-export-tool-in-microsoft-edge"></a>Uso de la herramienta de exportación de eDiscovery en Microsoft Edge

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Como resultado de los cambios recientes en la versión más reciente de Microsoft Edge, la compatibilidad con ClickOnce ya no está habilitada de forma predeterminada. Para seguir usando la herramienta de exportación de exhibición de documentos electrónicos para descargar los resultados de búsqueda de contenido o eDiscovery, debe usar [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) o habilitar ClickOnce compatibilidad con la versión más reciente de Microsoft Edge.

## <a name="enable-clickonce-support-in-microsoft-edge"></a>Habilitar la compatibilidad con ClickOnce en Microsoft Edge

1. En Microsoft Edge, vaya a **edge://flags/#edge-click-once**.

2. Si el valor existente se establece en **Predeterminado** o **Deshabilitado** en la lista desplegable, cámbielo a **Habilitado**.

   ![Seleccione Habilitado en la lista desplegable.](../media/ClickOnceimage1.png)

3. Desplácese hacia abajo hasta la parte inferior de la ventana del explorador y haga clic en **Reiniciar** para reiniciar Edge.

   ![Haga clic en Reiniciar.](../media/ClickOnceimage2.png)

**Nota:** Las organizaciones pueden usar directiva de grupo para deshabilitar ClickOnce soporte técnico. Para comprobar si hay una directiva organizativa para ClickOnce soporte técnico, vaya a **edge://policy**. En la captura de pantalla siguiente se muestra que ClickOnce está habilitado en toda la organización. Si este valor de directiva se establece en **false**, deberá ponerse en contacto con un administrador de la organización.

![Lista de directivas organizativas de Edge.](../media/ClickOnceimage3.png)

## <a name="install-and-run-the-ediscovery-export-tool"></a>Instalación y ejecución de la herramienta de exportación de eDiscovery

1. Haga clic en **Descargar resultados** en la página de control flotante de una exportación en Búsqueda de contenido o en un caso de exhibición de documentos electrónicos.

   ![Haga clic en Descargar resultados en la página de control flotante para descargar los resultados de la búsqueda.](../media/ClickOnceExport1.png)

2. Se le pedirá una confirmación para iniciar la herramienta, haga clic en **Abrir**.

   ![Haga clic en Abrir para iniciar la herramienta de exportación de exhibición de documentos electrónicos.](../media/ClickOnceimage4.png)

   Si la herramienta de exportación de eDiscovery no está instalada, se le pedirá una advertencia de seguridad, 

   ![Haga clic en Instalar para instalar la herramienta de exportación de eDiscovery.](../media/ClickOnceimage5.png)

3. Haga clic en **Instalar**. Una vez instalada, la herramienta de exportación se iniciará automáticamente.

Para obtener más información, consulte los siguientes temas:

- [Exportar resultados de la búsqueda de contenido](export-search-results.md)

- [Habilitación de marcas de experimento en Microsoft Edge](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
