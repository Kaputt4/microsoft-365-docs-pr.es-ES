---
title: Active la protección suministrada por la nube en Antivirus de Microsoft Defender
description: Active la protección entregada en la nube para beneficiarse de funciones de protección rápidas y avanzadas.
keywords: Antivirus de Microsoft Defender, antimalware, seguridad, nube, bloque a primera vista
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
> El servicio en la nube Antivirus de Microsoft Defender es un mecanismo para ofrecer protección actualizada a la red y los puntos de conexión. Aunque se denomina servicio en la nube, no es simplemente protección para los archivos almacenados en la nube; más bien, utiliza recursos distribuidos y aprendizaje automático para ofrecer protección a sus puntos de conexión a un ritmo mucho más rápido que las actualizaciones de inteligencia de seguridad tradicionales.

Antivirus de Microsoft Defender utiliza múltiples tecnologías de detección y prevención para ofrecer una protección precisa, en tiempo real e inteligente. [Conozca las tecnologías avanzadas en el núcleo de la protección de próxima generación de Microsoft Defender for Endpoint.](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)

Puede activar o desactivar Antivirus de Microsoft Defender protección entregada en la nube de varias maneras:

- Microsoft Intune
- Microsoft Endpoint Manager
- Directiva de grupo
- Cmdlets de PowerShell.

 También puede activarlo o desactivarlo en clientes individuales con la aplicación Seguridad de Windows.

Consulte [Usar la protección entregada en la nube por Microsoft](cloud-protection-microsoft-defender-antivirus.md) para obtener información general sobre Antivirus de Microsoft Defender protección entregada en la nube.

Para obtener más información acerca de los requisitos específicos de conectividad de red para garantizar que los puntos de conexión pueden conectarse al servicio de protección entregado en la nube, consulte [Configurar y validar conexiones de red.](configure-network-connections-microsoft-defender-antivirus.md)

> [!NOTE]
> En Windows 10, no hay diferencia entre las opciones de informes **básico** y **avanzado** que se describen en este tema. Esta es una distinción heredada y la elección de cualquiera de las configuraciones dará como resultado el mismo nivel de protección entregada en la nube. No hay diferencia en el tipo o cantidad de información que se comparte. Para obtener más información sobre lo que recopilamos, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=521839).

## <a name="use-intune-to-turn-on-cloud-delivered-protection"></a>Utilice Intune para activar la protección suministrada por la nube

1. Vaya al centro de administración de Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e inicie sesión.

2. En el panel **Inicio,** seleccione **Configuración del dispositivo > Perfiles**.

3. Seleccione el tipo de perfil **Restricciones de dispositivo** que desea configurar. Si necesita crear un nuevo tipo de perfil **restricciones de dispositivo,** consulte [Configurar la configuración de restricción de dispositivos en Microsoft Intune](/intune/device-restrictions-configure).

4. Seleccione **Configuración** de  >  **propiedades: Editar**  >  **Antivirus de Microsoft Defender**.

5. En el conmutador **de protección entregado en la nube,** seleccione **Habilitar**.

6. En el menú desplegable **Solicitar usuarios antes del envío de ejemplo,** seleccione Enviar todos los datos **automáticamente.**

Para obtener más información acerca de los perfiles de dispositivo de Intune, incluida la forma de crear y configurar sus configuraciones, consulte [¿Qué son Microsoft Intune perfiles de dispositivo?](/intune/device-profiles)

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-delivered-protection"></a>Utilice Microsoft Endpoint Manager para activar la protección suministrada por la nube

1. Vaya al centro de administración de Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e inicie sesión.

2. Elija **Endpoint Security**  >  **Antivirus**.

3. Seleccione un perfil antivirus. (Si aún no tiene uno o si desea crear un nuevo perfil, consulte [Configurar la configuración de restricción de dispositivos en Microsoft Intune](/intune/device-restrictions-configure).

4. Seleccione **Propiedades**. A continuación, junto a **Configuración ,** elija **Edit**.

5. Expanda **Protección en** la nube y, a continuación, en la lista Nivel de protección entregado en **la nube,** seleccione una de las siguientes opciones:
   - **Alto**: Aplica un fuerte nivel de detección.
   - **Alto plus**: Utiliza el **alto** nivel y aplica medidas de protección adicionales (pueden afectar al rendimiento del cliente).
   - **Tolerancia cero**: Bloquea todos los ejecutables desconocidos.

6. Seleccione **Revisar + guardar** y, a continuación, elija **Guardar**.

Para obtener más información acerca de cómo configurar Microsoft Endpoint Configuration Manager, consulte [Cómo crear e implementar directivas antimalware: servicio de protección en la nube.](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)

## <a name="use-group-policy-to-turn-on-cloud-delivered-protection"></a>Utilice la directiva de grupo para activar la protección entregada en la nube

1. En el dispositivo de administración de directivas de grupo, abra la [Consola de administración de directivas de grupo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))haga clic con el botón derecho en el objeto de directiva de grupo que desea configurar y seleccione **Editar**.

