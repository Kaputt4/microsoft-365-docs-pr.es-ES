---
title: Habilitar el mensaje de informe o los complementos de suplantación de identidad de informes
f1.keywords:
- NOCSH
ms.author: siosulli
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo habilitar el mensaje de informe o los complementos de suplantación de identidad de informes para Outlook y Outlook en la web, para usuarios individuales o para toda la organización.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 25c4f7d67fd4fa876544a17df0f4bc1abfd7b3e7
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782938"
---
# <a name="enable-the-report-message-or-the-report-phishing-add-ins"></a>Habilitar el mensaje de informe o los complementos de suplantación de identidad de informes

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> Si es administrador de una organización Microsoft 365 con buzones de correo Exchange Online, se recomienda usar el portal de envíos en el Centro de seguridad y & cumplimiento. Para obtener más información, vea [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).

Los complementos Report Message y Report Phishing para Outlook y Outlook en la web (anteriormente conocido como Outlook Web App) permiten a los usuarios notificar fácilmente falsos positivos (buen correo electrónico marcado como negativo) o falsos negativos (correo electrónico no permitido) a Microsoft y sus filiales para su análisis. 

Microsoft usa estos envíos para mejorar la eficacia de las tecnologías de protección de correo electrónico. Por ejemplo, supongamos que los usuarios están informando de muchos mensajes mediante el complemento Detección de suplantación de identidad de informes. Esta información se muestra en el Panel de seguridad y otros informes. El equipo de seguridad de la organización puede usar esta información como una indicación de que es posible que sea necesario actualizar las directivas contra suplantación de identidad. 

Puede instalar el complemento Report Message o Report Phishing. Si desea que los usuarios informen tanto de mensajes de correo no deseado como de suplantación de identidad( phishing), implemente el complemento Report Message en su organización. Para obtener más información, vea Enable the Report Message add-in. 

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

- Ambos complementos no están disponibles para buzones o buzones compartidos en organizaciones Exchange locales.

- El explorador web existente debe funcionar con los complementos Report Message y Report Phishing. Pero, si observa que el complemento no está disponible o no funciona como se esperaba, pruebe con un explorador diferente.

- Para las instalaciones organizativas, la organización debe configurarse para usar la autenticación de OAuth. Para obtener más información, vea [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).

- Los administradores deben ser miembros del grupo de roles Administradores globales. Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).

- Para obtener más información sobre cómo notificar un mensaje mediante la característica Mensaje de informe, vea [Report false positives and false negatives in Outlook](report-false-positives-and-false-negatives.md).

## <a name="get-the-report-message-add-in"></a>Obtener el complemento Mensaje de informe

### <a name="get-the-add-in-for-yourself"></a>Obtener el complemento por ti mismo

1. Vaya a Microsoft AppSource en <https://appsource.microsoft.com/marketplace/apps> y busque el complemento Mensaje de informe. Para ir directamente al complemento Mensaje de informe, vaya a <https://appsource.microsoft.com/product/office/wa104381180> .

2. Haga **clic en OBTENER AHORA**.

   ![Mensaje de informe: obtenerlo ahora](../../media/ReportMessageGETITNOW.png)

3. En el cuadro de diálogo que aparece, revise los términos de uso y la directiva de privacidad y, a continuación, haga clic **en Continuar**.

4. Inicie sesión con su cuenta laboral o educativa (para uso empresarial) o su cuenta Microsoft (para uso personal).

Después de instalar y habilitar el complemento, verá los siguientes iconos:

- En Outlook, el icono tiene este aspecto:

  > [!div class="mx-imgBorder"]
  > ![Icono del complemento Mensaje de informe para Outlook](../../media/OutlookReportMessageIcon.png)

- En Outlook web, el icono tiene este aspecto:

  > [!div class="mx-imgBorder"]
  > ![Outlook en el icono del complemento Mensaje de informe web](../../media/owa-report-message-icon.png)

### <a name="get-the-add-in-for-your-organization"></a>Obtener el complemento para su organización

> [!NOTE]
> El complemento podría tardar hasta 12 horas en aparecer en la organización.

1. En el centro Microsoft 365 administración, vaya a  la página Configuración complementos en \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> . Si no ves  la página Complemento, ve al vínculo **Configuración** Complementos de aplicaciones integradas en la parte superior de la \>  \>  página **Aplicaciones integradas.**

