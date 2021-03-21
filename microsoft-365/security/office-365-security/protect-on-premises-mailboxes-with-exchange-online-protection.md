---
title: Proteger los buzones locales en China con EOP independiente
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- GEU150
- GMA150
- GPA150
- MET150
ms.assetid: c5e95951-da67-4ec7-92c5-982abd477e69
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Los administradores de China que usan Office 365 operado por 21Vianet pueden aprender a usar Exchange Online Protection (EOP) independiente para proteger sus buzones locales.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4258d64721fc2042297bb15eaeecafa90dcf4bc1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929293"
---
# <a name="protect-on-premises-mailboxes-in-china-with-standalone-eop"></a>Proteger los buzones locales en China con EOP independiente

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Este artículo solo se aplica a Office 365 operado por 21Vianet en China.

Incluso si planea hospedar algunos o todos los buzones locales, puede proteger los buzones con Exchange Online Protection (EOP). Para configurar conectores, la cuenta debe ser un administrador global o un administrador de la compañía de Exchange (el grupo de roles Administración de la organización). Para obtener información sobre cómo se relacionan los permisos de Office 365 con los permisos de Exchange, vea Asignar roles de administrador en [Office 365 operado por 21Vianet](../../admin/add-users/assign-admin-roles.md?preserve-view=true&view=o365-21vianet). Si todos los buzones de Exchange son locales, siga estos pasos para configurar el servicio EOP.

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>Paso 1: Usar el Centro de administración de Microsoft 365 para agregar y comprobar el dominio

1. En el Centro de administración de Microsoft 365, vaya a Configuración para agregar el dominio al servicio.

2. Siga los pasos del portal para agregar los registros DNS aplicables al proveedor de hospedaje DNS para comprobar la propiedad del dominio.

> [!TIP]
> Agregar el dominio y los usuarios a Office 365 operado por [21Vianet](../../admin/setup/add-domain.md?preserve-view=true&view=o365-21vianet) y Crear registros DNS para [Office 365](../../admin/services-in-china/create-dns-records-when-you-manage-your-dns-records.md?preserve-view=true&view=o365-21vianet) cuando administre los registros DNS son recursos útiles a los que hacer referencia al agregar el dominio al servicio y configurar DNS.

### <a name="step-2-add-recipients-and-configure-the-domain-type"></a>Paso 2: Agregar destinatarios y configurar el tipo de dominio