2. En el **Editor de administración de directivas de** grupo, vaya a Configuración del **equipo**.

3. Seleccione **Plantillas administrativas**.

4. Expanda el árbol a **componentes Windows > Antivirus de Microsoft Defender > MAPS**

5. Haga doble clic en **Unirse a Microsoft MAPS**. Asegúrese de que la opción esté activada y establecida en **MAPAS básicos** o **MAPAS avanzados.** Seleccione **Aceptar**.

6. Haga doble clic en **Enviar ejemplos de archivos cuando se requiera un análisis posterior.** Asegúrese de que la primera opción está establecida en **Habilitado** y de que las otras opciones están establecidas en:

    1. **Enviar muestras seguras** (1)
    2. **Enviar todas las muestras** (3)

        >[!NOTE]
        > La opción **Enviar muestras seguras** (1) significa que la mayoría de las muestras se enviarán automáticamente. Los archivos que probablemente contengan información personal seguirán solicitando y requerirán confirmación adicional.
        > Establecer la opción en **Always Prompt** (0) reducirá el estado de protección del dispositivo. Establecerlo en **Nunca enviar** (2) significa que la característica Bloquear a [primera vista](configure-block-at-first-sight-microsoft-defender-antivirus.md) de Microsoft Defender para endpoint no funcionará.

7. Seleccione **Aceptar**.

## <a name="use-powershell-cmdlets-to-turn-on-cloud-delivered-protection"></a>Usar cmdlets de PowerShell para activar la protección entregada en la nube

Los siguientes cmdlets pueden activar la protección entregada en la nube:

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

Para obtener más información sobre cómo usar PowerShell con Antivirus de Microsoft Defender, vea [Usar cmdlets de PowerShell para configurar y ejecutar cmdlets de Antivirus de Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) y [Defender.](/powershell/module/defender/) [Directiva CSP - Defender](/windows/client-management/mdm/policy-csp-defender) también tiene más información específicamente en [-SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent).

>[!NOTE]
> También puede establecer **-SubmitSamplesConsent** `SendSafeSamples` en (la configuración predeterminada), `NeverSend` o `AlwaysPrompt` . La `SendSafeSamples` configuración significa que la mayoría de las muestras se enviarán automáticamente. Los archivos que probablemente contengan información personal seguirán solicitando y requerirán confirmación adicional.

>[!WARNING]
> Configuración **-SubmitSamplesConsent** `NeverSend` a o `AlwaysPrompt` bajará el nivel de protección del dispositivo. Además, establecerlo `NeverSend` significa que la característica [Bloquear a primera vista](configure-block-at-first-sight-microsoft-defender-antivirus.md) de Microsoft Defender para endpoint no funcionará.

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-delivered-protection"></a>Utilice Windows Instrucción de administración (WMI) para activar la protección suministrada en la nube

Utilice el método [ **Set** de la](/previous-versions/windows/desktop/defender/set-msft-mppreference) clase MSFT_MpPreference para las siguientes propiedades:

```WMI
MAPSReporting
SubmitSamplesConsent
```

Para obtener más información acerca de los parámetros permitidos, vea [Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="turn-on-cloud-delivered-protection-on-individual-clients-with-the-windows-security-app"></a>Activa la protección entregada en la nube a clientes individuales con la aplicación Seguridad de Windows

> [!NOTE]
> Si la **opción Configurar invalidación de configuración local para notificar** la configuración de directiva de grupo de Microsoft MAPS está establecida en **Deshabilitado**, la configuración de protección basada en **la nube** en Windows Configuración estará atenuada y no estará disponible. Los cambios realizados a través de un objeto de directiva de grupo deben implementarse en primer lugar en los extremos individuales antes de que se actualice la configuración en la configuración de Windows.

1. Abra la aplicación Seguridad de Windows seleccionando el icono de escudo en la barra de tareas o buscando en el menú inicio **de Defender**.

2. Seleccione el **icono de protección contra amenazas & virus** (o el icono de escudo en la barra de menús izquierda) y, a continuación, la etiqueta de configuración de protección contra amenazas & **virus:**

    ![Captura de pantalla de la etiqueta Protección contra virus y amenazas en la aplicación Seguridad de Windows](images/defender/wdav-protection-settings-wdsc.png)

3. Confirme que **la protección basada en la nube** y el envío automático de **muestras** se activan. 

> [!NOTE]
> Si el envío automático de ejemplo se ha configurado con directiva de grupo, la configuración se atenuará y no estará disponible.

## <a name="related-articles"></a>Artículos relacionados

- [Configurar el período de espera de bloqueo en la nube](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)
- [Configurar bloque a primera vista](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [Usar cmdlets PowerShell para administrar el Antivirus de Windows Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Ayude a proteger Windows PC con Endpoint Protection para Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]
- [Cmdlets defensores](/powershell/module/defender/)
- [Utilice la protección entregada en la nube de Microsoft en Antivirus de Microsoft Defender](cloud-protection-microsoft-defender-antivirus.md)
- [Cómo crear e implementar políticas antimalware: servicio de protección en la nube](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)
- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
