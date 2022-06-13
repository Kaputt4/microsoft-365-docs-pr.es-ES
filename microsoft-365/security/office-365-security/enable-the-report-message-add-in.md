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
description: Obtenga información sobre cómo habilitar el mensaje de informe o los complementos de suplantación de identidad de informe para Outlook y Outlook en la Web, para usuarios individuales o para toda la organización.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b0882a37161989248b8c970a5dbe01efc0bcff65
ms.sourcegitcommit: a7c1acfb3d2cbba913e32493b16ebd8cbfeee456
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/13/2022
ms.locfileid: "66043771"
---
# <a name="enable-the-report-message-or-the-report-phishing-add-ins"></a>Habilitar los complementos Informar sobre el mensaje o Informar sobre suplantación de identidad

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> Si es administrador de una organización Microsoft 365 con buzones de Exchange Online, se recomienda usar la página **Envíos** en el portal de Microsoft 365 Defender. Para obtener más información, consulte [Uso del envío de administrador para enviar sospechas de correo no deseado, fish, direcciones URL y archivos a Microsoft](admin-submission.md).

Los complementos Mensaje de informe y Suplantación de identidad de informe para Outlook y Outlook en la Web (anteriormente conocidos como Outlook Web App) facilitan la notificación de falsos positivos (un buen correo electrónico marcado como incorrecto) o falsos negativos (se permite el correo electrónico incorrecto) a Microsoft y sus filiales para su análisis.

Microsoft usa estos envíos para mejorar la eficacia de las tecnologías de protección de correo electrónico. Por ejemplo, supongamos que las personas están informando de muchos mensajes mediante el complemento De suplantación de identidad de informe. Esta información aparece en el panel de seguridad y en otros informes. El equipo de seguridad de su organización puede usar esta información como una indicación de que es posible que sea necesario actualizar las directivas anti phishing.

Puede instalar el complemento Mensaje de informe o Suplantación de identidad de informe. Si quiere que los usuarios informen de mensajes de spam y phishing, implemente el complemento Mensaje de informe en su organización.

El complemento Mensaje de informe proporciona la opción de informar de mensajes de correo no deseado y de suplantación de identidad (phishing). Los administradores pueden habilitar el complemento Mensaje de informe para la organización y los usuarios individuales pueden instalarlo por sí mismos.

El complemento De suplantación de identidad de informe proporciona la opción de notificar solo mensajes de suplantación de identidad (phishing). Los administradores pueden habilitar el complemento Report Phishing para la organización y los usuarios individuales pueden instalarlo por sí mismos.

Si es un usuario individual, puede habilitar ambos complementos por sí mismo.

