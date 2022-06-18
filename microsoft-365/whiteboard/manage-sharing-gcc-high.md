---
title: Administración del uso compartido para Microsoft Whiteboard en entornos GCC high
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
description: Obtenga información sobre cómo administrar el uso compartido para Microsoft Whiteboard en entornos GCC high.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 3c4df9c8bda42e8cda84729dc17506f6d808c582
ms.sourcegitcommit: b0b1be67de8f40b199bb9b51eb3568e59377e93a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2022
ms.locfileid: "66159980"
---
# <a name="manage-sharing-for-microsoft-whiteboard-in-gcc-high-environments"></a>Administración del uso compartido para Microsoft Whiteboard en entornos GCC high

>[!NOTE]
> Esta guía se aplica a los entornos de alta Government Community Cloud (GCC) de EE. UU.

La experiencia de uso compartido difiere en función del dispositivo y el cliente que se usan. 

## <a name="share-in-teams-meetings"></a>Compartir en reuniones Teams

Al compartir una pizarra en una reunión de Teams, Whiteboard crea un vínculo de uso compartido al que puede acceder cualquier persona de la organización. A continuación, comparte automáticamente la pizarra con cualquier usuario en el inquilino de la reunión.

>[!NOTE]
> El uso compartido externo durante una reunión de Teams aún no está disponible, pero se agregará en una versión futura.

|Escenario |Storage y propiedad |Configuración de uso compartido |Experiencia de uso compartido |
|---------|---------|---------|---------|
|Iniciar la pizarra desde un dispositivo móvil o de escritorio |Storage: OneDrive para la Empresa<br><br>Propietario: usuario que crea la pizarra |Aún no disponible |Usuarios en el inquilino: pueden crear, ver y colaborar<br><br>Usuarios externos: todavía no disponible<br><br>Cuentas de dispositivo compartido: aún no disponibles |
|Inicie la pizarra desde un Surface Hub o Salas de Microsoft Teams |Aún no disponible |         |         |

## <a name="add-as-a-tab-in-teams-channels-and-chats"></a>Agregar como pestaña en Teams canales y chats

Al agregar una pizarra como pestaña en un canal o chat de Teams, Whiteboard creará un vínculo de uso compartido al que pueda acceder cualquier persona de la organización.

|Escenario  |Storage y propiedad  |Configuración de uso compartido  |Experiencia de uso compartido  |
|---------|---------|---------|---------|
|Agregar la pizarra a un canal o chat desde un dispositivo móvil o de escritorio  |Storage: OneDrive para la Empresa<br><br>Propietario: usuario que crea la pizarra  |No aplicable  |Usuarios en el inquilino: pueden iniciar, ver y colaborar<br><br>Usuarios externos: no admitidos  |

## <a name="create-and-share-in-whiteboard-native-clients"></a>Creación y uso compartido en clientes nativos de Whiteboard

Al compartir una pizarra desde clientes web, de escritorio o móviles, puede elegir personas específicas. También puede crear un vínculo de uso compartido al que pueda acceder cualquier persona de la organización. 

>[!NOTE]
> El uso compartido externo durante una reunión de Teams aún no está disponible, pero se agregará en una versión futura.

|Escenario  |Storage y propiedad  |Configuración de uso compartido  |Experiencia de uso compartido  |
|---------|---------|---------|---------|
|Creación de la pizarra desde un dispositivo móvil o de escritorio  |Storage: OneDrive para la Empresa<br><br>Propietario: usuario que crea la pizarra  |No aplicable  |Usuarios en el inquilino: pueden compartir dentro de su organización<br><br>Usuarios externos: no se admite el uso compartido con usuarios externos en este momento  |
|Crear la pizarra a partir de un Surface Hub  |Storage: Local<br><br>Propietario: Ninguno  |No aplicable  |Usuarios en el inquilino (próximamente): el usuario podrá iniciar sesión para guardar y compartir el panel.<br><br>Usuarios externos: no se admite el uso compartido con usuarios externos en este momento |
|Creación de la pizarra a partir de Salas de Microsoft Teams  |Aún no disponible         |         |         |

## <a name="see-also"></a>Vea también

[Habilitación y administración del acceso a Whiteboard: GCC High](enable-whiteboard-access-gcc-high.md)

[Administración de datos para Whiteboard: GCC High](manage-data-gcc-high.md)

[Administración de clientes para Whiteboard: GCC High](manage-clients-gcc-high.md)
