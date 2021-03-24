---
title: Requisitos mínimos para Microsoft Defender para endpoint
description: Comprender los requisitos y requisitos de licencias para la incorporación de dispositivos al servicio
keywords: requisitos mínimos, licencias, tabla de comparación
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 7581c606a7903bd6d32c1e192f35992899289f30
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069435"
---
# <a name="minimum-requirements-for-microsoft-defender-for-endpoint"></a>Requisitos mínimos para Microsoft Defender para endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Existen algunos requisitos mínimos para incorporar dispositivos al servicio. Obtenga información sobre los requisitos de licencias, hardware y software y otras opciones de configuración para incorporar dispositivos al servicio.

> ¿Desea experimentar Microsoft Defender para endpoint? [Registrarse para obtener una versión de prueba gratuita](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-minreqs-abovefoldlink).

> [!TIP]
> - Obtenga información sobre las últimas mejoras en Defender for Endpoint: [Defender for Endpoint Tech Community](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced).
> - Defender for Endpoint demostró las capacidades de detección y óptica líderes del sector en la reciente evaluación de MITRE. Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).

## <a name="licensing-requirements"></a>Requisitos de licencia
Microsoft Defender para endpoint requiere una de las siguientes ofertas de licencias por volumen de Microsoft:

- Windows 10 Enterprise E5
- Windows 10 Education A5
- Microsoft 365 E5 (M365 E5) que incluye Windows 10 Enterprise E5
- Microsoft 365 A5 (M365 A5)
- Seguridad de Microsoft 365 E5
- Microsoft 365 A5 Security
- Microsoft Defender para punto de conexión

> [!NOTE]
> Los usuarios con licencia elegibles pueden usar Microsoft Defender para Endpoint en hasta cinco dispositivos simultáneos.
> Microsoft Defender para endpoint también está disponible para la compra de un proveedor de soluciones en la nube (CSP).

Microsoft Defender para endpoint para servidores requiere una de las siguientes opciones de licencia:

- [Centro de seguridad de Azure con Azure Defender habilitado](https://docs.microsoft.com/azure/security-center/security-center-pricing)
- Microsoft Defender para endpoint for Server (uno por servidor cubierto)

> [!NOTE]
> Los clientes pueden adquirir licencias de servidor (una por servidor cubierto Entorno de sistema operativo (OSE)) para Microsoft Defender para Endpoint for Servers si tienen un mínimo combinado de 50 licencias para una o más de las siguientes licencias de usuario:
>
> * Microsoft Defender para punto de conexión
> * Windows E5/A5
> * Microsoft 365 E5/A5
> * Seguridad de Microsoft 365 E5/A5

Para obtener información detallada sobre las licencias, consulta el sitio [términos](https://www.microsoft.com/licensing/terms/) del producto y trabaja con el equipo de tu cuenta para obtener más información sobre los términos y condiciones.

Para obtener más información sobre la matriz de características de las ediciones de Windows 10, consulta [Comparar ediciones de Windows 10.](https://www.microsoft.com/windowsforbusiness/compare)

Para obtener una tabla de comparación detallada de la comparación de la edición comercial de Windows 10, consulta [el PDF de comparación.](https://wfbdevicemanagementprod.blob.core.windows.net/windowsforbusiness/Windows10_CommercialEdition_Comparison.pdf)

## <a name="browser-requirements"></a>Requisitos de los exploradores
El acceso a Defender for Endpoint se realiza a través de un explorador, que admite los siguientes exploradores:

- Microsoft Edge
- Versión 11 de Internet Explorer
- Google Chrome

> [!NOTE]
> Aunque otros exploradores pueden funcionar, los exploradores mencionados son los que se admiten.


## <a name="hardware-and-software-requirements"></a>Requisitos de hardware y software

### <a name="supported-windows-versions"></a>Versiones compatibles de Windows
- Windows 7 SP1 Enterprise[(requiere ESU para ser compatible).)](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq)
- Windows 7 SP1 Pro ([Requiere ESU para admitir](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)
- Windows 8.1 Enterprise
- Windows 8.1 Pro
- Windows 10 Enterprise
- [Windows 10 Enterprise LTSC](https://docs.microsoft.com/windows/whats-new/ltsc/)
- Windows 10 Education
- Windows 10 Pro
- Windows 10 Pro Education
- Windows Server
  - Windows Server 2008 R2 SP1
  - Windows Server 2012 R2
  - Windows Server 2016
  - Windows Server, versión 1803 o posterior
  - Windows Server 2019
- Windows Virtual Desktop

Los dispositivos de la red deben ejecutar una de estas ediciones.

Los requisitos de hardware de Defender para Endpoint en dispositivos son los mismos para las ediciones admitidas.

> [!NOTE]
> Las máquinas que ejecutan versiones móviles de Windows (como Windows CE y Windows 10 Mobile) no son compatibles.
>
> Las máquinas virtuales que ejecutan Windows 10 Enterprise 2016 LTSB pueden encontrar problemas de rendimiento si se ejecutan en plataformas de virtualización que no son de Microsoft.
>
> Para entornos virtuales, se recomienda usar Windows 10 Enterprise LTSC 2019 o posterior.


### <a name="other-supported-operating-systems"></a>Otros sistemas operativos compatibles
- Android
- Linux
- macOS

> [!NOTE]
> Tendrás que conocer las distribuciones y versiones exactas de Linux de Android y macOS que son compatibles con Defender for Endpoint para que la integración funcione.



### <a name="network-and-data-storage-and-configuration-requirements"></a>Requisitos de configuración y almacenamiento de datos y red
Al ejecutar el asistente de incorporación por primera vez, debe elegir dónde se almacena la información relacionada con El punto de conexión de Microsoft Defender: en la Unión Europea, el Reino Unido o el centro de datos de Estados Unidos.

> [!NOTE]
> - No puede cambiar la ubicación de almacenamiento de datos después de la configuración por primera vez.
> - Revisa [Microsoft Defender para el almacenamiento y](data-storage-privacy.md) privacidad de datos de punto de conexión para obtener más información sobre dónde y cómo almacena Microsoft los datos.


### <a name="diagnostic-data-settings"></a>Configuración de datos de diagnóstico

> [!NOTE]
> Microsoft Defender para endpoint no requiere ningún nivel de diagnóstico específico mientras esté habilitado.

Asegúrese de que el servicio de datos de diagnóstico está habilitado en todos los dispositivos de la organización.
De forma predeterminada, este servicio está habilitado. Es una buena práctica comprobar para asegurarse de que los datos del sensor se obtienen de ellos.

Usa la línea de comandos para comprobar el tipo de inicio del servicio de datos de diagnóstico **de Windows 10:**

1. Abra un símbolo del sistema con privilegios elevados en el dispositivo:

   1.  Vaya a **Inicio** y escriba **cmd**.

   1.  Haga clic derecho en **Símbolo del sistema** y seleccione **Ejecutar como administrador**.

2. Escriba el siguiente comando y presione **Entrar**:

   ```console
   sc qc diagtrack
   ```

   Si el servicio está habilitado, el resultado debería ser parecido a la siguiente captura de pantalla:

   ![Resultado del comando de consulta sc para diagtrack](images/windefatp-sc-qc-diagtrack.png)


Deberá establecer el servicio para que se inicie automáticamente si el START_TYPE **no** está establecido en **AUTO_START**.


**Usa la línea de comandos para establecer el servicio de datos de diagnóstico de Windows 10 para que se inicie automáticamente:**

1.  Abra un símbolo del sistema con privilegios elevados en el extremo:

    1. Vaya a **Inicio** y escriba **cmd**.

    1. Haga clic derecho en **Símbolo del sistema** y seleccione **Ejecutar como administrador**.

2.  Escriba el siguiente comando y presione **Entrar**:

    ```console
    sc config diagtrack start=auto
    ```

3.  Se muestra un mensaje de éxito. Para comprobar el cambio, escriba el siguiente comando y presione **Entrar**:

    ```console
    sc qc diagtrack
    ```


#### <a name="internet-connectivity"></a>Conectividad a Internet
La conectividad a Internet en dispositivos es necesaria directamente o a través del proxy.

El sensor Defender for Endpoint puede usar un ancho de banda promedio diario de 5 MB para comunicarse con el servicio en la nube de Defender for Endpoint e informar de los datos cibernéticos. Las actividades únicas, como las cargas de archivos y la colección de paquetes de investigación, no se incluyen en este ancho de banda promedio diario.

Para obtener más información acerca de las opciones de configuración de proxy adicionales, vea [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).

Antes de incorporar dispositivos, el servicio de datos de diagnóstico debe estar habilitado. El servicio está habilitado de forma predeterminada en Windows 10.


## <a name="microsoft-defender-antivirus-configuration-requirement"></a>Requisito de configuración de Antivirus de Microsoft Defender
El agente de Defender for Endpoint depende de la capacidad de Antivirus de Microsoft Defender para examinar archivos y proporcionar información sobre ellos.

Configure las actualizaciones de inteligencia de seguridad en los dispositivos defender para puntos de conexión independientemente de si antivirus de Microsoft Defender es el antimalware activo o no. Para obtener más información, vea [Manage Microsoft Defender Antivirus updates and apply baselines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus).

Cuando Antivirus de Microsoft Defender no es el antimalware activo de la organización y usa el servicio Defender para endpoints, Antivirus de Microsoft Defender pasa al modo pasivo.

Si su organización ha desactivado Antivirus de Microsoft Defender a través de la directiva de grupo u otros métodos, los dispositivos que están incorporados deben excluirse de esta directiva de grupo.

Si está incorporando servidores y Antivirus de Microsoft Defender no es el antimalware activo en sus servidores, antivirus de Microsoft Defender tendrá que configurarse para ir en modo pasivo o desinstalar. La configuración depende de la versión del servidor. Para obtener más información, vea [Compatibilidad de Antivirus de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus-compatibility.md).

> [!NOTE]
> La directiva de grupo normal no se aplica a la Protección contra alteraciones y los cambios en la configuración de Antivirus de Microsoft Defender se omitirán cuando esté la protección contra alteraciones.


## <a name="microsoft-defender-antivirus-early-launch-antimalware-elam-driver-is-enabled"></a>El controlador antimalware de inicio anticipado (ELAM) de Antivirus de Microsoft Defender está habilitado
Si ejecuta Antivirus de Microsoft Defender como el producto antimalware principal en sus dispositivos, el agente defender para endpoint se incorporará correctamente.

Si ejecuta un cliente antimalware de terceros y usa soluciones de administración de dispositivos móviles o Microsoft Endpoint Manager (rama actual), deberá asegurarse de que el controlador ELAM de Antivirus de Microsoft Defender está habilitado. Para obtener más información, vea [Ensure that Microsoft Defender Antivirus is not disabled by policy](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).


## <a name="related-topics"></a>Temas relacionados
- [Configurar Microsoft Defender para la implementación de puntos de conexión](production-deployment.md)
- [Dispositivos integrados](onboard-configure.md)
