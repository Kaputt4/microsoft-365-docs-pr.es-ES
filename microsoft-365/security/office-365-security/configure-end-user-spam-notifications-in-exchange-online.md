---
title: Configurar notificaciones de correo no deseado para el usuario final en Exchange Online
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: bfc91c73-a955-40e1-a95f-ad466624339a
ms.collection:
- M365-security-compliance
description: Puede configurar notificaciones de correo no deseado para el usuario final para la directiva predeterminada de filtro de correo no deseado de toda la compañía o para directivas personalizadas de filtro de correo no deseado que se aplican a dominios.
ms.openlocfilehash: f7ef916eea8d9c926f53ef073874dfb299cb92f8
ms.sourcegitcommit: 4986032867b8664a215178b5e095cbda021f3450
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2020
ms.locfileid: "41957395"
---
# <a name="configure-end-user-spam-notifications-in-exchange-online"></a>Configurar notificaciones de correo no deseado para el usuario final en Exchange Online

> [!IMPORTANT]
> Este tema es para clientes de Exchange Online que protegen buzones hospedados en la nube. Exchange Online Protection (EOP) los clientes independientes que protegen buzones locales deben leer el siguiente tema: [configurar notificaciones de correo no deseado para el usuario final en EOP](configure-end-user-spam-notifications-in-eop.md). 
  
Puede configurar notificaciones de correo no deseado para el usuario final para la directiva predeterminada de filtro de correo no deseado para toda la compañía o para directivas personalizadas de filtro de correo no deseado. La habilitación de mensajes de notificación de correo no deseado para el usuario final permite a los usuarios administrar sus propios mensajes de correo no deseado, en masa o de suplantación de cuarentena.   
  
Las notificaciones de correo no deseado para el usuario final contienen una lista de los mensajes de correo no deseado puestos en cuarentena que recibió el usuario final durante el período de tiempo que usted configure (puede especificar cualquier valor entre 1 y 15 días). También puede configurar el idioma en el que está escrito el mensaje de notificación.
  
Después de recibir un mensaje de notificación, los usuarios finales pueden elegir entre las siguientes opciones:

**Bloquear remitente** si desea que Office 365 agregue el remitente a la lista de remitentes bloqueados.

**Release** si el mensaje no es correo no deseado y desea que Office 365 envíe el mensaje al buzón de correo.

**Revise** para navegar al portal de cuarentena en el centro de seguridad & cumplimiento si desea realizar otras acciones, como la versión preliminar o la versión.
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

Tiempo estimado para finalizar: 2 minutos
  
Deberá tener asignados permisos antes de poder llevar a cabo este procedimiento o procedimientos. Para ver qué permisos necesita, consulte el entrada "contra el correo electrónico no deseado" en el tema [permisos de características de Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions) . 
  
