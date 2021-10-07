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
ms.openlocfilehash: 47ba6d4d9f02934f05a98cf8ef01820a9daac8d9
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60191460"
---
# <a name="enable-the-report-message-or-the-report-phishing-add-ins"></a>Habilitar los complementos Informar sobre el mensaje o Informar sobre suplantación de identidad

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> Si es administrador de una organización Microsoft 365 con buzones de correo Exchange Online, se recomienda usar la página **Envíos** en el portal de Microsoft 365 Defender. Para obtener más información, vea [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).

Los complementos Report Message y Report Phishing para Outlook y Outlook en la Web (anteriormente conocidos como Outlook Web App) permiten a los usuarios notificar fácilmente falsos positivos (correo electrónico bueno marcado como negativo) o falsos negativos (correo electrónico no permitido) a Microsoft y sus filiales para su análisis.

Microsoft usa estos envíos para mejorar la eficacia de las tecnologías de protección de correo electrónico. Por ejemplo, supongamos que los usuarios están informando de muchos mensajes mediante el complemento Detección de suplantación de identidad de informes. Esta información se muestra en el Panel de seguridad y otros informes. El equipo de seguridad de la organización puede usar esta información como una indicación de que es posible que sea necesario actualizar las directivas contra suplantación de identidad.

Puede instalar el complemento Report Message o Report Phishing. Si desea que los usuarios informen tanto de mensajes de correo no deseado como de suplantación de identidad( phishing), implemente el complemento Report Message en su organización. Para obtener más información, vea Enable the Report Message add-in.

El complemento Mensaje de informe proporciona la opción de notificar mensajes de correo no deseado y de suplantación de identidad. Los administradores pueden habilitar el complemento Mensaje de informe para la organización y los usuarios individuales pueden instalarlo por sí mismos.

El complemento Report Phishing proporciona la opción de notificar solo mensajes de suplantación de identidad. Los administradores pueden habilitar el complemento Report Phishing para la organización y los usuarios individuales pueden instalarlo por sí mismos.

Si eres un usuario individual, puedes habilitar ambos complementos por ti mismo.

