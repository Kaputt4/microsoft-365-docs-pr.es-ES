---
title: Requisitos mínimos para Microsoft Defender para endpoint
description: Comprender los requisitos y requisitos de licencias para la incorporación de dispositivos al servicio
keywords: requisitos mínimos, licencias, tabla de comparación
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: b48503eddbb0093bc5e022d981fb719cd6f42e47
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2022
ms.locfileid: "61941809"
---
# <a name="minimum-requirements-for-microsoft-defender-for-endpoint"></a>Requisitos mínimos para Microsoft Defender para endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-minreqs-abovefoldlink)

Existen algunos requisitos mínimos para incorporar dispositivos al servicio. Obtenga información sobre los requisitos de licencias, hardware y software y otras opciones de configuración para incorporar dispositivos al servicio.

> [!TIP]
>
> - En este artículo se describen los requisitos mínimos para Microsoft Defender para el Plan de extremo 2. Si está buscando información sobre Defender for Endpoint Plan 1 (versión preliminar), consulte [Requirements for Defender for Endpoint Plan 1 (preview).](mde-p1-setup-configuration.md#review-the-requirements)
> - Obtenga información sobre las últimas mejoras de Defender for Endpoint: [Defender for Endpoint Tech Community](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced).
> - Defender for Endpoint demostró las capacidades de detección y óptica líderes del sector en la reciente evaluación de MITRE. Lectura: [Insights de la evaluación basada en MITRE ATT&CK](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).

## <a name="licensing-requirements"></a>Requisitos de licencias
Para obtener información sobre los requisitos de licencias para Microsoft Defender para Endpoint, consulte Información de licencias [de Microsoft Defender para endpoints](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#microsoft-defender-for-endpoint).


Para obtener información detallada sobre las licencias, consulta el sitio [términos](https://www.microsoft.com/licensing/terms/) del producto y trabaja con el equipo de tu cuenta para obtener más información sobre los términos y condiciones.

Para obtener más información sobre la matriz de características de Windows ediciones, vea [Comparar Windows ediciones](https://www.microsoft.com/windowsforbusiness/compare).

## <a name="browser-requirements"></a>Requisitos de los exploradores

El acceso a Defender for Endpoint se realiza a través de un explorador, que admite los siguientes exploradores:

- Microsoft Edge
- Google Chrome

> [!NOTE]
> Aunque otros exploradores pueden funcionar, los exploradores mencionados son los que se admiten.

## <a name="hardware-and-software-requirements"></a>Requisitos de hardware y software

### <a name="supported-windows-versions"></a>Versiones de Windows comptibles

- Windows 7 SP1 Enterprise ([Requiere ESU para admitir](/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)
- Windows 7 SP1 Pro ([Requiere ESU para admitir](/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)
- Windows 8.1 Enterprise
- Windows 8.1 Pro
- Windows 11 Enterprise
- Windows 11 Education
- Windows 11 Pro
- Windows 11 Pro Education
- Windows 10 Enterprise
- [Windows 10 Enterprise LTSC 2016 (o posterior)](/windows/whats-new/ltsc/)
- Windows 10 Education
- Windows 10 Pro
- Windows 10 Pro Education
- Windows servidor
  - Windows Server 2008 R2 SP1 ([Requiere ESU para ser compatible](/windows-server/get-started/extended-security-updates-deploy))
  - Windows Server 2012 R2
  - Windows Server 2016
  - Windows server, versión 1803 o posterior
  - Windows Server 2019
  - Windows Server 2022
- Windows Virtual Desktop

Los dispositivos de la red deben ejecutar una de estas ediciones.

Los requisitos de hardware de Defender para Endpoint en dispositivos son los mismos para las ediciones admitidas.

> Cores: 2 minimum, 4 preferred Memory: 1 GB minimum, 4 preferred

Para obtener más información sobre las versiones compatibles de Windows 10, vea (/windows/release-health/release-information).

> [!NOTE]
> Las máquinas que ejecutan versiones móviles de Windows (como Windows CE y Windows 10 Mobile) no son compatibles.
>
> Las máquinas virtuales que Windows 10 Enterprise 2016 LTSB pueden encontrar problemas de rendimiento si se ejecutan en plataformas de virtualización que no son de Microsoft.
>
> Para entornos virtuales, se recomienda usar Windows 10 Enterprise LTSC 2019 o posterior.



### <a name="other-supported-operating-systems"></a>Otros sistemas operativos compatibles

- [Android](microsoft-defender-endpoint-android.md)
- [iOS](microsoft-defender-endpoint-ios.md)
- [Linux](microsoft-defender-endpoint-linux.md)
- [macOS](microsoft-defender-endpoint-mac.md)

> [!NOTE]
> Tendrás que confirmar que las distribuciones de Linux y las versiones de Android, iOS y macOS son compatibles con Defender for Endpoint para que la integración funcione.

### <a name="network-and-data-storage-and-configuration-requirements"></a>Requisitos de configuración y almacenamiento de datos y red

Al ejecutar el asistente de incorporación por primera vez, debe elegir dónde se almacena la información relacionada con El punto de conexión de Microsoft Defender: en la Unión Europea, el Reino Unido o el centro de datos de Estados Unidos.

> [!NOTE]
>
> - No puede cambiar la ubicación de almacenamiento de datos después de la configuración por primera vez.
> - Revisa [Microsoft Defender para el almacenamiento y](data-storage-privacy.md) privacidad de datos de punto de conexión para obtener más información sobre dónde y cómo almacena Microsoft los datos.

### <a name="diagnostic-data-settings"></a>Configuración de datos de diagnóstico

> [!NOTE]
> Microsoft Defender para endpoint no requiere ningún nivel de diagnóstico específico mientras esté habilitado.

Asegúrese de que el servicio de datos de diagnóstico está habilitado en todos los dispositivos de la organización.
De forma predeterminada, este servicio está habilitado. Es una buena práctica comprobar para asegurarse de que los datos del sensor se obtienen de ellos.

#### <a name="use-the-command-line-to-check-the-windows-diagnostic-data-service-startup-type"></a>Use la línea de comandos para comprobar el tipo Windows inicio del servicio de datos de diagnóstico

1. Abra un símbolo del sistema con privilegios elevados en el dispositivo:
   1. Vaya a **Inicio** y escriba **cmd**.
   2. Haga clic derecho en **Símbolo del sistema** y seleccione **Ejecutar como administrador**.

2. Escriba el siguiente comando y presione **Entrar**:

   ```console
   sc qc diagtrack
   ```

   Si el servicio está habilitado, el resultado debería ser parecido a la siguiente captura de pantalla:

   ![Resultado del comando de consulta sc para diagtrack.](images/windefatp-sc-qc-diagtrack.png)

Deberá establecer el servicio para que se  inicie automáticamente si el START_TYPE no está establecido en **AUTO_START**.

#### <a name="use-the-command-line-to-set-the-windows-diagnostic-data-service-to-automatically-start"></a>Usar la línea de comandos para establecer el Windows de datos de diagnóstico para iniciarse automáticamente

1. Abra un símbolo del sistema con privilegios elevados en el extremo:
    1. Vaya a **Inicio** y escriba **cmd**.
    2. Haga clic derecho en **Símbolo del sistema** y seleccione **Ejecutar como administrador**.

2. Escriba el siguiente comando y presione **Entrar**:

    ```console
    sc config diagtrack start=auto
    ```

3. Se muestra un mensaje de éxito. Para comprobar el cambio, escriba el siguiente comando y presione **Entrar**:

    ```console
    sc qc diagtrack
    ```

#### <a name="internet-connectivity"></a>Conectividad a Internet

La conectividad a Internet en dispositivos es necesaria directamente o a través del proxy.

El sensor Defender for Endpoint puede usar un ancho de banda promedio diario de 5 MB para comunicarse con el servicio en la nube de Defender for Endpoint e informar de los datos cibernéticos. Las actividades únicas, como las cargas de archivos y la colección de paquetes de investigación, no se incluyen en este ancho de banda promedio diario.

Para obtener más información acerca de las opciones de configuración de proxy adicionales, vea [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).

Antes de incorporar dispositivos, el servicio de datos de diagnóstico debe estar habilitado. El servicio está habilitado de forma predeterminada en Windows 10 y Windows 11.

## <a name="microsoft-defender-antivirus-configuration-requirement"></a>Antivirus de Microsoft Defender de configuración

El agente de Defender for Endpoint depende de la capacidad de Antivirus de Microsoft Defender para examinar archivos y proporcionar información sobre ellos.

Configure las actualizaciones de inteligencia de seguridad en los dispositivos defender para puntos de conexión Antivirus de Microsoft Defender sea el antimalware activo o no. Para obtener más información, vea [Manage Antivirus de Microsoft Defender updates and apply baselines](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus).

Cuando Antivirus de Microsoft Defender no es el antimalware activo de la organización y usa el servicio Defender for Endpoint, Antivirus de Microsoft Defender pasa al modo pasivo.

Si su organización ha desactivado Antivirus de Microsoft Defender a través de la directiva de grupo u otros métodos, los dispositivos que se incorpore deben excluirse de esta directiva de grupo.

Si está incorporando servidores y Antivirus de Microsoft Defender no es el antimalware activo en los servidores, Antivirus de Microsoft Defender tendrá que configurarse para ir en modo pasivo o desinstalar. La configuración depende de la versión del servidor. Para obtener más información, [vea Antivirus de Microsoft Defender compatibilidad](microsoft-defender-antivirus-compatibility.md).

> [!NOTE]
> La directiva de grupo normal no se aplica a la Protección contra alteraciones y los cambios en la configuración Antivirus de Microsoft Defender se omitirán cuando esté la protección contra alteraciones.

## <a name="microsoft-defender-antivirus-early-launch-antimalware-elam-driver-is-enabled"></a>Antivirus de Microsoft Defender controlador antimalware de inicio anticipado (ELAM) está habilitado

Si está ejecutando el Antivirus de Microsoft Defender como el producto antimalware principal en sus dispositivos, el agente de Defender for Endpoint se incorporará correctamente.

Si ejecuta un cliente antimalware de terceros y usa soluciones de administración de dispositivos móviles o Microsoft Endpoint Manager (rama actual), deberá asegurarse de que el controlador ELAM de Antivirus de Microsoft Defender está habilitado. Para obtener más información, vea [Ensure that Antivirus de Microsoft Defender is not disabled by policy](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).

## <a name="related-topics"></a>Temas relacionados

- [Configurar Microsoft Defender para la implementación de puntos de conexión](production-deployment.md)
- [Incorporar dispositivos](onboard-configure.md)
