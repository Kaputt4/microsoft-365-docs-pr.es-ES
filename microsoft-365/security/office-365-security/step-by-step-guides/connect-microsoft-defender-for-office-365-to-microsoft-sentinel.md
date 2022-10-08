---
title: Conectar Microsoft Defender para Office 365 a Microsoft Sentinel
description: Pasos para conectar Microsoft Defender para Office 365 a Sentinel. Agregue los datos de Microsoft Defender para Office 365 (*y* los datos del resto del conjunto de Microsoft 365 Defender), incluidos los incidentes, a Microsoft Sentinel para obtener un único panel de cristal en su seguridad.
search.product: ''
ms.service: microsoft-365-security
ms.subservice: mdo
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
ms.collection:
- m365-guidance-templates
- m365-security
- tier3
ms.topic: how-to
search.appverid: met150
ms.openlocfilehash: dcc7d486b41d6a60a0fbda1c8398e81e8516d093
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68222878"
---
# <a name="connect-microsoft-defender-for-office-365-to-microsoft-sentinel"></a>Conectar Microsoft Defender para Office 365 a Microsoft Sentinel

Puede ingerir los datos de Microsoft Defender para Office 365 (*y* datos del resto del conjunto de Microsoft 365 Defender), incluidos los incidentes, en Microsoft Sentinel.

Aproveche la administración de eventos de información de seguridad (SIEM) enriquecida combinada con datos de otros orígenes de Microsoft 365, la sincronización de incidentes y alertas y la búsqueda avanzada.

> [!IMPORTANT]
> El conector de Microsoft 365 Defender está actualmente en **versión preliminar**. Consulte los Términos de uso complementarios para las versiones preliminares de Microsoft Azure para obtener más términos legales que se aplican a las características de Azure que están en versión beta, versión preliminar o que aún no se han publicado en la disponibilidad general.>

## <a name="what-you-will-need"></a>Lo que necesitará
- Microsoft Defender para Office 365 Plan 2 o superior. (Incluido en los planes E5)
- [Guía de inicio rápido de](/azure/sentinel/quickstart-onboard) Microsoft Sentinel.
- Permisos suficientes (administrador de seguridad en M365 & permisos de lectura y escritura en Sentinel).

## <a name="add-the-microsoft-365-defender-connector"></a>Agregar el conector de Microsoft 365 Defender
1. [Inicie sesión en Azure Portal](https://portal.azure.com) y vaya a **Microsoft Sentinel** > Elija el área de trabajo pertinente para integrarla con Microsoft 365 Defender
    1. En el menú de navegación izquierdo situado debajo del encabezado **Configuración** > elija **Conectores de datos**.
2. Cuando se cargue la página, **busque** Microsoft 365 Defender **y seleccione el conector Microsoft 365 Defender (versión preliminar).**
3. En el control flotante derecho, seleccione **Abrir página del conector**.
4. En la sección **Configuración** de la página que se carga, seleccione **Conectar incidentes & alertas**, dejando desactivadas todas las reglas de creación de incidentes de Microsoft para estos productos.
5. Desplácese hasta **Microsoft Defender para Office 365** en la sección **Conectar eventos** de la página. Seleccione **EmailEvents, EmailUrlInfo, EmailAttachmentInfo & EmailPostDeliveryEvents** y, a continuación,  **Aplicar cambios** en la parte inferior de la página. (Elija tablas de otros productos de Defender si es útil y aplicable, durante este paso).

## <a name="next-steps"></a>Pasos siguientes

Ahora, los administradores podrán ver incidentes, alertas y datos sin procesar en Microsoft Sentinel y usar estos datos para la *búsqueda avanzada*, pivotando sobre los datos nuevos y existentes de Microsoft Defender.

## <a name="more-information"></a>Más información

[Conexión de datos Microsoft 365 Defender a Microsoft Sentinel | Microsoft Docs](/azure/sentinel/connect-microsoft-365-defender?tabs=MDE)

[Conexión de Microsoft Teams a Microsoft Sentinel](/microsoftteams/teams-sentinel-guide)
