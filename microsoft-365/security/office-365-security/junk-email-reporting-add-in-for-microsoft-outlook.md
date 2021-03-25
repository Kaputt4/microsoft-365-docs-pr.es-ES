---
title: Instalar y usar el complemento De informes de correo no deseado para Microsoft Outlook
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 4650fec1-4ee3-4659-abbc-bf091718cb26
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo instalar y usar el complemento De informes de correo no deseado de Microsoft para notificar mensajes de correo no deseado, correo no deseado y suplantación de identidad a Microsoft.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e120ceec355ffc135e00e13a89a0f29085946a3b
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205469"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook"></a>Instalar y usar el complemento De informes de correo no deseado para Microsoft Outlook

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> Si actualmente no usa el complemento De informes de correo electrónico no deseado, se recomienda el complemento Report [Message](enable-the-report-message-add-in.md) o el complemento [Report Phishing.](enable-the-report-phish-add-in.md) Para obtener más información, consulte [Notificar mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).

El complemento de informes de correo no deseado para Microsoft Outlook permite a los usuarios enviar falsos positivos (buen correo electrónico marcado como correo no deseado), falsos negativos (correo electrónico no deseado permitido) y mensajes de suplantación de identidad a Microsoft. Si su organización no usa Exchange Online Protection (por ejemplo, exchange local o servicios de correo electrónico distintos de Exchange Online), el envío del informe de correo no deseado no afectará al filtrado de correo no deseado.

