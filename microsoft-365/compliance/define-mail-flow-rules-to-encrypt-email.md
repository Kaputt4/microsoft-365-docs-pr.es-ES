---
title: Definir reglas de flujo de correo para cifrar mensajes de correo electrónico
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 9b7daf19-d5f2-415b-bc43-a0f5f4a585e8
ms.collection:
- purview-compliance
- tier2
ms.custom:
- admindeeplinkMAC
- admindeeplinkEXCHANGE
description: Los administradores pueden aprender a crear reglas de flujo de correo (reglas de transporte) para cifrar y descifrar mensajes mediante Cifrado de mensajes de Microsoft Purview.
ms.openlocfilehash: b244cd1847d46f80bd56ec5a9aec09eadc6781cd
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68620731"
---
# <a name="define-mail-flow-rules-to-encrypt-email-messages"></a>Definir reglas de flujo de correo para cifrar mensajes de correo electrónico

Como administrador que administra Exchange Online, puede crear reglas de flujo de correo (también conocidas como reglas de transporte) para ayudar a proteger los mensajes de correo electrónico que envía y recibe. Puede configurar reglas para cifrar los mensajes de correo electrónico salientes y quitar el cifrado de los mensajes cifrados procedentes de dentro de la organización o de las respuestas a los mensajes cifrados enviados desde la organización. Puede usar el <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange (EAC)</a> o Exchange Online PowerShell para crear estas reglas. Además de las reglas de cifrado generales, puede habilitar o deshabilitar opciones de cifrado de mensajes individuales para los usuarios finales.

No puede cifrar el correo entrante de remitentes fuera de la organización.

Si ha migrado recientemente de Active Directory RMS a Azure Information Protection, deberá revisar las reglas de flujo de correo existentes para asegurarse de que siguen funcionando en el nuevo entorno. Además, para usar Cifrado de mensajes de Microsoft Purview con Azure Information Protection, debe actualizar las reglas de flujo de correo existentes. De lo contrario, los usuarios seguirán recibiendo correo cifrado que usa el formato de datos adjuntos HTML anterior en lugar de la nueva experiencia sin problemas. Si aún no ha configurado el cifrado de mensajes, consulte [Configuración de Cifrado de mensajes de Microsoft Purview](set-up-new-message-encryption-capabilities.md) para obtener información.

Para obtener información sobre los componentes que componen las reglas de flujo de correo y cómo funcionan las reglas de flujo de correo, consulte Reglas de flujo de correo [(reglas de transporte) en Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules). Para obtener información adicional sobre cómo funcionan las reglas de flujo de correo con Azure Information Protection, consulte [Configuración de Exchange Online reglas de flujo de correo para etiquetas de Azure Information Protection](/azure/information-protection/deploy-use/configure-exo-rules).

> [!IMPORTANT]
> En el caso de los entornos híbridos de Exchange, los usuarios locales pueden enviar y recibir correo cifrado mediante el cifrado de mensajes solo si el correo electrónico se enruta a través de Exchange Online. Para configurar el cifrado de mensajes en un entorno de Exchange híbrido, primero debe [configurar el híbrido mediante el Asistente para configuración híbrida](/Exchange/exchange-hybrid) y, a continuación, [configurar el correo para que fluya desde Office 365 al servidor de correo electrónico](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-1-configure-mail-to-flow-from-office-365-to-your-on-premises-email-server) y [configurar el correo para que fluya desde el servidor de correo electrónico a Office 365](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365). Una vez que haya configurado el correo para que fluya a través de Office 365, puede configurar reglas de flujo de correo para el cifrado de mensajes mediante esta guía.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="create-mail-flow-rules-to-encrypt-email-messages-with-microsoft-purview-message-encryption"></a>Creación de reglas de flujo de correo para cifrar mensajes de correo electrónico con Cifrado de mensajes de Microsoft Purview

Puede definir reglas de flujo de correo para desencadenar el cifrado de mensajes con mediante el EAC.

### <a name="use-the-eac-to-create-a-rule-for-encrypting-email-messages-with-microsoft-purview-message-encryption"></a>Use el EAC para crear una regla para cifrar mensajes de correo electrónico con Cifrado de mensajes de Microsoft Purview

