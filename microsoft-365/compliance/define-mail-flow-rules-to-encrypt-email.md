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
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 9b7daf19-d5f2-415b-bc43-a0f5f4a585e8
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a crear reglas de flujo de correo (reglas de transporte) para cifrar y descifrar mensajes mediante el cifrado de mensajes de Office 365.
ms.openlocfilehash: 28486f601a79e294550bbceb48ad57069024fd5a
ms.sourcegitcommit: ae3aa7f29be16d08950cf23cad489bc069aa8617
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2020
ms.locfileid: "48408610"
---
# <a name="define-mail-flow-rules-to-encrypt-email-messages"></a>Definir reglas de flujo de correo para cifrar mensajes de correo electrónico

Como administrador global, puede crear reglas de flujo de correo (también conocidas como reglas de transporte) para ayudar a proteger los mensajes de correo electrónico que envíe y reciba. Puede configurar reglas para cifrar los mensajes de correo electrónico salientes y quitar el cifrado de los mensajes cifrados que provengan de la organización o de las respuestas a los mensajes cifrados que se envían desde la organización. Puede usar el centro de administración de Exchange (EAC) o Exchange Online PowerShell para crear estas reglas. Además de las reglas de cifrado generales, puede habilitar o deshabilitar opciones de cifrado de mensajes individuales para los usuarios finales.

No se puede cifrar el correo entrante de remitentes externos a la organización.

Si migró recientemente de Active Directory RMS a Azure Information Protection, deberá revisar sus reglas de flujo de correo existentes para asegurarse de que siguen funcionando en su nuevo entorno. Además, si desea aprovechar las nuevas capacidades de cifrado de mensajes de Office 365 (OME) disponibles a través de Azure Information Protection, debe actualizar las reglas de flujo de correo existentes. De lo contrario, los usuarios seguirán recibiendo correo cifrado que usa el formato de datos adjuntos HTML anterior en lugar de la nueva experiencia de OME sin problemas. Si todavía no ha configurado OME, vea [configurar las nuevas capacidades de cifrado de mensajes de Office 365](set-up-new-message-encryption-capabilities.md) para obtener información.

Para obtener información sobre los componentes que conforman las reglas de flujo de correo y cómo funcionan las reglas de flujo de correo, consulte [reglas de flujo de correo (reglas de transporte) en Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules). Para obtener más información acerca de cómo funcionan las reglas de flujo de correo con Azure Information Protection, consulte [configuración de reglas de flujo de correo de Exchange Online para las etiquetas de Azure Information Protection](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-exo-rules).