2. Seleccione **Implementar complemento en** la parte superior de la página y, a continuación, seleccione **Siguiente**.

   ![Servicios y complementos en el Centro de administración de Microsoft 365 administración](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. En el menú desplegable Implementar un nuevo complemento que aparece, revise la información y, **a** continuación, haga clic **en Siguiente**.

4. En la página siguiente, haga clic **en Elegir en la Tienda**.

   ![Implementar una nueva página de complemento](../../media/NewAddInScreen2.png)

5. En la **página Seleccionar complemento** que aparece, haga clic en el cuadro Buscar, escriba **Mensaje** de informe y, a continuación, haga clic en **Buscar** en el icono Buscar  ![ ](../../media/search-icon.png) . En la lista de resultados, busque **Mensaje de informe** y, a continuación, haga clic en **Agregar**.

   ![Seleccionar resultados de búsqueda de complementos](../../media/NewAddInScreen3.png)

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

   ![Configurar página de complemento](../../media/configure-add-in.png)

   Cuando haya terminado, haga clic en **Implementar**.

8. En la **página Implementar mensaje de** informe que aparece, verá un informe de progreso seguido de una confirmación de que se implementó el complemento. Después de leer la información, haga clic **en Siguiente**.

   ![Página Implementar mensaje de informe](../../media/deploy-report-message-page.png)

9. En la **página Anunciar complemento que** aparece, revise la información y, a continuación, haga clic en **Cerrar**.

   ![Anunciar página de complemento](../../media/announce-add-in-page.png)

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a>Revisar o editar la configuración del complemento Mensaje de informe

1. En el centro Microsoft 365 administración, vaya a  la página Configuración complementos en \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> . Si no ves  la página Complemento, ve al vínculo **Configuración** Complementos de aplicaciones integradas en la parte superior de la \>  \>  página **Aplicaciones integradas.**

   ![Servicios y Add-Ins en el nuevo Centro de administración Microsoft 365 administración](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. Busque y seleccione el **complemento Mensaje** de informe.

3. En el **control desplegable Editar mensaje** de informe que aparece, revise y edite la configuración según corresponda para su organización. Cuando haya terminado, haga clic en **Guardar**.

   ![Configuración para el complemento Mensaje de informe](../../media/EditReportMessageAddIn.png)

## <a name="get-the-report-phishing-add-in"></a>Obtener el complemento de suplantación de identidad de informe

### <a name="get-the-add-in-for-yourself"></a>Obtener el complemento por ti mismo

1. Vaya a Microsoft AppSource en y busque el complemento <https://appsource.microsoft.com/marketplace/apps> Report Phishing.

2. Haga **clic en OBTENER AHORA**.

3. En el cuadro de diálogo que aparece, revise los términos de uso y la directiva de privacidad y, a continuación, haga clic **en Continuar**.

4. Inicie sesión con su cuenta laboral o educativa (para uso empresarial) o su cuenta Microsoft (para uso personal).

Después de instalar y habilitar el complemento, verá los siguientes iconos:

- En Outlook, el icono tiene este aspecto:

  ![Icono de complemento de phishing de informe para Outlook](../../media/Outlook-ReportPhishing.png)

- En Outlook web, el icono tiene este aspecto:

  > [!div class="mx-imgBorder"]
  > ![Outlook en el icono del complemento de phishing de informe web](../../media/OWA-ReportPhishing.png)

### <a name="get-the-add-in-for-your-organization"></a>Obtener el complemento para su organización

> [!NOTE]
> El complemento podría tardar hasta 12 horas en aparecer en la organización.

1. En el centro Microsoft 365 administración, vaya a  la página Configuración complementos en \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> . Si no ves  la página Complemento, ve al vínculo **Configuración** Complementos de aplicaciones integradas en la parte superior de la \>  \>  página **Aplicaciones integradas.**

2. Seleccione **Implementar complemento en** la parte superior de la página y, a continuación, seleccione **Siguiente**.

   ![Servicios y complementos en el Centro de administración de Microsoft 365 administración](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. En el menú desplegable Implementar un nuevo complemento que aparece, revise la información y, **a** continuación, haga clic **en Siguiente**.

4. En la página siguiente, haga clic **en Elegir en la Tienda**.

   ![Implementar una nueva página de complemento](../../media/NewAddInScreen2.png)

5. En la **página Seleccionar complemento** que aparece, haga clic en el cuadro Buscar, escriba Informe de **suplantación** de identidad y, a continuación, haga clic en **Buscar** icono  ![ ](../../media/search-icon.png) . En la lista de resultados, busque **Report Phishing** y, a continuación, haga clic **en Agregar**.

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

1. En el centro Microsoft 365 administración, vaya a  la página Configuración complementos en \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> . Si no ves  la página Complemento, ve al vínculo **Configuración** Complementos de aplicaciones integradas en la parte superior de la \>  \>  página **Aplicaciones integradas.**

2. Busque y seleccione el **complemento Report Phishing.**

3. En el **control desplegable Editar suplantación** de identidad de informe que aparece, revise y edite la configuración según corresponda para su organización. Cuando haya terminado, haga clic en **Guardar**.
