---
title: Información general de la página Administración de amenazas en Microsoft 365 Lighthouse
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
ms-reviewer: algreer
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
description: En el caso de los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga información sobre la página Administración de amenazas.
ms.openlocfilehash: a9e87d533c3693040bf2bea59f9d45a52863af34
ms.sourcegitcommit: 23a53b5c5e372a2a7ad5e175850224d3d464f6dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2022
ms.locfileid: "67056677"
---
# <a name="overview-of-the-threat-management-page-in-microsoft-365-lighthouse"></a>Información general de la página Administración de amenazas en Microsoft 365 Lighthouse 

**Se aplica a:**

- Windows

Antivirus de Microsoft Defender protege a los inquilinos, usuarios y dispositivos frente a amenazas de software, incluidos virus, malware y spyware. Es una protección sólida y continua que está integrada en Windows.  
  
Para acceder a la página Administración de amenazas de Microsoft 365 Lighthouse, seleccione **Administración de amenazas** de **dispositivos** >  en el panel de navegación izquierdo para ver la posición de seguridad de los inquilinos del cliente frente a amenazas. Verá inquilinos, usuarios y dispositivos que requieren su atención y recomendaciones que le ayudarán a reducir el riesgo.  
  
## <a name="overview-tab"></a>‎Pestaña da Información general  
  
En la pestaña Información general de la página Administración de amenazas, puede supervisar el estado del antivirus en todos los inquilinos para identificar las áreas que necesitan atención.

:::image type="content" source="../media/m365-lighthouse-threat-management-page-overview/threatmanagement-overview-tab.png" alt-text="Captura de pantalla de la pestaña Información general.":::

## <a name="threats-tab"></a>Pestaña Amenazas

En la pestaña Amenazas de la página Administración de amenazas, puede ver las amenazas activas, mitigadas, resueltas y permitidas en todos los inquilinos. También puede corregir varias amenazas al mismo tiempo en todos los inquilinos mediante el filtrado y la exploración en profundidad de cada amenaza para saber qué dispositivos, usuarios o inquilinos se ven afectados.

:::image type="content" source="../media/m365-lighthouse-threat-management-page-overview/threatmanagement-threats-tab.png" alt-text="Captura de pantalla de la página Línea base predeterminada.":::
  
Puede filtrar las amenazas por:

- Estado de la amenaza
- Gravedad de la amenaza
- Tipo de amenaza
- Intervalo de fechas

En la tabla siguiente se enumeran los distintos estados de amenaza y su definición:<br><br>

| Estado de la amenaza | Definición |
|---|---|
| Activo | La amenaza está activa en el dispositivo. |
| Sin estado | El estado de la amenaza no está disponible. Ejecute un examen completo en el dispositivo para que antivirus de Microsoft Defender vuelva a detectar la amenaza. |
| Error en la acción | El dispositivo no está en riesgo. Se ha producido un error en una acción, pero se ha detenido una amenaza potencial y no está activa en el dispositivo. Ejecute un examen completo en el dispositivo. |
| Pasos manuales necesarios | La amenaza se ha detenido, pero requiere que se complete un paso manual, como un examen completo o un reinicio del dispositivo. |
| Examen completo necesario | Se requiere un examen completo del dispositivo. |
| Reinicio necesario | Se requiere un reinicio del dispositivo. |
| Corregido con errores no críticos | La amenaza se ha corregido y no se necesitan más acciones. |
| Cuarentena | La amenaza se ha puesto en cuarentena. No se necesitan más acciones. |
| Eliminación | La amenaza se ha quitado correctamente del dispositivo. No se necesitan más acciones. |
| Limpiado | Antivirus de Microsoft Defender ha recuperado y desinfectado archivos. No se necesitan más acciones. |
| Permitido | Un administrador permite que la amenaza permanezca en el dispositivo. | 

## <a name="antivirus-protection-tab"></a>Pestaña Protección antivirus

La pestaña Protección antivirus de la página Administración de amenazas muestra los dispositivos en todos los inquilinos y su estado de protección antivirus de Microsoft Defender. Puede evaluar el estado y tomar medidas para uno o varios dispositivos que pueden ser vulnerables. También puede seleccionar un dispositivo para ver más información, como Información general del dispositivo, Amenazas actuales y Estados de acción del dispositivo.

:::image type="content" source="../media/m365-lighthouse-threat-management-page-overview/threatmanagement-antivirus-tab.png" alt-text="Captura de pantalla de la pestaña Antivirus.":::

## <a name="related-content"></a>Contenido relacionado

[Implementar líneas base Microsoft 365 Lighthouse](m365-lighthouse-deploy-baselines.md) (artículo)\
[Preguntas más frecuentes sobre Microsoft 365 Lighthouse](m365-lighthouse-faq.yml) (artículo)
