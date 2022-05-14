---
title: Especificar el nivel de protección en la nube para Antivirus de Microsoft Defender
description: Establezca el nivel de protección en la nube para Antivirus de Microsoft Defender.
keywords: Antivirus de Microsoft Defender, antimalware, seguridad, defender, nube, agresividad, nivel de protección
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.date: 08/26/2021
ms.reviewer: mkaminska
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.collection: M365-security-compliance
ms.openlocfilehash: 1f71e5cc2a944ce409a19b6493bda1b40747a066
ms.sourcegitcommit: ebbe8713297675db5dcb3e0d9c3ae5e746b99196
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2022
ms.locfileid: "65417488"
---
# <a name="specify-the-cloud-protection-level"></a>Especificar el nivel de protección en la nube

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

La protección en la nube funciona junto con Antivirus de Microsoft Defender para ofrecer protección a los puntos de conexión mucho más rápido que a través de las actualizaciones de inteligencia de seguridad tradicionales. Puede configurar el nivel de protección en la nube mediante Microsoft Endpoint Manager (recomendado) o directiva de grupo.

> [!NOTE]
> Al seleccionar **Alta**, **Alta +** o **Cero tolerancia** , se podrían detectar algunos archivos legítimos. Si esto sucede, puede desbloquear el archivo detectado o disputar esa detección en el portal de Microsoft 365 Defender.

## <a name="use-microsoft-endpoint-manager-to-specify-the-level-of-cloud-protection"></a>Uso de Microsoft Endpoint Manager para especificar el nivel de protección en la nube

1. Vaya al centro de administración de Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) e inicie sesión.

2. Elija **Antivirus de seguridad** \> de puntos de conexión.

3. Seleccione un perfil de antivirus. (Si aún no tiene uno, o si desea crear un nuevo perfil, consulte [Configuración de las opciones de restricción de dispositivos en Microsoft Intune](/intune/device-restrictions-configure).

4. Seleccione **Propiedades**. A continuación, junto a **Configuración,** elija **Editar**.

5. Expanda **Protección** en la nube y, a continuación, en la lista **Nivel de protección entregado** en la nube, seleccione una de las siguientes opciones:

    - **No configurado**: estado predeterminado.
    - **Alto**: aplica un alto nivel de detección.
    - **Plus alto**: usa el nivel **Alto** y aplica medidas de protección adicionales (podrían afectar al rendimiento del cliente).
    - **Tolerancia cero**: bloquea todos los ejecutables desconocidos.

6. Elija **Revisar y guardar** y, a continuación, elija **Guardar**.

> [!TIP]
> ¿Necesitas ayuda? Vea los siguientes recursos:
>
> - [Configurar Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
> - [Adición de la configuración de Endpoint Protection en Intune](/mem/intune/protect/endpoint-protection-configure)

## <a name="use-group-policy-to-specify-the-level-of-cloud-protection"></a>Uso de directiva de grupo para especificar el nivel de protección en la nube

1. En la máquina de administración de directiva de grupo, abra la [consola de administración de directiva de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).

2. Haga clic con el botón derecho en el objeto directiva de grupo que desea configurar y, a continuación, seleccione **Editar**.

3. En directiva de grupo **Editor de administración**, vaya a **Configuración** \> del equipo **Plantillas administrativas**.

4. Expanda el árbol para **Windows Components** \> **Antivirus de Microsoft Defender** \> **MpEngine**.

5. Haga doble clic en la opción **Seleccionar nivel de protección** en la nube y establézcala en **Habilitado**. Seleccione el nivel de protección:

    - **No configurado**: estado predeterminado.
    - **El nivel de bloqueo predeterminado** proporciona una detección segura sin aumentar el riesgo de detectar archivos legítimos.
    - **El nivel de bloqueo moderado** solo proporciona moderación para las detecciones de alta confianza.
    - **El alto nivel de bloqueo** aplica un alto nivel de detección al tiempo que optimiza el rendimiento del cliente (pero también puede ofrecer una mayor posibilidad de falsos positivos).
    - **Alto nivel de bloqueo** aplica medidas de protección adicionales (podrían afectar al rendimiento del cliente y aumentar la posibilidad de falsos positivos).
    - **El nivel de bloqueo de tolerancia cero** bloquea todos los ejecutables desconocidos.

6. Seleccione **Aceptar**.

7. Implemente el objeto directiva de grupo actualizado. Consulte [directiva de grupo Management Console](/windows/win32/srvnodes/group-policy)

> [!TIP]
> ¿Usa directiva de grupo Objetos en el entorno local? Vea cómo se traducen en la nube. [Analice los objetos de directiva de grupo locales mediante directiva de grupo análisis en Microsoft Endpoint Manager - Versión preliminar](/mem/intune/configuration/group-policy-analytics).

> [!TIP]
> Si busca información relacionada con antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características iOS](ios-configure-features.md)
  
## <a name="see-also"></a>Vea también

[¿Por qué se debe habilitar la protección en la nube para Antivirus de Microsoft Defender](why-cloud-protection-should-be-on-mdav.md)
