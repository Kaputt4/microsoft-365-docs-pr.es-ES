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
description: Obtenga información sobre cómo habilitar el complemento De mensaje de informe para Outlook y Outlook en la Web, para usuarios individuales o para toda la organización.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 08ad2f61cc5dcd2e59af89ca788319c81e2f6bdb
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287370"
---
# <a name="enable-the-report-message-add-in"></a>Habilitar el complemento Notificar mensajes

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

> [!NOTE]
> Si es administrador de una organización de Microsoft 365 con buzones de Exchange Online, le recomendamos que use el portal de envíos en el Centro de & cumplimiento. Para obtener más información, vea Usar envío de administrador para enviar correos sospechosos de correo no [deseado, phishing, direcciones URL y archivos a Microsoft.](admin-submission.md)

Los complementos de notificación de suplantación de identidad (phishing) para Outlook y Outlook en la Web (anteriormente conocido como Outlook Web App) permiten a los usuarios notificar fácilmente falsos positivos (correo electrónico bueno marcado como negativo) o falsos negativos (correo electrónico no deseado permitido) a Microsoft y sus filiales para su análisis.

Microsoft usa estos envíos para mejorar la eficacia de las tecnologías de protección de correo electrónico. Por ejemplo, si los usuarios informan de una gran cantidad de mensajes que se marcaron como correo no deseado mediante el complemento Informar de mensaje, es posible que el equipo de seguridad de su organización necesite ajustar las directivas contra correo no [deseado.](configure-your-spam-filter-policies.md)

Puede instalar el complemento Mensaje de informe o Informar de suplantación de identidad. Si desea que los usuarios informen solo de mensajes de suplantación de identidad, implemente el complemento Detección de suplantación de identidad en su organización. Para obtener más información, vea Habilitar el complemento [de suplantación de identidad de informes.](enable-the-report-phish-add-in.md)

El complemento Mensaje de informe ofrece la opción de notificar mensajes de correo no deseado y de suplantación de identidad. Los administradores pueden habilitar el complemento Mensaje de informe para la organización y los usuarios individuales pueden instalarlo por sí mismos.

