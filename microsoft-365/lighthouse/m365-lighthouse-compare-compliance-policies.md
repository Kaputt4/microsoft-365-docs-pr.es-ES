---
title: Comparar la configuración de directiva de cumplimiento de dispositivos
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Para los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga información sobre cómo comparar la configuración de directiva de cumplimiento de dispositivos.
ms.openlocfilehash: 05f67cda1e99aff0b43109c5f55f78efaf30049c
ms.sourcegitcommit: f3c912780bbcf5a5b47de192202adb3afbd5952b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2022
ms.locfileid: "62219030"
---
# <a name="compare-device-compliance-policy-settings"></a>Comparar la configuración de directiva de cumplimiento de dispositivos

> [!NOTE]
> Las características descritas en este artículo están en Versión preliminar, están sujetas a cambios y solo están disponibles para los partners que cumplen los [requisitos](m365-lighthouse-requirements.md). Si su organización no tiene Microsoft 365 Lighthouse, vea [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).

Microsoft 365 Lighthouse permite ver directivas de cumplimiento en todos los inquilinos en una sola vista. Puede impulsar la seguridad y la estandarización en todos los inquilinos comparando directivas. Puede filtrar las vistas para ver las opciones que se han configurado (frente a las opciones que no se han configurado), las opciones que difieren en sus configuraciones o simplemente las que coinciden. También puede buscar la configuración específica que le interesa y ver cómo se compara entre las directivas.

## <a name="before-you-begin"></a>Antes de empezar

- Los dispositivos deben tener una licencia de Intune y estar inscritos en Microsoft Endpoint Manager (MEM).

## <a name="compare-policy-settings"></a>Comparar la configuración de directiva

1. En el panel de navegación izquierdo de Lighthouse, seleccione **Dispositivos**.

2. Seleccione la pestaña **Directivas**.

3. En la **lista** desplegable Filtros, seleccione un sistema operativo/plataforma.

   > [!NOTE]
   > Solo puede comparar directivas con el mismo sistema operativo o plataforma.

4. En la lista filtrada, seleccione hasta tres directivas que desee comparar.

5. Seleccione **Comparar**.

Puede filtrar los resultados para ver Configuración **diferentes**, **Configuración que** coincidan o **Configuración de configuración**.

## <a name="configure-a-policy-setting"></a>Configurar una configuración de directiva

1. En el panel de navegación izquierdo de Lighthouse, seleccione **Dispositivos**.

2. Seleccione la pestaña **Directivas**.

3. En la lista, seleccione un nombre de directiva.

4. En el panel Detalles de directiva, seleccione **Ver esta directiva en Microsoft Endpoint Manager**.

5. En MEM, edite la configuración de directiva según sea necesario.

## <a name="next-steps"></a>Siguientes pasos

A medida que realiza ajustes de directiva, asegúrese de evaluar los cambios con respecto a la configuración de línea base actual. Para obtener más información, vea [Overview of using baselines to deploy standard tenant configurations](m365-lighthouse-deploy-standard-tenant-configurations-overview.md).

## <a name="related-content"></a>Contenido relacionado

[¿Qué es la inscripción de dispositivos en Intune?](/mem/intune/enrollment/device-enrollment) (artículo)  
[Usar directivas de cumplimiento para establecer reglas para los dispositivos que administra con Intune](/mem/intune/protect/device-compliance-get-started) (artículo)  
[Información general sobre el uso de líneas base para implementar configuraciones de inquilino estándar](m365-lighthouse-deploy-standard-tenant-configurations-overview.md) (artículo)
