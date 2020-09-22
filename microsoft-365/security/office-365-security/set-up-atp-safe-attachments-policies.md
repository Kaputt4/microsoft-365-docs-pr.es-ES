---
title: Configurar las directivas de datos adjuntos seguros de Office 365 ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo definir directivas de datos adjuntos seguros para proteger a su organización de archivos malintencionados en el correo electrónico.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5f9f1a6cc250fdd336e48c19c6cb5d73e9a05800
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197228"
---
# <a name="set-up-office-365-atp-safe-attachments-policies"></a>Configurar las directivas de datos adjuntos seguros de Office 365 ATP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!IMPORTANT]
> Este artículo está destinado a los clientes empresariales que tienen la [Protección contra amenazas avanzada de Office 365](office-365-atp.md). Si es un usuario doméstico que busca información sobre datos adjuntos seguros en Outlook, consulte [Advanced Outlook.com Security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Los usuarios envían, reciben y comparten con regularidad datos adjuntos, como documentos, presentaciones, hojas de cálculo, etc. No siempre es fácil saber si los datos adjuntos son seguros o malintencionados solo mirando un mensaje de correo electrónico. Y lo último que desea es tener un dato malintencionado para llegar a través del cual se causan estragos en su organización. Afortunadamente, la [protección contra amenazas avanzada de Office 365](office-365-atp.md) (ATP) puede resultar útil. Puede configurar directivas de [datos adjuntos seguros de ATP](atp-safe-attachments.md) para ayudar a garantizar que su organización está protegida contra ataques de datos adjuntos de correo electrónico no seguro.

## <a name="what-to-do"></a>Qué hacer

1. Revisión de los requisitos previos

2. Configurar una directiva de datos adjuntos seguros de ATP

3. Obtener información sobre las opciones de directiva de datos adjuntos seguros de ATP

## <a name="step-1-review-the-prerequisites"></a>Paso 1: revisar los requisitos previos

- Asegúrese de que su organización tiene la [protección contra amenazas avanzada de Office 365](office-365-atp.md).

- Asegúrese de que tiene los permisos necesarios. Para definir (o editar) las directivas de ATP, debe tener asignado un rol de administración de organización de Exchange Online (el administrador global tiene asignado este rol de forma predeterminada) o los roles de administrador de seguridad y administración de la protección en línea de Exchange Online. Para obtener más información, vea la tabla siguiente:

  ****

  |Rol|Dónde y cómo se asigna|
  |---|---|
  |administrador global |La persona que se registra para comprar Microsoft 365 es un administrador global de forma predeterminada. (Para obtener más información, consulte [acerca de los roles de administrador de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) .)|
  |Administrador de seguridad |Centro de administración de Azure Active Directory ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )|
  |Administración de la organización de Exchange Online, administración de la protección de Exchange Online |Centro de administración de Exchange ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) <br>o <br>  Cmdlets de PowerShell (vea [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))|
  |

  Para obtener más información acerca de los roles y los permisos, consulte [permisos en el centro de seguridad y &amp; cumplimiento](permissions-in-the-security-and-compliance-center.md).

