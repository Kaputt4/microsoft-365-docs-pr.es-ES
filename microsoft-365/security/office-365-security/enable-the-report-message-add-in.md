---
title: Habilitar los complementos Informar sobre el mensaje o Informar sobre suplantación de identidad
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo habilitar el mensaje de informe o los complementos de suplantación de identidad de informes para Outlook y Outlook en la Web, para usuarios individuales o para toda la organización.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: dc4c03a0ed1f0a03d96776c841203c9131c3067c
ms.sourcegitcommit: 9af389e4787383cd97bc807f7799ef6ecf0664d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2022
ms.locfileid: "63468886"
---
# <a name="enable-the-report-message-or-the-report-phishing-add-ins"></a>Habilitar los complementos Informar sobre el mensaje o Informar sobre suplantación de identidad

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> Si es administrador de una organización Microsoft 365 con buzones de correo Exchange Online, le recomendamos que use la página **Envíos** en el portal Microsoft 365 Defender correo. Para obtener más información, consulta [Usar el envío de administrador para enviar correo no deseado, phish, direcciones URL y archivos sospechosos a Microsoft](admin-submission.md).

Los complementos Report Message y Report Phishing para Outlook y Outlook en la Web (anteriormente conocidos como Outlook Web App) facilita la notificación de falsos positivos (correo electrónico bueno marcado como negativo) o falsos negativos (correo electrónico no permitido) a Microsoft y sus filiales para su análisis.

Microsoft usa estos envíos para mejorar la eficacia de las tecnologías de protección de correo electrónico. Por ejemplo, supongamos que los usuarios están informando de muchos mensajes mediante el complemento Detección de suplantación de identidad de informes. Esta información se muestra en el Panel de seguridad y otros informes. El equipo de seguridad de la organización puede usar esta información como una indicación de que es posible que sea necesario actualizar las directivas contra suplantación de identidad.

Puede instalar el mensaje de informe o el complemento Report Phishing. Si desea que los usuarios informen tanto de mensajes de correo no deseado como de suplantación de identidad( phishing), implemente el complemento Report Message en su organización.

El complemento Mensaje de informe proporciona la opción de notificar mensajes de correo no deseado y de suplantación de identidad. Los administradores pueden habilitar el complemento Mensaje de informe para la organización y los usuarios individuales pueden instalarlo por sí mismos.

El complemento Report Phishing proporciona la opción de notificar solo mensajes de suplantación de identidad. Los administradores pueden habilitar el complemento Report Phishing para la organización y los usuarios individuales pueden instalarlo por sí mismos.

Si eres un usuario individual, puedes habilitar ambos complementos por ti mismo.

