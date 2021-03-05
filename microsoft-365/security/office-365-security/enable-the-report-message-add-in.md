---
title: Habilitar el complemento Notificar mensajes
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
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
description: Obtenga información sobre cómo habilitar el complemento Report Message para Outlook y Outlook en la web, para usuarios individuales o para toda la organización.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5eed0fc8905020ea12d3fa6a51c5c8051205b0da
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453758"
---
# <a name="enable-the-report-message-add-in"></a>Habilitar el complemento Notificar mensajes

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

> [!NOTE]
> Si es administrador de una organización de Microsoft 365 con buzones de Exchange Online, le recomendamos que use el portal de envíos en el Centro de seguridad & cumplimiento. Para obtener más información, vea [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).

Los complementos Report Message y Report Phishing para Outlook y Outlook en la web (anteriormente conocidos como Outlook Web App) permiten a los usuarios notificar fácilmente falsos positivos (correo electrónico bueno marcado como negativo) o falsos negativos (correo electrónico no permitido) a Microsoft y sus filiales para su análisis.

Microsoft usa estos envíos para mejorar la eficacia de las tecnologías de protección de correo electrónico. Por ejemplo, si los usuarios están informando de una gran cantidad de mensajes que se marcaron como correo no deseado mediante el complemento Mensaje de informe, es posible que el equipo de seguridad de la organización necesite ajustar las directivas contra correo no [deseado.](configure-your-spam-filter-policies.md)

Puede instalar el complemento Report Message o Report Phishing. Si desea que los usuarios informen solo de mensajes de suplantación de identidad, implemente el complemento Report Phishing en su organización. Para obtener más información, vea [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).

El complemento Mensaje de informe proporciona la opción de notificar mensajes de correo no deseado y de suplantación de identidad. Los administradores pueden habilitar el complemento Mensaje de informe para la organización y los usuarios individuales pueden instalarlo por sí mismos.

Si es un usuario individual, puede habilitar el complemento Mensaje de [informe por usted mismo.](#get-the-report-message-add-in-for-yourself)

Si es un administrador global o un administrador de Exchange Online y Exchange está configurado para usar la autenticación de OAuth, puede habilitar el complemento Report [Message para su organización](#get-and-enable-the-report-message-add-in-for-your-organization). El mensaje de informe Add-In está disponible a través [de la implementación centralizada](../../admin/manage/centralized-deployment-of-add-ins.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- El complemento Mensaje de informe funciona con la mayoría de las suscripciones de Microsoft 365 y los siguientes productos:

  - Outlook en la Web
  - Outlook 2013 SP1 o posterior
  - Outlook 2016 para Mac
  - Outlook incluido con aplicaciones de Microsoft 365 para Empresas
  - Aplicación de Outlook para iOS y Android

- El complemento Mensaje de informe no está disponible para buzones o buzones compartidos en organizaciones locales de Exchange.

- Puede configurar los mensajes notificados para que se copien o redirijan a un buzón que especifique. Para obtener más información, vea [Directivas de envío de usuarios](user-submission.md).

- El explorador web existente debe funcionar con el complemento Mensaje de informe. Pero, si observa que el complemento no está disponible o no funciona como se esperaba, pruebe con un explorador diferente.

- Para las instalaciones organizativas, la organización debe configurarse para usar la autenticación de OAuth. Para obtener más información, vea [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).

- Los administradores deben ser miembros del grupo de roles Administradores globales. Para más información, consulte [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).

## <a name="get-the-report-message-add-in-for-yourself"></a>Obtener el complemento Mensaje de informe por usted mismo

1. Vaya a Microsoft AppSource en <https://appsource.microsoft.com/marketplace/apps> y busque el complemento Mensaje de informe. Para ir directamente al complemento Mensaje de informe, vaya a <https://appsource.microsoft.com/product/office/wa104381180> .

2. Haga **clic en OBTENER AHORA**.

   ![Mensaje de informe: obtenerlo ahora](../../media/ReportMessageGETITNOW.png)

3. En el cuadro de diálogo que aparece, revise los términos de uso y la directiva de privacidad y, a continuación, haga clic **en Continuar**.

4. Inicie sesión con su cuenta laboral o educativa (para uso empresarial) o su cuenta Microsoft (para uso personal).

Después de instalar y habilitar el complemento, verá los siguientes iconos:

- En Outlook, el icono tiene este aspecto:

  ![Icono del complemento Mensaje de informe para Outlook](../../media/OutlookReportMessageIcon.png)

- En Outlook en la web, el icono tiene este aspecto:

  ![Icono del complemento Mensaje de informe de Outlook en la web](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

Para obtener información sobre cómo usar el complemento, vea [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a>Obtener y habilitar el complemento Mensaje de informe para su organización

> [!NOTE]
> El complemento podría tardar hasta 12 horas en aparecer en la organización.

1. En el Centro de administración de Microsoft 365, vaya a la página Complementos de configuración en , Si no ve  la página Complementos, vaya al vínculo Configuración Complementos integrados en la parte superior de la página Aplicaciones \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \> **integradas.** 

2. Seleccione **Implementar complemento en** la parte superior de la página y, a continuación, seleccione **Siguiente**.

   ![Página Servicios y complementos en el Centro de administración de Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

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

## <a name="learn-how-to-use-the-report-message-add-in"></a>Obtenga información sobre cómo usar el complemento Mensaje de informe

Las personas que tengan asignado el complemento verán los siguientes iconos:

- En Outlook, el icono tiene este aspecto:

  ![Icono de complemento de mensaje de informe para Outlook](../../media/OutlookReportMessageIcon.png)

- En Outlook en la web, el icono tiene este aspecto:

  ![Outlook en el icono del complemento de mensaje de informe web](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

Cuando notifique a los usuarios sobre el complemento Mensaje de informe, incluya un vínculo para [Usar el complemento Mensaje de informe](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a>Revisar o editar la configuración del complemento Mensaje de informe

1. En el Centro de administración de Microsoft 365, vaya a la página Complementos de configuración en , Si no ve  la página Complementos, vaya al vínculo Configuración Complementos integrados en la parte superior de la página Aplicaciones \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \> **integradas.** 

   ![Servicios y Add-Ins en el nuevo Centro de administración de Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. Busque y seleccione el **complemento Mensaje** de informe.

3. En el **control desplegable Editar mensaje** de informe que aparece, revise y edite la configuración según corresponda para su organización. Cuando haya terminado, haga clic en **Guardar**.

   ![Configuración del complemento Mensaje de informe](../../media/EditReportMessageAddIn.png)

## <a name="view-and-review-reported-messages"></a>Ver y revisar los mensajes notificados

Para revisar los mensajes que los usuarios informan a Microsoft, tiene estas opciones:

- Use el portal de envíos de administrador. Para obtener más información, vea [Ver envíos de usuarios a Microsoft](admin-submission.md#view-user-submissions-to-microsoft).

- Cree una regla de flujo de correo (también conocida como regla de transporte) para enviar copias de los mensajes notificados. Para obtener instrucciones, consulte [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).
