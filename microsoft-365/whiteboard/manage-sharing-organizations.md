---
title: Administración del uso compartido para Microsoft Whiteboard
ms.author: chucked
author: chuckedmonson
manager: alexfaulkner
ms.reviewer: ''
audience: admin
ms.topic: article
ms.custom: ''
ms.prod: microsoft-365-enterprise
search.appverid: MET150
ms.collection: ''
ms.localizationpriority: medium
description: Obtenga información sobre cómo administrar el uso compartido para Microsoft Whiteboard.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 5a503bee9c83c0757bfa5c394949831839ea2279
ms.sourcegitcommit: b0b1be67de8f40b199bb9b51eb3568e59377e93a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2022
ms.locfileid: "66159992"
---
# <a name="manage-sharing-for-microsoft-whiteboard"></a>Administración del uso compartido para Microsoft Whiteboard

La experiencia de uso compartido difiere en función de si se encuentra en una reunión de Teams, si usa un dispositivo compartido o en qué configuración de uso compartido de nivel de inquilino está habilitada. Los siguientes escenarios solo se aplican a las nuevas pizarras creadas después de que Whiteboard cambie al uso de OneDrive para la Empresa almacenamiento. No hay ningún cambio en los paneles creados anteriormente todavía almacenados en Azure.

## <a name="share-in-teams-meetings"></a>Compartir en reuniones Teams

Al compartir una pizarra en una reunión de Teams, Whiteboard crea un vínculo de uso compartido al que puede acceder cualquier persona de la organización. A continuación, comparte automáticamente la pizarra con cualquier usuario en el inquilino de la reunión.

Hay una funcionalidad adicional para la colaboración temporal por parte de cuentas de dispositivos externos y compartidos durante una reunión. Esta funcionalidad permite a estos usuarios ver y colaborar temporalmente en pizarras cuando se comparten en una reunión de Teams, de forma similar a PowerPoint Live uso compartido.

>[!NOTE]
> Esto no es un vínculo de recurso compartido y no concede acceso al archivo. Proporciona visualización y colaboración temporales en la pizarra solo durante la Teams reunión.

Si tiene habilitado el uso compartido externo para OneDrive para la Empresa, no se requiere ninguna acción adicional.

Si restringe el uso compartido externo para OneDrive para la Empresa, puede mantenerlo restringido y simplemente habilitar una nueva configuración para que funcionen las cuentas de dispositivo externas y compartidas. Para hacerlo, siga estos pasos:

1. Con PowerShell, conéctese al inquilino y asegúrese de que el módulo SharePoint Online se actualiza mediante la ejecución del siguiente comando:

   <pre><code class="lang-powershell">Update-Module -Name Microsoft.Online.SharePoint.PowerShell</code></pre>
 
2. A continuación, ejecute el siguiente <code>Set-SPOTenant</code> cmdlet:

   <pre><code class="lang-powershell">Set-SPOTenant -AllowAnonymousMeetingParticipantsToAccessWhiteboards On</code></pre>

Esta configuración solo se aplica a las pizarras y reemplaza la configuración compartida anteriormente, **OneDriveLoopSharingCapability** y **CoreLoopSharingCapability**. Esa configuración ya no es aplicable y se puede omitir.

>[!NOTE]
> De forma predeterminada, está habilitada la configuración de reunión Teams **usuarios anónimos pueden interactuar con las aplicaciones de las reuniones**. Si la ha deshabilitado, los usuarios anónimos (en lugar de invitados o usuarios federados) no tendrán acceso a la pizarra durante la reunión.

Estos cambios deben tardar aproximadamente 60 minutos en aplicarse en todo el inquilino. 

