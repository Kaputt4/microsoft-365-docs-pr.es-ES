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
description: Los administradores pueden aprender a crear reglas de flujo de correo (reglas de transporte) para cifrar y descifrar mensajes con cifrado de mensajes de Office 365.
ms.openlocfilehash: 73cb642de38a29aeeb0e49e0a792970d9820c4d2
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007386"
---
# <a name="define-mail-flow-rules-to-encrypt-email-messages"></a>Definir reglas de flujo de correo para cifrar mensajes de correo electrónico

Como administrador que administra Exchange Online, puede crear reglas de flujo de correo (también conocidas como reglas de transporte) para ayudar a proteger los mensajes de correo electrónico que envíe y reciba. Puede configurar reglas para cifrar los mensajes de correo electrónico salientes y quitar el cifrado de los mensajes cifrados procedentes de dentro de la organización o de las respuestas a los mensajes cifrados enviados desde su organización. Puede usar el Centro de administración de Exchange (EAC) o Exchange Online PowerShell para crear estas reglas. Además de las reglas de cifrado generales, puede habilitar o deshabilitar opciones de cifrado de mensajes individuales para los usuarios finales.

No puede cifrar el correo entrante de remitentes externos a su organización.

Si ha migrado recientemente de Active Directory RMS a Azure Information Protection, deberá revisar las reglas de flujo de correo existentes para asegurarse de que siguen funcionando en el nuevo entorno. Además, si desea aprovechar las nuevas funcionalidades de cifrado de mensajes (OME) de Office 365 disponibles a través de Azure Information Protection, debe actualizar las reglas de flujo de correo existentes. De lo contrario, los usuarios seguirán recibiendo correo cifrado que usa el formato de datos adjuntos HTML anterior en lugar de la nueva experiencia de OME sin problemas. Si aún no ha configurado OME, consulte Configurar nuevas funcionalidades de cifrado de mensajes [de Office 365](set-up-new-message-encryption-capabilities.md) para obtener información.

Para obtener información acerca de los componentes que hacen las reglas de flujo de correo y cómo funcionan las reglas de flujo de correo, vea Reglas de flujo de correo (reglas de [transporte) en Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules). Para obtener información adicional sobre cómo funcionan las reglas de flujo de correo con Azure Information Protection, vea [Configuring Exchange Online mail flow rules for Azure Information Protection labels](/azure/information-protection/deploy-use/configure-exo-rules).

> [!IMPORTANT]
> Para entornos híbridos de Exchange, los usuarios locales pueden enviar y recibir correo cifrado con OME solo si el correo electrónico se enruta a través de Exchange Online. Para configurar OME en un entorno híbrido [](/Exchange/exchange-hybrid) de Exchange, primero debe configurar híbrido mediante el Asistente para configuración híbrida y, a continuación, configurar el correo para que fluya desde [Office 365](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-1-configure-mail-to-flow-from-office-365-to-your-on-premises-email-server) al servidor de correo electrónico y configurar el correo para que fluya desde el servidor de correo electrónico a [Office 365](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365). Una vez que haya configurado el correo para que fluya a través de Office 365, puede configurar las reglas de flujo de correo para OME mediante esta guía.

## <a name="create-mail-flow-rules-to-encrypt-email-messages-with-the-new-ome-capabilities"></a>Crear reglas de flujo de correo para cifrar mensajes de correo electrónico con las nuevas funcionalidades de OME

Puede definir reglas de flujo de correo para desencadenar el cifrado de mensajes con las nuevas funcionalidades de OME mediante el EAC.

### <a name="use-the-eac-to-create-a-rule-for-encrypting-email-messages-with-the-new-ome-capabilities"></a>Usar el EAC para crear una regla para cifrar mensajes de correo electrónico con las nuevas funcionalidades de OME