1. En un explorador web, con una cuenta profesional o educativa a la que se hayan concedido permisos de administrador global, [inicie sesión en Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Elija el **icono Administración**.

3. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a>, elija **Administración centros** \> **de Exchange**.

4. En el EAC, vaya a **Reglas** de **flujo** \> de correo y seleccione **Nuevo** ![icono nuevo.](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \>**Cree una nueva regla**. Para obtener más información sobre el uso del EAC, vea [Centro de administración de Exchange en Exchange Online](/exchange/exchange-admin-center).

5. En **Nombre**, escriba un nombre para la regla, como Cifrar correo para DrToniRamos@hotmail.com.

6. En **Aplicar esta regla si**, seleccione una condición y escriba un valor si es necesario. Por ejemplo, para cifrar los mensajes que van a DrToniRamos@hotmail.com:

   1. En **Aplicar esta regla si**, seleccione **el destinatario.**

   2. Seleccione un nombre existente en la lista de contactos o escriba una nueva dirección de correo electrónico en la casilla **nombres** .

      - Para seleccionar un nombre existente, selecciónelo en la lista y haga clic en **Aceptar**.

      - Para escribir un nombre nuevo, escriba una dirección de correo electrónico en la casilla **de verificación nombres** y, a continuación, active **los nombres** \> **correctos**.

7. Para agregar más condiciones, elija **Más opciones** y, a continuación, elija **Agregar condición** y seleccione en la lista.

   Por ejemplo, para aplicar la regla solo si el destinatario está fuera de su organización, seleccione **Agregar condición** y, a continuación, seleccione **El destinatario es externo o interno** \> **Fuera de la organización** \> **Aceptar**.

8. Para habilitar el cifrado de mensajes, en **Haga lo siguiente**, seleccione **Modificar la seguridad del mensaje** y, a continuación, elija **Aplicar Office 365 cifrado de mensajes y protección de derechos**. Seleccione una plantilla de RMS en la lista, elija **Guardar** y, a continuación, elija **Aceptar**.
  
  La lista de plantillas incluye todas las plantillas y opciones predeterminadas, así como las plantillas personalizadas que haya creado para su uso por Office 365. Si la lista está vacía, asegúrese de que ha configurado Cifrado de mensajes de Microsoft Purview como se describe en [Configuración de Cifrado de mensajes de Microsoft Purview](set-up-new-message-encryption-capabilities.md). Para obtener información sobre las plantillas predeterminadas, consulte [Configuración y administración de plantillas para Azure Information Protection](/information-protection/deploy-use/configure-policy-templates). Para obtener información sobre la opción **No reenviar** , vea [No reenviar opción para correos electrónicos](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). Para obtener información sobre la opción **de solo cifrado** , consulte [Opción de solo cifrado para correos electrónicos](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).

  Puede elegir **agregar acción** si desea especificar otra acción.

### <a name="use-the-eac-to-update-an-existing-mail-flow-rule-to-use-microsoft-purview-message-encryption"></a>Use el EAC para actualizar una regla de flujo de correo existente para usar Cifrado de mensajes de Microsoft Purview

1. En un explorador web, con una cuenta profesional o educativa a la que se hayan concedido permisos de administrador global, [inicie sesión en Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Elija el **icono Administración**.

3. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a>, elija **Administración centros** \> **de Exchange**.

4. En el EAC, vaya a **Flujo de correo** \> **Reglas**.

5. En la lista de reglas de flujo de correo, seleccione la regla que desea modificar para usarla con Cifrado de mensajes de Microsoft Purview y, a continuación, elija **Editar icono Editar**![.](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)

6. Para habilitar el cifrado mediante Cifrado de mensajes de Microsoft Purview, en **Haga lo siguiente**, elija **Modificar la seguridad del mensaje** y, a continuación, elija **Aplicar Office 365 cifrado de mensajes y protección de derechos**. Seleccione una plantilla rms de la lista, elija **Guardar** y, a continuación, elija **Aceptar**.

   La lista de plantillas incluye todas las plantillas y opciones predeterminadas, así como las plantillas personalizadas que haya creado para su uso por Office 365. Si la lista está vacía, asegúrese de que ha configurado Cifrado de mensajes de Microsoft Purview como se describe en [Configuración de Cifrado de mensajes de Microsoft Purview](set-up-new-message-encryption-capabilities.md). Para obtener información sobre las plantillas predeterminadas, consulte [Configuración y administración de plantillas para Azure Information Protection](/information-protection/deploy-use/configure-policy-templates). Para obtener información sobre la opción No reenviar, vea [No reenviar opción para correos electrónicos](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). Para obtener información sobre la opción de solo cifrado, vea [Opción Cifrar solo para correos electrónicos](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).

   Puede elegir **agregar acción** si desea especificar otra acción.

7. En la lista **Haga lo siguiente** , quite las acciones que se asignan a **Modificar la seguridad** \> del mensaje **Aplique la versión anterior de OME**.

8. Seleccione **Guardar**.

## <a name="create-mail-flow-rules-to-remove-encryption-for-email-messages-with-microsoft-purview-message-encryption"></a>Creación de reglas de flujo de correo para quitar el cifrado de mensajes de correo electrónico con Cifrado de mensajes de Microsoft Purview

Puede definir reglas de flujo de correo para quitar el cifrado de mensajes con Cifrado de mensajes de Microsoft Purview mediante el EAC.

### <a name="use-the-eac-to-create-a-rule-to-remove-encryption-from-email-messages-with-microsoft-purview-message-encryption"></a>Use el EAC para crear una regla para quitar el cifrado de los mensajes de correo electrónico con Cifrado de mensajes de Microsoft Purview

Puede quitar el cifrado de los mensajes aplicados por su organización. También puede quitar el cifrado de los datos adjuntos cifrados para asegurarse de que todo el mensaje de correo electrónico no tiene ninguna protección.

1. En un explorador web, con una cuenta profesional o educativa a la que se hayan concedido permisos de administrador global, [inicie sesión en Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Elija el **icono Administración**.

3. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a>, elija **Administración centros** \> **de Exchange**.

4. En el EAC, vaya a **Reglas** de **flujo** \> de correo y seleccione **Nuevo** ![icono nuevo.](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \>**Cree una nueva regla**. Para obtener más información sobre el uso del EAC, vea [Centro de administración de Exchange en Exchange Online](/exchange/exchange-admin-center).

5. En **Nombre**, escriba un nombre para la regla, como `Remove encryption from outgoing mail`.

6. En **Aplicar esta regla si**, seleccione las condiciones en las que se debe quitar el cifrado de los mensajes. Agregar **El remitente se encuentra** \> **dentro de la organización** para enviar correo _o_ **El destinatario se encuentra** \> **dentro de la organización** para recibir correo.

7. En **Hacer lo siguiente**, seleccione **Modificar la seguridad** \> del mensaje **Quitar Office 365 cifrado de mensajes y protección de derechos aplicada por la organización**.

8. (Opcional) En **Hacer lo siguiente**, seleccione **Modificar la seguridad** \> del mensaje Quitar protección de **derechos de datos adjuntos aplicada por la organización**.

Guarde la regla.

## <a name="create-mail-flow-rules-for-office-365-message-encryption-without-microsoft-purview-message-encryption"></a>Creación de reglas de flujo de correo para Office 365 cifrado de mensajes sin Cifrado de mensajes de Microsoft Purview

Si aún no ha movido su organización a Cifrado de mensajes de Microsoft Purview, Microsoft recomienda que realice un plan para moverse tan pronto como sea razonable para su organización. Para obtener instrucciones, consulte [Configuración de Cifrado de mensajes de Microsoft Purview](set-up-new-message-encryption-capabilities.md). De lo contrario, consulte [Definición de reglas de flujo de correo para Office 365 cifrado de mensajes que no usan Cifrado de mensajes de Microsoft Purview](legacy-information-for-message-encryption.md#defining-mail-flow-rules-for-office-365-message-encryption-that-dont-use-microsoft-purview-message-encryption).

## <a name="related-content"></a>Contenido relacionado

[Cifrado en Office 365](encryption.md)

[Configurar el cifrado de mensajes de Microsoft Purview](set-up-new-message-encryption-capabilities.md)

[Agregar personalización de marca a los mensajes cifrados](add-your-organization-brand-to-encrypted-messages.md)

[Reglas de flujo de correo (reglas de transporte) en Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