En este tema se explica cómo instalar y usar el complemento De informes de correo no deseado.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Para instalar el complemento De informes de correo no deseado, vea la sección [Instalar](#install-the-junk-email-reporting-add-in) el complemento De informes de correo no deseado más adelante en este artículo.

- El complemento De informes de correo no deseado funciona con las siguientes versiones de Outlook:

  - Outlook 2013 o posterior
  - Outlook incluido con Aplicaciones de Microsoft 365 para empresas

- Para obtener más información acerca de cómo notificar mensajes a Microsoft, vea [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a>Usar el complemento De informes de correo no deseado para notificar mensajes de correo no deseado y suplantación de identidad

1. Para los mensajes de la Bandeja de entrada o cualquier otra carpeta de correo electrónico excepto correo no deseado, use cualquiera de los siguientes métodos para notificar mensajes de correo no deseado y suplantación de identidad:

   - Seleccione el mensaje o abra el mensaje. En la pestaña **Inicio** **o** Mensaje de la  cinta de opciones, haga clic en Correo no deseado y, a continuación, seleccione Informar como correo no deseado o Informar **como suplantación de identidad**.

     ![Notificar correo electrónico no deseado o suplantación de identidad desde la cinta de opciones](../../media/junk-email-reporting-ribbon.png)

   - Haga clic con el botón secundario en  el mensaje, seleccione **Correo** no deseado y, a continuación, seleccione Informar como correo no deseado **o Informar como suplantación de identidad**.

     ![Notificar correo electrónico no deseado o suplantación de identidad desde el botón secundario](../../media/junk-email-reporting-right-click.png)

   - Seleccione varios mensajes, haga clic con el botón secundario y, a continuación, seleccione **Informar** como correo no deseado **o Informar como suplantación de identidad**.

     ![Informar de varios mensajes de correo electrónico no deseado o de suplantación de identidad desde el botón secundario](../../media/junk-email-reporting-right-click-multiple.png)

2. En el cuadro de diálogo que aparece, lea la información y haga clic en **Informe**. Si cambia de opinión, haga clic **en No informar.**

   ![Cuadro de diálogo Informar como correo no deseado](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![Cuadro de diálogo Informar como suplantación de identidad](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. Los mensajes seleccionados se enviarán a Microsoft para su análisis y:

   - Se ha movido a la carpeta correo no deseado si se ha notificado como correo no deseado.
   - Se elimina si se ha notificado como suplantación de identidad.

   Para confirmar que los mensajes se han enviado, abra la carpeta **Mensajes enviados** para ver los mensajes enviados.

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a>Usar el complemento De informes de correo no deseado para informar de mensajes no deseados y de suplantación de identidad desde la carpeta Correo no deseado

1. En la carpeta Correo no deseado, use cualquiera de los siguientes métodos para notificar falsos positivos de correo no deseado o mensajes de suplantación de identidad:

   - Seleccione el mensaje o abra el mensaje. En la pestaña **Inicio** **o Mensaje** de la cinta  de opciones, haga clic en No deseado **y,** a continuación, seleccione Informar como no deseado o Informar **como suplantación de identidad**.

     ![No informar de correo electrónico no deseado o de suplantación de identidad desde la cinta de opciones en la carpeta Correo no deseado](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - Haga clic con el botón secundario en el mensaje, haga **clic** en Correo no deseado y, a continuación, seleccione Informar como no deseado **o** **Informar como suplantación de identidad**.

     ![No informar de correo electrónico no deseado o de suplantación de identidad desde el botón secundario en la carpeta Correo no deseado](../../media/junk-email-reporting-junk-folder-right-click.png)

   - Seleccione varios mensajes, haga clic con el botón secundario y, a continuación, **seleccione Informar como** no deseado o Informar como **suplantación de identidad**.

     ![Informar de varios mensajes de correo electrónico no deseado o de suplantación de identidad desde el botón secundario en la carpeta Correo no deseado](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. En el cuadro de diálogo que aparece, lea la información y haga clic en **Informe**. Si cambia de opinión, haga clic **en No informar.**

   ![Informe como cuadro de diálogo no deseado](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![Cuadro de diálogo Informar como suplantación de identidad](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. Los mensajes seleccionados se enviarán a Microsoft para su análisis y:

   - Se ha movido a la carpeta correo no deseado si se ha notificado como correo no deseado.
   - Se elimina si se ha notificado como suplantación de identidad.

   Para confirmar que los mensajes se han enviado, abra la carpeta **Mensajes enviados** para ver los mensajes enviados.

## <a name="install-the-junk-email-reporting-add-in"></a>Instalar el complemento De informes de correo no deseado

- Debe tener privilegios de administrador en el equipo donde va a instalar el complemento.

- Vaya a y descargue el archivo .msi adecuado para su versión de Office en una ubicación fácil <https://www.microsoft.com/download/details.aspx?id=18275> de encontrar:

  - **32 bits:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`
  - **64 bits:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`

- Para Outlook 2013 o posterior, el único requisito previo es microsoft .NET Framework 2.0. En Windows 10, no instalas el .NET Framework 2.0 desde una descarga.

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a>Instalar el complemento de informes de correo no deseado con el Asistente para la instalación

1. En el equipo, cierre Outlook.

2. En Windows 10, comprueba que el .NET Framework 2.0 está habilitado. Para obtener instrucciones, vea [Enable the .NET Framework 3.5 in Control Panel](/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).

3. Busque el archivo .msi que descargó y haga doble clic en él.

4. En la página de **bienvenida a la instalación del complemento de notificación de correo no deseado de Microsoft**, haga clic en **Siguiente**.

5. Revise el contrato de licencia, haga clic en **Acepto** los términos del Contrato de licencia si acepta los términos y, a continuación, haga clic en **Siguiente**.

6. Cuando el asistente se haya completado, haga clic en **Finalizar**.

Inicie Outlook.

Busque el botón **Correo no deseado** en la cinta de Outlook. Ahora podrá notificar mensajes de correo no deseado a Microsoft seleccionando los mensajes de correo no deseado en la Bandeja de entrada y haciendo clic en el botón de **Informar de correo no deseado**.

Elija la flecha abajo que aparece junto a **Correo no deseado** para ver más opciones, como **Notificar como suplantación de identidad (phishing)** si desea informar a Microsoft sobre correos de suplantación de identidad (phishing). En la carpeta de correo no deseado, también puede seleccionar **Notificar como correo deseado** si un correo electrónico se ha identificado incorrectamente como correo no deseado.

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a>Instalar el complemento de notificación de correo no deseado en modo silencioso

1. En el equipo, cierre Outlook.

2. En Windows 10, instala el .NET Framework 2.0 ejecutando el siguiente comando:

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. Para instalar el complemento sin ninguna interacción del usuario, abra un símbolo del sistema y use la sintaxis siguiente:

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - `MaxMessageSelection` especifica el número máximo de mensajes que puede seleccionar para un único envío. Los valores válidos van del 1 al 50. El valor predeterminado es 15.

   - `BccEmailAddress` especifica destinatarios CCO adicionales que recibirán una copia de todos los envíos de usuario. El valor predeterminado está en blanco (no hay destinatarios CCO adicionales).

   En este ejemplo se instala la versión de 64 bits del complemento desde la ruta de acceso especificada con la configuración predeterminada.

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   En este ejemplo se instala la versión de 32 bits del complemento desde la ruta de acceso especificada con la siguiente configuración adicional:

   - Se pueden seleccionar hasta 20 mensajes en un solo envío.
   - junkreports@contoso.com y hollyd@treyresearch.net copias CCO de todos los envíos.

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a>¿Cómo saber si el proceso se ha completado correctamente?

Para comprobar que ha instalado correctamente el complemento de informes de correo no deseado, siga estos pasos en Outlook:

- Seleccione el mensaje o abra el mensaje. En la **pestaña Inicio** **o Mensaje** de la cinta de opciones, haga **clic** en Correo no deseado y compruebe que están disponibles las siguientes opciones:

  - **Informar como correo no deseado**
  - **Informar como suplantación de identidad**
  - **Opciones de informes no deseados**
  - **Report Junk Online Help**

  ![Notificar correo electrónico no deseado o suplantación de identidad desde la cinta de opciones](../../media/junk-email-reporting-ribbon.png)

- Haga clic con el botón secundario en el mensaje, seleccione **Correo** no deseado y compruebe que están disponibles las siguientes opciones:

  - **Informar como correo no deseado**
  - **Informar como suplantación de identidad**
  - **Opciones de informes no deseados**
  - **Report Junk Online Help**

  ![Notificar correo electrónico no deseado o suplantación de identidad desde el botón secundario](../../media/junk-email-reporting-right-click.png)

- Seleccione varios mensajes, haga clic con el botón secundario y compruebe que están disponibles las siguientes opciones:

  - **Informar como correo no deseado**
  - **Informar como suplantación de identidad**

  ![Informar de varios mensajes de correo electrónico no deseado o de suplantación de identidad desde el botón secundario](../../media/junk-email-reporting-right-click-multiple.png)

- Realice las acciones anteriores en la carpeta  **Correo no** deseado y compruebe que las opciones de informes de correo no deseado anteriores sean ahora **No deseado**.

  ![No informar de correo electrónico no deseado o de suplantación de identidad desde la cinta de opciones en la carpeta Correo no deseado](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![No informar de correo electrónico no deseado o de suplantación de identidad desde el botón secundario en la carpeta Correo no deseado](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![Informar de varios mensajes de correo electrónico no deseado o de suplantación de identidad desde el botón secundario en la carpeta Correo no deseado](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a>Desinstalar el complemento de notificación de correo no deseado

Después de cerrar Outlook, use cualquiera de los procedimientos siguientes para desinstalar el complemento de informes de correo no deseado:

- **Panel de** control: presione la tecla Windows + R. En el **cuadro de** diálogo Ejecutar que se abre, escriba `control appwiz.cpl` y, a continuación, haga clic en **Aceptar**.

  Busque y seleccione **Complemento de informes** de correo no deseado de Microsoft en la lista y, a continuación, haga clic en **Desinstalar**.

- **Paquete de Windows Installer:** busque o descargue el archivo .msi adecuado y haga doble clic en él.

  - **32 bits:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`

  - **64 bits:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`

  En el cuadro de diálogo que aparece, seleccione Quitar complemento de informes de correo no deseado de **Microsoft para Outlook** y, a continuación, haga clic en **Siguiente**.

- **Modo silencioso:** busque o descargue el archivo .msi adecuado. En una ventana del símbolo del sistema, reemplace por la ubicación del archivo .msi y \<PathToFile\> ejecute uno de los siguientes comandos:

  - **32 bits:**

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - **64 bits:**

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

Al abrir Outlook después de la desinstalación, las opciones de informes de correo no deseado, no correo no deseado y suplantación de identidad deben haber desaparecido.

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a>Solución de problemas del complemento de informes de correo no deseado

En ocasiones, es posible que tenga problemas con Outlook después de agregar el complemento de informes de correo no deseado. En esta sección se describen los problemas que puede encontrar, junto con sugerencias para resolver estos problemas.

### <a name="troubleshooting-for-users"></a>Solución de problemas para usuarios

Tiene uno o varios de los siguientes problemas:

- Al hacer clic en **Informar de correo electrónico no deseado**, no ocurre ninguna acción.
- Outlook deja de responder después de seleccionar un mensaje de correo electrónico.
- El correo no deseado notificado no se puede entregar debido a una respuesta de "no se puede entregar".

Para solucionar este problema, siga estos pasos:

1. Cierre y reinicie Outlook.
2. Cree y envíe un mensaje de prueba y compruebe que el destinatario recibió el mensaje.
3. Si el problema persiste, póngase en contacto con el administrador.

Para otros métodos que puede usar para enviar mensajes a Microsoft, vea [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).

### <a name="troubleshooting-for-admins"></a>Solución de problemas para administradores

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a>Problema: aparece continuamente un mensaje de error que pide a los usuarios que se pondrán en contacto con el administrador del sistema

1. Compruebe o establezca la clave `LoggingLevel` del Registro en el valor "Verbose":

   - **Outlook de 32 bits en Windows de 32 bits:**

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - **Outlook de 32 bits en Windows de 64 bits:**

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - **Outlook de 64 bits:**

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk E-mail Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

2. Reinicie Outlook y pida a los usuarios que informen cuando vean el mensaje de error.

3. Recopile la información de registro de la siguiente ubicación:

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. Póngase en contacto con el soporte técnico de Protección en línea de Exchange y proporcione la información de registro.

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a>Problema: los usuarios seleccionados no reciben un mensaje de confirmación cuando informan de los mensajes y ahora desean que se vuelva a enviar el mensaje.

1. Cree la `ConfirmReportJunk` clave del Registro con el valor "True":

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. Reinicie Outlook.