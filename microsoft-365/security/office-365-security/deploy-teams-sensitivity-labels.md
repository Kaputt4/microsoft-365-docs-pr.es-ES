---
title: Protección de los archivos de los equipos con etiquetas de confidencialidad
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: 5b9c8e41-25d2-436d-89bb-9aecb9ec2b80
description: 'Resumen: Aplique etiquetas de sensibilidad para proteger los archivos en un equipo extremadamente confidencial.'
ms.openlocfilehash: b263aeae335b83cadb45b16d70a2a45d56f1cbd3
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42083378"
---
# <a name="protect-files-in-teams-with-sensitivity-labels"></a>Protección de los archivos de los equipos con etiquetas de confidencialidad


A diferencia de una etiqueta de confidencialidad para datos altamente regulados que cualquier persona puede aplicar a cualquier archivo, un equipo extremadamente confidencial necesita su propia etiqueta o subetiqueta para que los archivos asignados:

- Se cifren individualmente.
- Contengan permisos personalizados para que solo los miembros del equipo puedan abrirlo.

Para lograr este nivel extra de seguridad en los archivos almacenados en el sitio de SharePoint subyacente del equipo, debe configurar una etiqueta de confidencialidad personalizada que sea su propia etiqueta o una subetiqueta de la etiqueta general para datos altamente regulados. Solo los miembros del equipo verán la etiqueta o subetiqueta personalizada en sus listas de etiquetas.

Use una etiqueta de confidencialidad cuando necesite un número reducido de etiquetas tanto para los equipos de uso global como para los individuales privados. 

Use una subetiqueta de confidencialidad cuando tenga un gran número de etiquetas o quiera organizar etiquetas para equipos extremadamente confidenciales bajo la etiqueta altamente regulada.

Siga [estas instrucciones ](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) para configurar una etiqueta o subetiqueta aparte con la siguiente configuración:

- El nombre de la etiqueta o de la subetiqueta contiene el nombre del equipo.
- El cifrado está habilitado.
- El grupo de Office 365 del equipo tiene permisos de coautoría.

Tras crear la nueva etiqueta o subetiqueta, publíquela para los usuarios, que podrán aplicarlas a los archivos, ya sea de forma local antes de cargarlas en el equipo o más tarde, cuando el archivo se almacene en el equipo.

Esta es la configuración del equipo extremadamente confidencial que usa etiquetas de confidencialidad para el cifrado de archivos y los permisos.

![Protección de nivel de línea base de un equipo público.](../../media/highly-confidential-team-dlp-sensitivity-labels.png)


## <a name="see-also"></a>Vea también

[Proteger los archivos en Microsoft Teams](secure-files-in-teams.md)
  
[Adopción de la nube y soluciones híbridas](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
