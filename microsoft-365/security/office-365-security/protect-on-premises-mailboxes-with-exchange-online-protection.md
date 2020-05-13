---
title: Proteger buzones locales en China con EOP independiente
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
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
description: Los administradores de China con Office 365 operado por 21Vianet pueden aprender a usar independiente de Exchange Online Protection (EOP) para proteger sus buzones locales.
ms.openlocfilehash: 6ce85e626f9bf4c960de57ad5cd15ac3148954cb
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208299"
---
# <a name="protect-on-premises-mailboxes-in-china-with-standalone-eop"></a>Proteger buzones locales en China con EOP independiente

> [!NOTE]
> Este artículo solo se aplica a Office 365 operado por 21Vianet en China.

Incluso si planea hospedar algunos o todos los buzones de correo locales, aún puede proteger los buzones con Exchange Online Protection (EOP). Para configurar conectores, la cuenta debe ser un administrador global o un administrador de la compañía de Exchange (el grupo de roles de administración de la organización). Para obtener información sobre cómo se relacionan los permisos de Office 365 con los permisos de Exchange, consulte [asignación de roles de administrador en Office 365 operado por 21Vianet](https://docs.microsoft.com/office365/admin/add-users/assign-admin-roles?&view=o365-21vianet). Si todos los buzones de Exchange son locales, siga estos pasos para configurar el servicio de EOP.

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>Paso 1: usar el centro de administración de Microsoft 365 para agregar y comprobar el dominio

1. En el centro de administración de Microsoft 365, vaya a configuración para agregar el dominio al servicio.

2. Siga los pasos del portal para agregar los registros DNS aplicables a su proveedor de host DNS para comprobar la propiedad del dominio.

> [!TIP]
> [Agregue el dominio y los usuarios a office 365 operado por 21Vianet](https://docs.microsoft.com/office365/admin/setup/add-domain?&view=o365-21vianet) y [cree registros dns para Office 365 cuando administre los registros DNS](https://docs.microsoft.com/office365/admin/services-in-china/create-dns-records-when-you-manage-your-dns-records?&view=o365-21vianet) son recursos útiles para hacer referencia a medida que agrega el dominio al servicio y configura el DNS.

### <a name="step-2-add-recipients-and-configure-the-domain-type"></a>Paso 2: agregar destinatarios y configurar el tipo de dominio

Antes de configurar el correo que circula hacia y desde el servicio EOP, se recomienda agregar los destinatarios al servicio. Hay varias maneras de hacerlo, tal y como se documenta en [Administrar usuarios de correo en EOP](manage-mail-users-in-eop.md). Además, si quiere habilitar el Bloqueo perimetral basado en directorios (DBEB) para aplicar la comprobación de destinatarios dentro del servicio después de agregarlos, debe establecer el tipo de dominio en Autoritativo. Para obtener más información sobre DBEB, consulte [usar bloqueo perimetral basado en directorios para rechazar mensajes enviados a destinatarios no válidos](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>Paso 3: Usar el EAC para configurar el flujo de correo

Cree conectores en el Centro de administración de Exchange (EAC) que permitan el flujo de correo entre EOP y los servidores de correo locales. Para obtener instrucciones detalladas, consulte [Configure mail Flow Using Connectors in Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

 ¿Cómo sabe si esta tarea funcionó?

 Consulte [probar el flujo de correo mediante la validación de los conectores de 365 de Office](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow).

## <a name="step-4-allow-inbound-port-25-smtp-access"></a>Paso 4: Permitir el acceso SMTP entrante al puerto 25

Después de configurar los conectores, espere 72 horas para que las actualizaciones de los registros DNS se propaguen. A continuación, restrinja el tráfico SMTP de entrada-25 entrante en el firewall o los servidores de correo para aceptar correo solo de los centros de recursos de EOP, específicamente de las direcciones IP que aparecen en [direcciones URL e intervalos de direcciones IP para Office 365](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints). Esto protege su entorno local al limitar el ámbito de los mensajes entrantes que puede recibir. Además, si tiene una configuración en su servidor de correo que controla las direcciones IP que se pueden conectar para retransmitir correo, actualice también esta configuración.

> [!TIP]
> Establezca la configuración en el servidor SMTP con un tiempo de espera de conexión de 60 segundos. La mayoría de las situaciones aceptan esta configuración, lo que permite algo de retraso en el caso de un mensaje enviado con datos adjuntos muy grandes, por ejemplo.

## <a name="step-5-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>Paso 5: asegurarse de que el correo no deseado se enruta a la carpeta de correo electrónico no deseado de cada usuario

Para asegurarse de que el correo no deseado se enrute correctamente a la carpeta de correo no deseado de cada usuario, debe realizar varios pasos de configuración. Los pasos se proporcionan en [Configure Standalone EOP para entregar el correo no deseado a la carpeta de correo no deseado en entornos híbridos](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). Si no desea mover mensajes a la carpeta de correo no deseado de cada usuario, puede elegir otra acción Si edita sus directivas contra correo no deseado (también conocidas como directivas de filtro de contenido). Para obtener más información, consulte [Configurar directivas contra correo electrónico no deseado en Office 365 ](configure-your-spam-filter-policies.md).

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>Paso 6: usar el centro de administración de Microsoft 365 para apuntar el registro MX a EOP

Siga los pasos de configuración de dominio de Office 365 para actualizar el registro MX de su dominio de forma que el correo entrante pase por EOP. Para obtener más información, puede hacer referencia de nuevo a [crear registros DNS para Office 365 cuando administre los registros DNS](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

¿Cómo sabe si esta tarea funcionó?

 Consulte [probar el flujo de correo mediante la validación de los conectores de 365 de Office](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow).

En este punto, ha comprobado la entrega del servicio para un conector local saliente configurado correctamente, y ha comprobado que su registro MX apunta a EOP. Ahora puede elegir ejecutar las siguientes pruebas adicionales para comprobar que un correo electrónico se entregará correctamente por el servicio a su entorno local:

- En Remote Connectivity Analyzer, haga clic en la pestaña **Office 365** y ejecute la prueba **Correo SMTP entrante** situada en **Pruebas de correo de Internet**.

- Envíe un mensaje de correo desde cualquier cuenta de correo electrónico basada en web a un destinatario de correo de su organización cuyo dominio coincida con el dominio que agregó al servicio. Confirme la entrega del mensaje al buzón de correo local mediante Microsoft Outlook u otro cliente de correo electrónico.

- Si quiere ejecutar una prueba de correo electrónico saliente, puede enviar un mensaje de correo electrónico de un usuario de su organización a una cuenta de correo electrónico basada en web y confirmar si se recibe el mensaje.

## <a name="less-common-a-hybrid-setup-with-mailboxes-on-premises-and-in-the-cloud"></a>Menos común: una configuración híbrida con buzones de correo locales y en la nube

Si tiene buzones de Exchange local y uno o más buzones en la nube en Exchange Online, tiene una configuración *híbrida* . En una configuración híbrida, características como el uso compartido del calendario de disponibilidad y el enrutamiento de correo funcionan en conjunto en entornos locales y en la nube. Es posible que tenga una instalación híbrida en su ubicación mientras realiza la transición de los buzones a Exchange Online. Un entorno híbrido se configura de forma diferente a la protección independiente de EOP.

Puede elegir un escenario híbrido para aprovechar el correo electrónico basado en la nube para la mayoría de los empleados. Puede hacer esto mientras hospeda también algunos buzones de correo locales; por ejemplo, para el departamento legal.

Una configuración híbrida puede ser compleja, pero tiene muchas ventajas. Para obtener más información acerca de la configuración de escenarios híbridos con Exchange, vea [Exchange Server Hybrid Deployments](https://docs.microsoft.com/Exchange/exchange-hybrid).
