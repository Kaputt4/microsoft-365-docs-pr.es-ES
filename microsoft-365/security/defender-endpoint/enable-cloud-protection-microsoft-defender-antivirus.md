---
title: Activar la protección en la nube en Antivirus de Microsoft Defender
description: Activa la protección en la nube para beneficiarte de las características de protección rápidas y avanzadas.
keywords: Antivirus de Microsoft Defender, antimalware, seguridad, nube, bloquear a primera vista
ms.prod: m365-security
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
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: 78f992e20ee0c0c2505777295ca3ba34a5c4ea66
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "64470645"
---
# <a name="turn-on-cloud-protection-in-microsoft-defender-antivirus"></a>Activar la protección en la nube en Antivirus de Microsoft Defender

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender

[La protección en la nube Antivirus de Microsoft Defender](cloud-protection-microsoft-defender-antivirus.md) proporciona una protección precisa, en tiempo real e inteligente. La protección en la nube debe estar habilitada de forma predeterminada; sin embargo, puede configurar la protección en la nube para que se adapte a las necesidades de su organización.

## <a name="methods-to-configure-cloud-protection"></a>Métodos para configurar la protección en la nube

Puede activar o desactivar Antivirus de Microsoft Defender protección en la nube mediante uno de varios métodos:

- Microsoft Endpoint Manager, que incluye Microsoft Intune y Configuration Manager
- Directiva de grupo
- Cmdlets de PowerShell

También puedes activar o desactivar la protección en la nube en puntos de conexión individuales mediante Seguridad de Windows aplicación. 

Para obtener más información acerca de los requisitos específicos de conectividad de red para garantizar que los puntos de conexión se puedan conectar al servicio de protección en la nube, vea [Configure and validate network connections](configure-network-connections-microsoft-defender-antivirus.md).

> [!NOTE]
> En Windows 10 y Windows 11, no hay ninguna diferencia entre las opciones de informes básicas y  avanzadas que  se describen en este artículo. Esta es una distinción heredada y elegir cualquiera de las dos opciones dará como resultado el mismo nivel de protección en la nube. No hay ninguna diferencia en el tipo o la cantidad de información que se comparte. Para obtener más información sobre lo que recopilamos, consulta la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=521839).

## <a name="use-intune-to-turn-on-cloud-protection"></a>Usar Intune para activar la protección en la nube

1. Vaya al Centro Microsoft Endpoint Manager administración ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) e inicie sesión.

2. En el **panel Inicio** , seleccione **Configuración del dispositivo > perfiles**.

3. Seleccione el **tipo de perfil Restricciones de** dispositivo que desea configurar. Si necesitas crear un nuevo tipo de perfil **de restricciones de** dispositivo, consulta Configurar la configuración de restricción de [dispositivo en Microsoft Intune](/intune/device-restrictions-configure).

4. Seleccione **Configuración** \> **de propiedades: Editar** \> **Antivirus de Microsoft Defender**.

5. En el **conmutador de protección entregado en** la nube, seleccione **Habilitar**.

6. En la **lista desplegable Preguntar a los usuarios antes del envío de** ejemplo, seleccione **Enviar todos los datos automáticamente**.

Para obtener más información acerca de los perfiles de dispositivo de Intune, incluido cómo crear y configurar sus opciones, consulta ¿Qué Microsoft Intune [perfiles de dispositivo?](/intune/device-profiles)

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-protection"></a>Usar Microsoft Endpoint Manager para activar la protección en la nube

1. Vaya al Centro Microsoft Endpoint Manager administración ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) e inicie sesión.

2. Elija **Endpoint security** \> **Antivirus**.

