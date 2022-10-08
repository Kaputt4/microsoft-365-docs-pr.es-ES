---
title: Activar la protección en la nube en Microsoft Defender Antivirus
description: Active la protección en la nube para beneficiarse de características de protección rápidas y avanzadas.
keywords: Microsoft Defender Antivirus, antimalware, seguridad, nube, bloquear a primera vista
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.date: 02/03/2022
ms.reviewer: mkaminska
manager: dansimp
ms.custom: nextgen
ms.subservice: mde
ms.collection:
- m365-security
- tier2
search.appverid: met150
ms.openlocfilehash: b46457a8215fc1eb5480558b6aa68fcf34029de6
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68174872"
---
# <a name="turn-on-cloud-protection-in-microsoft-defender-antivirus"></a>Activar la protección en la nube en Microsoft Defender Antivirus

**Se aplica a:**

- Antivirus de Microsoft Defender
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

**Plataformas**
- Windows

[La protección en la nube en Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md) ofrece una protección precisa, en tiempo real y inteligente. La protección en la nube debe estar habilitada de forma predeterminada; sin embargo, puede configurar la protección en la nube para satisfacer las necesidades de su organización.

## <a name="methods-to-configure-cloud-protection"></a>Métodos para configurar la protección en la nube

Puede activar o desactivar Microsoft Defender protección antivirus en la nube mediante uno de los métodos siguientes:

- Microsoft Endpoint Manager, que incluye Microsoft Intune y Configuration Manager
- Directiva de grupo
- Cmdlets de PowerShell

También puede activar o desactivar la protección en la nube en puntos de conexión individuales mediante la aplicación Seguridad de Windows. 

Para obtener más información sobre los requisitos específicos de conectividad de red para asegurarse de que los puntos de conexión se pueden conectar al servicio de protección en la nube, consulte [Configuración y validación de conexiones de red](configure-network-connections-microsoft-defender-antivirus.md).

> [!NOTE]
> En Windows 10 y Windows 11, no hay ninguna diferencia entre las opciones de informes **Básico** y **Avanzado** que se describen en este artículo. Se trata de una distinción heredada y elegir cualquiera de las opciones dará como resultado el mismo nivel de protección en la nube. No hay ninguna diferencia en el tipo o la cantidad de información que se comparte. Para obtener más información sobre lo que recopilamos, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=521839).

## <a name="use-intune-to-turn-on-cloud-protection"></a>Uso de Intune para activar la protección en la nube

1. Vaya al Centro de administración de Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) e inicie sesión.

2. En el panel **Inicio** , seleccione **Configuración del dispositivo > Perfiles**.

3. Seleccione el tipo **de perfil Restricciones** de dispositivos que desea configurar. Si necesita crear un nuevo tipo **de perfil Restricciones** de dispositivos, consulte [Configuración de las opciones de restricción de dispositivos en Microsoft Intune](/intune/device-restrictions-configure).

4. Seleccione **Propiedades** \> **Configuración: Editar** \> **Microsoft Defender Antivirus**.

5. En el conmutador **Protección entregada en la nube** , seleccione **Habilitar**.

6. En la lista desplegable **Preguntar a los usuarios antes del envío de ejemplo** , seleccione **Enviar todos los datos automáticamente**.

Para obtener más información sobre Intune perfiles de dispositivo, incluido cómo crear y configurar sus opciones, consulte [¿Qué son Microsoft Intune perfiles de dispositivo?](/intune/device-profiles)

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-protection"></a>Uso de Microsoft Endpoint Manager para activar la protección en la nube

1. Vaya al Centro de administración de Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) e inicie sesión.

2. Elija **Antivirus de seguridad** \> de puntos de conexión.