Antes de configurar el correo que circula hacia y desde el servicio EOP, se recomienda agregar los destinatarios al servicio. Hay varias maneras de hacerlo, tal y como se documenta en [Administrar usuarios de correo en EOP](manage-mail-users-in-eop.md). Además, si quiere habilitar el Bloqueo perimetral basado en directorios (DBEB) para aplicar la comprobación de destinatarios dentro del servicio después de agregarlos, debe establecer el tipo de dominio en Autoritativo. Para obtener más información acerca de DBEB, vea [Use Directory Based Edge Blocking to reject messages sent to invalid recipients](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>Paso 3: Usar el EAC para configurar el flujo de correo

Cree conectores en el Centro de administración de Exchange (EAC) que permitan el flujo de correo entre EOP y los servidores de correo locales. Para obtener instrucciones detalladas, vea [Configure mail flow using connectors in Office 365](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

 ¿Cómo sabe si esta tarea funcionó?

 Consulte [Probar el flujo de correo validando los conectores de Office 365](/exchange/mail-flow-best-practices/test-mail-flow).

## <a name="step-4-allow-inbound-port-25-smtp-access"></a>Paso 4: Permitir el acceso SMTP entrante al puerto 25

Después de configurar los conectores, espere 72 horas para que las actualizaciones de los registros DNS se propaguen. A continuación, restrinja el tráfico SMTP de puerto entrante 25 en el firewall o los servidores de correo para que acepte correo solo desde los centros de datos de EOP, específicamente de las direcciones IP enumeradas en direcciones URL e intervalos de direcciones IP para [Office 365](../../enterprise/managing-office-365-endpoints.md). Esto protege su entorno local al limitar el ámbito de los mensajes entrantes que puede recibir. Además, si tiene una configuración en su servidor de correo que controla las direcciones IP que se pueden conectar para retransmitir correo, actualice también esta configuración.

> [!TIP]
> Establezca la configuración en el servidor SMTP con un tiempo de espera de conexión de 60 segundos. La mayoría de las situaciones aceptan esta configuración, lo que permite algo de retraso en el caso de un mensaje enviado con datos adjuntos muy grandes, por ejemplo.

## <a name="step-5-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>Paso 5: Asegurarse de que el correo no deseado se enruta a la carpeta de correo no deseado de cada usuario

Para asegurarse de que el correo no deseado se enrute correctamente a la carpeta de correo no deseado de cada usuario, debe realizar varios pasos de configuración. Los pasos se proporcionan en [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). Si no desea mover mensajes a la carpeta correo no deseado de cada usuario, puede elegir otra acción editando las directivas contra correo no deseado (también conocidas como directivas de filtro de contenido). Para obtener más información, consulte [Configurar directivas contra correo electrónico no deseado en Office 365 ](configure-your-spam-filter-policies.md).

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>Paso 6: Usar el Centro de administración de Microsoft 365 para apuntar el registro MX a EOP

Siga los pasos de configuración de dominio de Office 365 para actualizar el registro MX de su dominio de forma que el correo entrante pase por EOP. Para obtener más información, puede volver a hacer referencia [a Crear registros DNS para Office 365 al administrar los registros DNS](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md?preserve-view=true&view=o365-21vianet).

¿Cómo sabe si esta tarea funcionó?

 Consulte [Probar el flujo de correo validando los conectores de Office 365](/exchange/mail-flow-best-practices/test-mail-flow).

En este punto, ha comprobado la entrega del servicio para un conector local saliente configurado correctamente, y ha comprobado que su registro MX apunta a EOP. Ahora puede elegir ejecutar las siguientes pruebas adicionales para comprobar que un correo electrónico se entregará correctamente por el servicio a su entorno local:

- En Remote Connectivity Analyzer, haga clic en la pestaña **Office 365** y ejecute la prueba **Correo SMTP entrante** situada en **Pruebas de correo de Internet**.

- Envíe un mensaje de correo desde cualquier cuenta de correo electrónico basada en web a un destinatario de correo de su organización cuyo dominio coincida con el dominio que agregó al servicio. Confirme la entrega del mensaje al buzón de correo local mediante Microsoft Outlook u otro cliente de correo electrónico.

- Si quiere ejecutar una prueba de correo electrónico saliente, puede enviar un mensaje de correo electrónico de un usuario de su organización a una cuenta de correo electrónico basada en web y confirmar si se recibe el mensaje.

## <a name="less-common-a-hybrid-setup-with-mailboxes-on-premises-and-in-the-cloud"></a>Menos común: una configuración híbrida con buzones locales y en la nube

Si tiene buzones de Exchange locales y uno o varios buzones en la nube en Exchange Online, tiene una *configuración* híbrida. En una configuración híbrida, las características como el uso compartido de calendarios de disponibilidad y el enrutamiento de correo funcionan juntos en los entornos locales y en la nube. Es posible que tenga una configuración híbrida mientras realiza la transición de buzones a Exchange Online. Un entorno híbrido se configura de forma diferente que la protección independiente de EOP.

Puede elegir un escenario híbrido para aprovechar el correo electrónico basado en la nube para la mayoría de los empleados. Puede hacerlo al mismo tiempo que hospeda algunos buzones localmente; por ejemplo, para su departamento legal.

Una configuración híbrida puede ser compleja, pero tiene muchas ventajas. Para obtener más información sobre cómo configurar escenarios híbridos con Exchange, [vea Exchange Server implementaciones híbridas.](/Exchange/exchange-hybrid)