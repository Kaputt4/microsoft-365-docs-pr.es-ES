---
title: Microsoft 365 Lighthouse de la página de administración de amenazas
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
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Para los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga información sobre la página Administración de amenazas.
ms.openlocfilehash: e57163ba462e241c74a96db78fe701c024a037ff
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63329888"
---
# <a name="microsoft-365-lighthouse-threat-management-page-overview"></a>Microsoft 365 Lighthouse de la página de administración de amenazas 

**Se aplica a:**

- Windows 10

Antivirus de Microsoft Defender los inquilinos, usuarios y dispositivos contra amenazas de software, incluidos virus, malware y spyware. Es una protección sólida y continua que está integrada en Windows 10 y se incluye con Microsoft 365 Empresa Premium y Microsoft365E3&nbsp;&nbsp;.  
  
Para obtener acceso a la página Administración de amenazas en Microsoft 365 Lighthouse, seleccione **Administración** de amenazas en el panel de navegación izquierdo para ver la posición de seguridad de los inquilinos del cliente frente a las amenazas. Verás inquilinos, usuarios y dispositivos que requieren tu atención y recomendaciones que te ayudarán a reducir el riesgo.  
  
## <a name="overview-tab"></a>Ficha Información general  
  
En la pestaña Información general de la página Administración de amenazas, puede supervisar el estado del antivirus en todos los inquilinos para identificar las áreas que necesitan atención.

:::image type="content" source="../media/m365-lighthouse-threat-management-page-overview/threatmanagement-overview-tab.png" alt-text="Captura de pantalla de la pestaña Información general.":::

## <a name="threats-tab"></a>Pestaña Amenazas

En la pestaña Amenazas de la página Administración de amenazas, puede ver las amenazas Activas, Mitigadas, Resueltas y Permitidas en todos los inquilinos. También puede corregir varias amenazas al mismo tiempo en todos los inquilinos filtrando y desglosando cada amenaza para saber qué dispositivos, usuarios o inquilinos se ven afectados.

:::image type="content" source="../media/m365-lighthouse-threat-management-page-overview/threatmanagement-threats-tab.png" alt-text="Captura de pantalla de la página de línea base predeterminada.":::
  
Puede filtrar las amenazas mediante:

- Estado de la amenaza
- Gravedad de la amenaza
- Tipo de amenaza
- Intervalo de fechas

En la tabla siguiente se enumeran los distintos estados de amenaza y su definición:<br><br>

| Estado de la amenaza | Definición |
|--|--|
| Activa | La amenaza está activa en el dispositivo. |
| Sin estado | El estado de la amenaza no está disponible. Ejecuta un examen completo en el dispositivo para que Antivirus de Microsoft Defender vuelva a detectar la amenaza. |
| Error en la acción | El dispositivo no está en riesgo. Se ha fallado una acción, pero se ha detenido una amenaza potencial y no está activa en el dispositivo. Ejecuta un examen completo en el dispositivo. |
| Pasos manuales necesarios | La amenaza se ha detenido, pero requiere un paso manual para completarse, como un examen completo o un reinicio del dispositivo. |
| Examen completo necesario | Se requiere un examen completo del dispositivo. |
| Se requiere reiniciar | Es necesario reiniciar el dispositivo. |
| Corregido con errores no críticos | La amenaza se ha corregido y no se necesitan más acciones. |
| En cuarentena | La amenaza se ha puesto en cuarentena. No se necesitan más acciones. |
| Eliminación | La amenaza se ha quitado correctamente del dispositivo. No se necesitan más acciones. |
| Limpiado | Antivirus de Microsoft Defender archivos recuperados y desinfectados. No se necesitan más acciones. |
| Permitido | Un administrador permite que la amenaza permanezca en el dispositivo. | 

## <a name="antivirus-protection-tab"></a>Ficha Protección antivirus

La pestaña Protección antivirus de la página Administración de amenazas muestra los dispositivos en todos los inquilinos y su Antivirus de Microsoft Defender protección. Puedes evaluar el estado y tomar medidas para uno o varios dispositivos que pueden ser vulnerables. También puedes seleccionar un dispositivo para ver más información, como Información general del dispositivo, Amenazas actuales y Estados de acción del dispositivo.

:::image type="content" source="../media/m365-lighthouse-threat-management-page-overview/threatmanagement-antivirus-tab.png" alt-text="Captura de pantalla de la pestaña Antivirus.":::

## <a name="related-content"></a>Contenido relacionado

[Implementar Microsoft 365 Lighthouse líneas base](m365-lighthouse-deploy-baselines.md) (artículo)\
[Microsoft 365 Lighthouse preguntas más frecuentes](m365-lighthouse-faq.yml) (artículo)
