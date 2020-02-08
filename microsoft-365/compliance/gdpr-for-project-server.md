---
title: RGPD para Project Server
description: Obtenga información sobre cómo cumplir los requisitos de RGPD en Project Server local.
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
titleSuffix: Microsoft GDPR
ms.openlocfilehash: a9fff9f085fd42f28801a82c3f83d6bdd1f74ff6
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596417"
---
# <a name="gdpr-for-project-server"></a>RGPD para Project Server

Project Server usa scripts personalizados para exportar y redactar datos de usuario en Project Web App. El proceso básico es:

1.  Busque los sitios de Project Web App en la granja de servidores.

2.  Busque los proyectos en cada sitio que contiene el usuario.

3.  Exporte y revise los tipos de datos que desee revisar.

4.  Redacte los datos según sea necesario.

Estos pasos se tratan con detalle en los siguientes artículos:

- [Exportar datos de usuario de Project Server](/Project/export-user-data-from-project-server?toc=/Office365/Enterprise/toc.json)

- [Eliminar datos de usuario de Project Server](/Project/delete-user-data-from-project-server?toc=/Office365/Enterprise/toc.json)


Tenga en cuenta que Project Server se basa en SharePoint Server y registra los eventos en los registros de ULS de SharePoint y la base de datos de uso. Para obtener más información, vea [RGPD para SharePoint Server](gdpr-for-sharepoint-server.md).
