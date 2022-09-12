---
title: Información y configuración de la detección de señales del explorador de administración de riesgos internos
description: Más información sobre la detección de señales del explorador de administración de riesgos internos en Microsoft Purview
keywords: Microsoft 365, Microsoft Purview, riesgo interno, administración de riesgos, cumplimiento
ms.localizationpriority: medium
ms.service: O365-seccomp
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.openlocfilehash: 20501814ccf87cfbbda6080b60515be374516cd2
ms.sourcegitcommit: a6cbc057e757771cc0e7b53b184fab9fa53a658a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2022
ms.locfileid: "67648623"
---
# <a name="learn-about-and-configure-insider-risk-management-browser-signal-detection"></a>Información y configuración de la detección de señales del explorador de administración de riesgos internos

Los exploradores web a menudo los usan los usuarios para acceder a archivos confidenciales y no confidenciales dentro de una organización. La administración de riesgos internos permite a su organización detectar y actuar sobre señales de filtración de exploradores para todos los archivos no ejecutables vistos en los exploradores [Microsoft Edge](https://www.microsoft.com/edge) y [Google Chrome](https://www.google.com/chrome) . Con estas señales, los analistas e investigadores pueden actuar rápidamente cuando los usuarios de directivas de ámbito realizan cualquiera de las siguientes actividades al usar estos exploradores:

- Archivos copiados en el almacenamiento en la nube personal
- Archivos impresos en dispositivos locales o de red
- Archivos transferidos o copiados a un recurso compartido de red
- Archivos copiados en dispositivos USB
- Exploración de sitios web de riesgo

Las señales de estos eventos se detectan en Microsoft Edge mediante funcionalidades integradas del explorador y mediante el complemento *Extensión de cumplimiento de Microsoft* . En Google Chrome, los clientes usan la *extensión de cumplimiento de Microsoft* para la detección de señales.

En la tabla siguiente se resumen las actividades detectadas y la compatibilidad con extensiones para cada explorador:

| **Actividades detectadas**                        | **Microsoft Edge** | **Google Chrome** |
| ---------------------------------------------- | ------------------ | ----------------- |
| Archivos copiados en el almacenamiento en la nube personal         | Nativa             | Extensión         |
| Archivos impresos en dispositivos locales o de red      | Nativa             | Extensión         |
| Archivos transferidos o copiados a un recurso compartido de red | Extensión          | Extensión         |
| Archivos copiados en dispositivos USB                    | Extensión          | Extensión         |
| Exploración de sitios web de riesgo                        | Extensión          | Extensión         |

## <a name="common-requirements"></a>Requisitos comunes

Antes de instalar el complemento de Microsoft Edge o la extensión de Google Chrome, los clientes deben asegurarse de que los dispositivos para los usuarios de directivas dentro del ámbito cumplan los siguientes requisitos:

- Se recomienda la compilación más reciente Windows 10 x64, Windows 10 compilación x64 1809 como mínimo para la compatibilidad con la detección de señales. La detección de señales del explorador no se admite actualmente en dispositivos que no son de Windows.
- Suscripción actual de [Microsoft 365](/microsoft-365/compliance/insider-risk-management-configure#subscriptions-and-licensing) con soporte técnico para la administración de riesgos internos.
- Los dispositivos deben [incorporarse](/microsoft-365/compliance/insider-risk-management-settings#enable-device-indicators-and-onboard-devices) al portal de cumplimiento Microsoft Purview.

Para conocer los requisitos de configuración específicos del explorador, consulte las secciones Microsoft Edge y Google Chrome más adelante en este artículo.

## <a name="additional-requirements"></a>Requisitos adicionales 

Si usa directivas basadas en la plantilla *de uso de explorador de riesgo*, se debe seleccionar al menos un *indicador de exploración* en **Indicadores de directivas** de **configuración** >  de **administración** >  de riesgos internos.

## <a name="configure-browser-signal-detection-for-microsoft-edge"></a>Configuración de la detección de señales del explorador para Microsoft Edge

### <a name="microsoft-edge-browser-requirements"></a>Requisitos del explorador Microsoft Edge

- Cumplir los requisitos comunes
- Versión más reciente de Microsoft Edge x64 (91.0.864.41 o posterior)
- Complemento *de extensión de cumplimiento de Microsoft* más reciente (1.0.0.44 o posterior)
- Edge.exe no está configurado como un explorador no permitido

### <a name="option-1-basic-setup-recommended-for-testing-with-edge"></a>Opción 1: Configuración básica (se recomienda para las pruebas con Edge)

Use esta opción para configurar un autohospedaje de máquina único para cada dispositivo de la organización al probar la detección de señales del explorador.

Para la opción de configuración básica, complete los pasos siguientes:

1. Vaya a [Extensión de cumplimiento de Microsoft](https://microsoftedge.microsoft.com/addons/detail/microsoft-compliance-exte/lcmcgbabdcbngcbcfabdncmoppkajglo).
2. Instale la extensión.

### <a name="option-2-intune-setup-for-edge"></a>Opción 2: configuración de Intune para Edge

Use esta opción para configurar la extensión y los requisitos de su organización mediante Intune.

Para la opción de configuración Intune, complete los pasos siguientes:

1. Inicie sesión en el [Centro de Endpoint Manager Administración de Microsoft](https://endpoint.microsoft.com) con permisos de administrador.
2. Vaya a **Perfiles de configuración**.
3. Seleccione **Crear perfil**.
4. Elija **Windows 10** como plataforma.
5. Elija **Plantillas administrativas** como *Tipo de perfil* y seleccione **Crear.**
6. Seleccione la pestaña **Configuración**.
7. Seleccione **Edge Version 77 y versiones posteriores.**
8. Busque **Extensiones** , que le proporciona información general sobre todas las configuraciones relacionadas con las extensiones.
9. Seleccione la configuración **Control de las extensiones que se instalan de forma silenciosa.**
10. Seleccione **Habilitado.**
11. Agregue el identificador de extensión cuando se le solicite: *lcmcgbabdcbngcbcfabdncmoppkajglo***.**
12. Seleccione **Aceptar.**

### <a name="option-3-group-policy-setup-for-edge"></a>Opción 3: configuración de directiva de grupo para Edge

Use esta opción para configurar la extensión y los requisitos de toda la organización mediante directiva de grupo.

Para la opción de configuración directiva de grupo, complete los pasos siguientes:

**Paso 1: Importe el archivo de plantilla administrativa de Microsoft Edge (.admx) más reciente.**

Los dispositivos deben administrarse mediante directivas de grupo y todas las [plantillas administrativas de Microsoft Edge](https://www.microsoft.com/edge/business/download) deben importarse en el almacén central de directiva de grupo. Para más información, consulte [Cómo crear y administrar el almacén central de plantillas administrativas de directiva de grupo en Windows](/troubleshoot/windows-client/group-policy/create-and-manage-central-store).

**Paso 2: Agregue el complemento *Extensión de cumplimiento de Microsoft* a la lista *Forzar instalación* .**

Complete los pasos siguientes para agregar la extensión:

1. En el **Editor de administración de directiva de grupo**, vaya a la unidad organizativa (OU).
2. Expanda la siguiente ruta de acceso **Directivas** de configuración \> de **equipo o usuario** **Plantillas** \> \> **administrativas** \> **clásicas Extensiones de** **Microsoft Edge**\>. Esta ruta de acceso puede variar en función de la configuración de la organización.
3. Seleccione **Configurar qué extensiones se instalan de forma silenciosa.**
4. Haga clic con el botón derecho y seleccione **Editar**.
5. Active el botón **de radio Habilitado** .
6. Seleccionar **Mostrar**.
7. En **Valor**, agregue la entrada siguiente: *lcmcgbabdcbngcbcfabdncmoppkajglo;https://edge.microsoft.com/extensionwebstorebase/v1/crx*
8. Seleccione **Aceptar** y seleccione **Aplicar**.

## <a name="configure-browser-signal-detection-for-google-chrome"></a>Configuración de la detección de señales del explorador para Google Chrome

La compatibilidad con la detección de señales del explorador de administración de riesgos internos para Google Chrome está habilitada a través de la *extensión de cumplimiento de Microsoft*. Esta extensión también admite DLP de punto de conexión en Chrome. Para obtener más información sobre la compatibilidad con DLP de punto de conexión, consulte [Introducción a la extensión de cumplimiento de Microsoft (versión preliminar).](/microsoft-365/compliance/dlp-chrome-get-started)

### <a name="google-chrome-browser-requirements"></a>Requisitos del explorador Google Chrome

- Cumplir los requisitos comunes
- Versión más reciente de Google Chrome x64
- Versión más reciente *de la extensión de cumplimiento de Microsoft* (2.0.0.183 o posterior)
- Chrome.exe no está configurado como un explorador no permitido

### <a name="option-1-basic-setup-recommended-for-testing-with-chrome"></a>Opción 1: Configuración básica (se recomienda para las pruebas con Chrome)

Use esta opción para configurar un autohospedaje de máquina único para cada dispositivo de la organización al probar la detección de señales del explorador.

Para la opción de configuración básica, complete los pasos siguientes:

**Paso 1: Habilitar las claves del Registro necesarias con PowerShell**

```PowerShell
Get-Item -path "HKLM:\\SOFTWARE\\Microsoft\\Windows Defender\\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
```

>[!Important]
>Estas claves del Registro son necesarias para garantizar la funcionalidad adecuada de la extensión. Debe habilitar estas claves del Registro antes de probar las señales.*

**Paso 2: Instalar la *extensión de cumplimiento de Microsoft***

1. Vaya a [Extensión de cumplimiento de Microsoft](https://chrome.google.com/webstore/detail/microsoft-compliance-exte/echcggldkblhodogklpincgchnpgcdco).
2. Instale la extensión.

### <a name="option-2-intune-setup-for-chrome"></a>Opción 2: configuración de Intune para Chrome

Use esta opción para configurar la extensión y los requisitos de su organización mediante Intune.

Para la opción de configuración Intune, complete los pasos siguientes:

**Paso 1: Habilitar la clave del Registro necesaria con Intune**

1. Ejecute el siguiente script de PowerShell:

```PowerShell
Get-Item -path "HKLM:\\SOFTWARE\\Microsoft\\Windows Defender\\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
```

2. Inicie sesión en el [Centro de Endpoint Manager Administración de Microsoft](https://endpoint.microsoft.com).
3. Vaya a **Scripts de dispositivos** \> y seleccione **Agregar.** 
4. Cuando se le solicite, vaya a la ubicación del script creado.
5. Seleccione la siguiente configuración:

    - Ejecute este script con las credenciales iniciadas: *Sí*
    - Aplicar comprobación de firma de script: *No*
    - Ejecución de un script en un host de PowerShell de 64 bits: *Sí*

6. Seleccione los grupos de dispositivos adecuados y aplique la directiva.

**Paso 2: Configurar Intune forzar la instalación**

Antes de agregar la extensión de Chrome DLP de Microsoft a la lista de extensiones instaladas por fuerza, debe instalar el archivo de plantilla administrativa de Chrome (.admx) para la administración de Intune. Para obtener instrucciones paso a paso, consulta [Administrar Chrome Browser con Microsoft Intune](https://support.google.com/chrome/a/answer/9102677?hl=en#zippy=%2Cstep-ingest-the-chrome-admx-file-into-intune). Después de instalar el archivo de plantilla administrativa, complete los pasos siguientes:

1. Inicie sesión en el [Centro de Endpoint Manager Administración de Microsoft](https://endpoint.microsoft.com).
2. Vaya a **Perfiles de configuración**.
3. Seleccione **Crear perfil**.
4. Elija **Windows 10** como *plataforma*.
5. Elija **Personalizado** como tipo *de perfil* .
6. Seleccione la pestaña **Configuración**.
7. Seleccione **Agregar.**
8. Escriba la siguiente información de directiva:

    - OMA-URI: *./Device/Vendor/MSFT/Policy/Config/Chrome~Policy~googlechrome~Extensions/ExtensionInstallForcelist*
    - Tipo de datos: *String*
    - Valor: *\<enabled/\>\<data id="ExtensionInstallForcelistDesc" value="1&\#xF000; echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx"/\>*

9. Seleccione **Crear**.

### <a name="option-3-group-policy-setup-for-chrome"></a>Opción 3: configuración de directiva de grupo para Chrome

Use esta opción para configurar la extensión y los requisitos de toda la organización mediante directiva de grupo.

Para la opción de configuración directiva de grupo, complete los pasos siguientes:

**Paso 1: Importar el archivo de plantilla administrativa de Chrome**

Los dispositivos deben poder administrarse mediante directiva de grupo y todas las [plantillas administrativas de Chrome](https://chromeenterprise.google/browser/download/) deben importarse a la tienda central de directiva de grupo. Para más información, consulte [Cómo crear y administrar el almacén central de plantillas administrativas de directiva de grupo en Windows](/troubleshoot/windows-client/group-policy/create-and-manage-central-store).

**Paso 2: Habilitar la clave del Registro necesaria con PowerShell**

1. Cree un script de PowerShell con el contenido siguiente:

    ```PowerShell
    Get-Item -path "HKLM:\\SOFTWARE\\Microsoft\\Windows Defender\\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
    ```

2. Abra la **Consola de administración de la directiva de grupo** y vaya a la unidad organizativa (OU).
3. Haga clic con el botón derecho y seleccione **Crear un GPO en este dominio y vincúlelo aquí**. Cuando se le solicite, asigne un nombre descriptivo a este objeto directiva de grupo (GPO). Por ejemplo, *script de PowerShell inmediato de Chrome DLP*.
4. Después de crear el GPO, haga clic con el botón derecho y seleccione **Editar**. Esta selección le lleva al objeto directiva de grupo.
5. Vaya a Configuración **del equipo** \> **Preferencias** \> **Configuración del panel de control Tareas** \> **programadas**.
6. Haga clic con el botón derecho en el área en blanco en **Tareas programadas** y seleccione **Nueva** \> **tarea inmediata (al menos Windows 7).**
7. Escriba un *nombre* y una *descripción* de la tarea.
8. Elija la cuenta correspondiente para ejecutar la tarea inmediata. Por ejemplo, *NT Authority*.
9. Seleccione **Ejecutar con los privilegios más altos**.
10. Configure la directiva para Windows 10.
11. En la pestaña **Acciones** , elija **Iniciar un programa**.
12. Escriba la ruta de acceso al programa o script creado en el **paso 1**.
13. Seleccione **Aplicar**.

**Paso 3: Agregar la extensión de Chrome a la lista Forzar instalación**

1. En el **Editor de administración de directiva de grupo**, vaya a la unidad organizativa (OU).
2. Expanda la siguiente ruta de acceso **Directivas** \> de configuración \> de **equipo o usuario** **Plantillas** \> **administrativas clásicas Extensiones** \> **de** **Google Chrome** \> de **Google**\>. Esta ruta de acceso puede variar en función de la configuración de la organización.
3. Seleccione **Configurar la lista de extensiones forzadas instaladas**.
4. Haga clic con el botón derecho y seleccione **Editar**.
5. Seleccione el botón de radio **Habilitado** .
6. Seleccionar **Mostrar**.
7. En **Valor**, agregue la entrada siguiente: *echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx*
8. Seleccione **Aceptar** y seleccione **Aplicar**.

## <a name="test-and-verify-insider-risk-management-browser-signal-detections"></a>Prueba y comprobación de detecciones de señales del explorador de administración de riesgos internos

1. Cree una directiva de administración de riesgos internos con los indicadores de dispositivo habilitados.
2. Para probar la detección de señales de los archivos copiados en el almacenamiento en la nube personal, complete los pasos siguientes desde un dispositivo Windows compatible:

    - Abra un sitio web de uso compartido de archivos (Microsoft OneDrive, Google Drive, etc.) con el tipo de explorador que ha configurado para la detección de señales.
    - Con el explorador, cargue un archivo no ejecutable en el sitio web.
3. Para probar la detección de señales de archivos impresos en dispositivos locales o de red, archivos transferidos o copiados a un recurso compartido de red y archivos copiados en dispositivos USB, complete los pasos siguientes desde un dispositivo Windows compatible:

    - Abra un archivo no ejecutable directamente en el explorador. El archivo debe abrirse directamente a través de Explorador de archivos o abrirse en una nueva pestaña del explorador para su visualización en lugar de una página web.
    - Imprima el archivo.
    - Guarde el archivo en un dispositivo USB.
    - Guarde el archivo en una unidad de red.
  
4. Una vez creada la primera directiva de administración de riesgos internos, empezará a recibir alertas de indicadores de actividad después de aproximadamente 24 horas. Compruebe en el [panel Alertas](/microsoft-365/compliance/insider-risk-management-activities#alert-dashboard) las alertas de administración de riesgos internos para las actividades probadas.
