---
title: Configuración de inquilino de Microsoft 365 Multi-Geo
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.collection:
- SPO_Content
- Strat_SP_gtc
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.localizationpriority: medium
description: En este artículo, aprenderá a agregar ubicaciones de satélite y a configurar su espacio empresarial de Microsoft 365 Multi-Geo
ms.openlocfilehash: a656dc718dfaac14d87ea0ae5e1fa792d41a0648
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2022
ms.locfileid: "68804694"
---
# <a name="microsoft-365-multi-geo-_tenant_-configuration"></a>Configuración del _inquilino multigeográfico_ de Microsoft 365

Antes de configurar el _inquilino_ para Microsoft 365 Multi-Geo, asegúrese de que ha leído [Plan for Microsoft 365 Multi-Geo(Plan for Microsoft 365 Multi-Geo](plan-for-multi-geo.md)).

Para seguir los pasos de este artículo, necesitará una lista de las ubicaciones _geography_ que desea habilitar como ubicaciones _de Geografía satélite_ y los usuarios de prueba que desea aprovisionar para esas ubicaciones.

No todas las cargas de trabajo multigeográficas requieren una configuración controlada por el cliente.

## <a name="configuring-exchange-online-for-multi-geo"></a>Configuración de Exchange Online para multigeográfica

No se requiere ninguna configuración controlada por el cliente para preparar Exchange Online en un inquilino habilitado para varias zonas _geográficas_. Un cliente puede usar todas las zonas geográficas con Exchange Online tan pronto como Multi-Geo se haya habilitado dentro de Exchange Online para su _inquilino_.

## <a name="configuring-microsoft-teams-for-multi-geo"></a>Configuración de Microsoft Teams para multigeográfica

No se requiere ninguna configuración controlada por el cliente para preparar Microsoft Teams en un inquilino habilitado para varias zonas geográficas. Un cliente puede usar todas las zonas geográficas con Microsoft Teams en cuanto se haya habilitado Multi-Geo en Microsoft Teams para su _inquilino_.

## <a name="configuring-sharepoint-online-and-onedrive-for-business-for-multi-geo"></a>Configuración de SharePoint Online y OneDrive para la Empresa para multigeográfica

Si desea almacenar datos en una geografía determinada, esa geografía debe configurarse para SharePoint Online y OneDrive con antelación.

Una vez que se ha habilitado Multi-Geo para el _inquilino_ en SharePoint Online y OneDrive para la Empresa, la pestaña **Ubicaciones geográficas** estará disponible en los centros de administración de OneDrive para la Empresa y SharePoint Online. Si no ve la pestaña **Ubicaciones geográficas** , el _inquilino_ aún no ha terminado de habilitarse para Multi-Geo.

Para agregar cada ubicación de geografía satélite para SharePoint y OneDrive donde desea almacenar datos:

1. Abra el Centro de administración de SharePoint. y vaya a **Ubicaciones geográficas**.
1. Seleccione **Agregar ubicación**.
1. Seleccione la ubicación que desea agregar y, a continuación, seleccione **Siguiente**.
1. Escriba el dominio que desea usar con la ubicación geográfica y, a continuación, seleccione **Agregar**.
1. Seleccione **Cerrar**.

El aprovisionamiento puede tardar desde unas horas hasta 72 horas, en función del tamaño del _inquilino_. Una vez completado el aprovisionamiento de una ubicación _de Geografía satélite_ , recibirá una confirmación por correo electrónico. Cuando la nueva ubicación _de Geography_ aparece en azul en el mapa en la pestaña Ubicaciones geográficas del Centro de administración de OneDrive y SharePoint, puede continuar para establecer la ubicación de datos preferida de los usuarios en esa ubicación _geográfica_ .

> [!IMPORTANT]
> La nueva ubicación _de Geografía satélite_ se configurará con la configuración predeterminada. Esto le permitirá configurar la ubicación _de Satellite Geography_ según corresponda para sus necesidades de cumplimiento local.
