---
title: Activar la protección entregada en la nube en Antivirus de Microsoft Defender
description: Active la protección entregada en la nube para beneficiarse de las características de protección rápidas y avanzadas.
keywords: Antivirus de Microsoft Defender, antimalware, seguridad, nube, bloquear a primera vista
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 05/18/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 8c45fb4b60e3c20c2001cc0008ecc8154e854273
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572062"
---
# <a name="turn-on-cloud-delivered-protection"></a>Activar la protección proporcionada en la nube

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> El Antivirus de Microsoft Defender en la nube es un mecanismo para ofrecer protección actualizada a la red y los puntos de conexión. Aunque se denomina servicio en la nube, no es simplemente protección para los archivos almacenados en la nube; en su lugar, usa recursos distribuidos y aprendizaje automático para ofrecer protección a los puntos de conexión a una velocidad mucho más rápida que las actualizaciones de inteligencia de seguridad tradicionales.

Antivirus de Microsoft Defender varias tecnologías de detección y prevención para ofrecer una protección precisa, en tiempo real e inteligente. [Conozca las tecnologías avanzadas en el núcleo de La](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)protección de última generación de Microsoft Defender para endpoint.

Puede activar o desactivar la Antivirus de Microsoft Defender de entrega en la nube de varias maneras:

- Microsoft Intune
- Microsoft Endpoint Manager
- Directiva de grupo
- Cmdlets de PowerShell.

 También puedes activarla o desactivarla en clientes individuales con la Seguridad de Windows aplicación.

Consulte [Usar la protección entregada en la nube de Microsoft](cloud-protection-microsoft-defender-antivirus.md) para obtener información general Antivirus de Microsoft Defender protección entregada en la nube.

Para obtener más información acerca de los requisitos específicos de conectividad de red para garantizar que los puntos de conexión se puedan conectar al servicio de protección entregado en la nube, vea [Configure and validate network connections](configure-network-connections-microsoft-defender-antivirus.md).

> [!NOTE]
> En Windows 10, no hay ninguna diferencia  entre  las opciones de informes básicas y avanzadas que se describen en este tema. Esta es una distinción heredada y elegir cualquiera de las dos opciones dará como resultado el mismo nivel de protección entregada en la nube. No hay ninguna diferencia en el tipo o la cantidad de información que se comparte. Para obtener más información sobre lo que recopilamos, vea la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=521839).

## <a name="use-intune-to-turn-on-cloud-delivered-protection"></a>Usar Intune para activar la protección entregada en la nube

1. Vaya al Centro Microsoft Endpoint Manager administración ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e inicie sesión.

2. En el **panel Inicio,** seleccione **Configuración del dispositivo > perfiles**.

3. Seleccione el **tipo de perfil Restricciones de** dispositivo que desea configurar. Si necesitas crear un nuevo tipo de perfil **de restricciones** de dispositivo, consulta Configurar la configuración de restricción de dispositivo [en Microsoft Intune](/intune/device-restrictions-configure).

4. Seleccionar **opciones de** configuración de  >  **propiedades: editar**  >  **Antivirus de Microsoft Defender**.

5. En el **conmutador de protección entregado en** la nube, seleccione **Habilitar**.

6. En la lista **desplegable Preguntar a los usuarios antes** del envío de ejemplo, seleccione Enviar todos los datos **automáticamente.**

Para obtener más información acerca de los perfiles de dispositivo de Intune, incluido cómo crear y configurar sus opciones, consulta ¿Qué Microsoft Intune [perfiles de dispositivo?](/intune/device-profiles)

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-delivered-protection"></a>Usar Microsoft Endpoint Manager para activar la protección entregada en la nube

1. Vaya al Centro Microsoft Endpoint Manager administración ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e inicie sesión.

2. Elija **Endpoint security**  >  **Antivirus**.

