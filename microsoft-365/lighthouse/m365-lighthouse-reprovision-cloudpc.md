---
title: Reprovisione un PC en la nube Windows 365 en Microsoft 365 Lighthouse
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolib
- M365-Lighthouse
search.appverid: MET150
description: En el caso de los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga información sobre cómo volver a aprovisionar un PC en la nube Windows 365 en Microsoft 365 Lighthouse.
ms.openlocfilehash: c3ff7dac53798f26da212ac4790ba0cb1412c307
ms.sourcegitcommit: e624221597480295b799d56568c4f6f56d40b41d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2022
ms.locfileid: "65535889"
---
# <a name="reprovision-a-windows-365-cloud-pc-in-microsoft-365-lighthouse"></a>Reprovisione un PC en la nube Windows 365 en Microsoft 365 Lighthouse

Microsoft 365 Lighthouse admite el reaprovisionamiento de equipos en la nube que tienen una directiva de aprovisionamiento. Es posible que tenga que volver a aprovisionar un dispositivo para un nuevo usuario o si el dispositivo no funciona correctamente. Cuando se desencadena un reaprovisionamiento, el PC en la nube se elimina y se vuelve a crear como uno nuevo. Se eliminarán todos los datos de usuario, aplicaciones, personalizaciones y similares.

## <a name="before-you-begin"></a>Antes de empezar

Debe ser administrador de PC en la nube en el inquilino del asociado.

## <a name="reprovision-a-windows-365-cloud-pc"></a>Reprovisione un PC en la nube Windows 365

1. En el panel de navegación izquierdo de Lighthouse, seleccione **Windows 365**.

2. Seleccione la pestaña **Todos los equipos en la nube** .

3. En la lista desplegable **Filtros** , seleccione Tipo de licencia.

4. En la lista filtrada, seleccione un dispositivo.

5. En el panel de detalles del dispositivo, seleccione **Reprovisionar**.

6. En el cuadro de diálogo de confirmación, seleccione **Reprovisionar**.

> [!NOTE]
> El usuario actual del equipo en la nube se iniciará sesión inmediatamente y se quitarán todos los datos de usuario.

## <a name="check-the-device-action-status"></a>Comprobación del estado de la acción del dispositivo

1. En el panel de navegación izquierdo de Lighthouse, seleccione **Windows 365**.

2. Seleccione la pestaña **Todos los equipos en la nube** .

3. En la lista de dispositivos, seleccione un dispositivo.

4. En el panel de detalles del dispositivo, seleccione la pestaña **Estado de la acción del dispositivo** .

La pestaña muestra las acciones actuales en cola para este dispositivo, incluidos el tipo de acción, el estado y la marca de tiempo.

## <a name="related-content"></a>Contenido relacionado

[Información general sobre el aprovisionamiento](/windows-365/enterprise/provisioning) (artículo)\
[Editar directivas de aprovisionamiento](/windows-365/enterprise/edit-provisioning-policy) (artículo)
