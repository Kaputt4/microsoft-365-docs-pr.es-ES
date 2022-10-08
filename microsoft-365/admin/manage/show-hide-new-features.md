---
title: Administrar qué características de Office aparecen en Novedades
f1.keywords:
- NOCSH
ms.author: danbrown
author: DHB-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- admindeeplinkMAC
search.appverid:
- BCS160
- MET150
- MOE150
description: Decida qué características de Office se mostrarán u ocultarán cuando un usuario elija Ayuda > Novedades de su aplicación de Office en Windows mediante la característica "Novedades de Office" en el Centro de administración de Microsoft 365.
ms.openlocfilehash: 53372a4075de6d6a4790d49dc23e79e0ca60d65d
ms.sourcegitcommit: f72ea75c6d5c1bca0e0ed8fd228d3a84c6104361
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "67879269"
---
# <a name="manage-which-office-features-appear-in-whats-new"></a>Administrar qué características de Office aparecen en Novedades

Cuando se publica una característica importante de Office, los usuarios recibirán un mensaje al respecto cuando elijan **Ayuda** \> **sobre las novedades** de su aplicación de Office en Windows.

Puede controlar cuáles de estos mensajes de característica se muestran a los usuarios mediante la característica **Novedades de Office** en el Centro de administración de Microsoft 365. Si decide ocultar un mensaje de característica a los usuarios, siempre puede volver más tarde y decidir mostrarlo a ellos.

> [!NOTE]
>
> - Ocultar un mensaje de característica de los usuarios no deshabilita la característica en la aplicación de Office.
> - Debe tener asignado el rol de administrador global o el rol de administrador de aplicaciones de Office para usar la característica **Novedades de Office** .

## <a name="show-or-hide-new-features"></a>Mostrar u ocultar nuevas características

1. En el Centro de administración de Microsoft 365, en **Configuración**, elija **Configuración de la organización**, seleccione la <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">pestaña **Servicios**</a> y, a continuación, seleccione **Novedades de Office**.
1. Al hacer clic en el nombre de la característica, aparece un panel flotante con la siguiente información:
     - Breve descripción de la característica.
     - Vínculo a un artículo para obtener más información sobre la característica.
     - Las aplicaciones de Office en las que aparece la característica.
     - La primera versión (versión) en la que está disponible la característica para ese canal.
1. Elija **Ocultar de los usuarios**. O bien, si previamente ocultó la característica, elija **Mostrar a los usuarios**.

También puede seleccionar varias características en la página **Administrar qué características de Office aparecen en Novedades** y, a continuación, elegir **Ocultar** o **Mostrar**.

> [!NOTE]
>
> - Si una característica está disponible en varias aplicaciones de Office, al establecer la característica en **Oculto** se oculta el mensaje de característica en todas esas aplicaciones de Office.
> - Todos los mensajes de características se muestran a los usuarios de forma predeterminada. Este es el estado predeterminado de todas las características y el estado solo cambia si ha elegido ocultar o mostrar un mensaje de característica.
> - También puede acceder a la característica **Novedades de Office** desde el centro de administración de Aplicaciones Microsoft 365 (<https://config.office.com>). La característica se encuentra en **Personalización** > **de la nueva administración**.

## <a name="list-of-features"></a>Lista de características

Puede filtrar qué características aparecen en la página **Administrar qué características de Office aparecen en Novedades** . Puede filtrar por canal, aplicación o estado, o por alguna combinación de ellos.

Las nuevas características aparecen en la página según la siguiente programación:

<br>

****

|Canal|Fecha|Tomar medidas|
|---|---|---|
|**Current**|15 del mes|1 a 3 semanas antes de la versión mensual|
|**Empresarial mensual**|Primero de mes|Dos semanas antes de la versión principal que trae nuevas características|
|**Empresa semestral (versión preliminar)**|1 de septiembre y 1 de marzo| 2 semanas antes de la versión principal que trae nuevas características|
|**Empresa semestral**|1 de enero y 1 de julio| 2 semanas antes de la versión principal que trae nuevas características|
|

Para obtener más información sobre cuándo se publican nuevas versiones en cada canal de actualización, consulte [Historial de actualizaciones para Aplicaciones Microsoft 365 (lista por fecha).](/officeupdates/update-history-microsoft365-apps-by-date)

## <a name="add-the-whats-new-in-office-card-to-the-admin-center-home-page"></a>Agregue la tarjeta "Novedades de Office" a la página principal del Centro de administración.

1. En la página administrador de Microsoft 365, elija **Agregar tarjeta** en la parte superior de la página.
2. Busque **Administrar qué características de Office aparecen en Novedades** de la lista y selecciónela.
3. Una vez que la tarjeta esté en la página principal, puede elegir **Novedades de Office** para [mostrar u ocultar las características de su](#show-or-hide-new-features) organización.

## <a name="related-articles"></a>Artículos relacionados

[La administración de Office What's New ya está disponible con carácter general](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-what-s-new-management-is-now-generally-available/ba-p/1179954)
