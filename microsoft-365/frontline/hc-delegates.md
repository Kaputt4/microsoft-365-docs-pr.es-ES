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
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.reviewer: acolonna
description: Obtenga información sobre cómo un usuario con estado Away o Do Not Disturb puede establecer explícitamente otro usuario como delegado en su mensaje de estado.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 190b1f8bfdcf06c124163d97ecf77465f66ad67c
ms.sourcegitcommit: 5e5c2c1f7c321b5eb1c5b932c03bdd510005de13
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2022
ms.locfileid: "66998618"
---
# <a name="message-delegation"></a>Delegación de mensajes

Un usuario ya puede establecer explícitamente su estado en Ausente o No molestar, y proporcionar texto personalizado. La característica de delegación de mensajes funciona de la siguiente manera:

1. Un usuario @username menciona a otro usuario en parte de un mensaje de estado de texto, lo que sugiere que, aunque no están disponibles, las personas que quieren ponerse en contacto con él en su lugar se ponen en contacto con el @username usuario mencionado.
2. Se notifica a la persona a la que se ha asignado como delegado que se le nombró delegado.
3. Alguien que intente ponerse en contacto con el primer usuario puede mantener el puntero sobre el delegado designado y enviar fácilmente un mensaje al delegado en su lugar.  

Se trata de un proceso iniciado por el usuario en el cliente y no se requiere ninguna intervención Administración para habilitar la característica. 

## <a name="delegation-use-scenario-in-healthcare"></a>Escenario de uso de delegación en el sector sanitario

*Ejemplo de uso sin establecer delegados:*  el Dr. Franco Piccio está de guardia en el departamento de radiología. Recibe una llamada personal urgente y tiene que apartarse durante las próximas horas. Lena Ehrle le pide a uno de sus compañeros del departamento de radiología que lo cubra mientras no está. Informalmente entrega su buscapersonas al Dr. Ehrle, quien está escuchando mensajes urgentes y pings en el buscapersonas y responde a ellos en nombre de la Dra. Piccio, además de sus responsabilidades actuales. Es posible que otros miembros del equipo no se den cuenta de que se produjo la delegación informal y se da confusión con el cuidado de un paciente.

*Ejemplo de uso con delegados de configuración:* el Dr. Franco Piccio está de guardia en el departamento de radiología. Recibe una llamada personal urgente y tiene que apartarse durante las próximas horas. Lena Ehrle le pide a uno de sus compañeros del departamento de radiología que lo cubra mientras no está. Cambia su mensaje de estado personalizado para decir algo similar a "No estoy disponible para las próximas horas. Póngase en contacto con @DrEhrle para cualquier emergencia".  Otros miembros del equipo se dan cuenta de que la delegación ocurrió mientras intentaban ponerse en contacto con el Dr. Piccio, por lo que ahora saben que se ponen en contacto con el Dr. Ehrle mientras tanto. Poco o nada de confusión se produce con el cuidado de un paciente.

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a>Impacto de los modos de coexistencia en el estado del usuario en el cliente de Teams

Los administradores deben tener en cuenta que los comportamientos de las notas de estado y las menciones de delegación dependerán en parte del modo de coexistencia de un usuario. Esta matriz muestra las posibilidades:

|Modo Co-Existence | Comportamiento esperado|
|---|---|
|TeamsOnly |Los usuarios solo pueden establecer una nota desde Teams. <br> La nota de Teams del usuario está visible en Teams & SfB. |
|Aplicaciones aisladas | Nota del usuario establecida en Teams visible solo en Teams. <br> Nota del usuario establecida en SfB visible solo en SfB |
|Modos SfB* | Los usuarios solo pueden establecer una nota desde SfB. <br> La nota de SfB del usuario está visible en SfB & Teams.  |
|||

Un usuario solo puede establecer una nota en Teams si su modo es TeamsOnly o Islands.  

### <a name="displaying-notes-set-in-skype-for-business"></a>Mostrar notas establecidas en Skype Empresarial
  
No hay ninguna indicación visual de que se haya establecido una nota de Skype Empresarial.

Skype Empresarial no aplica un límite de caracteres en las notas de estado. Microsoft Teams solo mostrará los primeros 280 caracteres de un conjunto de notas de Skype Empresarial. Una elipse (...) al final de una nota indica truncamiento.
  
Skype Empresarial no admite tiempos de expiración para las notas.

No se admite la migración de notas de Skype Empresarial a Teams cuando un usuario se actualiza al modo TeamsOnly.

## <a name="related-topics"></a>Temas relacionados

[Coexistencia con Skype Empresarial](/microsoftteams/coexistence-chat-calls-presence)
