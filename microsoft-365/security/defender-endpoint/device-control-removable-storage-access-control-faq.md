---
title: preguntas más frecuentes sobre el almacenamiento extraíble Microsoft Defender para punto de conexión Control de dispositivos
description: Responde a las preguntas más frecuentes sobre el almacenamiento extraíble de control de dispositivos MDE.
ms.service: microsoft-365-security
ms.subservice: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
ms.date: 08/25/2022
ms.reviewer: tewchen
search.appverid: met150
ms.openlocfilehash: 2b76369567e111e429c86a942bd11ab626606ca1
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68201559"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-frequently-asked-questions"></a>preguntas más frecuentes sobre el almacenamiento extraíble Microsoft Defender para punto de conexión Control de dispositivos

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

## <a name="how-do-i-generate-guid-for-group-idpolicyrule-identry-id"></a>Cómo generar GUID para id. de grupo, id. de regla de directiva o id. de entrada?

Puede generar el GUID a través de código abierto en línea o mediante PowerShell. Para obtener más información, vea [Cómo generar GUID a través de PowerShell](/powershell/module/microsoft.powershell.utility/new-guid).

![Captura de pantalla del GUID en PowerShell.](https://user-images.githubusercontent.com/81826151/159046476-26ea0a21-8087-4f01-b8ae-5aa73b392d8f.png)

## <a name="what-are-the-removable-storage-media-and-policy-limitations"></a>¿Cuáles son las limitaciones de directivas y medios de almacenamiento extraíbles?

La llamada de back-end se realiza a través de OMA-URI (GET para leer o PATCH para actualizar) desde el Centro de administración de Microsoft Endpoint Manager (Intune) o a través de Microsoft Graph API. La limitación es la misma que cualquier perfil de configuración personalizada de OMA-URI en Microsoft, que oficialmente tiene 350 000 caracteres para los archivos XML.

Por ejemplo, si necesita dos bloques de entradas por SID de usuario para "Permitir" o "Auditar permitidos" usuarios específicos y, a continuación, dos bloques de entradas al final para "Denegar" todos, podrá administrar 2.276 usuarios.

## <a name="why-doesnt-the-policy-work"></a>¿Por qué la directiva no funciona?

1. La razón más común es que no hay ninguna [versión de cliente antimalware](/microsoft-365/security/defender-endpoint/device-control-removable-storage-access-control#prepare-your-endpoints) necesaria.

2. Otra razón podría ser que el archivo XML no tiene el formato correcto. Por ejemplo, si no se usa el formato markdown correcto para el carácter "&" en el archivo XML o el editor de texto puede agregar una marca de orden de bytes (BOM) 0xEF 0xBB 0xBF al principio de los archivos, lo que hace que el análisis XML no funcione. Una solución sencilla consiste en descargar el [archivo de ejemplo](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) (seleccione **Sin procesar** y, a continuación, **Guardar como**) y, a continuación, actualizar.

3. Si va a implementar y administrar la directiva mediante directiva de grupo, asegúrese de combinar todo PolicyRule en un archivo XML dentro de un nodo primario denominado PolicyRules. Combine también todos los grupos en un archivo XML dentro de un nodo primario denominado Grupos. Si administra a través de Intune, mantenga un archivo XML PolicyRule y un archivo XML group one.

Si todavía no funciona, póngase en contacto con el soporte técnico y comparta su cabina de soporte técnico. Para obtener ese archivo, use el símbolo del sistema como administrador: 

`"%programfiles%\Windows Defender\MpCmdRun.exe" -GetFiles`

## <a name="why-is-there-no-configuration-ux-for-some-policy-groups"></a>¿Por qué no hay experiencia de usuario de configuración para algunos grupos de directivas? 

No hay ninguna experiencia de usuario de configuración para **Definir grupos de directivas de control de dispositivos** y **Definir reglas de directiva de control de dispositivos** en el directiva de grupo. Sin embargo, puede obtener los archivos .adml y .admx relacionados seleccionando **Raw** y **Save as** en los archivos [WindowsDefender.adml](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/WindowsDefender.adml) y [WindowsDefender.admx](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/WindowsDefender.admx) .

## <a name="how-do-i-confirm-that-the-latest-policy-has-been-deployed-to-the-target-machine"></a>Cómo confirmar que la directiva más reciente se ha implementado en la máquina de destino?

Puede ejecutar el cmdlet `Get-MpComputerStatus` de PowerShell como administrador. El siguiente valor mostrará si la directiva más reciente se ha aplicado a la máquina de destino.

:::image type="icon" source="images/148609885-bea388a9-c07d-47ef-b848-999d794d24b8.png" border="false":::

## <a name="how-can-i-know-which-machine-is-using-out-of-date-anti-malware-client-version-in-the-organization"></a>¿Cómo puedo saber qué máquina usa la versión de cliente antimalware obsoleta en la organización?

Puede usar la siguiente consulta para obtener la versión de cliente antimalware en el portal de seguridad de Microsoft 365:

```kusto
//check the anti-malware client version
DeviceFileEvents
|where FileName == "MsMpEng.exe"
|where FolderPath contains @"C:\ProgramData\Microsoft\Windows Defender\Platform\"
|extend PlatformVersion=tostring(split(FolderPath, "\\", 5))
//|project DeviceName, PlatformVersion // check which machine is using legacy platformVersion
|summarize dcount(DeviceName) by PlatformVersion // check how many machines are using which platformVersion
|order by PlatformVersion desc
```

## <a name="how-do-i-find-the-media-property-in-the-device-manager"></a>Cómo encontrar la propiedad media en el Administrador de dispositivos?

1. Conecte el medio.

2. Abra el Administrador de dispositivos. 

   ![Captura de pantalla de Administrador de dispositivos.](https://user-images.githubusercontent.com/81826151/181859412-affd6aa1-09ad-44bf-9541-330499cc2c87.png)

3. Busque el medio en el Administrador de dispositivos, haga clic con el botón derecho y, a continuación, seleccione **Propiedades**.

   :::image type="content" alt-text="Captura de pantalla de los medios en el Administrador de dispositivos." source="https://user-images.githubusercontent.com/81826151/181859700-62a6f704-b12e-41e3-a048-7d63432654a4.png":::

4. Abra **Detalles** y seleccione **Propiedades**.

   :::image type="content" alt-text="Captura de pantalla de la propiedad del dispositivo en Administrador de dispositivos." source="https://user-images.githubusercontent.com/81826151/181859852-00bc8b11-8ee5-4d46-9770-fa29f894d13f.png":::
    