- [Obtenga información sobre las opciones de directiva de datos adjuntos seguros de ATP](#step-3-learn-about-atp-safe-attachments-policy-options) (en este artículo). Algunas opciones, como las opciones supervisar o reemplazar, pueden dar lugar a un retraso de correo electrónico menor mientras se analizan los datos adjuntos. Para evitar retrasos en los mensajes, considere la posibilidad de usar la [entrega dinámica y la vista previa](dynamic-delivery-and-previewing.md).

- Espere hasta 30 minutos para que la directiva nueva o actualizada se extienda a todos los centros de recursos de Microsoft 365.

## <a name="step-2-set-up-or-edit-an-atp-safe-attachments-policy"></a>Paso 2: configurar (o editar) una directiva de datos adjuntos seguros de ATP

1. Vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión con su cuenta profesional o educativa.

2. En el panel de navegación izquierdo del centro de seguridad y cumplimiento, en &amp; **Administración de amenazas**, elija **Policy** \> **datos adjuntos seguros**de directiva.

3. Si ve la opción **Activar ATP para SharePoint, OneDrive y Microsoft Teams**, le recomendamos que seleccione esta opción. Esto permitirá la [protección contra amenazas avanzada de Office 365 para SharePoint, OneDrive y Microsoft Teams](atp-for-spo-odb-and-teams.md) para su entorno de Microsoft 365.

4. Elija **nuevo** (el botón nuevo es similar a un signo más ( **+** )) para comenzar a crear la Directiva.

5. Especifique el nombre, la descripción y la configuración de la Directiva.<br/><br/>**Ejemplo:** Para configurar una directiva denominada "sin demoras" que entregue inmediatamente los mensajes de todos los usuarios y vuelva a adjuntar los datos adjuntos después de su examen, puede especificar la siguiente configuración:

   - En el cuadro **nombre** , escriba sin retrasos.

   - En el cuadro **Descripción** , escriba una descripción como, entrega los mensajes inmediatamente y vuelve a adjuntar los datos adjuntos después del análisis.

   - En la sección respuesta, elija la opción de **entrega dinámica** . ([Obtenga más información sobre la vista previa y la entrega dinámica con datos adjuntos seguros de ATP](dynamic-delivery-and-previewing.md)).

   - En la sección **redirigir datos adjuntos** , seleccione la opción Habilitar redirección y escriba la dirección de correo electrónico del administrador global, el administrador de seguridad o el analista de seguridad que investigará los datos adjuntos malintencionados.

   - En la sección **aplicado a** , elija **el dominio del destinatario es**y, a continuación, seleccione su dominio. Elija **Agregar**y, después, haga clic en **Aceptar**.

6. Seleccione **Guardar**.

Considere la posibilidad de configurar varias directivas de datos adjuntos seguros de ATP para su organización. Estas directivas se aplicarán en el orden en que aparezcan en la página de **datos adjuntos seguros de ATP** . Una vez definida o modificada una directiva, permita al menos 30 minutos para que las directivas entren en vigor en los centros de recursos de Microsoft.

## <a name="step-3-learn-about-atp-safe-attachments-policy-options"></a>Paso 3: información sobre las opciones de directiva de datos adjuntos seguros de ATP

A medida que configure las directivas de datos adjuntos seguros de ATP, podrá elegir entre varias opciones, como monitor, bloqueo, reemplazo, entrega dinámica, etc. En caso de que se haya preguntado sobre lo que hacen estas opciones, en la tabla siguiente se resumen cada uno de ellos y su efecto.

****

|Opción|Efecto|Se usa cuando se desea:|
|---|---|---|
|**Desactivar**|No analiza los datos adjuntos en busca de malware  <br/> No retrasa la entrega de mensajes|Desactivar el análisis para los destinatarios seleccionados.  <br/> Evitar retrasos innecesarios en el correo interno de enrutamiento.  <br/> **Esta opción no se recomienda para la mayoría de los usuarios. Solo debe usar esta opción para desactivar el examen de datos adjuntos seguros de ATP para los destinatarios que solo reciben mensajes de correo electrónico de remitentes de confianza.**|
|**Monitor**|Entrega los mensajes con datos adjuntos y, a continuación, realiza un seguimiento de lo que ocurre con malware detectado|Ver dónde se encuentra el malware detectado en su organización|
|**Desbloquear**|Impide que se prosigan los mensajes con datos adjuntos de malware detectados  <br/> Envía mensajes con malware detectado a [cuarentena en Office 365](manage-quarantined-messages-and-files.md) donde un administrador o Analista de seguridad puede revisar y liberar (o eliminar) dichos mensajes  <br/> Bloquea los mensajes y datos adjuntos futuros de forma automática|Proteger a su organización de ataques repetidos con los mismos datos adjuntos de malware|
|**Replace**|Quita los datos adjuntos de malware detectados  <br/> Notifica a los destinatarios que se han quitado datos adjuntos  <br/> Envía mensajes con malware detectado a [cuarentena en Office 365](manage-quarantined-messages-and-files.md) donde un administrador o Analista de seguridad puede revisar y liberar (o eliminar) dichos mensajes|Elevar la visibilidad a los destinatarios que los datos adjuntos se quitaron debido al malware detectado|
|**Entrega dinámica**|Entrega los mensajes inmediatamente  <br/> Reemplaza datos adjuntos con un archivo de marcador de posición hasta que se completa la búsqueda y, a continuación, vuelve a adjuntar los datos adjuntos si no se detecta malware  <br/> Incluye funciones de vista previa de datos adjuntos para la mayoría de los PDF y archivos de Office durante el examen  <br/> Envía mensajes con malware detectado a cuarentena donde un administrador o Analista de seguridad puede revisar y liberar (o eliminar) dichos mensajes  <br/> [Obtener información sobre la vista previa y la entrega dinámica con datos adjuntos seguros de ATP](dynamic-delivery-and-previewing.md) <br/> |Evitar retrasos en los mensajes al proteger a los destinatarios de archivos malintencionados  <br/> Permitir a los destinatarios obtener una vista previa de los datos adjuntos en modo seguro mientras se lleva a cabo el análisis|
|**Habilitar redireccionamiento**|Se aplica cuando se elige la opción supervisar, bloquear o reemplazar  <br/> Envía datos adjuntos a una dirección de correo electrónico especificada en la que los administradores o analistas de seguridad pueden investigar|Permitir que los administradores de seguridad y analistas investiguen datos adjuntos sospechosos|
|**Aplicar la selección anterior si el análisis de malware para archivos adjuntos se agota el tiempo de espera o se produce un error**|Aplica la acción configurada para datos adjuntos no seguros a los datos adjuntos que no se pueden analizar (debido a un tiempo de espera o un error)|
|

## <a name="next-steps"></a>Siguientes pasos

Una vez que se hayan implementado las directivas de datos adjuntos seguros de ATP, puede ver cómo está trabajando ATP para su organización consultando los informes. Vea los siguientes recursos para obtener más información:

- [Ver informes para la protección contra amenazas avanzada de Office 365](view-reports-for-atp.md)

- [Usar el explorador en el Centro de seguridad y cumplimiento](threat-explorer.md)

Manténgase al tanto de las nuevas características que llegarán a ATP. visite el [plan de desarrollo de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) y obtenga información sobre [las nuevas características que se agregan a ATP](office-365-atp.md#new-features-in-office-365-atp).
