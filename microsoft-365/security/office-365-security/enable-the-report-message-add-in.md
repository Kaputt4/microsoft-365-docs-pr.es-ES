---
title: Habilitar el complemento Notificar mensajes
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo habilitar el complemento de mensajes de informe para Outlook y Outlook en la web, para usuarios individuales o para toda la organización.
ms.openlocfilehash: 2e9d6ae87d0f6da7721c5c86d904a836d4610a5e
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196614"
---
# <a name="enable-the-report-message-add-in"></a>Habilitar el complemento Notificar mensajes

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Si es administrador de una organización de Microsoft 365 con buzones de correo de Exchange Online, le recomendamos que use el portal de envíos del centro de seguridad & cumplimiento. Para obtener más información, vea [usar el envío de administración para enviar un correo no deseado, phish, direcciones URL y archivos sospechosos a Microsoft](admin-submission.md).

El complemento de mensajes de informe para Outlook y Outlook en la web (anteriormente conocido como Outlook Web App) permite a los usuarios informar fácilmente de falsos positivos (correo electrónico bueno marcado como malo) o falsos negativos (se permite correo electrónico erróneo) para Microsoft y sus filiales para el análisis. Microsoft usa estos envíos para mejorar la eficacia de las tecnologías de protección de correo electrónico.

Por ejemplo, supongamos que las personas están notificando una gran cantidad de mensajes como suplantación de identidad. Esta información se Surfaces en el [Panel de seguridad](security-dashboard.md) y otros informes. El equipo de seguridad de su organización puede usar esta información como indicación de que es posible que sea necesario actualizar las directivas antiphishing. O bien, si los usuarios notifican un gran número de mensajes que se marcaron como correo no deseado mediante el complemento de mensajes de informe, es posible que el equipo de seguridad de la organización deba ajustar [las directivas contra correo no deseado](configure-your-spam-filter-policies.md).

Además, si su organización usa [Office 365 Advanced Threat Protection Plan 1](office-365-atp.md) o [plan 2](office-365-ti.md), el complemento de mensajes de informe proporciona al equipo de seguridad de su organización información útil que puede usar para revisar y actualizar las directivas de seguridad.

Los administradores pueden habilitar el complemento de mensajes de informe para la organización y los usuarios individuales pueden instalarlo por sí mismos.

