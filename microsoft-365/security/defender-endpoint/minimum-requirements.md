---
title: Requisitos mínimos para Microsoft Defender para punto de conexión
description: Descripción de los requisitos y requisitos de licencia para la incorporación de dispositivos al servicio
keywords: requisitos mínimos, licencias, tabla de comparación
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier1
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 530a10beecab3c0f371db7a607e1b2a5d441c5a9
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68635430"
---
# <a name="minimum-requirements-for-microsoft-defender-for-endpoint"></a>Requisitos mínimos para Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-minreqs-abovefoldlink)

Hay algunos requisitos mínimos para incorporar dispositivos al servicio. Obtenga información sobre las licencias, los requisitos de hardware y software y otras opciones de configuración para incorporar dispositivos al servicio.

> [!TIP]
>
> - En este artículo se describen los requisitos mínimos para Microsoft Defender para punto de conexión plan 2. Si busca información sobre El plan 1 de Defender para punto de conexión, consulte [Requisitos de Defender para el plan de punto de conexión 1](mde-p1-setup-configuration.md#review-the-requirements).
> - Obtenga información sobre las mejoras más recientes en Defender para punto de conexión: [Defender para endpoint Tech Community](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced).
> - Defender para punto de conexión demostró las funcionalidades de óptica y detección líderes del sector en la evaluación reciente de MITRE. Lectura: [Insights de la evaluación basada en MITRE ATT&CK](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).

## <a name="licensing-requirements"></a>Requisitos de licencias

Las versiones independientes de [Defender para el plan 1 y el plan 2](defender-endpoint-plan-1-2.md), incluso cuando se incluyen como parte de otros planes de Microsoft 365, no incluyen licencias de servidor. Para incorporar servidores a esos planes, necesitará Defender for Servers Plan 1 o Plan 2 como parte de la oferta de [Defender for Cloud](/azure/defender-for-cloud/defender-for-cloud-introduction) . Para obtener más información, consulte la introducción a [Microsoft Defender para servidores](/azure/defender-for-cloud/defender-for-servers-introduction).

Para obtener información sobre los requisitos de licencia de Microsoft Defender para punto de conexión, consulte [Microsoft Defender para punto de conexión información de licencias](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#microsoft-defender-for-endpoint).

Para obtener información detallada sobre las licencias, consulte el [sitio términos del producto](https://www.microsoft.com/licensing/terms/) y trabaje con el equipo de su cuenta para obtener más información sobre los términos y condiciones.

Para obtener más información sobre la matriz de características en las ediciones de Windows, consulta [Comparar ediciones de Windows](https://www.microsoft.com/windowsforbusiness/compare).
## <a name="browser-requirements"></a>Requisitos de los exploradores

El acceso a Defender para punto de conexión se realiza a través de un explorador, lo que admite los siguientes exploradores:

- Microsoft Edge
- Google Chrome

> [!NOTE]
> Aunque otros exploradores pueden funcionar, los exploradores mencionados son los que se admiten.

## <a name="hardware-and-software-requirements"></a>Requisitos de hardware y software

### <a name="supported-windows-versions"></a>Versiones de Windows comptibles

- Windows 11 Enterprise
- Windows 11 Education
- Windows 11 Pro
- Windows 11 Pro Education
- Windows 10 Enterprise
- [Windows 10 Enterprise LTSC 2016 (o posterior)](/windows/whats-new/ltsc/)
- Windows 10 Enterprise loT

    >[!NOTE]
    >Aunque Windows 10 IoT Enterprise es un sistema operativo compatible en Microsoft Defender para punto de conexión y permite que los OEM/ODM lo distribuyan como parte de su producto o solución, los clientes deben seguir las instrucciones del OEM/ODM sobre el software instalado basado en host y la compatibilidad.

- Windows 10 Education
- Windows 10 Pro
- Windows 10 Pro Education
- Windows 8.1 Enterprise
- Windows 8.1 Pro
- Windows 7 SP1 Enterprise ([requiere ESU para soporte técnico](/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq)).
- Windows 7 SP1 Pro ([requiere ESU para soporte técnico](/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq)).
- Windows Server
  - Windows Server 2008 R2 SP1 ([requiere ESU para soporte técnico](/windows-server/get-started/extended-security-updates-deploy))
  - Windows Server 2012 R2
  - Windows Server 2016
  - Windows Server, versión 1803 o posterior
  - Windows Server 2019 y versiones posteriores
  - Edición principal de Windows Server 2019
  - Windows Server 2022
- Windows Virtual Desktop
- Windows 365

Los dispositivos de la red deben ejecutar una de estas ediciones.

Los requisitos de hardware de Defender para punto de conexión en dispositivos son los mismos para las ediciones admitidas.

> Núcleos: 2 memorias mínimas y 4 preferidas: 1 GB como mínimo, 4 preferidas

Para obtener más información sobre las versiones admitidas de Windows 10, consulte [Windows 10 información de versión](/windows/release-health/release-information).

> [!NOTE]
> - No se admiten los puntos de conexión que ejecutan versiones móviles de Windows (como Windows CE y Windows 10 Mobile).
>
> - Las máquinas virtuales que ejecutan Windows 10 Enterprise 2016 LTSB pueden encontrar problemas de rendimiento si se ejecutan en plataformas de virtualización que no son de Microsoft.
>
> - Para entornos virtuales, se recomienda usar Windows 10 Enterprise LTSC 2019 o posterior.
>
> - Las versiones independientes de [Defender para el plan 1 y el plan 2](defender-endpoint-plan-1-2.md) no incluyen licencias de servidor. Para incorporar servidores a esos planes, necesitará Defender for Servers Plan 1 o Plan 2 como parte de la oferta de [Defender for Cloud](/azure/defender-for-cloud/defender-for-cloud-introduction) . Para obtener más información. consulte [Información general de Microsoft Defender para servidores](/azure/defender-for-cloud/defender-for-servers-introduction).

Cuando los componentes están actualizados en los sistemas operativos Microsoft Windows, Microsoft Defender para punto de conexión soporte técnico seguirá el ciclo de vida del sistema operativo correspondiente. Para obtener más información, consulte [Preguntas más frecuentes sobre el ciclo de vida](/lifecycle/faq/general-lifecycle). Por lo general, las nuevas características o funcionalidades solo se proporcionan en sistemas operativos que aún no han alcanzado el final de su ciclo de vida. Las actualizaciones de inteligencia de seguridad (actualizaciones de definición y motor) y la lógica de detección seguirán proporcionándose hasta al menos:

- Fecha [de finalización del soporte](/lifecycle/products/) técnico (para sistemas operativos que no tienen un programa de Novedades de seguridad extendida (ESU).
- Fecha [de finalización de la ESU](/lifecycle/faq/extended-security-updates) (para sistemas operativos que tienen un programa ESU).

### <a name="other-supported-operating-systems"></a>Otros sistemas operativos admitidos

- [Android](microsoft-defender-endpoint-android.md)
- [iOS](microsoft-defender-endpoint-ios.md)
- [Linux](microsoft-defender-endpoint-linux.md)
- [macOS](microsoft-defender-endpoint-mac.md)

> [!NOTE]
> Tendrá que confirmar que las distribuciones y versiones de Linux de Android, iOS y macOS son compatibles con Defender para punto de conexión para que la integración funcione.

### <a name="network-and-data-storage-and-configuration-requirements"></a>Requisitos de configuración y almacenamiento de datos y red

Al ejecutar el asistente de incorporación por primera vez, debe elegir dónde se almacena la información relacionada con Microsoft Defender para punto de conexión: en la Unión Europea, el Reino Unido o el centro de datos de Estados Unidos.

> [!NOTE]
>
> - No se puede cambiar la ubicación de almacenamiento de datos después de la configuración por primera vez.
> - Revise la [Microsoft Defender para punto de conexión el almacenamiento de datos y la privacidad](data-storage-privacy.md) para obtener más información sobre dónde y cómo Microsoft almacena los datos.

### <a name="diagnostic-data-settings"></a>Configuración de datos de diagnóstico

> [!NOTE]
> Microsoft Defender para punto de conexión no requiere ningún nivel de diagnóstico específico siempre que esté habilitado.

Asegúrese de que el servicio de datos de diagnóstico está habilitado en todos los dispositivos de la organización.
De forma predeterminada, este servicio está habilitado. Es recomendable comprobar para asegurarse de que obtendrá datos del sensor de ellos.

#### <a name="use-the-command-line-to-check-the-windows-diagnostic-data-service-startup-type"></a>Usar la línea de comandos para comprobar el tipo de inicio del servicio de datos de diagnóstico de Windows

1. Abra un símbolo del sistema con privilegios elevados en el dispositivo:
   1. Vaya a **Inicio** y escriba **cmd**.
   2. Haga clic derecho en **Símbolo del sistema** y seleccione **Ejecutar como administrador**.

2. Escriba el siguiente comando y presione **Entrar**:

   ```console
   sc qc diagtrack
   ```

   Si el servicio está habilitado, el resultado debe tener un aspecto similar al de la captura de pantalla siguiente:

   :::image type="content" source="images/windefatp-sc-qc-diagtrack.png" alt-text="Resultado del comando de consulta sc para diagtrack" lightbox="images/windefatp-sc-qc-diagtrack.png":::

Tendrá que establecer que el servicio se inicie automáticamente si el **START_TYPE** no está establecido en **AUTO_START**.

#### <a name="use-the-command-line-to-set-the-windows-diagnostic-data-service-to-automatically-start"></a>Use la línea de comandos para establecer que el servicio de datos de diagnóstico de Windows se inicie automáticamente.

1. Abra un símbolo del sistema con privilegios elevados en el punto de conexión:
    1. Vaya a **Inicio** y escriba **cmd**.
    2. Haga clic derecho en **Símbolo del sistema** y seleccione **Ejecutar como administrador**.

2. Escriba el siguiente comando y presione **Entrar**:

    ```console
    sc config diagtrack start=auto
    ```

3. Se muestra un mensaje correcto. Para comprobar el cambio, escriba el siguiente comando y presione **Entrar**:

    ```console
    sc qc diagtrack
    ```

#### <a name="internet-connectivity"></a>Conectividad a Internet

La conectividad a Internet en los dispositivos es necesaria directamente o a través de proxy.

El sensor de Defender para punto de conexión puede usar un ancho de banda medio diario de 5 MB para comunicarse con el servicio en la nube de Defender para punto de conexión e informar de los datos cibernéticos. Las actividades puntuales, como las cargas de archivos y la recopilación de paquetes de investigación, no se incluyen en este ancho de banda medio diario.

Para obtener más información sobre las opciones de configuración de proxy adicionales, consulte [Configuración del proxy de dispositivo y las opciones de conectividad a Internet](configure-proxy-internet.md).

Antes de incorporar dispositivos, el servicio de datos de diagnóstico debe estar habilitado. El servicio está habilitado de forma predeterminada en Windows 10 y Windows 11.

## <a name="microsoft-defender-antivirus-configuration-requirement"></a>Microsoft Defender requisito de configuración de Antivirus

El agente de Defender para punto de conexión depende de la capacidad de Microsoft Defender Antivirus para examinar archivos y proporcionar información sobre ellos.

Configure las actualizaciones de inteligencia de seguridad en los dispositivos de Defender para punto de conexión independientemente de si Microsoft Defender Antivirus es el antimalware activo o no. Para obtener más información, consulte [Administración de actualizaciones Microsoft Defender Antivirus y aplicación de líneas base](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus).

Cuando Microsoft Defender Antivirus no es el antimalware activo de su organización y usa el servicio Defender para punto de conexión, Microsoft Defender Antivirus pasa al modo pasivo.

Si su organización ha desactivado Microsoft Defender Antivirus a través de la directiva de grupo u otros métodos, los dispositivos incorporados deben excluirse de esta directiva de grupo.

Si va a incorporar servidores y Microsoft Defender Antivirus no es el antimalware activo en los servidores, Microsoft Defender Antivirus deberá configurarse para ir en modo pasivo o desinstalarse. La configuración depende de la versión del servidor. Para obtener más información, consulte [compatibilidad con Microsoft Defender Antivirus](microsoft-defender-antivirus-compatibility.md).

> [!NOTE]
> La directiva de grupo normal no se aplica a La protección contra alteraciones y los cambios en Microsoft Defender configuración del Antivirus se omitirán cuando la protección contra alteraciones esté activada.

## <a name="microsoft-defender-antivirus-early-launch-antimalware-elam-driver-is-enabled"></a>Microsoft Defender controlador antimalware de inicio anticipado del Antivirus (ELAM) está habilitado

Si ejecuta Microsoft Defender Antivirus como producto antimalware principal en los dispositivos, el agente de Defender para punto de conexión se incorporará correctamente.

Si ejecuta un cliente antimalware de terceros y usa soluciones de administración de dispositivos móviles o Microsoft Endpoint Manager (rama actual), deberá asegurarse de que el controlador ELAM de antivirus de Microsoft Defender está habilitado. Para obtener más información, vea [Asegurarse de que Microsoft Defender Antivirus no está deshabilitado por directiva](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).

## <a name="related-topics"></a>Temas relacionados

- [Configuración de Microsoft Defender para punto de conexión implementación](production-deployment.md)
- [Incorporación de dispositivos](onboard-configure.md)
