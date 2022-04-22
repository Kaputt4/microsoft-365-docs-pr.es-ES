---
title: Comparar la configuración de la directiva de cumplimiento de dispositivos en Microsoft 365 Lighthouse
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
description: En el caso de los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga información sobre cómo comparar la configuración de directivas de cumplimiento de dispositivos.
ms.openlocfilehash: 1ea7a278a58cd6d864c32ab7b25569ae463658f9
ms.sourcegitcommit: 339d2c2ffea06726f69429f73c1113c649f37b18
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2022
ms.locfileid: "65022778"
---
# <a name="compare-device-compliance-policy-settings-in-microsoft-365-lighthouse"></a>Comparar la configuración de la directiva de cumplimiento de dispositivos en Microsoft 365 Lighthouse

Microsoft 365 Lighthouse permite ver las directivas de cumplimiento entre los inquilinos en una sola vista. Puede impulsar la seguridad y la estandarización entre los inquilinos mediante la comparación de directivas. Puede filtrar las vistas para ver la configuración que se ha configurado (frente a la configuración que no se ha configurado), la configuración que difiere en sus configuraciones o la configuración que coincide. También puede buscar configuraciones específicas para ver cómo se comparan entre directivas.

## <a name="before-you-begin"></a>Antes de empezar

Asegúrese de que los dispositivos tengan una licencia de Microsoft Intune y que estén inscritos en Microsoft Endpoint Manager (MEM).

## <a name="compare-policy-settings"></a>Comparación de la configuración de directiva

1. En el panel de navegación izquierdo de Lighthouse, seleccione **Dispositivos**.

2. Seleccione la pestaña **Directivas**.

3. En la lista desplegable **Filtros** , seleccione un sistema operativo o una plataforma.

   > [!NOTE]
   > Solo puede comparar directivas con el mismo sistema operativo o plataforma.

4. En la lista filtrada, seleccione hasta tres directivas que quiera comparar.

5. Seleccione **Comparar**.

Puede filtrar los resultados para ver **Configuración que difieren**, **Configuración que coinciden** o **configuración configurada**.

## <a name="configure-a-policy-setting"></a>Configuración de una directiva

1. En el panel de navegación izquierdo de Lighthouse, seleccione **Dispositivos**.

2. Seleccione la pestaña **Directivas**.

3. En la lista, seleccione un nombre de directiva.

4. En el panel Detalles de la directiva, seleccione **Ver esta directiva en Microsoft Endpoint Manager**.

5. En MEM, edite la configuración de directiva según sea necesario.

## <a name="next-steps"></a>Siguientes pasos

A medida que realice ajustes de directiva, asegúrese de evaluar los cambios con respecto a la configuración de línea base actual. Para obtener más información, consulte [Información general sobre el uso de líneas base para implementar configuraciones de inquilino estándar](m365-lighthouse-deploy-standard-tenant-configurations-overview.md).

## <a name="related-content"></a>Contenido relacionado

[¿Qué es la inscripción de dispositivos en Intune?](/mem/intune/enrollment/device-enrollment) (artículo)  
[Usar directivas de cumplimiento para establecer reglas para los dispositivos que administra con Intune](/mem/intune/protect/device-compliance-get-started) (artículo)  
[Información general sobre el uso de líneas base de Microsoft 365 Lighthouse para implementar configuraciones de inquilino estándar](m365-lighthouse-deploy-standard-tenant-configurations-overview.md) (artículo)
