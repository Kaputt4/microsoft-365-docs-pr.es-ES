---
title: Administrar las exclusiones de carpeta de automatización
description: Agregue exclusiones de carpetas de automatización para controlar los archivos que se excluyen de una investigación automatizada.
keywords: administrar, automatización, exclusión, bloquear, limpiar, malintencionada
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: article
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 7b6a2cdfaf420e04e8964b955934f5aea9ca86f9
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68233120"
---
# <a name="manage-automation-folder-exclusions"></a>Administrar las exclusiones de carpeta de automatización

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-automationexclusionfolder-abovefoldlink)

Las exclusiones de carpetas de Automation permiten especificar carpetas que la investigación automatizada omitirá.

Puede controlar los siguientes atributos sobre la carpeta que desea omitir:

- **Carpetas**: puede especificar una carpeta y sus subcarpetas que se omitirán.

  > [!NOTE]
  > En este momento, todavía no se admite el uso de comodín como forma de excluir archivos en un directorio.

- **Extensiones de los archivos**: puede especificar las extensiones que se van a excluir en un directorio específico. Las extensiones son una manera de evitar que un atacante use una carpeta excluida para ocultar una vulnerabilidad de seguridad. Las extensiones definen explícitamente qué archivos se van a omitir.

- **Nombres de archivo**: puede especificar los nombres de archivo que desea excluir en un directorio específico. Los nombres son una manera de evitar que un atacante use una carpeta excluida para ocultar una vulnerabilidad de seguridad. Los nombres definen explícitamente qué archivos se van a omitir.

## <a name="add-an-automation-folder-exclusion"></a>Agregar una exclusión de carpeta de automatización

1. En el panel de navegación, seleccione **Configuración** \> Exclusiones \> de **carpetas de Automatización** de **reglas** \> de **puntos de conexión**.

2. Haga clic en **Nueva exclusión de carpeta**.

3. Escriba los detalles de la carpeta:

    - Folder
    - Extensiones
    - Nombres de archivo
    - Descripción

4. Haga clic en **Guardar**.

> [!NOTE]
> Los comandos de respuesta dinámica para recopilar o examinar archivos excluidos producirán un error: "El archivo está excluido". Además, las investigaciones automatizadas omitirán los elementos excluidos.

## <a name="edit-an-automation-folder-exclusion"></a>Edición de una exclusión de carpeta de automatización

1. En el panel de navegación, seleccione **Configuración** \> Exclusiones \> de **carpetas de Automatización** de **reglas** \> de **puntos de conexión**.
2. Haga clic en **Editar** en la exclusión de carpetas.
3. Actualice los detalles de la regla y haga clic en **Guardar**.

## <a name="remove-an-automation-folder-exclusion"></a>Eliminación de una exclusión de carpeta de automatización

1. En el panel de navegación, seleccione **Configuración** \> Exclusiones \> de **carpetas de Automatización** de **reglas** \> de **puntos de conexión**.
2. Haga clic en **Quitar exclusión**.

## <a name="related-topics"></a>Temas relacionados

- [Administración de listas de automatización permitidas o bloqueadas](manage-indicators.md)
- [Administrar cargas de archivos de automatización](manage-automation-file-uploads.md)