Si es un administrador global o un administrador de Exchange Online y Exchange está configurado para usar la autenticación de OAuth, puede habilitar el complemento Report Message y el complemento Report Phishing para su organización. Ambos complementos ya están disponibles a través [de la implementación centralizada](../../admin/manage/centralized-deployment-of-add-ins.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Tanto el complemento Report Message como el complemento Report Phishing funcionan con la mayoría Microsoft 365 suscripciones y los siguientes productos:
  - Outlook en la Web
  - Outlook 2013 SP1 o posterior
  - Outlook 2016 para Mac
  - Outlook se incluye con Microsoft 365 aplicaciones para Enterprise
  - Outlook aplicación para iOS y Android

- Ambos complementos no están disponibles para buzones compartidos.

- Ambos complementos no están disponibles para buzones de correo Exchange local. 

- El explorador web existente debe funcionar con los complementos Report Message y Report Phishing. Pero, si observa que el complemento no está disponible o no funciona como se esperaba, pruebe con un explorador diferente.

- Para las instalaciones organizativas, la organización debe configurarse para usar la autenticación de OAuth. Para obtener más información, vea [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).

- Los administradores deben ser miembros del grupo de roles Administradores globales. Para obtener más información, consulte [Permisos en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md).

- Para obtener más información sobre cómo notificar un mensaje mediante la característica Mensaje de informe, vea [Report false positives and false negatives in Outlook](report-false-positives-and-false-negatives.md).

- Las organizaciones que tienen una solución de seguridad o filtrado de direcciones URL (como un proxy o firewall) en su lugar, deben tener puntos de conexión ipagave.azurewebsites.net y outlook.office.com que se puedan alcanzar en el protocolo HTTPS.

### <a name="turn-off-the-built-in-reporting-experience"></a>Desactivar la experiencia de informes integrada

No recomendamos la experiencia de informes integrada en Outlook porque no puede usar la directiva [de envío de usuarios](./user-submission.md). Se recomienda usar el complemento Report Message o el complemento Report Phishing en su lugar.

Deberá tener asignados permisos antes de poder ejecutar este cmdlet. Para obtener los permisos necesarios para ejecutar cualquier cmdlet o parámetro en su organización, consulte [Find the permissions required to run any Exchange cmdlet](/powershell/exchange/find-exchange-cmdlet-permissions).

Ejecute el siguiente comando de PowerShell para deshabilitar la experiencia de informes integrada:

```powershell
Set-OwaMailboxPolicy -Identity OwaMailboxPolicy-Default -ReportJunkEmailEnabled $false
```

## <a name="get-the-report-message-add-in"></a>Obtener el complemento Mensaje de informe

### <a name="get-the-report-message-add-in-for-yourself"></a>Obtener el complemento Mensaje de informe por usted mismo

1. Vaya a Microsoft AppSource en <https://appsource.microsoft.com/marketplace/apps> y busque el complemento Mensaje de informe. Para ir directamente al complemento Mensaje de informe, vaya a <https://appsource.microsoft.com/product/office/wa104381180>.

2. Haga **clic en OBTENER AHORA**.

   ![Mensaje de informe: obtenerlo ahora.](../../media/ReportMessageGETITNOW.png)

3. En el cuadro de diálogo que aparece, revise los términos de uso y la directiva de privacidad y, a continuación, haga clic en **Continuar**.

4. Inicie sesión con su cuenta laboral o educativa (para uso empresarial) o su cuenta Microsoft (para uso personal).

Después de instalar y habilitar el complemento, verá los siguientes iconos:

- En Outlook, el icono tiene este aspecto:

    > [!div class="mx-imgBorder"]
    > ![Icono del complemento Mensaje de informe para Outlook.](../../media/OutlookReportMessageIcon.png)

- En Outlook en la Web, el icono tiene este aspecto:

    > [!div class="mx-imgBorder"]
    > ![Outlook en la Web de complemento Mensaje de informe.](../../media/owa-report-message-icon.png)

### <a name="get-the-report-message-add-in-for-your-organization"></a>Obtener el complemento Mensaje de informe para su organización

> [!NOTE]
> El complemento podría tardar hasta 12 horas en aparecer en la organización.

1. En el [Centro de administración de Microsoft 365](https://admin.microsoft.com/AdminPortal/Home?#/homepage), **ve a Configuración** \> **aplicaciones integradas**. Haz clic **en Obtener aplicaciones**.

    > [!div class="mx-imgBorder"]
    > ![Centro de administración de Microsoft 365 aplicaciones integradas](../../media/microsoft-365-admin-center-integrated-apps.png)

2. En la **Aplicaciones Microsoft 365** que aparece, haga clic en el cuadro Buscar,  escriba **Mensaje** de informe y, a continuación, haga clic en **Buscar** ![en el icono Buscar.](../../media/search-icon.png) En la lista de resultados, busque y seleccione **Mensaje de informe**. 

3. Se abre la página de detalles de la aplicación. Seleccione **Obtener ahora**. 

    > [!div class="mx-imgBorder"]
    > ![Complemento Mensaje de informe](../../media/microsoft-365-admin-center-report-message.png)  

4. Complete la información básica del perfil y, a continuación, haga clic **en Continuar**. 

    > [!div class="mx-imgBorder"]
    > ![Configuración del perfil del complemento De mensaje de informe](../../media/microsoft-365-admin-center-profile-info.png)

5. Se **abrirá el menú desplegable Implementar** nueva aplicación. Configure las siguientes opciones. Haga **clic en** Siguiente para ir a la página siguiente para completar la instalación. 

   - **Agregar usuarios**: seleccione uno de los siguientes valores:
     - **Sólo yo**
     - **Toda la organización**
     - **Usuarios o grupos específicos**

   - **Implementación**:
     - **Aceptar solicitudes de permisos**: lea detenidamente los permisos y capacidades de la aplicación antes de ir a la página siguiente.

        > [!div class="mx-imgBorder"]
        > ![Permisos de aplicación](../../media/microsoft-365-admin-center-deploy-new-app.png)

     - **Finalizar la implementación**: revise y termine de implementar el complemento. 
     - **Implementación completada**: seleccione **Listo** para completar la instalación. 

        > [!div class="mx-imgBorder"]
        > ![Implementación completada](../../media/microsoft-365-admin-center-deployment-complete.png)

## <a name="edit-settings-for-the-report-message-add-in"></a>Editar la configuración del complemento Mensaje de informe

1. En el Centro de administración de Microsoft 365, **ve a Configuración** \> **aplicaciones integradas** \. A continuación, busque **y seleccione Agregar** mensaje de informe.

2. En el control desplegable que aparece, seleccione **Editar usuarios** para editar la configuración del usuario.

    > [!div class="mx-imgBorder"]
    > ![Flyout de mensaje de informe](../../media/microsoft-365-admin-center-report-message-edit.png)

3. Para quitar el complemento, selecciona **Quitar aplicación en** **Acciones** en el mismo control desplegable. 

## <a name="get-the-report-phishing-add-in"></a>Obtener el complemento de suplantación de identidad de informe

### <a name="get-the-report-phishing-add-in-for-yourself"></a>Obtener el complemento de suplantación de identidad de informe por sí mismo

1. Vaya a Microsoft AppSource en <https://appsource.microsoft.com/marketplace/apps> y busque el complemento Report Phishing.

2. Haga **clic en OBTENER AHORA**.

3. En el cuadro de diálogo que aparece, revise los términos de uso y la directiva de privacidad y, a continuación, haga clic en **Continuar**.

4. Inicie sesión con su cuenta laboral o educativa (para uso empresarial) o su cuenta Microsoft (para uso personal).

Después de instalar y habilitar el complemento, verá los siguientes iconos:

- En Outlook, el icono tiene este aspecto:

  ![Report Phishing add-in icon for Outlook.](../../media/Outlook-ReportPhishing.png)

- En Outlook en la Web, el icono tiene este aspecto:

    > [!div class="mx-imgBorder"]
    > ![Outlook en la Web de complemento de suplantación de identidad de informes.](../../media/OWA-ReportPhishing.png)

### <a name="get-the-report-phishing-add-in-for-your-organization"></a>Obtener el complemento de suplantación de identidad de informes para su organización

> [!NOTE]
> El complemento podría tardar hasta 12 horas en aparecer en la organización.

1. En el [Centro de administración de Microsoft 365](https://admin.microsoft.com/AdminPortal/Home?#/homepage), **ve a Configuración** \> **aplicaciones integradas**. Haz clic **en Obtener aplicaciones**.

    > [!div class="mx-imgBorder"]
    > ![Centro de administración de Microsoft 365 aplicaciones integradas](../../media/microsoft-365-admin-center-integrated-apps.png)

2. En la **Aplicaciones Microsoft 365** que aparece, haga clic en el cuadro Buscar,  escriba Informar de **suplantación** de identidad y, a continuación, haga clic en **Buscar** ![en el icono Buscar.](../../media/search-icon.png) En la lista de resultados, busque y seleccione **Report Phishing**. 
 
3. Se abre la página de detalles de la aplicación. Seleccione **Obtener ahora**.

4. Complete la información básica del perfil y, a continuación, haga clic **en Continuar**.

5. Se **abrirá el menú desplegable Implementar** nueva aplicación. Siga los pasos [descritos anteriormente](enable-the-report-message-add-in.md#get-the-report-message-add-in-for-your-organization) para completar la configuración. 

## <a name="edit-settings-for-the-report-phishing-add-in"></a>Editar la configuración del complemento de suplantación de identidad de informe

1. En el Centro de administración de Microsoft 365, **ve a Configuración** \> **aplicaciones integradas** \. A continuación, busque **y seleccione Report Phishing** add-in.

2. En el control desplegable que aparece, seleccione **Editar usuarios** para editar la configuración del usuario.

    > [!div class="mx-imgBorder"]
    > ![Report Phishing flyout](../../media/microsoft-365-admin-center-report-phishing-edit.png)

3. Para quitar el complemento, selecciona **Quitar aplicación en** **Acciones** en el mismo control desplegable. 
