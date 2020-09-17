---
title: Información sobre la confiabilidad
description: ''
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 06e1446ca290439c9e6689f4461c825438cf6aaf
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950347"
---
# <a name="reliability-insights"></a>Información sobre la confiabilidad

Esta vista le proporciona un resumen de estado de los dispositivos administrados. Para ver los datos de confiabilidad, seleccione la ficha **confiabilidad** .


![Panel confiabilidad: confiabilidad en los dispositivos en la parte superior izquierda, la confiabilidad con el gráfico de tiempo en la esquina superior derecha, la tabla de problemas principales en la parte inferior. Botones de ayuda y comentarios en la parte inferior derecha.](../../media/insights_reliability.png)

La sección **confiabilidad en todos los dispositivos** ofrece un resumen rápido del estado de la implementación en los últimos 14 días mediante la generación de informes sobre el porcentaje de dispositivos considerados "correctos" y el tiempo medio observado desde el último error notificado. 

 
El gráfico **confiabilidad sobre el tiempo** de la derecha informa sobre el número de dispositivos con errores críticos y el número total de errores críticos observados a lo largo del tiempo.

En la sección **problemas principales** se explican los problemas específicos detectados que afectan al menos el 5% de los dispositivos administrados. Los detalles que se indican incluyen:

- El tipo de problema
    - Bloqueos de aplicación, en los que una aplicación deja de funcionar o se detiene inesperadamente
    - La aplicación se bloquea, donde una aplicación deja de responder a la entrada
    - Errores críticos, que se producen cuando Windows ha encontrado un problema del que no se puede recuperar
- El número de dispositivos afectados por el mismo problema
- El porcentaje de dispositivos administrados que representa el número
- Número total de ocurrencias del problema específico
- Componente de software que parece ser el origen del problema
- La categoría del problema detectado:
    - Explorador (Edge, Chrome, IE)
    - Desconocido (componentes que no son de Microsoft)
    - Controlador (audio, gráficos u otros controladores)
    - Productividad (margen de demora, G-Suites, Microsoft Office y sus complementos o extensiones, Teams)
    - Multimedia (imagen, música o aplicaciones de vídeo
    - Seguridad (componentes de seguridad de Windows)
- El estado actual de Microsoft Managed Desktop Operations investiga y corrige el problema

