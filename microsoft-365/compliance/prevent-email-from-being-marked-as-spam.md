---
title: Cómo evitar los falsos positivos en Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Obtenga información sobre cómo evitar los falsos positivos y evitar que el correo electrónico deseado se marque como no deseado en Office 365.
ms.openlocfilehash: 3c7c2c8b3a66c940612a28d54d847a1c273abe6e
ms.sourcegitcommit: 18b5f6e9913147cea911c0fd347fcd880fb86f17
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2019
ms.locfileid: "37167136"
---
# <a name="how-to-prevent-real-email-from-being-marked-as-spam-in-office-365"></a>Evitar que el correo electrónico real se marque como correo no deseado en Office 365

 **¿Se está marcando el correo electrónico real como correo no deseado en Office 365? Siga este procedimiento.**

Si recibe un falso positivo, debe informar del mensaje a Microsoft mediante el [complemento de mensaje de informe](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2). Además, puede enviar el mensaje con [el explorador de envíos](/security/office-365-security/admin-submission.md).

## <a name="determine-the-reason-why-the-message-was-marked-as-spam"></a>Determinar el motivo por el que un mensaje se marcó como correo no deseado

Muchos de los problemas relacionados con el correo no deseado en Office 365 pueden solucionarse si se [analizan los encabezados de mensaje de correo electrónico](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c) y se determina cuál fue el problema. Deberá buscar un encabezado llamado X-Forefront-Antispam-Report. Obtenga más información sobre los [encabezados de mensaje contra correo no deseado](https://technet.microsoft.com/library/dn205071%28v=exchg.150%29.aspx).

En el encabezado, busque los siguientes encabezados y valores.

### <a name="x-forefront-antispam-report"></a>X-Forefront-Antispam-Report

- **SFV:SPM**: Indica que el mensaje se marcó como correo no deseado por el filtro contra correo no deseado EOP.

- **SFV:BLK**: Indica que el mensaje se marcó como correo no deseado porque la dirección de envío se encuentra en la lista de remitentes bloqueados del destinatario.

- **SFV:SKS**: Indica que el mensaje se marcó como correo no deseado antes de que se aplicara el filtro de contenido. Esto podría incluir una regla de flujo de correo (también conocida como una regla de transporte) que marque el mensaje como correo no deseado. Ejecute un seguimiento de mensajes para comprobar si se activó una regla de flujo de correo que pueda haber establecido un nivel de confianza elevado contra correo no deseado (SCL).

- **SFV:SKB**: Indica que el mensaje se marcó como correo no deseado porque coincidía con una lista de bloqueados en la directiva de filtro contra correo no deseado.

- **SFV:BULK**: Indica que el valor del nivel de quejas de correo masivo (BCL), ubicado en el encabezado x-microsoft-antispam, supera el umbral de correo masivo que se estableció para el filtro de contenido. El correo masivo son correos electrónicos a los que puede que se suscribieran los usuarios, pero siguen siendo correo no deseado. En el encabezado del mensaje, busque la propiedad del nivel de confianza en masa (BCL) en el encabezado X-Microsoft-Antispam. Si el valor de BCL es inferior al umbral establecido en el filtro de correo no deseado, puede ajustar el umbral para, en su lugar, marcar estos tipos de mensajes masivos como correo no deseado. Los usuarios tienen distintas tolerancias y preferencias sobre [cómo administrar el correo masivo](https://docs.microsoft.com/microsoft-365/security/office-365-security/bulk-complaint-level-values). Puede crear distintas directivas o reglas para diferentes preferencias de usuario.

- **CAT:SPOOF** o **CAT:PHISH**: Indican que el ﻿mensaje parece suplantado, lo que significa que el origen del mensaje no se puede validar y podría ser sospechoso. Si es válido, el remitente tendrá que asegurarse de que posee una configuración correcta de SPF y DKIM. Para obtener más información, consulte el encabezado Authentication-Results. Aunque puede resultar complicado conseguir que todos los remitentes usen métodos de autenticación de correo electrónico adecuados, omitir estas comprobaciones puede ser muy peligroso y es una de las principales causas de las amenazas.

### <a name="x-customspam"></a>X-CustomSpam

- La presencia de este encabezado indica que el mensaje se marcó como correo no deseado porque una de las [opciones avanzadas contra correo no deseado está habilitada](https://technet.microsoft.com/library/jj200750%28v=exchg.150%29.aspx) en el filtro de correo no deseado. A menos que necesite estas características, le recomendamos que use la configuración predeterminada.

## <a name="solutions-to-additional-causes-of-too-much-spam"></a>Soluciones para otras causas de recibir demasiado correo no deseado

Para funcionar correctamente, Exchange Online Protection (EOP) necesita que los administradores completen algunas tareas. Si no es el administrador de su espacio empresarial de Office 365 y recibe demasiado correo no deseado, le recomendamos que trabaje con su administrador en relación con estas tareas. De lo contrario, puede ir directamente a la sección para usuarios.

### <a name="for-admins"></a>Para administradores

- **Apuntar los registros DNS a Office 365**: Para que EOP pueda ofrecer protección, los registros DNS del agente de intercambio de correo (MX) de todos los dominios tienen que apuntar a Office 365 de manera exclusiva. Si el registro MX no apunta a Office 365, EOP no filtrará el correo no deseado de los usuarios. Si quiere usar otro servicio o aplicación para filtrar el correo no deseado en su dominio, puede deshabilitar la protección contra correo no deseado en EOP. Para hacerlo, cree una regla de flujo de correo que establezca el valor de SCL en -1. Si más tarde decide usar EOP, asegúrese de quitar esta regla de flujo de correo.

- **Activar el complemento de denuncia de mensajes para los usuarios**: Es muy recomendable que [habilite el complemento de denuncia de mensajes para los usuarios](/security/office-365-security/enable-the-report-message-add-in.md).

- **Usar [el explorador de envíos](/security/office-365-security/admin-submission.md)**: Ahora los administradores pueden enviar mensajes de correo electrónico con el ID de mensaje de red o archivo, las direcciones URL y los archivos para que Microsoft pueda analizarlos en Office 365. Como administrador, también puede ver los comentarios que envían los usuarios y usar patrones para ajustar las opciones de configuración que pueden causar problemas.

- **Asegúrese de que sus usuarios se encuentran dentro de los límites permitidos** para enviar y recibir correos electrónicos, como se muestra [aquí](https://docs.microsoft.com/es-ES/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).

- **Vuelva a comprobar los niveles de quejas** tal como se especifica [aquí](/security/office-365-security/bulk-complaint-level-values.md).

### <a name="for-users"></a>Para usuarios

- **Crear una lista de remitentes seguros**: Los usuarios pueden agregar direcciones de remitentes de confianza a su lista de remitentes seguros en [Outlook](https://go.microsoft.com/fwlink/p/?LinkId=270065) o [Outlook en la Web](https://go.microsoft.com/fwlink/p/?LinkId=294862) (anteriormente denominada Outlook Web App). Para empezar en Outlook en la Web, elija **Configuración**![ConfigureAPowerBIAnalysisServicesConnector_settingsIcon](media/24bd5467-c8d2-4936-9c37-a179bd0e21ec.png) \> **Opciones** \> **Bloquear o permitir**. El siguiente diagrama muestra un ejemplo de cómo agregar algo a una lista de remitentes seguros.

![Agregar un remitente de confianza en Outlook en la Web](media/8de6b24e-429e-4e8f-8ce8-53ba659cbfcb.png)

EOP respetará los remitentes y destinatarios seguros de los usuarios, pero no los dominios seguros. Esto ocurre independientemente de si el dominio se agrega a través de Outlook en la Web o mediante Outlook, y si se sincroniza después con la Sincronización de directorios.

- **Deshabilitar el filtro SmartScreen en Outlook**: Si usa el cliente para equipo de escritorio de Outlook, tendrá que deshabilitar la función de filtro SmartScreen, que se considera descontinuada. Si está habilitada, puede causar falsos positivos. Esto no es necesario si se ejecuta una versión actualizada del cliente de Outlook para equipo de escritorio.

## <a name="troubleshooting-a-message-ends-up-in-the-junk-folder-even-though-eop-marked-the-message-as-non-spam"></a>Solución de problemas: Un mensaje acaba en la carpeta de correo no deseado aunque EOP lo haya marcado como correo deseado

Si los usuarios tienen habilitada la opción de Outlook "Solo listas seguras: solo correo de personas o dominios de la lista de remitentes seguros o de la lista de destinatarios seguros se enviará a la Bandeja de entrada", todo el correo electrónico se enviará a la carpeta de correo no deseado a menos que el remitente esté incluido en la lista de remitentes seguros del destinatario. Esto ocurre independientemente de si EOP marca un mensaje como no deseado o si ha configurado una regla en EOP para marcar un mensaje como correo deseado.

También puede deshabilitar la opción Solo listas seguras para los usuarios de Outlook siguiendo las instrucciones en [Outlook: configuración de directiva para deshabilitar la interfaz de usuario de correo electrónico no deseado y el mecanismo de filtrado](https://support.microsoft.com/es-ES/kb/2180568).

Si ve el mensaje en Outlook en la Web, habrá un aviso de seguridad amarillo que indica que el mensaje está en la carpeta de correo no deseado porque el remitente no está en la lista de remitentes seguros del destinatario.

Si observa el encabezado de un mensaje, es posible que incluya la marca SFV:SKN (direcciones IP o ETR permitidas) o SFV:NSPM (correo deseado), pero, aun así, el mensaje llegue a la carpeta de correo no deseado del usuario. No hay nada en el encabezado del mensaje que indique que el usuario tiene habilitada la opción "Solo listas seguras". Esto ocurre porque dicha opción, configurada por los usuarios de Outlook, anula la configuración de EOP.

### <a name="to-verify-why-a-message-from-a-safe-sender-is-marked-as-non-spam-in-the-message-header-but-still-ends-up-in-the-users-junk-folder"></a>Cómo comprobar por qué un mensaje de un remitente seguro se marca como correo deseado en el encabezado del mensaje y, aun así, termina en la carpeta de correo no deseado del usuario

1. Para más información sobre cómo conectarse a Exchange Online PowerShell, vea [Conectarse a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).

2. Ejecute el siguiente comando para ver la configuración de correo no deseado del usuario:

  ```Powershell
  Get-MailboxJunkEmailConfiguration example@contoso.com | Format-List TrustedListsOnly,ContactsTrusted,TrustedSendersAndDomains
  ```

- Si TrustedListsOnly es True, significa que esta configuración está habilitada.

- Si ContactsTrusted es True, significa que el usuario confía en los contactos y en los remitentes seguros.

- TrustedSendersAndDomains enumera el contenido de la lista de remitentes seguros del usuario.

## <a name="eop-only-customers-use-directory-synchronization"></a>Solo clientes de EOP: uso de la sincronización de directorios

Si es un cliente de EOP, es decir, se suscribe al servicio de EOP para su uso con el servidor de correo local (Exchange), se recomienda sincronizar la configuración de usuario con el servicio mediante la sincronización de directorios. Esto garantiza que EOP respete las listas de remitentes seguros. Para obtener más información, consulte "Usar sincronización de directorios para administrar usuarios de correo" en [Administrar usuarios de correo en EOP](https://go.microsoft.com/fwlink/?LinkId=534098).