3. Seleccione un perfil antivirus. (Si aún no tienes uno, o si quieres crear un perfil nuevo, consulta Configurar la configuración de restricción de [dispositivos en Microsoft Intune](/intune/device-restrictions-configure).

4. Seleccione **Propiedades**. A continuación, junto **a Configuración,** elija **Editar**.

5. Expanda **Protección en la** nube y, a continuación, en la lista Nivel de protección entregado en **la** nube, seleccione una de las siguientes opciones:
   - **High:** aplica un nivel de detección fuerte.
   - **High plus:** usa el **nivel alto** y aplica medidas de protección adicionales (puede afectar al rendimiento del cliente).
   - **Tolerancia cero:** bloquea todos los ejecutables desconocidos.

6. Seleccione **Revisar y guardar** y, a continuación, elija **Guardar**.

Para obtener más información sobre cómo configurar Microsoft Endpoint Configuration Manager, vea [How to create and deploy antimalware policies: Cloud-protection service](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service).

## <a name="use-group-policy-to-turn-on-cloud-delivered-protection"></a>Usar la directiva de grupo para activar la protección entregada en la nube

1. En el dispositivo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y **seleccione Editar**.

2. En el **Editor de administración de directivas de** grupo, vaya a Configuración del **equipo**.

3. Seleccione **Plantillas administrativas**.

4. Expanda el árbol para Windows **componentes > Antivirus de Microsoft Defender > MAPS**

5. Haga doble clic **en Unirse a Microsoft MAPS**. Asegúrese de que la opción está activada y establecida en **Mapas** básicos o **mapas avanzados**. Seleccione **Aceptar**.

6. Haga doble clic en **Enviar ejemplos de archivos cuando sea necesario realizar un análisis adicional.** Asegúrese de que la primera opción esté establecida en **Enabled** y de que las demás opciones estén establecidas en:

    1. **Enviar muestras seguras** (1)
    2. **Enviar todos los ejemplos** (3)

        >[!NOTE]
        > La **opción Enviar muestras seguras** (1) significa que la mayoría de las muestras se enviarán automáticamente. Los archivos que probablemente contengan información personal seguirán solicitando y necesitarán confirmación adicional.
        > Al establecer la opción **en Preguntar siempre** (0), se disminuirá el estado de protección del dispositivo. Establecerlo en **Nunca enviar** (2) significa que la característica Bloquear a primera [vista](configure-block-at-first-sight-microsoft-defender-antivirus.md) de Microsoft Defender para endpoint no funcionará.

7. Seleccione **Aceptar**.

## <a name="use-powershell-cmdlets-to-turn-on-cloud-delivered-protection"></a>Usar cmdlets de PowerShell para activar la protección entregada en la nube

Los cmdlets siguientes pueden activar la protección entregada en la nube:

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

Para obtener más información sobre cómo usar PowerShell con Antivirus de Microsoft Defender, vea [Use PowerShell cmdlets to configure and run Antivirus de Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/). [CSP de directiva: Defender](/windows/client-management/mdm/policy-csp-defender) también tiene más información específica sobre [-SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent).

>[!NOTE]
> También puede establecer **-SubmitSamplesConsent** en `SendSafeSamples` (la configuración predeterminada), `NeverSend` o `AlwaysPrompt` . La `SendSafeSamples` configuración significa que la mayoría de las muestras se enviarán automáticamente. Los archivos que probablemente contengan información personal seguirán solicitando y necesitarán confirmación adicional.

>[!WARNING]
> Establecer **-SubmitSamplesConsent** en `NeverSend` o `AlwaysPrompt` disminuirá el nivel de protección del dispositivo. Además, establecerlo en significa que la característica Bloquear a primera vista de Microsoft Defender para endpoint `NeverSend` no funcionará. [](configure-block-at-first-sight-microsoft-defender-antivirus.md)

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-delivered-protection"></a>Use Windows Management Instruction (WMI) para activar la protección entregada en la nube

Utilice el [ **método Set** de la **clase MSFT_MpPreference**](/previous-versions/windows/desktop/defender/set-msft-mppreference) para las siguientes propiedades:

```WMI
MAPSReporting
SubmitSamplesConsent
```

Para obtener más información acerca de los parámetros [permitidos, vea Windows Defender API wmiv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="turn-on-cloud-delivered-protection-on-individual-clients-with-the-windows-security-app"></a>Activar la protección entregada en la nube en clientes individuales con la Seguridad de Windows aplicación

> [!NOTE]
> Si la opción Configurar invalidación de configuración local para informar  de la directiva de grupo de **Microsoft MAPS** está establecida en **Deshabilitado,** la configuración de protección basada en la nube en Windows Configuración estará gris y no estará disponible. Los cambios realizados a través de un objeto de directiva de grupo deben implementarse en primer lugar en los extremos individuales antes de que se actualice la configuración en la configuración de Windows.

1. Abra la aplicación Seguridad de Windows mediante la selección del icono de escudo en la barra de tareas o mediante la búsqueda en el menú inicio de **Defender**.

2. Seleccione el **icono Protección contra &** virus (o el icono de escudo de la barra de menús izquierda) y, a continuación, la etiqueta & **de** protección contra amenazas:

    ![Captura de pantalla de la etiqueta Protección contra virus y amenazas en la aplicación Seguridad de Windows](images/defender/wdav-protection-settings-wdsc.png)

3. Confirme que **la protección basada en la nube y** el **envío** automático de muestras se cambien a **On**.

> [!NOTE]
> Si el envío de ejemplo automático se ha configurado con la directiva de grupo, la configuración será gris y no estará disponible.

## <a name="related-articles"></a>Artículos relacionados

- [Configurar el período de espera de bloqueo en la nube](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)
- [Configurar bloque a primera vista](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [Usar cmdlets PowerShell para administrar el Antivirus de Windows Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Ayudar a proteger Windows equipos con Endpoint Protection para Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]
- [Cmdlets de Defender](/powershell/module/defender/)
- [Usar la protección entregada en la nube de Microsoft en Antivirus de Microsoft Defender](cloud-protection-microsoft-defender-antivirus.md)
- [Cómo crear e implementar directivas antimalware: Servicio de protección en la nube](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)
- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