3. Seleccione un perfil de antivirus. (Si aún no tiene uno, o si desea crear un nuevo perfil, consulte [Configuración de las opciones de restricción de dispositivos en Microsoft Intune](/intune/device-restrictions-configure).

4. Seleccione **Propiedades**. A continuación, junto a **Configuración,** elija **Editar**.

5. Expanda **Protección** en la nube y, a continuación, en la lista **Nivel de protección entregado** en la nube, seleccione una de las siguientes opciones:
   - **Alto**: aplica un alto nivel de detección.
   - **Plus alto**: usa el nivel **alto** y aplica más medidas de protección (puede afectar al rendimiento del cliente).
   - **Tolerancia cero**: bloquea todos los ejecutables desconocidos.

6. Seleccione **Revisar y guardar** y, a continuación, elija **Guardar**.

Para obtener más información sobre cómo configurar Configuration Manager de punto de conexión de Microsoft, consulte [Creación e implementación de directivas antimalware: servicio de protección en la nube](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service).

## <a name="use-group-policy-to-turn-on-cloud-protection"></a>Uso de directiva de grupo para activar la protección en la nube

1. En el dispositivo de administración de directiva de grupo, abra la [consola de administración de directiva de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), haga clic con el botón derecho en el objeto directiva de grupo que desea configurar y seleccione **Editar**.

2. En el **Editor de administración de directiva de grupo**, vaya a **Configuración del equipo**.

3. Seleccione **Plantillas administrativas**.

4. Expanda el árbol a **componentes** >  de Windows **Microsoft Defender Antivirus > MAPS**

    > [!NOTE]
    > La configuración de MAPS es igual a la protección proporcionada por la nube.

5. Haga doble clic en **Unirse a Microsoft MAPS**. Asegúrese de que la opción está activada y establecida en **MAPAS básicos** o **MAPAS avanzados**. Seleccione **Aceptar**.

    Puede elegir enviar información básica o adicional sobre el software detectado:

    - MAPAS básicos: la pertenencia básica enviará información básica a Microsoft sobre malware y software potencialmente no deseado que se ha detectado en el dispositivo. La información incluye de dónde procede el software (como direcciones URL y rutas de acceso parciales), las acciones realizadas para resolver la amenaza y si las acciones se realizaron correctamente.

    - MAPAS avanzados: además de la información básica, la pertenencia avanzada enviará información detallada sobre malware y software potencialmente no deseado, incluida la ruta de acceso completa al software, e información detallada sobre cómo el software ha afectado a su dispositivo.

6. Haga doble clic en **Enviar ejemplos de archivos cuando se requiera un análisis adicional**. Asegúrese de que la primera opción está establecida en **Habilitado** y de que las otras opciones están establecidas en:

   - **Envío de muestras seguras** (1)
   - **Enviar todos los ejemplos** (3)

   >[!NOTE]
   > La opción **Enviar ejemplos seguros** (1) significa que la mayoría de las muestras se enviarán automáticamente. Los archivos que probablemente contengan información personal seguirán solicitando y requieren confirmación adicional.
   > Al establecer la opción **en Always Prompt** (0), se reducirá el estado de protección del dispositivo. Establecerlo en **Nunca enviar** (2) significa que la característica [Bloquear a primera vista](configure-block-at-first-sight-microsoft-defender-antivirus.md) de Microsoft Defender para punto de conexión no funcionará.

7. Seleccione **Aceptar**.

## <a name="use-powershell-cmdlets-to-turn-on-cloud-protection"></a>Uso de cmdlets de PowerShell para activar la protección en la nube

Los siguientes cmdlets pueden activar la protección en la nube:

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

Para obtener más información sobre cómo usar PowerShell con Microsoft Defender Antivirus, consulte [Uso de cmdlets de PowerShell para configurar y ejecutar Microsoft Defender antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) y [cmdlets Microsoft Defender Antivirus](/powershell/module/defender/). [CSP de directiva: Defender](/windows/client-management/mdm/policy-csp-defender) también tiene más información específicamente sobre [-SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent).

> [!IMPORTANT]
> Puede establecer **-SubmitSamplesConsent** en `SendSafeSamples` (el valor predeterminado, recomendado), `NeverSend`o `AlwaysPrompt`. La `SendSafeSamples` configuración significa que la mayoría de los ejemplos se enviarán automáticamente. Los archivos que probablemente contengan información personal darán lugar a un aviso para continuar y requerirán confirmación.
> La `NeverSend` configuración y `AlwaysPrompt` reducen el nivel de protección del dispositivo. Además, la `NeverSend` configuración significa que la característica [Bloquear a primera vista](configure-block-at-first-sight-microsoft-defender-antivirus.md) de Microsoft Defender para punto de conexión no funcionará.

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-protection"></a>Uso de Instrucciones de administración de Windows (WMI) para activar la protección en la nube

Use el [método **Set** de la clase **MSFT_MpPreference**](/previous-versions/windows/desktop/defender/set-msft-mppreference) para las siguientes propiedades:

```WMI
MAPSReporting
SubmitSamplesConsent
```

Para obtener más información sobre los parámetros permitidos, consulte [Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

## <a name="turn-on-cloud-protection-on-individual-clients-with-the-windows-security-app"></a>Activar la protección en la nube en clientes individuales con la aplicación Seguridad de Windows

> [!NOTE]
> Si la opción **Configurar la configuración local para informar de microsoft MAPS** directiva de grupo está establecida en **Deshabilitado**, la configuración de **protección basada en la nube** en Configuración de Windows se atenuará y no estará disponible. Los cambios realizados a través de un objeto de directiva de grupo deben implementarse en primer lugar en los extremos individuales antes de que se actualice la configuración en la configuración de Windows.

1. Abra la aplicación Seguridad de Windows seleccionando el icono de escudo en la barra de tareas o buscando **Seguridad de Windows** en el menú inicio.

2. Seleccione el icono **Protección contra amenazas de Virus &** (o el icono de escudo en la barra de menús de la izquierda) y, a continuación, en **Administrar configuración** , seleccione **Virus & configuración de protección contra amenazas**.

   :::image type="content" source="../../media/wdav-protection-settings-wdsc.png" alt-text="Configuración de protección contra amenazas de Virus &" lightbox="../../media/wdav-protection-settings-wdsc.png":::

3. Confirme que **la protección basada en la nube** y el **envío automático de ejemplos** cambien a **Activado**.

   > [!NOTE]
   > Si el envío automático de ejemplo se ha configurado con directiva de grupo, la configuración se atenuará y no estará disponible.

> [!TIP]
> Si busca información relacionada con el antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características iOS](ios-configure-features.md)

## <a name="see-also"></a>Vea también

- [Uso de la protección en la nube de Microsoft en Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md)

- [Creación e implementación de directivas antimalware: servicio de protección en la nube](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)

- [Usar cmdlets PowerShell para administrar el Antivirus de Windows Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md)