3. Seleccione un perfil antivirus. (Si aún no tienes uno, o si quieres crear un perfil nuevo, consulta Configurar la configuración de restricción de [dispositivos en Microsoft Intune](/intune/device-restrictions-configure).

4. Seleccione **Propiedades**. A continuación, junto **a Configuración,** elija **Editar**.

5. Expanda **Protección en la** nube y, a continuación, en la **lista Nivel** de protección entregado en la nube, seleccione una de las siguientes opciones:
   - **Alto**: aplica un nivel de detección fuerte.
   - **High plus**: usa el **nivel alto** y aplica más medidas de protección (puede afectar al rendimiento del cliente).
   - **Tolerancia cero**: bloquea todos los ejecutables desconocidos.

6. Seleccione **Revisar y guardar** y, a continuación, **elija Guardar**.

Para obtener más información sobre cómo configurar Microsoft Endpoint Configuration Manager, vea [How to create and deploy antimalware policies: Cloud-protection service](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service).

## <a name="use-group-policy-to-turn-on-cloud-protection"></a>Usar la directiva de grupo para activar la protección en la nube

1. En el dispositivo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y **seleccione Editar**.

2. En el **Editor de administración de directivas de** grupo, vaya a **Configuración del equipo**.

3. Seleccione **Plantillas administrativas**.

4. Expanda el árbol para **Windows componentes** >  **Antivirus de Microsoft Defender > MAPS**

    > [!NOTE]
    > La configuración de MAPS es igual a la protección entregada en la nube.

5. Haga doble clic **en Unirse a Microsoft MAPS**. Asegúrese de que la opción está activada y establecida en **Mapas** básicos o **mapas avanzados**. Seleccione **Aceptar**.

    Puede elegir enviar información básica o adicional sobre el software detectado:

    - MAPAS básicos: la pertenencia básica enviará información básica a Microsoft sobre malware y software potencialmente no deseado detectado en el dispositivo. La información incluye de dónde provenía el software (como direcciones URL y rutas parciales), las acciones realizadas para resolver la amenaza y si las acciones se realizaron correctamente.

    - MAPAS avanzados: Además de la información básica, la pertenencia avanzada enviará información detallada sobre malware y software potencialmente no deseado, incluida la ruta completa del software, e información detallada sobre cómo el software ha afectado al dispositivo.

6. Haga doble clic en **Enviar ejemplos de archivos cuando sea necesario realizar un análisis adicional**. Asegúrese de que la primera opción esté establecida en **Enabled** y de que las demás opciones estén establecidas en:

   - **Enviar muestras seguras** (1)
   - **Enviar todos los ejemplos** (3)

   >[!NOTE]
   > La **opción Enviar muestras seguras** (1) significa que la mayoría de las muestras se enviarán automáticamente. Los archivos que probablemente contengan información personal seguirán solicitando y necesitarán confirmación adicional.
   > Al establecer la opción **en Preguntar siempre** (0), se disminuirá el estado de protección del dispositivo. Establecerlo en **Nunca enviar** (2) significa que la característica [Bloquear](configure-block-at-first-sight-microsoft-defender-antivirus.md) a primera vista de Microsoft Defender para endpoint no funcionará.

7. Seleccione **Aceptar**.

## <a name="use-powershell-cmdlets-to-turn-on-cloud-protection"></a>Usar cmdlets de PowerShell para activar la protección en la nube

Los cmdlets siguientes pueden activar la protección en la nube:

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

Para obtener más información sobre cómo usar PowerShell con Antivirus de Microsoft Defender, vea [Use PowerShell cmdlets to configure and run Antivirus de Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Antivirus de Microsoft Defender cmdlets](/powershell/module/defender/). [CSP de directivas: Defender](/windows/client-management/mdm/policy-csp-defender) también tiene más información específicamente en [-SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent).

> [!IMPORTANT]
> Puede establecer **-SubmitSamplesConsent** en `SendSafeSamples` (la configuración predeterminada, recomendada), `NeverSend`o `AlwaysPrompt`. La `SendSafeSamples` configuración significa que la mayoría de las muestras se enviarán automáticamente. Los archivos que probablemente contengan información personal darán como resultado un mensaje para continuar y requerirán confirmación.
> La `NeverSend` configuración y `AlwaysPrompt` reduce el nivel de protección del dispositivo. Además, la configuración `NeverSend` significa que la característica [Bloquear a primera vista](configure-block-at-first-sight-microsoft-defender-antivirus.md) de Microsoft Defender para endpoint no funcionará.

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-protection"></a>Usar Windows de administración de aplicaciones (WMI) para activar la protección en la nube

Utilice el [**método Set** de la **clase MSFT_MpPreference**](/previous-versions/windows/desktop/defender/set-msft-mppreference) para las siguientes propiedades:

```WMI
MAPSReporting
SubmitSamplesConsent
```

Para obtener más información acerca de los parámetros permitidos, [vea Windows Defender API wmiv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="turn-on-cloud-protection-on-individual-clients-with-the-windows-security-app"></a>Activar la protección en la nube en clientes individuales con la Seguridad de Windows aplicación

> [!NOTE]
> Si la opción Configurar invalidación de configuración local para informar de la directiva de grupo de **Microsoft MAPS** está establecida  en **Deshabilitado**, la configuración de protección basada en la nube en Windows Configuración estará gris y no estará disponible. Los cambios realizados a través de un objeto de directiva de grupo deben implementarse en primer lugar en los extremos individuales antes de que se actualice la configuración en la configuración de Windows.

1. Abre la aplicación Seguridad de Windows seleccionando el icono de escudo en la barra de tareas o buscando en el menú inicio para **Seguridad de Windows**.

2. Seleccione el **icono Protección contra &** virus (o el icono escudo de la barra de menús izquierda) y, a continuación, en Administrar configuración, seleccione **Configuración de protección contra & virus**.

   :::image type="content" source="../../media/wdav-protection-settings-wdsc.png" alt-text="La configuración de protección contra & virus" lightbox="../../media/wdav-protection-settings-wdsc.png":::

3. Confirme que **la protección basada en la nube y** **el envío** automático de muestras se han cambiado a **On**.

   > [!NOTE]
   > Si el envío de ejemplo automático se ha configurado con la directiva de grupo, la configuración será gris y no estará disponible.

## <a name="see-also"></a>Vea también

- [Usar la protección en la nube de Microsoft en Antivirus de Microsoft Defender](cloud-protection-microsoft-defender-antivirus.md)

- [Cómo crear e implementar directivas antimalware: Servicio de protección en la nube](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)

- [Usar cmdlets PowerShell para administrar el Antivirus de Windows Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md)