Si es un usuario individual, puede [Habilitar el complemento de mensajes de informe para usted mismo](#get-the-report-message-add-in-for-yourself).

Si es administrador global o administrador de Exchange Online y Exchange está configurado para usar la autenticación OAuth, puede [Habilitar el complemento de mensajes de informe para su organización](#get-and-enable-the-report-message-add-in-for-your-organization). El complemento de mensajes de informe ahora está disponible a través de la [implementación centralizada](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

- El complemento de mensajes de informe funciona con la mayoría de las suscripciones de Microsoft 365 y los productos siguientes:

  - Outlook en la Web
  - Outlook 2013 SP1 o posterior
  - Outlook 2016 para Mac
  - Outlook incluido con las aplicaciones de Microsoft 365 para empresas

- El complemento de mensajes de informe no está disponible para los buzones de la organización de Exchange local.

- Puede configurar los mensajes notificados para que se copien o redirijan a un buzón de correo que especifique. Para obtener más información, vea [especificar un buzón para los envíos de usuarios de correo no deseado y mensajes de suplantación de identidad en Exchange Online](user-submission.md).

- El explorador Web existente debe funcionar con el complemento de mensajes de informe. Pero, si observa que el complemento no está disponible o no funciona como se esperaba, pruebe con otro explorador.

- Para las instalaciones organizativas, la organización debe estar configurada para usar la autenticación OAuth. Para obtener más información, vea [determinar si la implementación centralizada de complementos funciona para su organización](../../admin/manage/centralized-deployment-of-add-ins.md).

- Los administradores deben ser miembros del grupo de roles de administradores globales. Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).

## <a name="get-the-report-message-add-in-for-yourself"></a>Obtener el complemento de mensajes de informe para usted mismo

1. Vaya a Microsoft AppSource en <https://appsource.microsoft.com/marketplace/apps> y busque el complemento de mensajes de informe. Para ir directamente al complemento de mensajes de informe, vaya a <https://appsource.microsoft.com/product/office/wa104381180> .

2. Haga clic en **obtener ahora**.

   ![Mensaje de informe: obtenerlo ahora](../../media/ReportMessageGETITNOW.png)

3. En el cuadro de diálogo que aparece, revise las condiciones de uso y la Directiva de privacidad y, a continuación, haga clic en **continuar**.

4. Inicie sesión con su cuenta profesional o educativa (para uso empresarial) o su cuenta Microsoft (para uso personal).

Una vez instalado y habilitado el complemento, verá los iconos siguientes:

- En Outlook, el icono tiene el siguiente aspecto:

  ![Icono del complemento de mensajes de informe para Outlook](../../media/OutlookReportMessageIcon.png)

- En Outlook en la web, el icono tiene el siguiente aspecto:

  ![Icono del complemento de mensaje de informe de Outlook en la web](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

Para obtener información sobre cómo usar el complemento, vea [usar el complemento de mensajes de informe](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a>Obtener y habilitar el complemento de mensajes de informe para la organización

> [!NOTE]
> El complemento puede tardar hasta 12 horas en aparecer en la organización.

1. En el centro de administración de Microsoft 365, vaya a la página **servicios & complementos** en <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns> y, a continuación, haga clic en **implementar complemento**.

   ![Página servicios y complementos en el centro de administración de Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. En el control flotante **implementar un nuevo complemento** que aparece, revise la información y, a continuación, haga clic en **siguiente**.

3. En la página siguiente, haga clic en **elegir en la tienda**.

   ![Implementar una nueva página de complemento](../../media/NewAddInScreen2.png)

4. En la página **seleccionar complemento** que aparece, haga clic en el cuadro de **búsqueda** , escriba **mensaje de informe**y, a continuación, haga clic en buscar en el icono de **Search** ![ búsqueda ](../../media/search-icon.png) . En la lista de resultados, buscar **mensaje de informe** y, a continuación, haga clic en **Agregar**.

   ![Seleccionar resultados de la búsqueda de complementos](../../media/NewAddInScreen3.png)

5. En el cuadro de diálogo que aparece, revise la información de licencias y privacidad y, a continuación, haga clic en **continuar**.

6. En la página **configurar complemento** que aparece, configure las opciones siguientes:

   - **Usuarios asignados**: Seleccione uno de los siguientes valores:

     - **Todos** (predeterminado)
     - **Usuarios o grupos específicos**
     - **Sólo yo**

   - **Método de implementación**: Seleccione uno de los siguientes valores:

     - **Fijo (predeterminado)**: el complemento se implementa automáticamente en los usuarios especificados y no puede quitarlo.
     - **Disponible**: los usuarios pueden instalar el complemento en **casa** \> **obtener complementos** \> **administrados por el administrador**.
     - **Opcional**: el complemento se implementa automáticamente para los usuarios especificados, pero puede elegir quitarlo.

   ![Página de configuración del complemento](../../media/configure-add-in.png)

   Cuando haya terminado, haga clic en **implementar**.

7. En la página **implementar mensaje de informe** que aparece, verá un informe de progreso seguido de una confirmación de que se ha implementado el complemento. Una vez que haya leído la información, haga clic en **siguiente**.

   ![Página implementar mensaje de informe](../../media/deploy-report-message-page.png)

8. En la página **anunciar complemento** que aparece, revise la información y, a continuación, haga clic en **cerrar**.

   ![Página de complementos de anuncio](../../media/announce-add-in-page.png)

## <a name="learn-how-to-use-the-report-message-add-in"></a>Obtener información sobre cómo usar el complemento de mensajes de informe

Los usuarios que tengan el complemento asignado verán los iconos siguientes:

- En Outlook, el icono tiene el siguiente aspecto:

  ![Icono del complemento de mensajes de informe para Outlook](../../media/OutlookReportMessageIcon.png)

- En Outlook en la web, el icono tiene el siguiente aspecto:

  ![Icono del complemento de mensaje de informe de Outlook en la web](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

Cuando notifique a los usuarios sobre el complemento de mensajes de informe, incluya un vínculo para [usar el complemento de mensajes de informe](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a>Revisión o edición de la configuración del complemento de mensajes de informe

1. En el centro de administración de Microsoft 365, vaya a la página **servicios & complementos** en <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns> .

   ![Página servicios y complementos en el nuevo centro de administración de Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. Busque y seleccione el complemento de **mensajes de informe** .

3. En el control flotante de **mensaje de informe de edición** que aparece, revise y edite las opciones según corresponda para su organización. Cuando haya terminado, haga clic en **Guardar**.

   ![Configuración del complemento de mensajes de informe](../../media/EditReportMessageAddIn.png)

## <a name="view-and-review-reported-messages"></a>Ver y revisar los mensajes notificados

Para revisar los mensajes que los usuarios notifican a Microsoft, tiene estas opciones:

- Usar el portal de envíos de administración. Para obtener más información, vea [Ver envíos de usuarios a Microsoft](admin-submission.md#view-user-submissions-to-microsoft).

- Crear una regla de flujo de correo (también denominada regla de transporte) para enviar copias de mensajes enviados. Para obtener instrucciones, vea [usar reglas de flujo de correo para ver qué están notificando los usuarios a Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).
