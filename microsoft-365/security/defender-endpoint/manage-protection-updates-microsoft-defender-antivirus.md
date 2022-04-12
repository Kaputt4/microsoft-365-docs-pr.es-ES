---
title: Administrar cómo y dónde Antivirus de Microsoft Defender recibe actualizaciones
description: Administre el orden de reserva para saber cómo Antivirus de Microsoft Defender recibe actualizaciones de protección.
keywords: actualizaciones, líneas base de seguridad, protección, orden de reserva, ADL, MMPC, UNC, ruta de acceso de archivo, recurso compartido, wsus
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: 076b445a6ac129c1debd7cba813798f51aa6f86b
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/12/2022
ms.locfileid: "64789038"
---
# <a name="manage-the-sources-for-microsoft-defender-antivirus-protection-updates"></a>Administrar el original para las actualizaciones de protección del Antivirus de Windows Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

<a id="protection-updates"></a>
<!-- this has been used as anchor in VDI content -->

Mantener actualizada la protección antivirus es fundamental. Hay dos componentes para administrar las actualizaciones de protección para Antivirus de Microsoft Defender:

- *Dónde* se descargan las actualizaciones; Y
- *Cuando* se descargan y aplican actualizaciones.

En este artículo se describe cómo especificar desde dónde se deben descargar las actualizaciones (esto también se conoce como pedido de reserva). Consulte [el tema Administrar Antivirus de Microsoft Defender actualizaciones y aplicar líneas base](manage-updates-baselines-microsoft-defender-antivirus.md) para obtener información general sobre cómo funcionan las actualizaciones y cómo configurar otros aspectos de las actualizaciones (como la programación de actualizaciones).

> [!IMPORTANT]
> Antivirus de Microsoft Defender las actualizaciones de la plataforma y las actualizaciones de inteligencia de seguridad se entregan a través de Windows Update y, a partir del lunes 21 de octubre de 2019, todas las actualizaciones de inteligencia de seguridad se firmarán exclusivamente en SHA-2. Los dispositivos deben actualizarse para admitir SHA-2 con el fin de actualizar la inteligencia de seguridad. Para obtener más información, consulte [2019 SHA-2 Code Signing Support requirement for Windows and WSUS (Requisito de compatibilidad con la firma de código SHA-2 de 2019 para Windows y WSUS](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus)).

<a id="fallback-order"></a>

## <a name="fallback-order"></a>Orden de reserva

Normalmente, los puntos de conexión se configuran para descargar actualizaciones individualmente desde un origen principal seguidos de otros orígenes en orden de prioridad, en función de la configuración de red. Las actualizaciones se obtienen de orígenes en el orden especificado. Si las actualizaciones del origen actual están obsoletas, el siguiente origen de la lista se usa inmediatamente.

Cuando se publican las actualizaciones, se aplica alguna lógica para minimizar el tamaño de la actualización. En la mayoría de los casos, solo se descargan y aplican las diferencias entre la actualización más reciente y la actualización que está instalada actualmente (esto se conoce como delta) en el dispositivo. Sin embargo, el tamaño de la diferencia depende de dos factores principales:

- La antigüedad de la última actualización en el dispositivo; Y
- Origen que se usa para descargar y aplicar actualizaciones.

Cuanto más antiguas sean las actualizaciones en un punto de conexión, mayor será la descarga. Sin embargo, también debe tener en cuenta la frecuencia de descarga. Una programación de actualización más frecuente puede dar lugar a un mayor uso de la red, mientras que una programación menos frecuente puede dar lugar a tamaños de archivo más grandes por descarga.

Hay cinco ubicaciones donde puede especificar dónde debe obtener actualizaciones un punto de conexión:

- [Microsoft Update](https://support.microsoft.com/help/12373/windows-update-faq)
- [Windows Server Update Service](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus) <sup>[[1](#fn1)]<sup></sup>  
- [Microsoft Endpoint Configuration Manager](/configmgr/core/servers/manage/updates)
- [Recurso compartido de archivos de red](#unc-share)
- [Actualizaciones de inteligencia de seguridad para Antivirus de Microsoft Defender y otros antimalware](https://www.microsoft.com/wdsi/defenderupdates) <sup>de Microsoft [[2](#fn1)]<sup></sup>

(<a id="fn1">1</a>) Intune servidor de actualización de definiciones internas: si usa SCCM/SUP para obtener actualizaciones de definiciones para Antivirus de Microsoft Defender y necesita acceder a Windows Update en dispositivos cliente bloqueados, puede realizar la transición a la administración conjunta y descargar la carga de trabajo de Endpoint Protection a Intune. En la directiva antimalware configurada en Intune hay una opción para "servidor de actualización de definiciones internas" que se puede configurar para usar WSUS local como origen de actualización. Esto le ayuda a controlar qué actualizaciones del servidor wu oficial están aprobadas para la empresa, y también ayuda a proxy y a guardar el tráfico de red a la red oficial Windows UPdates.

(<a id="fn1">2</a>) Es posible que la directiva y el registro aparezcan como inteligencia de seguridad Centro de protección contra malware de Microsoft (MMPC), su nombre anterior.

Para garantizar el mejor nivel de protección, Microsoft Update permite versiones rápidas, lo que significa descargas más pequeñas con frecuencia. El servicio Windows Server Update, Microsoft Endpoint Configuration Manager, las actualizaciones de inteligencia de seguridad de Microsoft y los orígenes de actualizaciones de plataforma ofrecen actualizaciones menos frecuentes. Por lo tanto, el delta puede ser mayor, lo que da lugar a descargas más grandes.

> [!NOTE]
> Las actualizaciones de inteligencia de seguridad contienen actualizaciones del motor y se publican con una cadencia mensual.
Las actualizaciones de inteligencia de seguridad también se entregan varias veces al día, pero este paquete no contiene un motor.


> [!IMPORTANT]
> Si ha establecido las actualizaciones de [la página de inteligencia de](https://www.microsoft.com/security/portal/definitions/adl.aspx) seguridad de Microsoft como origen de reserva después de Windows Server Update Service o Microsoft Update, las actualizaciones solo se descargan de las actualizaciones de inteligencia de seguridad y de la plataforma cuando la actualización actual se considera obsoleta. (De forma predeterminada, se trata de siete días consecutivos de no poder aplicar actualizaciones desde Windows Server Update Service o servicios de Microsoft Update).
> Sin embargo, puede [establecer el número de días antes de que la protección se notifique como obsoleta](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date).<p>
> A partir del lunes 21 de octubre de 2019, las actualizaciones de inteligencia de seguridad y las actualizaciones de la plataforma estarán firmadas exclusivamente por SHA-2. Los dispositivos deben actualizarse para admitir SHA-2 con el fin de obtener las últimas actualizaciones de inteligencia de seguridad y actualizaciones de la plataforma. Para obtener más información, consulte [2019 SHA-2 Code Signing Support requirement for Windows and WSUS (Requisito de compatibilidad con la firma de código SHA-2 de 2019 para Windows y WSUS](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus)).

Cada origen tiene escenarios típicos que dependen de cómo se configura la red, además de la frecuencia con la que publican actualizaciones, como se describe en la tabla siguiente:

<br/><br/>

|Ubicación|Ejemplo ficticio|
|---|---|
|Windows Server Update Service|Está usando Windows Server Update Service para administrar las actualizaciones de la red.|
|Microsoft Update|Quiere que los puntos de conexión se conecten directamente a Microsoft Update. Esto puede ser útil para los puntos de conexión que se conectan de forma irregular a la red empresarial o si no usa Windows Server Update Service para administrar las actualizaciones.|
|Compartir archivos|Tiene dispositivos no conectados a Internet (por ejemplo, máquinas virtuales). Puede usar el host de máquina virtual conectado a Internet para descargar las actualizaciones en un recurso compartido de red, desde el que las máquinas virtuales pueden obtener las actualizaciones. Consulte la [guía de implementación de VDI](deployment-vdi-microsoft-defender-antivirus.md) para ver cómo se pueden usar recursos compartidos de archivos en entornos de infraestructura de escritorio virtual (VDI).|
|Administrador de puntos de conexión de Microsoft|Está usando Microsoft Endpoint Manager para actualizar los puntos de conexión.|
|Actualizaciones de inteligencia de seguridad y actualizaciones de plataforma para Antivirus de Microsoft Defender y otro antimalware de Microsoft (anteriormente conocido como MMPC)|[Asegúrese de que los dispositivos están actualizados para admitir SHA-2](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus). Antivirus de Microsoft Defender las actualizaciones de la plataforma e inteligencia de seguridad se entregan a través de Windows Update, y a partir del lunes 21 de octubre de 2019, las actualizaciones de inteligencia de seguridad y las actualizaciones de la plataforma estarán firmadas exclusivamente por SHA-2. <br/>Descargue las últimas actualizaciones de protección debido a una infección reciente o para ayudar a aprovisionar una imagen fuerte y base para la [implementación de VDI](deployment-vdi-microsoft-defender-antivirus.md). Por lo general, esta opción solo se debe usar como origen de reserva final y no como origen principal. Solo se usará si las actualizaciones no se pueden descargar desde Windows Server Update Service o Microsoft Update durante [un número especificado de días](/microsoft-365/security/defender-endpoint/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date).|

Puede administrar el orden en que se usan los orígenes de actualización con directiva de grupo, Microsoft Endpoint Configuration Manager, cmdlets de PowerShell y WMI.

> [!IMPORTANT]
> Si establece Windows Server Update Service como una ubicación de descarga, debe aprobar las actualizaciones, independientemente de la herramienta de administración que use para especificar la ubicación. Puede configurar una regla de aprobación automática con Windows Server Update Service, que podría ser útil, ya que las actualizaciones llegan al menos una vez al día. Para más información, consulte [Sincronización de actualizaciones de Endpoint Protection en Windows Server Update Service independiente](/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).

Los procedimientos de este artículo describen primero cómo establecer el orden y, a continuación, cómo configurar la opción **Recurso compartido** de archivos si la ha habilitado.

## <a name="use-group-policy-to-manage-the-update-location"></a>Uso de directiva de grupo para administrar la ubicación de actualización

1. En la máquina de administración de directiva de grupo, abra la [consola de administración de directiva de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), haga clic con el botón derecho en el objeto directiva de grupo que desea configurar y haga clic en **Editar**.

2. En el **Editor de administración de directiva de grupo** vaya a **Configuración del equipo**.

3. Haga clic en **Directivas** y, a continuación, **en Plantillas administrativas**.

4. Expanda el árbol para **Windows componentes** \> **Windows Defender** \> **actualizaciones de firma** y configure los valores siguientes:

   1. Haga doble clic en **la opción Definir el orden de los orígenes para descargar las actualizaciones de inteligencia de seguridad** y establezca la opción **en Habilitado**.

   2. Escriba el orden de los orígenes, separados por una sola canalización, por ejemplo: `InternalDefinitionUpdateServer|MicrosoftUpdateServer|MMPC`, como se muestra en la captura de pantalla siguiente.

      :::image type="content" source="../../media/wdav-order-update-sources.png" alt-text="Configuración de directiva de grupo que enumera el orden de los orígenes" lightbox="../../media/wdav-order-update-sources.png":::

   3. Seleccione **Aceptar**. Esto establecerá el orden de los orígenes de actualización de protección.

   4. Haga doble clic en la opción **Definir recursos compartidos de archivos para descargar actualizaciones de inteligencia de seguridad** y establezca la opción **en Habilitado**.

   5. Especifique el origen del recurso compartido de archivos. Si tiene varios orígenes, escriba cada origen en el orden en que se deben usar, separados por una sola canalización. Use la [notación UNC estándar](/openspecs/windows_protocols/ms-dtyp/62e862f4-2a51-452e-8eeb-dc4ff5ee33cc) para indicar la ruta de acceso, por ejemplo: `\\host-name1\share-name\object-name|\\host-name2\share-name\object-name`. Si no escribe ninguna ruta de acceso, este origen se omitirá cuando la máquina virtual descargue las actualizaciones.

   6. Haga clic en **Aceptar**. Esto establecerá el orden de los recursos compartidos de archivos cuando se haga referencia a ese origen en **la configuración de directiva definir el orden de los orígenes...** de grupo.

> [!NOTE]
> Para Windows 10, versiones 1703 hasta 1809 incluidas, la ruta de acceso de la directiva es **Windows Components > Antivirus de Microsoft Defender > Signature Updates** For Windows 10, versión 1903, la ruta de acceso de la directiva es **Windows Components > actualizaciones de inteligencia de seguridad de Antivirus de Microsoft Defender >**

## <a name="use-configuration-manager-to-manage-the-update-location"></a>Uso de Configuration Manager para administrar la ubicación de actualización

Consulte [Configuración de actualizaciones de inteligencia de seguridad para Endpoint Protection](/configmgr/protect/deploy-use/endpoint-definition-updates) para obtener más información sobre la configuración de Microsoft Endpoint Manager (rama actual).

## <a name="use-powershell-cmdlets-to-manage-the-update-location"></a>Uso de cmdlets de PowerShell para administrar la ubicación de actualización

Use los siguientes cmdlets de PowerShell para establecer el orden de actualización.

```PowerShell
Set-MpPreference -SignatureFallbackOrder {LOCATION|LOCATION|LOCATION|LOCATION}
Set-MpPreference -SignatureDefinitionUpdateFileSharesSource {\\UNC SHARE PATH|\\UNC SHARE PATH}
```

Consulte los artículos siguientes para obtener más información:

- [Set-MpPreference -SignatureFallbackOrder](/powershell/module/defender/set-mppreference)
- [Set-MpPreference -SignatureDefinitionUpdateFileSharesSource](/powershell/module/defender/set-mppreference#-signaturedefinitionupdatefilesharessources)
- [Use cmdlets de PowerShell para configurar y ejecutar Antivirus de Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Cmdlets de Antivirus de Defender](/powershell/module/defender/index)

## <a name="use-windows-management-instruction-wmi-to-manage-the-update-location"></a>Uso de Windows Management Instruction (WMI) para administrar la ubicación de actualización

Use el [método **Set** de la clase **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para las siguientes propiedades:

```WMI
SignatureFallbackOrder
SignatureDefinitionUpdateFileSharesSource
```

Consulte los artículos siguientes para obtener más información:

- [API Windows Defender WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="use-mobile-device-management-mdm-to-manage-the-update-location"></a>Uso de Mobile Administración de dispositivos (MDM) para administrar la ubicación de actualización

Consulte [CSP de directiva: Defender/SignatureUpdateFallbackOrder](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdatefallbackorder) para obtener más información sobre cómo configurar MDM.

## <a name="what-if-were-using-a-third-party-vendor"></a>¿Qué ocurre si usamos un proveedor de terceros?

En este artículo se describe cómo configurar y administrar actualizaciones para Antivirus de Microsoft Defender. Sin embargo, se pueden usar proveedores de terceros para realizar estas tareas.

Por ejemplo, supongamos que Contoso ha contratado a Fabrikam para administrar su solución de seguridad, lo que incluye Antivirus de Microsoft Defender. Fabrikam suele usar [Windows Instrumentación de administración](./use-wmi-microsoft-defender-antivirus.md), [cmdlets de PowerShell](./use-powershell-cmdlets-microsoft-defender-antivirus.md) o [Windows línea de comandos](./command-line-arguments-microsoft-defender-antivirus.md) para implementar revisiones y actualizaciones.

> [!NOTE]
> Microsoft no prueba soluciones de terceros para administrar Antivirus de Microsoft Defender.

<a id="unc-share"></a>

## <a name="create-a-unc-share-for-security-intelligence-and-platform-updates"></a>Creación de un recurso compartido de UNC para la inteligencia de seguridad y las actualizaciones de la plataforma

Configure un recurso compartido de archivos de red (unidad UNC/asignada) para descargar la inteligencia de seguridad y las actualizaciones de la plataforma desde el sitio MMPC mediante una tarea programada.

1. En el sistema en el que desea aprovisionar el recurso compartido y descargar las actualizaciones, cree una carpeta en la que guardará el script.

    ```console
    Start, CMD (Run as admin)
    MD C:\Tool\PS-Scripts\
    ```

2. Cree la carpeta en la que guardará las actualizaciones de firma.

    ```console
    MD C:\Temp\TempSigs\x64
    MD C:\Temp\TempSigs\x86
    ```

3. Descargue el script de PowerShell de [www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4).

4. Haga clic en **Descargar manual**.

5. Haga clic en **Descargar el archivo nupkg sin procesar**.

6. Extraiga el archivo.

7. Copie el archivo SignatureDownloadCustomTask.ps1 en la carpeta que creó anteriormente, `C:\Tool\PS-Scripts\` .

8. Use la línea de comandos para configurar la tarea programada.

   > [!NOTE]
   > Hay dos tipos de actualizaciones: full y delta.

   - Para x64 delta:

       ```powershell
       Powershell (Run as admin)

       C:\Tool\PS-Scripts\

       ".\SignatureDownloadCustomTask.ps1 -action create -arch x64 -isDelta $true -destDir C:\Temp\TempSigs\x64 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

   - Para x64 completo:

       ```powershell
       Powershell (Run as admin)

       C:\Tool\PS-Scripts\

       ".\SignatureDownloadCustomTask.ps1 -action create -arch x64 -isDelta $false -destDir C:\Temp\TempSigs\x64 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

   - Para x86 delta:

       ```powershell
       Powershell (Run as admin)

       C:\Tool\PS-Scripts\

       ".\SignatureDownloadCustomTask.ps1 -action create -arch x86 -isDelta $true -destDir C:\Temp\TempSigs\x86 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

   - Para x86 completo:

       ```powershell
       Powershell (Run as admin)

       C:\Tool\PS-Scripts\

       ".\SignatureDownloadCustomTask.ps1 -action create -arch x86 -isDelta $false -destDir C:\Temp\TempSigs\x86 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

   > [!NOTE]
   > Cuando se crean las tareas programadas, puede encontrarlas en el Programador de tareas en `Microsoft\Windows\Windows Defender`.

9. Ejecute cada tarea manualmente y compruebe que tiene datos (`mpam-d.exe`, `mpam-fe.exe`y `nis_full.exe`) en las carpetas siguientes (es posible que haya elegido ubicaciones diferentes):

   - `C:\Temp\TempSigs\x86`
   - `C:\Temp\TempSigs\x64`

   Si se produce un error en la tarea programada, ejecute los siguientes comandos:

    ```console
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x64 -isDelta $False -destDir C:\Temp\TempSigs\x64"

    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x64 -isDelta $True -destDir C:\Temp\TempSigs\x64"

    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x86 -isDelta $False -destDir C:\Temp\TempSigs\x86"

    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x86 -isDelta $True -destDir C:\Temp\TempSigs\x86"
    ```

    > [!NOTE]
    > Los problemas también pueden deberse a la directiva de ejecución.

10. Cree un recurso compartido que apunte a `C:\Temp\TempSigs` (por ejemplo, `\\server\updates`).

    > [!NOTE]
    > Como mínimo, los usuarios autenticados deben tener acceso de "Lectura". Este requisito también se aplica a los equipos de dominio, el recurso compartido y NTFS (seguridad).

11. Establezca la ubicación del recurso compartido de la directiva en el recurso compartido.

    > [!NOTE]
    > No agregue la carpeta x64 (o x86) en la ruta de acceso. El proceso de mpcmdrun.exe lo agrega automáticamente.

> [!TIP]
> Si busca información relacionada con antivirus para otras plataformas, consulte:
> - [Establecer preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configuración de características de Defender para punto de conexión en Android](android-configure.md)
> - [Configuración de Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)

## <a name="related-articles"></a>Artículos relacionados

- [Implementación de Antivirus de Microsoft Defender](deploy-manage-report-microsoft-defender-antivirus.md)
- [Administración de actualizaciones Antivirus de Microsoft Defender y aplicación de líneas base](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Administrar las actualizaciones de los puntos de conexión que están obsoletos](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [Administrar las actualizaciones forzadas basadas en eventos](manage-event-based-updates-microsoft-defender-antivirus.md)
- [Administración de actualizaciones para dispositivos móviles y máquinas virtuales](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