> [!IMPORTANT]
> Para entornos híbridos de Exchange, los usuarios locales pueden enviar y recibir correo cifrado usando OME solo si el correo electrónico se enruta a través de Exchange Online. Para configurar OME en un entorno híbrido de Exchange, primero debe [configurar un híbrido mediante el Asistente para la configuración híbrida](https://docs.microsoft.com/Exchange/exchange-hybrid) y, a continuación, [configurar el correo para que fluya desde Office 365 al servidor de correo electrónico](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-1-configure-mail-to-flow-from-office-365-to-your-on-premises-email-server) y [Configure el correo para que fluya desde su servidor de correo electrónico hacia Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365). Una vez que haya configurado el correo para que fluya a través de Office 365, puede configurar las reglas de flujo de correo para OME mediante esta guía.

## <a name="create-mail-flow-rules-to-encrypt-email-messages-with-the-new-ome-capabilities"></a>Crear reglas de flujo de correo para cifrar los mensajes de correo electrónico con las nuevas funciones de OME

Puede definir reglas de flujo de correo para desencadenar el cifrado de mensajes con las nuevas capacidades de OME mediante el EAC.

### <a name="use-the-eac-to-create-a-rule-for-encrypting-email-messages-with-the-new-ome-capabilities"></a>Usar el EAC para crear una regla para cifrar mensajes de correo electrónico con las nuevas funciones de OME

1. En un explorador Web, con una cuenta profesional o educativa a la que se le han concedido permisos de administrador global, [inicie sesión en Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Elija el icono **Administración** .

3. En el centro de administración de Microsoft 365, elija centro de **Administración** , \> **Exchange**.

4. En el EAC, vaya a reglas de **flujo de correo** \> **Rules** y seleccione **nuevo** icono nuevo para ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **crear una nueva regla**. Para obtener más información acerca del uso de EAC, consulte [centro de administración de Exchange en Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).

5. En **nombre**, escriba un nombre para la regla, como cifrar correo para DrToniRamos@hotmail.com.

6. En **aplicar esta regla si**, seleccione una condición y escriba un valor si es necesario. Por ejemplo, para cifrar los mensajes dirigidos a DrToniRamos@hotmail.com:

   1. En **aplicar esta regla si**, seleccione **el destinatario es**.

   2. Seleccione un nombre existente de la lista de contactos o escriba una nueva dirección de correo electrónico en el cuadro **Comprobar nombres** .

      - Para seleccionar un nombre existente, selecciónelo en la lista y, a continuación, haga clic en **Aceptar**.

      - Para escribir un nuevo nombre, escriba una dirección de correo electrónico en el cuadro **Comprobar nombres** y, a continuación, seleccione **Comprobar nombres** \> **correctos**.

7. Para agregar más condiciones, elija **más opciones** y, a continuación, elija **Agregar condición** y seleccione en la lista.

   Por ejemplo, para aplicar la regla solo si el destinatario está fuera de la organización, seleccione **Agregar condición** y, a continuación, seleccione **el destinatario es externo o interno** \> **fuera de la organización** \> **OK**.

8. Para habilitar el cifrado con las nuevas capacidades de OME, desde **haga lo siguiente**, seleccione **modificar la seguridad de los mensajes** y, a continuación, elija **aplicar el cifrado de mensajes de Office 365 y la protección de derechos**. Seleccione una plantilla RMS de la lista, elija **Guardar**y, después, haga clic en **Aceptar**.
  
  La lista de plantillas incluye todas las plantillas y opciones predeterminadas, así como las plantillas personalizadas que haya creado para su uso por parte de Office 365. Si la lista está vacía, asegúrese de haber configurado el cifrado de mensajes de Office 365 con las nuevas funciones, tal como se describe en [set up New Office 365 Message Encryption Capabilities](set-up-new-message-encryption-capabilities.md). Para obtener información sobre las plantillas predeterminadas, vea [Configuring and Managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). Para obtener información sobre la opción no **reenviar** , vea la [opción no reenviar para los correos electrónicos](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). Para obtener información sobre la opción **solo cifrar** , vea la [opción cifrar solo para los correos electrónicos](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).

  Puede elegir **Agregar acción** si desea especificar otra acción.

### <a name="use-the-eac-to-update-an-existing-mail-flow-rule-to-use-the-new-ome-capabilities"></a>Usar el EAC para actualizar una regla de flujo de correo existente para usar las nuevas funciones de OME

1. En un explorador Web, con una cuenta profesional o educativa a la que se le han concedido permisos de administrador global, [inicie sesión en Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Elija el icono **Administración** .

3. En el centro de administración de Microsoft 365, elija centro de **Administración** , \> **Exchange**.

4. En el EAC, vaya a **Flujo de correo** \> **Reglas**.

5. En la lista de reglas de flujo de correo, seleccione la regla que desea modificar para usar las nuevas funciones de OME y, a continuación, elija **Editar** ![ icono Editar ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) .

6. Para habilitar el cifrado con las nuevas capacidades de OME, desde **haga lo siguiente**, elija **modificar la seguridad de los mensajes** y, a continuación, elija **aplicar el cifrado de mensajes de Office 365 y la protección de derechos**. Seleccione una plantilla RMS de la lista, elija **Guardar** y, a continuación, elija **Aceptar**.

   La lista de plantillas incluye todas las plantillas y opciones predeterminadas, así como las plantillas personalizadas que haya creado para su uso por parte de Office 365. Si la lista está vacía, asegúrese de haber configurado el cifrado de mensajes de Office 365 con las nuevas funciones, tal y como se describe en [configurar nuevas capacidades de cifrado de mensajes de office 365 que se basan en Azure Information Protection](set-up-new-message-encryption-capabilities.md). Para obtener información sobre las plantillas predeterminadas, vea [Configuring and Managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). Para obtener información sobre la opción no **reenviar** , vea la [opción no reenviar para los correos electrónicos](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). Para obtener información sobre la opción **solo cifrar** , vea la [opción cifrar solo para los correos electrónicos](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).

   Puede elegir **Agregar acción** si desea especificar otra acción.

7. En la **siguiente** lista, quite las acciones asignadas para **modificar la seguridad** de los mensajes, \> **aplique la versión anterior de OME**.

8. Seleccione **Guardar**.

## <a name="create-mail-flow-rules-to-remove-encryption-for-outgoing-email-messages-with-the-new-ome-capabilities"></a>Crear reglas de flujo de correo para quitar el cifrado de los mensajes de correo electrónico salientes con las nuevas capacidades de OME

Puede definir reglas de flujo de correo para desencadenar la eliminación de cifrado de mensajes con las nuevas capacidades de OME mediante el EAC.

### <a name="use-the-eac-to-create-a-rule-to-remove-encryption-from-email-messages-with-the-new-ome-capabilities"></a>Usar el EAC para crear una regla para quitar el cifrado de los mensajes de correo electrónico con las nuevas capacidades de OME

1. En un explorador Web, con una cuenta profesional o educativa a la que se le han concedido permisos de administrador global, [inicie sesión en Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Elija el icono **Administración** .

3. En el centro de administración de Microsoft 365, elija centro de **Administración** , \> **Exchange**.

4. En el EAC, vaya a reglas de **flujo de correo** \> **Rules** y seleccione **nuevo** icono nuevo para ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **crear una nueva regla**. Para obtener más información acerca del uso de EAC, consulte [centro de administración de Exchange en Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).

5. En **nombre**, escriba un nombre para la regla, como quitar el cifrado del correo saliente.

6. En **aplicar esta regla si**, seleccione las condiciones en las que se debe quitar el cifrado de los mensajes. Add **el remitente se encuentra** \> **dentro de la organización**. Ahora, agregue condiciones adicionales para dirigirse a destinatarios específicos, como **el destinatario está ubicado** \> **fuera de la organización**.

7. En **hacer lo siguiente**, seleccione **modificar la seguridad de los mensajes** , \> **quitar el cifrado de mensajes de Office 365 y la protección de derechos**.

8. Seleccione **Guardar**.

## <a name="create-mail-flow-rules-for-office-365-message-encryption-without-the-new-capabilities"></a>Crear reglas de flujo de correo para el cifrado de mensajes de Office 365 sin las nuevas funciones

Si todavía no ha movido su organización a las nuevas capacidades de OME, Microsoft recomienda que cree un plan para cambiar las nuevas funciones de OME en cuanto sea razonable para su organización. Para obtener instrucciones, vea [configurar las nuevas funciones de cifrado de mensajes de Office 365 basadas en Azure Information Protection](set-up-new-message-encryption-capabilities.md). De lo contrario, vea [definir reglas de flujo de correo para el cifrado de mensajes de Office 365 que no usan las nuevas funciones de OME](legacy-information-for-message-encryption.md#defining-mail-flow-rules-for-office-365-message-encryption-that-dont-use-the-new-ome-capabilities).

## <a name="related-topics"></a>Temas relacionados

[Cifrado en Office 365](encryption.md)

[Configurar las nuevas capacidades de cifrado de mensajes de Office 365](set-up-new-message-encryption-capabilities.md)

[Agregar personalización de marca a los mensajes cifrados](add-your-organization-brand-to-encrypted-messages.md)

[Reglas de flujo de correo (reglas de transporte) en Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=506707)

[Reglas de flujo de correo (reglas de transporte) en Exchange Online Protection](https://go.microsoft.com/fwlink/p/?LinkId=506708)
