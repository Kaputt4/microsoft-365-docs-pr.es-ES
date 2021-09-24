---
title: Especifique el nivel de protección de nube para Antivirus de Microsoft Defender
description: Establece el nivel de protección en la nube para Antivirus de Microsoft Defender.
keywords: Antivirus de Microsoft Defender, antimalware, seguridad, defensa, nube, agresividad, nivel de protección
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.date: 08/26/2021
ms.reviewer: mkaminska
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.collection: M365-security-compliance
ms.openlocfilehash: 16d61be33af8a4d30090470e066111ba2bcde0e9
ms.sourcegitcommit: 584445b62cb82218597b62495fb76fcb5b12af9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2021
ms.locfileid: "59497997"
---
# <a name="specify-the-cloud-protection-level"></a>Especificar el nivel de protección en la nube

**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)
- Antivirus de Microsoft Defender

La protección en la nube funciona Antivirus de Microsoft Defender para ofrecer protección a los puntos de conexión mucho más rápido que a través de las actualizaciones de inteligencia de seguridad tradicionales. Puede configurar el nivel de protección en la nube mediante Microsoft Endpoint Manager (recomendado) o la directiva de grupo.

> [!NOTE]
> Si se **selecciona High,** **High +** o **Zero tolerance,** es posible que se detecten algunos archivos legítimos. Si esto ocurre, puede desbloquear el archivo detectado o la disputa que se detecte en el portal Microsoft 365 Defender web.

## <a name="use-microsoft-endpoint-manager-to-specify-the-level-of-cloud-protection"></a>Use Microsoft Endpoint Manager para especificar el nivel de protección en la nube

1. Vaya al Centro Microsoft Endpoint Manager de administración ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e inicie sesión.

2. Elija **Endpoint security** \> **Antivirus**.

3. Seleccione un perfil antivirus. (Si aún no tienes uno, o si quieres crear un perfil nuevo, consulta Configurar la configuración de restricción de [dispositivos en Microsoft Intune](/intune/device-restrictions-configure).

4. Seleccione **Propiedades**. A continuación, junto **a Configuración,** elija **Editar**.

5. Expanda **Protección en la** nube y, a continuación, en la lista Nivel de protección entregado en **la** nube, seleccione una de las siguientes opciones:

    - **High:** aplica un nivel de detección fuerte.
    - **High plus:** usa el **nivel alto** y aplica medidas de protección adicionales (puede afectar al rendimiento del cliente).
    - **Tolerancia cero:** bloquea todos los ejecutables desconocidos.

6. Elija **Revisar + guardar** y, a continuación, elija **Guardar**.

> [!TIP]
> ¿Necesita ayuda? Vea los siguientes recursos:
>
> - [Configurar Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
> - [Agregar configuración de protección de puntos de conexión en Intune](/mem/intune/protect/endpoint-protection-configure)

## <a name="use-group-policy-to-specify-the-level-of-cloud-protection"></a>Usar la directiva de grupo para especificar el nivel de protección en la nube

1. En el equipo de administración de directivas de grupo, abra la Consola [de administración de directivas de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).

2. Haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y, a continuación, **seleccione Editar**.

3. En el **Editor de administración de directivas de grupo** vaya a **Configuración** del equipo \> **Plantillas administrativas.**

4. Expanda el árbol para **Windows componentes** \> **Antivirus de Microsoft Defender** \> **MpEngine**.

5. Haga doble clic en la **configuración Seleccionar nivel de** protección en la nube y estabóla en **Habilitado**. Seleccione el nivel de protección:
    - **El nivel de bloqueo predeterminado** proporciona una detección segura sin aumentar el riesgo de detectar archivos legítimos.
    - **El nivel de bloqueo moderado** proporciona moderación solo para detecciones de elevada confianza
    - **El nivel alto de bloqueo** aplica un alto nivel de detección a la vez que optimiza el rendimiento del cliente (pero también puede ofrecer una mayor probabilidad de falsos positivos).
    - **El nivel alto + de bloqueo** aplica medidas de protección adicionales (puede afectar al rendimiento del cliente y aumentar la probabilidad de falsos positivos).
    - **El nivel de bloqueo de tolerancia cero** bloquea todos los ejecutables desconocidos.

6. Seleccione **Aceptar**.

7. Implemente el objeto de directiva de grupo actualizado. Consulta [Consola de administración de directivas de grupo](/windows/win32/srvnodes/group-policy)

> [!TIP]
> ¿Usa objetos de directiva de grupo local? Vea cómo se traducen en la nube. [Analice los objetos de directiva de grupo locales mediante el análisis](/mem/intune/configuration/group-policy-analytics)de directivas de grupo en Microsoft Endpoint Manager - Vista previa . 
  
## <a name="see-also"></a>Ver también

[¿Por qué se debe habilitar la protección en la nube para Antivirus de Microsoft Defender](why-cloud-protection-should-be-on-mdav.md)