|Escenario  |Storage y propiedad  |Configuración de uso compartido  |Experiencia de uso compartido  |
|---------|---------|---------|---------|
|Iniciar la pizarra desde un dispositivo móvil o de escritorio  |Storage: OneDrive para la Empresa<br><br>Propietario: usuario que crea la pizarra  |Habilitado  |Usuarios en el inquilino: pueden crear, ver y colaborar<br><br>Usuarios externos: solo pueden ver y colaborar durante la reunión (el botón para compartir una pizarra no aparecerá para los usuarios externos)<br><br>Cuentas de dispositivo compartido: solo puede ver y colaborar durante la reunión.  |
|Iniciar la pizarra desde un dispositivo móvil o de escritorio  |Storage: OneDrive para la Empresa<br><br>Propietario: usuario que crea la pizarra  |Deshabilitada  |Usuarios en el inquilino: pueden iniciar, ver y colaborar<br><br>Usuarios externos: no se puede ver ni colaborar<br><br>Cuentas de dispositivo compartido: no se puede ver ni colaborar  |
|Inicie la pizarra desde un Surface Hub o Salas de Microsoft Teams  |Storage: Azure (se moverá a OneDrive para la Empresa en el futuro)<br><br>Propietario: Participante de la reunión   |No aplicable  |Usuarios en el inquilino: pueden iniciar, ver y colaborar<br><br>Usuarios externos: solo pueden ver y colaborar durante la reunión.<br><br>Cuentas de dispositivo compartido: solo puede ver y colaborar durante la reunión.  |

## <a name="add-as-a-tab-in-teams-channels-and-chats"></a>Agregar como pestaña en Teams canales y chats

Al agregar una pizarra como pestaña en un canal o chat de Teams, Whiteboard creará un vínculo de uso compartido al que pueda acceder cualquier persona de la organización.

|Escenario  |Storage y propiedad  |Configuración de uso compartido  |Experiencia de uso compartido  |
|---------|---------|---------|---------|
|Agregar la pizarra a un canal o chat desde un dispositivo móvil o de escritorio  |Storage: OneDrive para la Empresa<br><br>Propietario: usuario que crea la pizarra  |No aplicable (solo se aplica a reuniones)  |Usuarios en el inquilino: pueden iniciar, ver y colaborar<br><br>Usuarios externos: no admitidos<br><br>Teams invitados: puede ver y colaborar<br><br>Cuentas de dispositivo compartido: no aplicables  |

## <a name="create-and-share-in-whiteboard-native-clients"></a>Creación y uso compartido en clientes nativos de Whiteboard

Al compartir pizarras desde clientes web, de escritorio o móviles, puede elegir personas específicas. También puede crear un vínculo de uso compartido al que pueda acceder cualquier persona de la organización. 

>[!NOTE]
> El uso compartido externo durante una reunión de Teams aún no está disponible, pero se agregará en una versión futura.

|Escenario  |Storage y propiedad  |Configuración de uso compartido  |Experiencia de uso compartido  |
|---------|---------|---------|---------|
|Creación de la pizarra desde un dispositivo móvil o de escritorio  |Storage: OneDrive para la Empresa<br><br>Propietario: usuario que crea la pizarra  |No aplicable (solo se aplica a reuniones)  |Usuarios en el inquilino: pueden compartir dentro de su organización<br><br>Usuarios externos: no se admite el uso compartido con usuarios externos en este momento  |
|Crear la pizarra a partir de un Surface Hub  |Storage: Local<br><br>Propietario: Ninguno (a menos que el usuario inicie sesión para guardar y compartir el panel, lo que se guarda en OneDrive para la Empresa. El uso compartido fácil se agregará de nuevo en el futuro.  |No aplicable (solo se aplica a reuniones)  |Usuarios en el inquilino: el usuario debe iniciar sesión para guardar y compartir el panel (el recurso compartido fácil se agregará en el futuro).<br><br>Usuarios externos: no se admite el uso compartido con usuarios externos en este momento fuera de una reunión de Teams  |
|Creación de la pizarra a partir de Salas de Microsoft Teams  |Todavía no se admite  |No aplicable (solo se aplica a reuniones)  |Todavía no se admite  |

## <a name="see-also"></a>Vea también

[Habilitación y administración del acceso a Whiteboard](enable-whiteboard-access-organizations.md)

[Administración de datos para Whiteboard](manage-data-organizations.md)

[Implementación de Whiteboard en Windows](deploy-on-windows-organizations.md)