Si es un usuario individual, puede habilitar el complemento Mensaje [de informe para usted mismo.](#get-the-report-message-add-in-for-yourself)

Si es un administrador global o un administrador de Exchange Online y Exchange está configurado para usar la autenticación de OAuth, puede habilitar el complemento Mensaje de [informe para su organización.](#get-and-enable-the-report-message-add-in-for-your-organization) El mensaje de Add-In ahora está disponible a través [de la implementación centralizada.](../../admin/manage/centralized-deployment-of-add-ins.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

- El complemento Mensaje de informe funciona con la mayoría de las suscripciones de Microsoft 365 y los siguientes productos:

  - Outlook en la Web
  - Outlook 2013 SP1 o posterior
  - Outlook 2016 para Mac
  - Outlook incluido con aplicaciones de Microsoft 365 para empresas
  - Aplicación de Outlook para iOS y Android

- El complemento De mensaje de informe no está disponible para buzones en organizaciones de Exchange locales.

- Puede configurar los mensajes notificados para que se copien o redirijan a un buzón que especifique. Para obtener más información, consulta [Directivas de envío de usuarios.](user-submission.md)

- El explorador web existente debe funcionar con el complemento Mensaje de informe. Pero, si observa que el complemento no está disponible o no funciona como se esperaba, pruebe con un explorador diferente.

- Para las instalaciones organizativas, la organización debe configurarse para usar la autenticación de OAuth. Para obtener más información, vea Determinar si la implementación centralizada de complementos [funciona para su organización.](../../admin/manage/centralized-deployment-of-add-ins.md)

- Los administradores deben ser miembros del grupo de roles Administradores globales. Para más información, consulte [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).

## <a name="get-the-report-message-add-in-for-yourself"></a>Obtener el complemento de mensaje de informe por sí mismo

1. Vaya a Microsoft AppSource en <https://appsource.microsoft.com/marketplace/apps> y busque el complemento Mensaje de informe. Para ir directamente al complemento Mensaje de informe, vaya a <https://appsource.microsoft.com/product/office/wa104381180> .

2. Haga **clic en OBTENER AHORA.**

   ![Mensaje de informe: obtenerlo ahora](../../media/ReportMessageGETITNOW.png)

3. En el cuadro de diálogo que aparece, revise los términos de uso y la directiva de privacidad y, a continuación, haga clic en **Continuar.**

4. Inicia sesión con tu cuenta de trabajo o escuela (para uso empresarial) o tu cuenta de Microsoft (para uso personal).

Después de instalar y habilitar el complemento, verá los siguientes iconos:

- En Outlook, el icono tiene este aspecto:

  ![Icono de complemento de mensaje de informe para Outlook](../../media/OutlookReportMessageIcon.png)

- En Outlook en la Web, el icono tiene este aspecto:

  ![Icono de complemento de mensaje de informe de Outlook en la web](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

Para obtener información sobre cómo usar el complemento, vea Usar el complemento De [mensaje de informe.](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a>Obtener y habilitar el complemento De mensaje de informe para su organización

> [!NOTE]
> El complemento puede tardar hasta 12 horas en aparecer en la organización.

1. In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> , If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the Integrated **apps** page.

2. Seleccione **Implementar complemento en** la parte superior de la página y, a continuación, seleccione **Siguiente**.

   ![Página servicios y complementos en el Centro de administración de Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. En el **menú desplegable Implementar** un nuevo complemento que aparece, revise la información y, a continuación, haga clic en **Siguiente.**

4. En la página siguiente, haga clic **en Elegir en la Tienda.**

   ![Implementar una nueva página de complemento](../../media/NewAddInScreen2.png)

5. En la **página Seleccionar complemento** que aparece, haga clic en el cuadro De búsqueda, escriba Mensaje de informe y, a continuación, haga clic en el icono    ![ Buscar. ](../../media/search-icon.png) En la lista de resultados, busque **Mensaje de** informe y, a continuación, haga clic **en Agregar**.

   ![Seleccionar resultados de búsqueda de complementos](../../media/NewAddInScreen3.png)

6. En el cuadro de diálogo que aparece, revise la información de licencia y privacidad y, a continuación, haga clic **en Continuar.**

7. En la **página Configurar complemento que** aparece, configure las siguientes opciones:

   - **Usuarios asignados:** seleccione uno de los siguientes valores:

     - **Todos** (predeterminado)
     - **Usuarios o grupos específicos**
     - **Sólo yo**

   - **Método de implementación:** seleccione uno de los siguientes valores:

     - **Corregido (predeterminado):** el complemento se implementa automáticamente en los usuarios especificados y no pueden quitarlo.
     - **Disponible:** los usuarios pueden instalar el complemento en **Inicio** \> **Obtener complementos** \> **administrados por el administrador.**
     - **Opcional:** el complemento se implementa automáticamente en los usuarios especificados, pero pueden elegir quitarlo.

   ![Configurar la página del complemento](../../media/configure-add-in.png)

   Cuando haya terminado, haga clic en **Implementar.**

8. En la **página Implementar mensaje de** informe que aparece, verá un informe de progreso seguido de una confirmación de que el complemento se implementó. Después de leer la información, haga clic **en Siguiente**.

   ![Página Implementar mensaje de informe](../../media/deploy-report-message-page.png)

9. En la **página Anunciar complemento que** aparece, revise la información y, a continuación, haga clic en **Cerrar**.

   ![Anunciar página de complemento](../../media/announce-add-in-page.png)

## <a name="learn-how-to-use-the-report-message-add-in"></a>Obtenga información sobre cómo usar el complemento Mensaje de informe

Las personas que tengan asignado el complemento verán los siguientes iconos:

- En Outlook, el icono tiene este aspecto:

  ![Icono de complemento de mensaje de informe para Outlook](../../media/OutlookReportMessageIcon.png)

- En Outlook en la Web, el icono tiene este aspecto:

  ![Icono de complemento de mensaje de informe de Outlook en la Web](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

Cuando notifique a los usuarios sobre el complemento Mensaje de informe, incluya un vínculo para [Usar el complemento Mensaje de informe.](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a>Revisar o editar la configuración del complemento Mensaje de informe

1. In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> , If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the Integrated **apps** page.

   ![Servicios y Add-Ins página en el nuevo Centro de administración de Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. Busque y seleccione el **complemento Mensaje** de informe.

3. En el **control desplegable Editar mensaje** de informe que aparece, revise y edite la configuración según corresponda a su organización. Cuando haya terminado, haga clic en **Guardar**.

   ![Configuración del complemento De mensaje de informe](../../media/EditReportMessageAddIn.png)

## <a name="view-and-review-reported-messages"></a>Ver y revisar los mensajes notificados

Para revisar los mensajes que los usuarios envían a Microsoft, tiene estas opciones:

- Usa el portal de envíos de administrador. Para obtener más información, vea [Ver envíos de usuario a Microsoft.](admin-submission.md#view-user-submissions-to-microsoft)

- Cree una regla de flujo de correo (también conocida como regla de transporte) para enviar copias de los mensajes notificados. Para obtener instrucciones, consulte Usar reglas de flujo de correo para ver lo que los [usuarios están informando a Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).
