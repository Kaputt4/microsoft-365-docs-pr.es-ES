---
title: Configurar IRM para usar un servidor de AD RMS local
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/13/2017
audience: End User
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 3ecde857-4b7c-451d-b4aa-9eeffc8a8c61
ms.collection:
- purview-compliance
- tier3
description: Aprenda a configurar Information Rights Management (IRM) en Exchange Online para usar un servidor de Active Directory Rights Management Service (AD RMS).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 87f776964e6aacb9407350ef905ee7680035dbce
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68621414"
---
# <a name="configure-irm-to-use-an-on-premises-ad-rms-server"></a>Configurar IRM para usar un servidor de AD RMS local

Para su uso con implementaciones locales, Information Rights Management (IRM) en Exchange Online usa Active Directory Rights Management Services (AD RMS), una tecnología de protección de la información en Windows Server 2008 y versiones posteriores. La protección de IRM se implanta en el correo electrónico mediante la aplicación de una plantilla de directiva de permisos de AD RMS a un mensaje de correo electrónico. Los derechos se adjuntan al propio mensaje para que la protección se produzca en línea y sin conexión, dentro y fuera del firewall de la organización.

En este tema se muestra cómo configurar IRM para usar un servidor de AD RMS. Para obtener información sobre el uso de Cifrado de mensajes de Microsoft Purview con Azure Active Directory y Azure Rights Management, consulte preguntas [más frecuentes sobre el cifrado de mensajes](./ome-faq.yml).

Para obtener más información sobre IRM en Exchange Online, consulte [Information Rights Management en Exchange Online](information-rights-management-in-exchange-online.md).

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

- Tiempo estimado para finalizar esta tarea: 30 minutos

- You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Information Rights Management" entry in the [Messaging policy and compliance permissions](/Exchange/permissions/feature-permissions/policy-and-compliance-permissions) topic.

- The AD RMS server must be running Windows Server 2008 or later. For details about how to deploy AD RMS, see [Installing an AD RMS Cluster](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc726041(v=ws.11)).