Si es un administrador global o un administrador de Exchange Online y Exchange está configurado para usar la autenticación de OAuth, puede habilitar el complemento Report Message y el complemento Report Phishing para su organización. Ambos complementos ya están disponibles a través [de la implementación centralizada](../../admin/manage/centralized-deployment-of-add-ins.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

- Tanto el complemento Report Message como el complemento Report Phishing funcionan con la mayoría Microsoft 365 suscripciones y los siguientes productos:
  - Outlook en la Web
  - Outlook 2013 SP1 o posterior
  - Outlook 2016 para Mac
  - Outlook se incluye con Microsoft 365 aplicaciones para Enterprise
  - Outlook aplicación para iOS y Android

- Ambos complementos no están disponibles para buzones o buzones compartidos en organizaciones Exchange locales.

- El explorador web existente debe funcionar con los complementos Report Message y Report Phishing. Pero, si observa que el complemento no está disponible o no funciona como se esperaba, pruebe con un explorador diferente.

- Para las instalaciones organizativas, la organización debe configurarse para usar la autenticación de OAuth. Para obtener más información, vea [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).

- Los administradores deben ser miembros del grupo de roles Administradores globales. Para obtener más información, consulte [Permisos en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md).

- Para obtener más información sobre cómo notificar un mensaje mediante la característica Mensaje de informe, vea [Report false positives and false negatives in Outlook](report-false-positives-and-false-negatives.md).

- Las organizaciones que tengan una solución de seguridad o filtrado de direcciones URL (como Proxy y FireWall) tendrán que tener puntos de conexión ipagave.azurewebsites.net y outlook.office.com que se puedan alcanzar en el protocolo HTTPS.


> [!IMPORTANT]
> No recomendamos la experiencia de informes integrada en Outlook porque no puede usar la directiva [de envío de usuario](./user-submission.md). Se recomienda usar el complemento Report Message o el complemento Report Phishing en su lugar.

## <a name="get-the-report-message-add-in"></a>Obtener el complemento Mensaje de informe

### <a name="get-the-report-message-add-in-for-yourself"></a>Obtener el complemento Mensaje de informe por usted mismo

1. Vaya a Microsoft AppSource en <https://appsource.microsoft.com/marketplace/apps> y busque el complemento Mensaje de informe. Para ir directamente al complemento Mensaje de informe, vaya a <https://appsource.microsoft.com/product/office/wa104381180> .

2. Haga **clic en OBTENER AHORA**.

   ![Mensaje de informe: obtenerlo ahora.](../../media/ReportMessageGETITNOW.png)

3. En el cuadro de diálogo que aparece, revise los términos de uso y la directiva de privacidad y, a continuación, haga clic **en Continuar**.

4. Inicie sesión con su cuenta laboral o educativa (para uso empresarial) o su cuenta Microsoft (para uso personal).

Después de instalar y habilitar el complemento, verá los siguientes iconos:

- En Outlook, el icono tiene este aspecto:

  > [!div class="mx-imgBorder"]
  > ![Icono de complemento Mensaje de informe para Outlook.](../../media/OutlookReportMessageIcon.png)

- En Outlook en la Web, el icono tiene este aspecto:

  > [!div class="mx-imgBorder"]
  > ![Outlook en la Web Icono del complemento Mensaje de informe.](../../media/owa-report-message-icon.png)

### <a name="get-the-report-message-add-in-for-your-organization"></a>Obtener el complemento Mensaje de informe para su organización

> [!NOTE]
> El complemento podría tardar hasta 12 horas en aparecer en la organización.

1. En el Centro de administración de Microsoft 365, vaya a la **página Configuración** \> **Complementos** en <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> . Si no ves  la página Complemento, ve al vínculo **Configuración** Complementos de aplicaciones integradas en la parte superior de la \>  \>  página **Aplicaciones integradas.**

2. Seleccione **Implementar complemento en** la parte superior de la página y, a continuación, seleccione **Siguiente**.

   ![Servicios y complementos de la página Centro de administración de Microsoft 365.](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. En el menú desplegable Implementar un nuevo complemento que aparece, revise la información y, **a** continuación, haga clic **en Siguiente**.

4. En la página siguiente, haga clic **en Elegir en la Tienda**.

   ![Implementar una nueva página de complemento.](../../media/NewAddInScreen2.png)

5. En la **página Seleccionar complemento** que aparece, haga clic en el cuadro Buscar, escriba **Mensaje** de informe y, a continuación, haga clic en **Buscar** en el icono  ![ Buscar. ](../../media/search-icon.png) . En la lista de resultados, busque **Mensaje de informe** y, a continuación, haga clic en **Agregar**.

   ![Seleccione resultados de búsqueda de complementos.](../../media/NewAddInScreen3.png)

6. En el cuadro de diálogo que aparece, revise la información de privacidad y licencias y, a continuación, haga clic **en Continuar**.

7. En la **página Configurar complemento que** aparece, configure las siguientes opciones:

   - **Usuarios asignados:** seleccione uno de los siguientes valores:
     - **Todos** (predeterminado)
     - **Usuarios o grupos específicos**
     - **Sólo yo**

   - **Método de implementación:** seleccione uno de los siguientes valores:
     - **Corregido (predeterminado):** el complemento se implementa automáticamente en los usuarios especificados y no pueden quitarlo.
     - **Disponible:** los usuarios pueden instalar el complemento en **Home** \> **Get add-ins** \> **Admin-managed**.
     - **Opcional:** el complemento se implementa automáticamente en los usuarios especificados, pero pueden elegir quitarlo.

   ![Configurar la página del complemento.](../../media/configure-add-in.png)

   Cuando haya terminado, haga clic en **Implementar**.

8. En la **página Implementar mensaje de** informe que aparece, verá un informe de progreso seguido de una confirmación de que se implementó el complemento. Después de leer la información, haga clic **en Siguiente**.

   ![Página Implementar mensaje de informe.](../../media/deploy-report-message-page.png)

9. En la **página Anunciar complemento que** aparece, revise la información y, a continuación, haga clic en **Cerrar**.

   ![Anunciar página de complemento.](../../media/announce-add-in-page.png)

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a>Revisar o editar la configuración del complemento Mensaje de informe

1. En el Centro de administración de Microsoft 365, vaya a la página **Configuración** \> **complementos** en <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> . Si no ves  la página Complemento, ve al vínculo **Configuración** Complementos de aplicaciones integradas en la parte superior de la \>  \>  página **Aplicaciones integradas.**

   ![Servicios y Add-Ins en el nuevo Centro de Administración de Microsoft 365 datos.](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. Busque y seleccione el **complemento Mensaje** de informe.

3. En el **control desplegable Editar mensaje** de informe que aparece, revise y edite la configuración según corresponda para su organización. Cuando haya terminado, haga clic en **Guardar**.

   ![Configuración para el complemento Mensaje de informe.](../../media/EditReportMessageAddIn.png)

## <a name="get-the-report-phishing-add-in"></a>Obtener el complemento de suplantación de identidad de informe

### <a name="get-the-report-phishing-add-in-for-yourself"></a>Obtener el complemento de suplantación de identidad de informe por sí mismo

1. Vaya a Microsoft AppSource en y busque el complemento <https://appsource.microsoft.com/marketplace/apps> Report Phishing.

2. Haga **clic en OBTENER AHORA**.

3. En el cuadro de diálogo que aparece, revise los términos de uso y la directiva de privacidad y, a continuación, haga clic **en Continuar**.

4. Inicie sesión con su cuenta laboral o educativa (para uso empresarial) o su cuenta Microsoft (para uso personal).

Después de instalar y habilitar el complemento, verá los siguientes iconos:

- En Outlook, el icono tiene este aspecto:

  ![Report Phishing add-in icon for Outlook.](../../media/Outlook-ReportPhishing.png)

- En Outlook en la Web, el icono tiene este aspecto:

  > [!div class="mx-imgBorder"]
  > ![Outlook en la Web Report Phishing add-in icon.](../../media/OWA-ReportPhishing.png)

### <a name="get-the-report-phishing-add-in-for-your-organization"></a>Obtener el complemento de suplantación de identidad de informes para su organización

> [!NOTE]
> El complemento podría tardar hasta 12 horas en aparecer en la organización.

1. En el Centro de administración de Microsoft 365, vaya a la página **Configuración** \> **complementos** en <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> . Si no ves  la página Complemento, ve al vínculo **Configuración** Complementos de aplicaciones integradas en la parte superior de la \>  \>  página **Aplicaciones integradas.**

2. Seleccione **Implementar complemento en** la parte superior de la página y, a continuación, seleccione **Siguiente**.

   ![Servicios y complementos de la página Centro de administración de Microsoft 365.](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. En el menú desplegable Implementar un nuevo complemento que aparece, revise la información y, **a** continuación, haga clic **en Siguiente**.

4. En la página siguiente, haga clic **en Elegir en la Tienda**.

   ![Implementar una nueva página de complemento.](../../media/NewAddInScreen2.png)

5. En la **página Seleccionar complemento** que aparece, haga clic en el cuadro Buscar, escriba Informe de **suplantación** de identidad y, a continuación, haga clic en **Icono Buscar**  ![ búsqueda. ](../../media/search-icon.png) . En la lista de resultados, busque **Report Phishing** y, a continuación, haga clic **en Agregar**.

6. En el cuadro de diálogo que aparece, revise la información de privacidad y licencias y, a continuación, haga clic **en Continuar**.

7. En la **página Configurar complemento que** aparece, configure las siguientes opciones:

   - **Usuarios asignados:** seleccione uno de los siguientes valores:
     - **Todos** (predeterminado)
     - **Usuarios o grupos específicos**
     - **Sólo yo**

   - **Método de implementación:** seleccione uno de los siguientes valores:
     - **Corregido (predeterminado):** el complemento se implementa automáticamente en los usuarios especificados y no pueden quitarlo.
     - **Disponible:** los usuarios pueden instalar el complemento en **Home** \> **Get add-ins** \> **Admin-managed**.
     - **Opcional:** el complemento se implementa automáticamente en los usuarios especificados, pero pueden elegir quitarlo.

   Cuando haya terminado, haga clic en **Implementar**.

8. En la **página Implementar suplantación** de identidad de informes que aparece, verá un informe de progreso seguido de una confirmación de que el complemento se implementó. Después de leer la información, haga clic **en Siguiente**.

9. En la **página Anunciar complemento que** aparece, revise la información y, a continuación, haga clic en **Cerrar**.

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a>Revisar o editar la configuración del complemento de suplantación de identidad de informes

1. En el Centro de administración de Microsoft 365, vaya a la página **Configuración** \> **complementos** en <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> . Si no ves  la página Complemento, ve al vínculo **Configuración** Complementos de aplicaciones integradas en la parte superior de la \>  \>  página **Aplicaciones integradas.**

2. Busque y seleccione el **complemento Report Phishing.**

3. En el **control desplegable Editar suplantación** de identidad de informe que aparece, revise y edite la configuración según corresponda para su organización. Cuando haya terminado, haga clic en **Guardar**.