Para obtener información acerca de los métodos abreviados de teclado que se pueden aplicar a los procedimientos de este tema, consulte [métodos abreviados de teclado para el centro de administración de Exchange en Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a>Usar el EAC para configurar las notificaciones de correo no deseado para el usuario final

1. En el Centro de administración de Exchange (EAC), vaya a **Protección** \> **Filtro de correo no deseado**.
    
2. Seleccione la Directiva de filtro de correo no deseado para la que desea habilitar las notificaciones de correo no deseado para el usuario final (están deshabilitadas de forma predeterminada).
    
3. En el panel derecho, donde aparece la información de resumen sobre la directiva, haga clic en el vínculo **Configurar notificaciones de correo no deseado para el usuario final**. 
    
4. En el cuadro de diálogo siguiente, puede configurar las siguientes opciones:
    
   - **Habilitar las notificaciones de correo no deseado para el usuario final** Active esta casilla para habilitar las notificaciones de correo no deseado para el usuario final en esta directiva. (Y viceversa: si la directiva está habilitada, puede desactivar la casilla para deshabilitar las notificaciones de correo no deseado para el usuario final en esta directiva). 
    
   - **Enviar notificaciones de correo no deseado para el usuario final cada (días)** Especifique la frecuencia con la que quiere que se envíen las notificaciones de correo no deseado para el usuario final. El valor predeterminado es 3 días. Puede especificar cualquier valor entre 1 y 15 días. Si especifica 7 días, por ejemplo, la notificación incluirá una lista de todos los mensajes destinados a ese usuario en los 7 últimos días que se enviaron, en lugar de al usuario, a la cuarentena de correo no deseado. 
    
   - **Idioma de notificación** En la lista desplegable, seleccione el idioma en el que se escribirán las notificaciones de correo no deseado para el usuario final en esta directiva. 
    
   - Haga clic en **Guardar**. En el panel derecho aparecerá un resumen de la configuración de la Directiva de filtro de correo no deseado, incluida la configuración de notificaciones de correo no deseado para el usuario final.
    
> [!NOTE]
>  Las notificaciones de correo no deseado para el usuario final solo serán compatibles con las directivas de filtro de correo no deseado que estén habilitadas. >  Las notificaciones de correo no deseado para el usuario final se envían solo una vez al día. La hora de envío de la notificación no es configurable y, como tal, no se puede confirmar para ningún cliente en concreto. 
  
 **Sugerencia:** Si desea probar las notificaciones de correo no deseado para el usuario final enviándolas a un conjunto limitado de usuarios antes de implementarlos por completo, cree una directiva personalizada de filtro de correo no deseado que permita notificaciones de correo no deseado para el usuario final para los dominios en los que residen los usuarios. A continuación, en el EAC, en **reglas \> de flujo de correo**, cree una regla de flujo de correo (también denominada regla de transporte) para bloquear mensajes de Quarantine@messaging.microsoft.com (la dirección de correo electrónico que envía notificaciones) con excepciones para los usuarios que desea que reciban las notificaciones. La siguiente imagen es un ejemplo de cómo crear una excepción para dos usuarios (SaraD y AlexD) desde el dominio Contoso.com: 
  
![Regla de transporte para probar las notificaciones de correo no deseado de usuario final](../media/EOP-ESN-testspecificusers.jpg)
  
## <a name="use-the-scc-to-configure-end-user-spam-notifications"></a>Usar el SCC para configurar las notificaciones de correo no deseado para el usuario final

También puede usar el centro de seguridad y cumplimiento (SCC) para configurar las notificaciones de correo no deseado para el usuario final. Siga estos pasos:

1. Abra el centro de seguridad y cumplimiento, vaya a **Threat Management** \> **Policy** \> **anti-spam** o use el vínculo https://protection.office.com/antispamdirecto.

2. Haga clic en la flecha hacia abajo junto a la Directiva de filtro de correo no deseado para la que desea habilitar las notificaciones de correo no deseado para el usuario final.

3. Haga clic en el vínculo **configurar notificaciones de correo no deseado para el usuario final** .

4. En el cuadro de diálogo siguiente, puede configurar las siguientes opciones:
    
   - **Habilitar las notificaciones de correo no deseado para el usuario final** Active esta casilla para habilitar las notificaciones de correo no deseado para el usuario final en esta directiva. (Y viceversa: si la directiva está habilitada, puede desactivar la casilla para deshabilitar las notificaciones de correo no deseado para el usuario final en esta directiva). 
    
   - **Enviar notificaciones de correo no deseado para el usuario final cada (días)** Especifique la frecuencia con la que quiere que se envíen las notificaciones de correo no deseado para el usuario final. El valor predeterminado es 3 días. Puede especificar cualquier valor entre 1 y 15 días. Si especifica 7 días, por ejemplo, la notificación incluirá una lista de todos los mensajes destinados a ese usuario en los 7 últimos días que se enviaron, en lugar de al usuario, a la cuarentena de correo no deseado. 
    
   - **Idioma de notificación** En la lista desplegable, seleccione el idioma en el que se escribirán las notificaciones de correo no deseado para el usuario final en esta directiva. 
    
   - Haga clic en **Guardar**. En el panel aparecerá un resumen de la configuración de la Directiva de filtro de correo no deseado, incluida la configuración de notificaciones de correo no deseado para el usuario final.

## <a name="for-more-information"></a>Más información

[Configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md)
  
