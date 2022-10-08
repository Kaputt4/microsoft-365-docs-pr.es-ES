---
title: Delegación de mensajes
author: samanro
ms.author: samanro
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: microsoft-365-frontline
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
- m365-frontline
- highpri
- EngageScoreSep2022
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.reviewer: acolonna
description: Obtenga información sobre cómo un usuario con estado Away o Do Not Disturb puede establecer explícitamente otro usuario como delegado en su mensaje de estado.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 327c0d5a5bd0e3149cbf418da97ae82c5a03b2ce
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68079521"
---
# <a name="message-delegation"></a>Delegación de mensajes

Los usuarios de Microsoft Teams pueden establecer su estado en Ausente o No molestar e incluir un mensaje de estado de texto personalizado. Un usuario que va a estar ausente puede asignar a alguien como delegado con el que los usuarios puedan ponerse en contacto en su lugar. La característica de delegación de mensajes funciona de la siguiente manera:

1. El usuario que va a estar fuera @mentions otro usuario (el delegado) en su mensaje de estado para que los usuarios sepan que se pongan en contacto con el delegado mientras el usuario está fuera.

    ![Captura de pantalla de un mensaje de estado con un usuario establecido como delegado.](media/message-delegation.png)

1. Al usuario que ha sido @mentioned se le notifica que se le ha designado como delegado.
1. Cuando alguien abre un chat con el usuario de distancia y ve su mensaje de estado, puede mantener el puntero sobre el delegado y enviarle un mensaje fácilmente en su lugar.

Los usuarios pueden iniciar el proceso por sí mismos y no se requiere ninguna intervención del administrador para habilitar la característica.

## <a name="delegation-use-scenario-in-healthcare"></a>Escenario de uso de delegación en el sector sanitario

**Ejemplo de uso sin establecer delegados**

Franco Piccio está de guardia en el departamento de radiología. Recibe una llamada personal urgente y tiene que apartarse durante las próximas horas. Lena Ehrle le pide a uno de sus compañeros del departamento de radiología que lo cubra mientras se ha ido. Informalmente entrega su buscapersonas al Dr. Ehrle, quien escucha mensajes urgentes y hace ping en el buscapersonas y responde a ellos en nombre del Dr. Piccio, además de sus responsabilidades actuales. Es posible que otros miembros del equipo no se den cuenta de que se produjo la delegación informal. La confusión se da con el cuidado de un paciente.

**Ejemplo de uso con la configuración de delegados**

Franco Piccio está de guardia en el departamento de radiología. Recibe una llamada personal urgente y tiene que apartarse durante las próximas horas. Lena Ehrle le pide a uno de sus compañeros del departamento de radiología que lo cubra mientras se ha ido. Cambia su mensaje de estado personalizado para decir "No estoy disponible para las próximas horas. Póngase en contacto con @DrEhrle para cualquier emergencia".  Otros miembros del equipo se dan cuenta de que la delegación ocurrió mientras intentaban ponerse en contacto con el Dr. Piccio, por lo que ahora saben que se ponen en contacto con el Dr. Ehrle mientras tanto. Poco o nada de confusión se produce con el cuidado de un paciente.

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a>Impacto de los modos de coexistencia en el estado del usuario en el cliente de Teams

Los comportamientos de las notas de estado y las menciones de delegación dependen en parte del modo de coexistencia de un usuario. Esta matriz muestra las posibilidades:

|Modo Co-Existence | Comportamiento esperado|
|---|---|
|TeamsOnly |Los usuarios solo pueden establecer una nota desde Teams. <br> La nota de Teams del usuario está visible en Teams & SfB. |
|Aplicaciones aisladas | Nota del usuario establecida en Teams visible solo en Teams. <br> Nota del usuario establecida en SfB visible solo en SfB |
|Modos SfB* | Los usuarios solo pueden establecer una nota desde SfB. <br> La nota de SfB del usuario está visible en SfB & Teams.  |

Un usuario solo puede establecer una nota en Teams si su modo es TeamsOnly o Islands.  

### <a name="displaying-notes-set-in-skype-for-business"></a>Mostrar notas establecidas en Skype Empresarial
  
No hay ninguna indicación visual de que se haya establecido una nota de Skype Empresarial.

Skype Empresarial no aplica un límite de caracteres en las notas de estado. Sin embargo, Microsoft Teams solo mostrará los primeros 280 caracteres de un conjunto de notas de Skype Empresarial. Un botón de puntos suspensivos (...) al final de una nota indica que se ha truncado.
  
Skype Empresarial no admite tiempos de expiración para las notas.

No se admite la migración de notas de Skype Empresarial a Teams cuando un usuario se actualiza al modo TeamsOnly.

## <a name="related-topics"></a>Temas relacionados

[Obtenga más información sobre coexistencia con Skype Empresarial](/microsoftteams/coexistence-chat-calls-presence).