1. En un explorador web, con una cuenta laboral o educativa a la que se han concedido permisos de administrador global, [inicie sesión en Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Elija el **icono** Administrador.

3. En el Centro de administración de Microsoft 365, elija **Centros de administración** \> **exchange**.

4. En el EAC, vaya a **Flujo de correo** \> **Reglas** y **seleccione Nuevo** icono Nuevo ![ Crear una nueva ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **regla**. Para obtener más información acerca del uso del EAC, vea [Centro de administración de Exchange en Exchange Online](/exchange/exchange-admin-center).

5. En **Nombre**, escriba un nombre para la regla, como Cifrar correo para DrToniRamos@hotmail.com.

6. En **Aplicar esta regla si**, seleccione una condición y escriba un valor si es necesario. Por ejemplo, para cifrar mensajes que van a DrToniRamos@hotmail.com:

   1. En **Aplicar esta regla si**, seleccione el destinatario **es**.

   2. Seleccione un nombre existente de la lista de contactos o escriba una nueva dirección de correo electrónico en la **casilla nombres.**

      - Para seleccionar un nombre existente, selecciónelo en la lista y, a continuación, haga clic en **Aceptar**.

      - Para escribir un nuevo nombre, escriba una dirección de correo electrónico en la casilla **nombres** y, a continuación, seleccione **nombres de casilla** \> **Aceptar**.

7. Para agregar más condiciones, elija **Más opciones y,** a continuación, **elija Agregar condición** y seleccione en la lista.

   Por ejemplo, para aplicar la regla solo si  el destinatario está fuera de la organización, seleccione agregar condición y, a continuación, seleccione El destinatario es **externo/interno** Fuera de \> **la organización** \> **Aceptar**.

8. Para habilitar el cifrado con las nuevas funcionalidades  de OME, en Hacer lo **siguiente,** seleccione Modificar la seguridad del mensaje y, a continuación, elija Aplicar cifrado de mensajes de **Office 365 y** protección de derechos. Seleccione una plantilla RMS de la lista, elija **Guardar** y, a continuación, elija **Aceptar**.
  
  La lista de plantillas incluye todas las plantillas y opciones predeterminadas, así como todas las plantillas personalizadas que haya creado para su uso por Office 365. Si la lista está vacía, asegúrese de configurar el cifrado de mensajes de Office 365 con las nuevas funcionalidades, tal como se describe en Configurar nuevas capacidades de cifrado de mensajes de [Office 365.](set-up-new-message-encryption-capabilities.md) Para obtener información sobre las plantillas predeterminadas, vea [Configuring and managing templates for Azure Information Protection](/information-protection/deploy-use/configure-policy-templates). Para obtener información acerca **de la opción No** reenviar, vea Do Not Forward option for [emails](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). Para obtener información acerca de **la opción de solo cifrado,** vea [Encrypt-only option for emails](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).

  Puede elegir **agregar acción** si desea especificar otra acción.

### <a name="use-the-eac-to-update-an-existing-mail-flow-rule-to-use-the-new-ome-capabilities"></a>Usar el EAC para actualizar una regla de flujo de correo existente para usar las nuevas funcionalidades de OME

1. En un explorador web, con una cuenta laboral o educativa a la que se han concedido permisos de administrador global, [inicie sesión en Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Elija el **icono** Administrador.

3. En el Centro de administración de Microsoft 365, elija **Centros de administración** \> **exchange**.

4. En el EAC, vaya a **Flujo de correo** \> **Reglas**.

5. En la lista de reglas de flujo de correo, seleccione la regla que desea modificar para usar las nuevas funcionalidades de OME y, a continuación, elija **Editar** ![ icono Editar ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) .

6. Para habilitar el cifrado con las nuevas funcionalidades  de OME, en **Hacer** lo siguiente, elija Modificar la seguridad del mensaje y, a continuación, elija Aplicar cifrado de mensajes de **Office 365 y** protección de derechos. Seleccione una plantilla RMS de la lista, elija **Guardar** y, a continuación, elija **Aceptar**.

   La lista de plantillas incluye todas las plantillas y opciones predeterminadas, así como todas las plantillas personalizadas que haya creado para su uso por Office 365. Si la lista está vacía, asegúrese de configurar el cifrado de mensajes de Office 365 con las nuevas funcionalidades, tal como se describe en Configurar nuevas funcionalidades de cifrado de mensajes de [Office 365](set-up-new-message-encryption-capabilities.md)integradas en Azure Information Protection. Para obtener información sobre las plantillas predeterminadas, vea [Configuring and managing templates for Azure Information Protection](/information-protection/deploy-use/configure-policy-templates). Para obtener información acerca de la opción No reenviar, vea [Do Not Forward option for emails](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). Para obtener información acerca de la opción de solo cifrado, vea [Encrypt Only option for emails](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).

   Puede elegir **agregar acción** si desea especificar otra acción.

7. En la **lista Hacer lo siguiente,** quite las acciones asignadas a **Modificar** la seguridad del mensaje Aplicar la versión anterior \> **de OME**.

8. Seleccione **Guardar**.

## <a name="create-mail-flow-rules-to-remove-encryption-for-email-messages-with-the-new-ome-capabilities"></a>Crear reglas de flujo de correo para quitar el cifrado de mensajes de correo electrónico con las nuevas funcionalidades de OME

Puede definir reglas de flujo de correo para desencadenar la eliminación del cifrado de mensajes con las nuevas funcionalidades de OME mediante el EAC.

### <a name="use-the-eac-to-create-a-rule-to-remove-encryption-from-email-messages-with-the-new-ome-capabilities"></a>Usar el EAC para crear una regla para quitar el cifrado de los mensajes de correo electrónico con las nuevas funcionalidades de OME

Puede quitar el cifrado al que su organización tiene acceso. Esto significa cualquier correo con cifrado aplicado por la organización o cualquier correo protegido con restricciones de solo cifrado.

1. En un explorador web, con una cuenta laboral o educativa a la que se han concedido permisos de administrador global, [inicie sesión en Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Elija el **icono** Administrador.

3. En el Centro de administración de Microsoft 365, elija **Centros de administración** \> **exchange**.

4. En el EAC, vaya a **Flujo de correo** \> **Reglas** y **seleccione Nuevo** icono Nuevo ![ Crear una nueva ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **regla**. Para obtener más información acerca del uso del EAC, vea [Centro de administración de Exchange en Exchange Online](/exchange/exchange-admin-center).

5. En **Nombre**, escriba un nombre para la regla, como Quitar cifrado del correo saliente.

6. En **Aplicar esta regla si**, seleccione las condiciones en las que se debe quitar el cifrado de los mensajes. Agregar **El remitente se encuentra dentro** de la organización para enviar correo \>  _o_ El destinatario **se encuentra** dentro de la \> **organización** para recibir correo.

7. En **Hacer lo siguiente,** seleccione **Modificar la seguridad del** mensaje Quitar el cifrado de mensajes de Office \> **365 y la protección de derechos**.

8. Seleccione **Guardar**.

## <a name="create-mail-flow-rules-for-office-365-message-encryption-without-the-new-capabilities"></a>Crear reglas de flujo de correo para cifrado de mensajes de Office 365 sin las nuevas funcionalidades

Si aún no ha movido su organización a las nuevas funcionalidades de OME, Microsoft recomienda que realice un plan para pasar a las nuevas funcionalidades de OME tan pronto como sea razonable para su organización. Para obtener instrucciones, vea [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md). De lo contrario, vea [Defining mail flow rules for Office 365 Message Encryption that don't use the new OME capabilities](legacy-information-for-message-encryption.md#defining-mail-flow-rules-for-office-365-message-encryption-that-dont-use-the-new-ome-capabilities).

## <a name="related-topics"></a>Temas relacionados

[Cifrado en Office 365](encryption.md)

[Configurar las nuevas capacidades de cifrado de mensajes de Office 365](set-up-new-message-encryption-capabilities.md)

[Agregar personalización de marca a los mensajes cifrados](add-your-organization-brand-to-encrypted-messages.md)

[Reglas de flujo de correo (reglas de transporte) en Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
