---
title: Optimización y corrección de directivas de seguridad con el analizador de configuración
description: Pasos para optimizar y corregir directivas de seguridad con el analizador de configuración. El analizador de configuración es una ubicación central y un único panel de cristal para administrar y ver las directivas de seguridad de correo electrónico que ha configurado en el inquilino.
search.product: ''
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-guidance-templates
ms.topic: how-to
ms.technology: mdo
ms.openlocfilehash: 7dcce2bb3f71ebf6400ece3296da71a7f686db10
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67691197"
---
# <a name="optimize-and-correct-security-policies-with-configuration-analyzer"></a>Optimización y corrección de directivas de seguridad con el analizador de configuración

El analizador de configuración es una ubicación central y un único panel de cristal para administrar y ver las directivas de seguridad de correo electrónico que ha configurado en el inquilino. Puede realizar una comparación lateral de la configuración con nuestra configuración recomendada estándar y estricta, aplicar recomendaciones y ver los cambios históricos que afectaron a su posición.

## <a name="what-youll-need"></a>Lo que necesitará
- Exchange Online Protection
- Permisos suficientes (rol administrador de seguridad)
- 5 minutos para realizar los pasos siguientes.

## <a name="compare-settings-and-apply-recommendations"></a>Comparación de la configuración y aplicación de recomendaciones
1. Vaya a [https://security.microsoft.com/configurationAnalyzer](https://security.microsoft.com/configurationAnalyzer).
1. Elija **Recomendaciones estándar** o **Recomendaciones estrictas** en el menú superior en función de la comparación lateral que quiera realizar.
1. Se mostrarán las recomendaciones para los cambios de directiva. (Si procede)
1. A continuación, puede seleccionar una recomendación, anotar la acción recomendada, la directiva a la que se aplica la recomendación, establecer el nombre & la configuración actual, etc.
1. Con una recomendación seleccionada, puede presionar **Aplicar recomendación** y, a continuación, **Aceptar** en el mensaje de confirmación que aparece.
1. Si desea editar manualmente una directiva o confirmar la configuración directamente dentro de la directiva, puede presionar **Ver directiva** en lugar de **Aplicar recomendación** , que cargará una nueva pestaña y le llevará directamente a la directiva afectada para facilitarla.

## <a name="view-historical-configuration-changes"></a>Visualización de los cambios de configuración históricos

Mientras que en **El analizador de configuración** puede seleccionar **Análisis e historial de desfase de configuración** en la barra de menús superior.

La página que se carga le mostrará las modificaciones en las directivas de seguridad en el período de tiempo seleccionado por los filtros, junto con los datos sobre el cambio y si ha aumentado o reducido su posición general.

Para obtener más información sobre Configuration Analyzer, consulte [Analizador de configuración para directivas de seguridad: Office 365 | Microsoft Docs](../../office-365-security/configuration-analyzer-for-security-policies.md).
