---
title: Configurar la integración con Microsoft Cloud App Security
ms.reviewer: ''
description: Obtenga información sobre cómo activar la configuración para habilitar la integración de Microsoft Defender para endpoints con Microsoft Cloud App Security.
keywords: nube, aplicación, seguridad, configuración, integración, detección, informe
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4f7aca5cb532510d55042c70d04d65f2aa08baa3
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844759"
---
# <a name="configure-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a>Configurar Microsoft Cloud App Security en Microsoft Defender para endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Para beneficiarse de las señales de detección de aplicaciones en la nube de Microsoft Defender para endpoint, activa Microsoft Cloud App Security integración.

>[!NOTE]
>Esta característica estará disponible con una licencia E5 para [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) en dispositivos que ejecutan Windows 10, versión 1709 (compilación del sistema operativo 16299.1085 con [KB4493441](https://support.microsoft.com/help/4493441)), Windows 10, versión 1803 (compilación del sistema operativo 17134.704 con [KB4493464](https://support.microsoft.com/help/4493464)), Windows 10, versión 1809 (compilación del sistema operativo 17763.379 con [KB4489899)](https://support.microsoft.com/help/4489899)o versiones Windows 10 posteriores.

> Consulta [Integración de Microsoft Defender para endpoints con Microsoft Cloud App Security](/cloud-app-security/mde-integration) para obtener información detallada sobre la integración de Microsoft Defender para Endpoint con Microsoft Cloud App Security. 

## <a name="enable-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a>Habilitar Microsoft Cloud App Security en Microsoft Defender para endpoint

1. En el panel de navegación, seleccione **Configuración de**  >  **preferencias Características avanzadas**.
2. Seleccione **Microsoft Cloud App Security** y cambie la alternancia a **On**.
3. Haga clic **en Guardar preferencias**.

Una vez activado, Microsoft Defender para endpoint iniciará inmediatamente el reenvío de señales de detección a Cloud App Security.

## <a name="view-the-data-collected"></a>Ver los datos recopilados

Para ver y obtener acceso a los datos de Microsoft Defender para puntos de conexión en Microsoft Cloud Apps Security, vea [Investigar dispositivos en Cloud App Security](/cloud-app-security/mde-integration#investigate-devices-in-cloud-app-security).


Para obtener más información acerca de la detección en la nube, consulta [Trabajar con aplicaciones detectadas.](/cloud-app-security/discovered-apps)

Si está interesado en probar Microsoft Cloud App Security, vea [Microsoft Cloud App Security trial](https://signup.microsoft.com/Signup?OfferId=757c4c34-d589-46e4-9579-120bba5c92ed&ali=1).

## <a name="related-topic"></a>Tema relacionado
- [Microsoft Cloud App Security integración](microsoft-cloud-app-security-integration.md)