Si es un administrador global o un administrador de Exchange Online y Exchange está configurado para usar la autenticación de OAuth, puede habilitar el complemento Mensaje de informe y el complemento De suplantación de identidad de informe para su organización. Ambos complementos ya están disponibles a través de [la implementación centralizada](../../admin/manage/centralized-deployment-of-add-ins.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

- Tanto el complemento mensaje de informe como el complemento de suplantación de identidad de informe funcionan con la mayoría de las suscripciones Microsoft 365 y los siguientes productos:
  - Outlook en la Web
  - Outlook 2013 SP1 o posterior
  - Outlook 2016 para Mac
  - Outlook incluye con aplicaciones de Microsoft 365 para Enterprise
  - Outlook aplicación para iOS y Android

- Ambos complementos no están disponibles para buzones compartidos, de grupo o delegados (los complementos se atenuarán).

- Ambos complementos no están disponibles para los buzones de correo de Exchange locales.

- El explorador web existente debe funcionar con los complementos Mensaje de informe y Suplantación de identidad de informe. Sin embargo, si observa que el complemento no está disponible o no funciona según lo esperado, pruebe con otro explorador.

- Para las instalaciones de la organización, la organización debe configurarse para usar la autenticación de OAuth. Para obtener más información, vea [Determinar si la implementación centralizada de complementos funciona para su organización](../../admin/manage/centralized-deployment-of-add-ins.md).

- Los administradores deben ser miembros del grupo de roles Administradores globales. Para obtener más información, consulte [Permisos en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md).

- Para obtener más información sobre cómo notificar un mensaje mediante la característica Mensaje de informe, vea [Notificar falsos positivos y falsos negativos en Outlook](report-false-positives-and-false-negatives.md).

- Las organizaciones que tienen una solución de seguridad o filtrado de direcciones URL (como un proxy o firewall) en su lugar, deben tener ipagave.azurewebsites.net y outlook.office.com puntos de conexión permitidos en el protocolo HTTPS.

## <a name="get-the-report-message-add-in"></a>Obtención del complemento mensaje de informe

### <a name="get-the-report-message-add-in-for-yourself"></a>Obtener el complemento de mensaje de informe por sí mismo

1. Vaya a Microsoft AppSource en <https://appsource.microsoft.com/marketplace/apps> y busque el complemento Mensaje de informe. Para ir directamente al complemento Mensaje de informe, vaya a <https://appsource.microsoft.com/product/office/wa104381180>.

2. Haga clic en **OBTENERLO AHORA**.

   :::image type="content" source="../../media/ReportMessageGETITNOW.png" alt-text="Mensaje de informe Obtener ahora." lightbox="../../media/ReportMessageGETITNOW.png":::

3. En el cuadro de diálogo que aparece, revise los términos de uso y la directiva de privacidad y, a continuación, haga clic en **Continuar**.

4. Inicie sesión con su cuenta profesional o educativa (para uso empresarial) o con su cuenta Microsoft (para uso personal).

Una vez instalado y habilitado el complemento, verá los iconos siguientes:

- En Outlook, el icono tiene este aspecto:

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="../../media/OutlookReportMessageIcon.png" alt-text="Icono del complemento Mensaje de informe para Outlook." lightbox="../../media/OutlookReportMessageIcon.png":::

- En Outlook en la Web, el icono tiene este aspecto:

    > [!div class="mx-imgBorder"]
    > ![Outlook en la Web icono de complemento de mensaje de informe.](../../media/owa-report-message-icon.png)

### <a name="get-the-report-message-add-in-for-your-organization"></a>Obtener el complemento de mensaje de informe para su organización

> [!NOTE]
> El complemento puede tardar hasta 12 horas en aparecer en su organización.

1. En el [Centro de administración de Microsoft 365](https://admin.microsoft.com/AdminPortal/Home?#/homepage), vaya a **Configuración** \> **Aplicaciones integradas**. Haga clic en **Obtener aplicaciones**.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="../../media/microsoft-365-admin-center-integrated-apps.png" alt-text="Las aplicaciones integradas de Centro de administración de Microsoft 365." lightbox="../../media/microsoft-365-admin-center-integrated-apps.png":::

2. En la página **Aplicaciones Microsoft 365** que aparece, haga clic en el cuadro **Buscar**, escriba Mensaje de **informe** y, a continuación, haga clic en el icono **Buscar** ![búsqueda.](../../media/search-icon.png) En la lista de resultados, busque y seleccione **Mensaje de informe**.

3. Se abre la página de detalles de la aplicación. Seleccione **Obtener ahora**.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="../../media/microsoft-365-admin-center-report-message.png" alt-text="Complemento Mensaje de informe." lightbox="../../media/microsoft-365-admin-center-report-message.png":::

4. Complete la información básica del perfil y, a continuación, haga clic en **Continuar**.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="../../media/microsoft-365-admin-center-profile-info.png" alt-text="Configuración del perfil del complemento de mensaje de informe." lightbox="../../media/microsoft-365-admin-center-profile-info.png":::

5. Se abre el control flotante **Implementar nueva aplicación** . Configure los siguientes valores. Haga clic en **Siguiente** para ir a la página siguiente para completar la configuración.

   - **Agregar usuarios**: seleccione uno de los valores siguientes:
     - **Sólo yo**
     - **Toda la organización**
     - **Usuarios o grupos específicos**

   - **Implementación**:
     - **Aceptar solicitudes de permisos**: lea detenidamente los permisos y funcionalidades de la aplicación antes de ir a la página siguiente.

        > [!div class="mx-imgBorder"]
        > :::image type="content" source="../../media/microsoft-365-admin-center-deploy-new-app.png" alt-text="La página Aceptar solicitudes de permisos." lightbox="../../media/microsoft-365-admin-center-deploy-new-app.png":::

     - **Finalizar la implementación**: revise y termine de implementar el complemento.
     - **Implementación completada**: seleccione **Listo** para completar la instalación.

        > [!div class="mx-imgBorder"]
        > :::image type="content" source="../../media/microsoft-365-admin-center-deployment-complete.png" alt-text="Mensaje de notificación de la implementación completada." lightbox="../../media/microsoft-365-admin-center-deployment-complete.png":::

## <a name="edit-settings-for-the-report-message-add-in"></a>Editar la configuración del complemento Mensaje de informe

1. En el Centro de administración de Microsoft 365, vaya a **Configuración** \> **Aplicaciones integradas** \. A continuación, busque y seleccione **Complemento de mensaje** de informe.

2. En el control flotante que aparece, seleccione **Editar usuarios** para editar la configuración del usuario.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="../../media/microsoft-365-admin-center-report-message-edit.png" alt-text="El control flotante Mensaje de informe." lightbox="../../media/microsoft-365-admin-center-report-message-edit.png":::

3. Para quitar el complemento, seleccione **Quitar aplicación** en **Acciones** en el mismo control flotante.

## <a name="get-the-report-phishing-add-in"></a>Obtención del complemento de suplantación de identidad de informe

### <a name="get-the-report-phishing-add-in-for-yourself"></a>Obtener el complemento de suplantación de identidad de informe por sí mismo

1. Vaya a Microsoft AppSource en <https://appsource.microsoft.com/marketplace/apps> y busque el complemento De suplantación de identidad de informe.

2. Haga clic en **OBTENERLO AHORA**.

3. En el cuadro de diálogo que aparece, revise los términos de uso y la directiva de privacidad y, a continuación, haga clic en **Continuar**.

4. Inicie sesión con su cuenta profesional o educativa (para uso empresarial) o con su cuenta Microsoft (para uso personal).

Una vez instalado y habilitado el complemento, verá los iconos siguientes:

- En Outlook, el icono tiene este aspecto:

  ![Icono de complemento de suplantación de identidad de informe para Outlook.](../../media/Outlook-ReportPhishing.png)

- En Outlook en la Web, el icono tiene este aspecto:

    > [!div class="mx-imgBorder"]
    > ![Outlook en la Web icono de complemento de suplantación de identidad de informe.](../../media/OWA-ReportPhishing.png)

### <a name="get-the-report-phishing-add-in-for-your-organization"></a>Obtención del complemento de suplantación de identidad de informe para su organización

> [!NOTE]
> El complemento puede tardar hasta 12 horas en aparecer en su organización.

1. En el [Centro de administración de Microsoft 365](https://admin.microsoft.com/AdminPortal/Home?#/homepage), vaya a **Configuración** \> **Aplicaciones integradas**. Haga clic en **Obtener aplicaciones**.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="../../media/microsoft-365-admin-center-integrated-apps.png" alt-text="Las aplicaciones integradas de Centro de administración de Microsoft 365." lightbox="../../media/microsoft-365-admin-center-integrated-apps.png":::

2. En la página **Aplicaciones Microsoft 365** que aparece, haga clic en el cuadro **Buscar**, escriba **Suplantación de identidad** de informe y, a continuación, haga clic en el icono **Buscar** ![búsqueda.](../../media/search-icon.png) En la lista de resultados, busque y seleccione **Suplantación de identidad de** informe.

3. Se abre la página de detalles de la aplicación. Seleccione **Obtener ahora**.

4. Complete la información básica del perfil y, a continuación, haga clic en **Continuar**.

5. Se abre el control flotante **Implementar nueva aplicación** . Siga los pasos [descritos anteriormente](enable-the-report-message-add-in.md#get-the-report-message-add-in-for-your-organization) para completar la configuración.

## <a name="edit-settings-for-the-report-phishing-add-in"></a>Editar la configuración del complemento de suplantación de identidad de informe

1. En el Centro de administración de Microsoft 365, vaya a **Configuración** \> **Aplicaciones integradas** \. A continuación, busque y seleccione Report Phishing add-in (Notificar complemento de **suplantación de identidad** ).

2. En el control flotante que aparece, seleccione **Editar usuarios** para editar la configuración del usuario.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="../../media/microsoft-365-admin-center-report-phishing-edit.png" alt-text="Control flotante De suplantación de identidad de informe." lightbox="../../media/microsoft-365-admin-center-report-phishing-edit.png":::

3. Para quitar el complemento, seleccione **Quitar aplicación** en **Acciones** en el mismo control flotante.