- Para obtener más información sobre cómo instalar y configurar Windows PowerShell y conectarse al servicio, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Para obtener información sobre los métodos abreviados de teclado que se pueden aplicar a los procedimientos de este tema, vea [Métodos abreviados de teclado para el Centro de administración de Exchange en Exchange Online](/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> ¿Problemas? Solicite ayuda en los foros de Exchange. Visite los foros en [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), o [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).

## <a name="how-do-you-do-this"></a>¿Cómo debe hacer esto?
<a name="sectionSection1"> </a>

### <a name="step-1-use-the-ad-rms-console-to-export-a-trusted-publishing-domain-tpd-from-an-ad-rms-server"></a>Paso 1: Use la consola AD RMS para exportar un dominio de publicación de confianza (TPD) desde un servidor AD RMS

The first step is to export a trusted publishing domain (TPD) from the on-premises AD RMS server to an XML file. The TPD contains the following settings needed to use RMS features:

- El certificado emisor de licencias de servidor (SLC) utilizado para firmar y cifrar certificados y licencias

- Las direcciones URL utilizadas para emitir licencias y publicar

- Las plantillas de directiva de permisos de AD RMS que se crearon con el certificado emisor de licencias de servidor específico para ese dominio de publicación de confianza

Al importar el dominio de publicación de confianza, se almacena y se protege en Exchange Online.

1. Abra la consola de Active Directory Rights Management Services y, a continuación, expanda el clúster AD RMS.

2. En el árbol de consola, expanda **Directivas de confianza** y, a continuación, haga clic en **Dominios de publicación de confianza**.

3. En el panel de resultados, seleccione el certificado para el dominio que desea exportar.

4. En el panel **Acciones**, haga clic en **Exportar dominio de publicación de confianza**.

5. En el cuadro **Archivo de dominio de publicación**, haga clic en **Guardar como** para guardar el archivo en una ubicación concreta del equipo local. Escriba un nombre de archivo, asegúrese de especificar la `.xml` extensión de nombre de archivo y, a continuación, haga clic en **Guardar**.

6. In the **Password** and **Confirm Password** boxes, type a strong password that will be used to encrypt the trusted publishing domain file. You will have to specify this password when you import the TPD to your cloud-based email organization.

### <a name="step-2-use-the-exchange-management-shell-to-import-the-tpd-to-exchange-online"></a>Paso 2: use el Shell de administración de Exchange para importar el dominio de publicación de confianza a Exchange Online

After the TPD is exported to an XML file, you have to import it to Exchange Online. When a TPD is imported, your organization's AD RMS templates are also imported. When the first TPD is imported, it becomes the default TPD for your cloud-based organization. If you import another TPD, you can use the **Default** switch to make it the default TPD that is available to users.

Para importar el TPD, ejecute el siguiente comando en Exchange Online PowerShell:

```powershell
Import-RMSTrustedPublishingDomain -FileData ([System.IO.File]::ReadAllBytes('<path to exported TPD file>')) -Name "<name of TPD>" -ExtranetLicensingUrl <URL> -IntranetLicensingUrl <URL>
```

Puede obtener los valores de los parámetros _ExtranetLicensingUrl_ e _IntranetLicensingUrl_ en la consola de Active Directory Rights Management Services. Seleccione el clúster AD RMS en el árbol de consola. Las direcciones URL de emisión de licencias aparecen en el panel de resultados. Los clientes de correo electrónico utilizan estas direcciones URL cuando el contenido tiene que ser descifrado y cuando Exchange Online necesita determinar qué dominio de publicación de confianza utilizar.

When you run this command, you'll be prompted for a password. Enter the password that you specified when you exported the TPD from your AD RMS server.

For example, the following command imports the TPD named Exported TPD using the XML file that you exported from your AD RMS server and saved to the desktop of the Administrator account. The Name parameter is used to specify a name to the TPD.

```powershell
Import-RMSTrustedPublishingDomain -FileData ([System.IO.File]::ReadAllBytes('C:\Users\Administrator\Desktop\ExportTPD.xml')) -Name "Exported TPD" -ExtranetLicensingUrl https://corp.contoso.com/_wmcs/licensing -IntranetLicensingUrl https://rmsserver/_wmcs/licensing
```

Para información detallada sobre la sintaxis y los parámetros, vea [Import-RMSTrustedPublishingDomain](/powershell/module/exchange/import-rmstrustedpublishingdomain).

#### <a name="how-do-you-know-that-you-successfully-imported-the-tpd"></a>¿Cómo sabe que importó correctamente el TPD?

To verify that you have successfully imported the TPD, run the **Get-RMSTrustedPublishingDomain** cmdlet to retrieve TPDs in your Exchange Online organization. For details, see the examples in [Get-RMSTrustedPublishingDomain](/powershell/module/exchange/get-rmstrustedpublishingdomain).

### <a name="step-3-use-the-exchange-management-shell-to-distribute-an-ad-rms-rights-policy-template"></a>Paso 3: use el Shell de administración de Exchange para distribuir una plantilla de directiva de permisos AD RMS

Después de importar el dominio de publicación de confianza, debe asegurarse de que la plantilla de directiva de permisos AD RMS esté distribuida. Una plantilla distribuida es visible para Outlook en la Web usuarios (anteriormente conocidos como Outlook Web App), que pueden aplicar las plantillas a un mensaje de correo electrónico.

Para obtener una lista de todas las plantillas que incluye el TPD predeterminado, ejecute el comando siguiente:

```powershell
Get-RMSTemplate -Type All | fl
```

Si el valor del parámetro _Type_ es `Archived`, la plantilla no es visible para los usuarios. Solo las plantillas distribuidas del TPD predeterminado están disponibles en Outlook en la Web.

Para distribuir una plantilla, ejecute el comando siguiente:

```powershell
Set-RMSTemplate -Identity "<name of the template>" -Type Distributed
```

Por ejemplo, el siguiente comando importa la plantilla Company Confidential.

```powershell
Set-RMSTemplate -Identity "Company Confidential" -Type Distributed
```

Para obtener más información acerca de la sintaxis y los parámetros, consulte [Get-RMSTemplate](/powershell/module/exchange/get-rmstemplate) y [Set-RMSTemplate](/powershell/module/exchange/set-rmstemplate).

#### <a name="the-do-not-forward-template"></a>Plantilla No reenviar

When you import the default TPD from your on-premises organization into Exchange Online, one AD RMS rights policy template named **Do Not Forward** is imported. By default, this template is distributed when you import the default TPD. You can't use the **Set-RMSTemplate** cmdlet to modify the **Do Not Forward** template.

When the **Do Not Forward** template is applied to a message, only the recipients addressed in the message can read the message. Additionally, recipients can't do the following:

- Reenviar el mensaje a otra persona.
- Copiar el contenido del mensaje.
- Imprimir el mensaje.

> [!IMPORTANT]
> La plantilla **No reenviar** no puede evitar que la información de un mensaje se copie con programas de captura de pantalla de otros fabricantes, con cámaras o que los usuarios transcriban la información manualmente.

You can create additional AD RMS rights policy templates on the AD RMS server in your on-premises organization to meet your IRM protection requirements. If you create additional AD RMS rights policy templates, you have to export the TPD from the on-premises AD RMS server again and refresh the TPD in the cloud-based email organization.

#### <a name="how-do-you-know-that-you-successfully-distributed-the-ad-rms-rights-policy-template"></a>¿Cómo sabe que ha distribuido correctamente la plantilla de directiva de derechos de AD RMS?

To verify that you have successfully distributed and AD RMS rights policy template, run the **Get-RMSTemplate** cmdlet to check the template's properties. For details, see the examples in [Get-RMSTemplate](/powershell/module/exchange/get-rmstemplate).

### <a name="step-4-use-the-exchange-management-shell-to-enable-irm"></a>Paso 4: use el Shell de administración de Exchange para habilitar IRM

Después de importar el dominio de publicación de confianza y distribuir una plantilla de directiva de permisos AD RMS, ejecute el siguiente comando para habilitar IRM para la organización de correo electrónico basada en nube.

```powershell
Set-IRMConfiguration -InternalLicensingEnabled $true
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration).

#### <a name="how-do-you-know-that-you-successfully-enabled-irm"></a>¿Cómo sabe que ha habilitado IRM correctamente?

Para comprobar que IRM se haya habilitado correctamente, ejecute el cmdlet [Get-IRMConfiguration](/powershell/module/exchange/get-irmconfiguration) para comprobar la configuración de IRM en la organización de Exchange Online.

## <a name="how-do-you-know-this-task-worked"></a>¿Cómo sabe si esta tarea funcionó?
<a name="sectionSection2"> </a>

Para comprobar si ha importado el TPD y ha habilitado IRM correctamente, haga lo siguiente:

- Use el cmdlet **Test-IRMConfiguration** para probar si IRM funciona. Para obtener más información, vea "Ejemplo 1" en [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration).

- Redacte un nuevo mensaje en Outlook en la Web y protéjalo con IRM; para ello, seleccione la opción **Establecer permisos** en el menú extendido (![icono Más opciones).](../media/ITPro-EAC-MoreOptionsIcon.gif)
