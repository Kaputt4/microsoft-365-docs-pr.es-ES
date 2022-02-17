---
title: Información y configuración de la detección de señales del explorador de administración de riesgos insider
description: Obtenga información sobre la detección de señales del explorador de administración de riesgos de insider en Microsoft 365
keywords: Microsoft 365, administración de riesgos internos, administración de riesgos, cumplimiento
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
ms.openlocfilehash: c3cb9e432f3ea94f88c63cfad928ba577471b420
ms.sourcegitcommit: 007822d16e332522546e948f5c216327254a4d49
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2022
ms.locfileid: "62879089"
---
# <a name="learn-about-and-configure-insider-risk-management-browser-signal-detection"></a>Información y configuración de la detección de señales del explorador de administración de riesgos insider

Los exploradores web suelen ser usados por los usuarios para tener acceso a archivos confidenciales y no confidenciales dentro de una organización. La administración de riesgos de Insider permite a la organización detectar y actuar en las señales de exfiltración del explorador para todos los archivos no ejecutables que se ven en [los exploradores](https://www.microsoft.com/edge) Microsoft Edge [y Google Chrome](https://www.google.com/chrome). Con estas señales, los analistas e investigadores pueden actuar rápidamente cuando los usuarios de directivas en el ámbito realizan alguna de las siguientes actividades al usar estos exploradores:

- Archivos copiados en el almacenamiento en la nube personal
- Archivos impresos en dispositivos locales o de red
- Archivos transferidos o copiados en un recurso compartido de red
- Archivos copiados en dispositivos USB

Las señales de estos eventos se detectan en Microsoft Edge las funciones del explorador integradas y mediante el complemento *de extensión de* cumplimiento de Microsoft. En Google Chrome, los clientes usan la *Extensión de cumplimiento de Microsoft para* la detección de señales.

En la tabla siguiente se resumen las actividades detectadas y la compatibilidad con extensiones para cada explorador:

| **Actividades detectadas**                        | **Microsoft Edge** | **Google Chrome** |
| ---------------------------------------------- | ------------------ | ----------------- |
| Archivos copiados en el almacenamiento en la nube personal         | Nativa             | Extensión         |
| Archivos impresos en dispositivos locales o de red      | Nativa             | Extensión         |
| Archivos transferidos o copiados en un recurso compartido de red | Extensión          | Extensión         |
| Archivos copiados en dispositivos USB                    | Extensión          | Extensión         |

## <a name="common-requirements"></a>Requisitos comunes

Antes de instalar Microsoft Edge complemento o extensión de Google Chrome, los clientes deben asegurarse de que los dispositivos para usuarios de directivas de ámbito cumplan los siguientes requisitos:

- Se Windows 10 compilación x64 más reciente, Windows 10 x64 compilación 1809 para la compatibilidad con la detección de señales. Actualmente, la detección de señales del explorador no se admite en dispositivos que no Windows dispositivos.
- Suscripción [Microsoft 365 con soporte](/microsoft-365/compliance/insider-risk-management-configure#subscriptions-and-licensing) técnico de administración de riesgos de insider.
- Los dispositivos deben [incorporarse](/microsoft-365/compliance/insider-risk-management-settings#enable-device-indicators-and-onboard-devices) al portal Microsoft 365 cumplimiento.

Para obtener requisitos de configuración de explorador específicos, consulta las secciones Microsoft Edge y Google Chrome más adelante en este artículo.

## <a name="configure-browser-signal-detection-for-microsoft-edge"></a>Configurar la detección de señales del explorador Microsoft Edge

### <a name="microsoft-edge-browser-requirements"></a>Microsoft Edge de explorador

- Cumplir los requisitos comunes
- Microsoft Edge x64, versión 91.0.864.41 o posterior
- *Complemento de extensión* de cumplimiento de Microsoft versión 1.0.0.44 o posterior
- Edge.exe no está configurado como un explorador no permitido

### <a name="option-1-basic-setup-recommended-for-testing-with-edge"></a>Opción 1: Configuración básica (recomendada para pruebas con Edge)

Usa esta opción para configurar el autohosgo de una sola máquina para cada dispositivo de la organización al probar la detección de señal del explorador.

Para la opción de configuración básica, siga estos pasos:

1. Vaya a [Extensión de cumplimiento de Microsoft](https://microsoftedge.microsoft.com/addons/detail/microsoft-compliance-exte/lcmcgbabdcbngcbcfabdncmoppkajglo).
2. Instale la extensión.

### <a name="option-2-intune-setup-for-edge"></a>Opción 2: Configuración de Intune para Edge

Use esta opción para configurar la extensión y los requisitos de su organización mediante Intune.

Para la opción de configuración de Intune, siga estos pasos:

1. Inicie sesión en el [Centro Microsoft Endpoint Manager administración con](https://endpoint.microsoft.com) permisos de administrador.
2. Vaya a **Perfiles de configuración**.
3. Seleccione **Crear perfil**.
4. Elija **Windows 10** como plataforma.
5. Elija **Plantillas administrativas como** *tipo de perfil y* seleccione **Crear.**
6. Seleccione la pestaña **Configuración**.
7. Seleccione **Edge Version 77 y versiones posteriores.**
8. Busque Extensiones **que** le ofrece información general sobre todas las opciones relacionadas con la extensión.
9. Seleccione la configuración **Controlar qué extensiones se instalan de forma silenciosa.**
10. Seleccione **Habilitado.**
11. Agregue el identificador de extensión cuando se le pida: *lcmcgbabdcbngcbcfabdncmoppkajglo***.**
12. Seleccione **Aceptar.**

### <a name="option-3-group-policy-setup-for-edge"></a>Opción 3: Configuración de directiva de grupo para Edge

Use esta opción para configurar la extensión y los requisitos de toda la organización mediante la directiva de grupo.

Para la opción de configuración de directiva de grupo, siga estos pasos:

**Paso 1: Importar el último Microsoft Edge archivo de plantilla administrativa (.admx).**

Los dispositivos deben ser administrables mediante directivas de grupo [y todas Microsoft Edge las](https://www.microsoft.com/edge/business/download) plantillas administrativas deben importarse en el Almacén central de directivas de grupo. Para más información, consulte [Cómo crear y administrar el almacén central de plantillas administrativas de directiva de grupo en Windows](/troubleshoot/windows-client/group-policy/create-and-manage-central-store).

**Paso 2: Agregar el complemento *Extensión de cumplimiento de Microsoft* a la *lista Forzar instalación* .**

Siga estos pasos para agregar la extensión:

1. En el **Editor de administración de directivas de** grupo, vaya a la Unidad organizativa (OU).
2. Expanda la siguiente  ruta de **acceso Directivas de configuración de equipo/** \>  \> Usuario **Plantillas administrativas** \> \> Plantillas administrativas **clásicas Microsoft Edge** \> **extensiones**. Esta ruta de acceso puede variar según la configuración de la organización.
3. Seleccione **Configurar qué extensiones se instalan de forma silenciosa.**
4. Haga clic con el botón secundario y **seleccione Editar**.
5. Compruebe el **botón de** opción Habilitado.
6. Seleccionar **Mostrar**.
7. Para **Value**, agregue la siguiente entrada: *lcmcgbabdcbngcbcfabdncmoppkajglo;https://edge.microsoft.com/extensionwebstorebase/v1/crx*
8. Seleccione **Aceptar** **y aplicar.**

## <a name="configure-browser-signal-detection-for-google-chrome"></a>Configurar la detección de señales del explorador para Google Chrome

La compatibilidad de detección de señales del explorador de administración de riesgos de Insider para Google Chrome está habilitada a través de *la extensión de cumplimiento de Microsoft*. Esta extensión también admite DLP de extremo en Chrome. Para obtener más información acerca de la compatibilidad con DLP de extremo, vea [Introducción a la extensión de cumplimiento de Microsoft (versión preliminar).](/microsoft-365/compliance/dlp-chrome-get-started).

### <a name="google-chrome-browser-requirements"></a>Requisitos del explorador Google Chrome

- Cumplir los requisitos comunes
- Versión más reciente de Google Chrome x64
- *Extensión de cumplimiento de Microsoft* versión 2.0.0.183 o posterior
- Chrome.exe no está configurado como un explorador no permitido

### <a name="option-1-basic-setup-recommended-for-testing-with-chrome"></a>Opción 1: Configuración básica (recomendada para pruebas con Chrome)

Usa esta opción para configurar el autohosgo de una sola máquina para cada dispositivo de la organización al probar la detección de señal del explorador.

Para la opción de configuración básica, siga estos pasos:

**Paso 1: Habilitar las claves del Registro necesarias con PowerShell**

```PowerShell
Get-Item -path "HKLM:\\SOFTWARE\\Microsoft\\Windows Defender\\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
```

>[!Important]
>Estas claves del Registro son necesarias para garantizar la funcionalidad correcta de la extensión. Debe habilitar estas claves del Registro antes de probar cualquier señal.*

**Paso 2: Instalar la *extensión de cumplimiento de Microsoft***

1. Vaya a [Extensión de cumplimiento de Microsoft](https://chrome.google.com/webstore/detail/microsoft-compliance-exte/echcggldkblhodogklpincgchnpgcdco).
2. Instale la extensión.

### <a name="option-2-intune-setup-for-chrome"></a>Opción 2: Configuración de Intune para Chrome

Use esta opción para configurar la extensión y los requisitos de su organización mediante Intune.

Para la opción de configuración de Intune, siga estos pasos:

**Paso 1: Habilitar la clave del Registro necesaria con Intune**

1. Ejecute el siguiente script de PowerShell:

```PowerShell
Get-Item -path "HKLM:\\SOFTWARE\\Microsoft\\Windows Defender\\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
```

2. Inicie sesión en el [Centro Microsoft Endpoint Manager administración](https://endpoint.microsoft.com).
3. Vaya a **Scripts de dispositivos** \> y **seleccione Agregar.** 
4. Cuando se le solicite, vaya a la ubicación del script creado.
5. Seleccione la siguiente configuración:

    - Ejecute este script con las credenciales de inicio de sesión: *Sí*
    - Exigir la comprobación de firma de script: *No*
    - Ejecutar script en host de PowerShell de 64 bits: *Sí*

6. Selecciona los grupos de dispositivos adecuados y aplica la directiva.

**Paso 2: Configurar La instalación de fuerza de Intune**

Antes de agregar la extensión de Microsoft DLP Chrome a la lista de extensiones instaladas de fuerza, debe instalar el archivo de plantilla administrativa de Chrome (.admx) para la administración de Intune. Para obtener instrucciones paso a paso, consulta [Manage Chrome Browser with Microsoft Intune](https://support.google.com/chrome/a/answer/9102677?hl=en#zippy=%2Cstep-ingest-the-chrome-admx-file-into-intune). Después de instalar el archivo de plantilla administrativa, siga estos pasos:

1. Inicie sesión en el [Centro Microsoft Endpoint Manager administración](https://endpoint.microsoft.com).
2. Vaya a **Perfiles de configuración**.
3. Seleccione **Crear perfil**.
4. Elija **Windows 10** como *plataforma*.
5. Elija **Personalizado** como tipo *de* perfil.
6. Seleccione la pestaña **Configuración**.
7. Seleccione **Agregar.**
8. Escriba la siguiente información de directiva:

    - OMA-URI: *./Device/Vendor/MSFT/Policy/Config/Chrome~Policy~googlechrome~Extensions/ExtensionInstallForcelist*
    - Tipo de datos: *String*
    - Valor: *\<enabled/\>\<data id=”ExtensionInstallForcelistDesc” value=”1&\#xF000; echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx″/\>*

9. Seleccione **Crear**.

### <a name="option-3-group-policy-setup-for-chrome"></a>Opción 3: Configuración de directiva de grupo para Chrome

Use esta opción para configurar la extensión y los requisitos de toda la organización mediante la directiva de grupo.

Para la opción de configuración de directiva de grupo, siga estos pasos:

**Paso 1: Importar el archivo de plantilla administrativa de Chrome**

Los dispositivos deben ser manejables mediante la directiva de grupo y todas las plantillas administrativas de [Chrome](https://chromeenterprise.google/browser/download/) deben importarse al Almacén central de directivas de grupo. Para más información, consulte [Cómo crear y administrar el almacén central de plantillas administrativas de directiva de grupo en Windows](/troubleshoot/windows-client/group-policy/create-and-manage-central-store).

**Paso 2: Habilitar la clave del Registro necesaria con PowerShell**

1. Cree un script de PowerShell con el contenido siguiente:

    ```PowerShell
    Get-Item -path "HKLM:\\SOFTWARE\\Microsoft\\Windows Defender\\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
    ```

2. Abra la **Consola de administración de la directiva de grupo** y vaya a la unidad organizativa (OU).
3. Haga clic con el botón secundario y **seleccione Crear un GPO en este dominio y vincule aquí**. Cuando se le pida, asigne un nombre descriptivo a este objeto de directiva de grupo (GPO). Por ejemplo, *Script de PowerShell inmediato de DLP Chrome*.
4. Después de crear el GPO, haga clic con el botón secundario y seleccione **Editar**. Esta selección le lleva al objeto de directiva de grupo.
5. Vaya a **Configuración del equipo Preferencias** \>  \> **Configuración del panel de control** \> **Tareas programadas**.
6. Haga clic con el botón secundario en el área en blanco en **Tareas programadas** y seleccione **Nueva** \> tarea inmediata (al menos **Windows 7).**
7. Escriba un nombre *y una* *descripción de tarea*.
8. Elija la cuenta correspondiente para ejecutar la tarea inmediata. Por ejemplo, *NT Authority*.
9. Seleccione **Ejecutar con los privilegios más altos**.
10. Configure la directiva para Windows 10.
11. En la **pestaña Acciones** , elija **Iniciar un programa**.
12. Escriba la ruta de acceso al programa o script creado en **el paso 1**.
13. Seleccione **Aplicar**.

**Paso 3: Agregar la extensión de Chrome a la lista Forzar instalación**

1. En el **Editor de administración de directivas de** grupo, vaya a la unidad organizativa (OU).
2. Expanda la siguiente ruta de acceso **Directivas de configuración del equipo/** \>  \> Usuario **Plantillas administrativas** \> **clásicas Plantillas administrativas** \> **de Google** \> **Chrome** \> **Extensiones**. Esta ruta de acceso puede variar según la configuración de la organización.
3. Seleccione **Configurar la lista de extensiones instaladas de fuerza**.
4. Haga clic con el botón secundario y **seleccione Editar**.
5. Seleccione el **botón de** radio Habilitado.
6. Seleccionar **Mostrar**.
7. Para **Value**, agregue la siguiente entrada: *echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx*
8. Seleccione **Aceptar** **y aplicar.**

## <a name="test-and-verify-insider-risk-management-browser-signal-detections"></a>Probar y comprobar detecciones de señales del explorador de administración de riesgos insider

1. Crea una directiva de administración de riesgos de insider con indicadores de dispositivo habilitados.
2. Para probar la detección de señales de archivos copiados en el almacenamiento en la nube personal, siga estos pasos desde un dispositivo Windows compatible:

    - Abra un sitio web de uso compartido de archivos (Microsoft OneDrive, Google Drive, etc.) con el tipo de explorador que haya configurado para la detección de señales.
    - Con el explorador, cargue un archivo no ejecutable en el sitio web.
3. Para probar la detección de señales para archivos impresos en dispositivos locales o de red, archivos transferidos o copiados a un recurso compartido de red y archivos copiados en dispositivos USB, complete los siguientes pasos desde un dispositivo Windows compatible:

    - Abra un archivo no ejecutable directamente en el explorador. El archivo debe abrirse directamente a través del Explorador de archivos o abrirse en una nueva pestaña del explorador para su visualización en lugar de una página web.
    - Imprimir el archivo.
    - Guarde el archivo en un dispositivo USB.
    - Guarde el archivo en una unidad de red.
  
4. Después de crear la primera directiva de administración de riesgos de insider, empezarás a recibir alertas de indicadores de actividad después de unas 24 horas. Compruebe en el [panel de alertas](/microsoft-365/compliance/insider-risk-management-activities#alert-dashboard) las alertas de administración de riesgos de insider para las actividades probadas.
