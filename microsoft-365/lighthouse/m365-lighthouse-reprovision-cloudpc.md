---
title: Reprovisione un PC en la nube Windows 365 en Microsoft 365 Lighthouse
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
ms.reviewer: katmartin
audience: Admin
ms.topic: article
ms.service: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolib
- M365-Lighthouse
search.appverid: MET150
description: En el caso de los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga información sobre cómo volver a aprovisionar un PC en la nube Windows 365 en Microsoft 365 Lighthouse.
ms.openlocfilehash: 9b33f9be3bef3a3ae069866e5c31f724695913ee
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2022
ms.locfileid: "68663003"
---
# <a name="reprovision-a-windows-365-cloud-pc-in-microsoft-365-lighthouse"></a>Reprovisione un PC en la nube Windows 365 en Microsoft 365 Lighthouse

Microsoft 365 Lighthouse admite el reaprovisionamiento de equipos en la nube que tienen una directiva de aprovisionamiento. Es posible que tenga que volver a aprovisionar un dispositivo para un nuevo usuario o si el dispositivo no funciona correctamente. Cuando se desencadena un reaprovisionamiento, el equipo en la nube se elimina y se vuelve a crear como un nuevo equipo en la nube. Se eliminan todos los datos de usuario, las aplicaciones y las personalizaciones.

## <a name="before-you-begin"></a>Antes de empezar

Debe ser administrador de PC en la nube en el inquilino del asociado.

## <a name="reprovision-a-windows-365-cloud-pc"></a>Reprovisione un PC en la nube Windows 365

1. En el panel de navegación izquierdo de Lighthouse, seleccione **Dispositivos** >  **Windows 365**.

2. Seleccione la pestaña **Todos los equipos en la nube** .

3. En la lista desplegable **Filtros** , seleccione Tipo de licencia.

4. En la lista filtrada, seleccione un dispositivo.

5. En el panel de detalles del dispositivo, seleccione **Reprovisionar**.

6. En el cuadro de diálogo de confirmación, seleccione **Reprovisionar**.

> [!NOTE]
> El usuario actual del equipo en la nube se ha iniciado sesión inmediatamente y se quitan todos los datos de usuario.

## <a name="check-the-device-action-status"></a>Comprobación del estado de la acción del dispositivo

1. En el panel de navegación izquierdo de Lighthouse, seleccione **Dispositivos** >  **Windows 365**.

2. Seleccione la pestaña **Todos los equipos en la nube** .

3. En la lista de dispositivos, seleccione un dispositivo.

4. En el panel de detalles del dispositivo, seleccione la pestaña **Estado de la acción del dispositivo** .

La pestaña muestra las acciones actuales en cola para este dispositivo, incluidos el tipo de acción, el estado y la marca de tiempo.

## <a name="related-content"></a>Contenido relacionado

[Información general sobre el aprovisionamiento](/windows-365/enterprise/provisioning) (artículo)\
[Editar directivas de aprovisionamiento](/windows-365/enterprise/edit-provisioning-policy) (artículo)
