---
title: Administrar las exclusiones de carpeta de automatización
description: Agregue exclusiones de carpetas de automatización para controlar los archivos que se excluyen de una investigación automatizada.
keywords: administrar, automatización, exclusión, bloquear, limpiar, malintencionada
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 54c0f7f67b62216eae4264c8e7a55c0e34c82fb0
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2021
ms.locfileid: "61166127"
---
# <a name="manage-automation-folder-exclusions"></a>Administrar las exclusiones de carpeta de automatización

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Plan 2 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-automationexclusionfolder-abovefoldlink)

Las exclusiones de carpetas de automatización permiten especificar carpetas que omitirá la investigación automatizada.

Puede controlar los siguientes atributos acerca de la carpeta que desea omitir:

- **Carpetas:** puede especificar una carpeta y sus subcarpetas que se omitirán.

  > [!NOTE]
  > En este momento, aún no se admite el uso de comodines como forma de excluir archivos en un directorio.

- **Extensiones de los archivos:** puede especificar las extensiones que se excluirán en un directorio específico. Las extensiones son una forma de impedir que un atacante use una carpeta excluida para ocultar una vulnerabilidad. Las extensiones definen explícitamente los archivos que se deben omitir.

- **Nombres de** archivo: puede especificar los nombres de archivo que desea excluir en un directorio específico. Los nombres son una forma de impedir que un atacante use una carpeta excluida para ocultar una vulnerabilidad. Los nombres definen explícitamente los archivos que se deben omitir.

## <a name="add-an-automation-folder-exclusion"></a>Agregar una exclusión de carpeta de automatización

1. En el panel de navegación, seleccione **Configuración** exclusiones de \> **carpetas** de automatización de reglas de \>  \> **extremo**.

2. Haga **clic en Nueva exclusión de carpeta**.

3. Escriba los detalles de la carpeta:

    - Folder
    - Extensiones
    - Nombres de archivo
    - Description

4. Haga clic en **Guardar**.

> [!NOTE]
> Los comandos live response para recopilar o examinar archivos excluidos producirán un error: "Se excluye el archivo". Además, las investigaciones automatizadas omitirán los elementos excluidos.

## <a name="edit-an-automation-folder-exclusion"></a>Editar una exclusión de carpetas de automatización

1. En el panel de navegación, seleccione **Configuración** exclusiones de \> **carpetas** de automatización de reglas de \>  \> **extremo**.
2. Haga **clic en Editar** en la exclusión de carpetas.
3. Actualice los detalles de la regla y haga clic en **Guardar**.

## <a name="remove-an-automation-folder-exclusion"></a>Quitar una exclusión de carpetas de automatización

1. En el panel de navegación, seleccione **Configuración** exclusiones de \> **carpetas** de automatización de reglas de \>  \> **extremo**.
2. Haga clic **en Quitar exclusión**.

## <a name="related-topics"></a>Temas relacionados

- [Administrar listas de automatización permitidas o bloqueadas](manage-indicators.md)
- [Administrar cargas de archivos de automatización](manage-automation-file-uploads.md)
