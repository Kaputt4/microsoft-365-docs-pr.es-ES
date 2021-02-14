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

Esta vista proporciona un resumen de estado de los dispositivos administrados. Para ver los datos de confiabilidad, seleccione la **pestaña** Confiabilidad.


![Panel de confiabilidad: confiabilidad en todos los dispositivos en la parte superior izquierda, confiabilidad en el gráfico de tiempo en la parte superior derecha, tabla de problemas superior en la parte inferior. Botones de ayuda y comentarios en la parte inferior derecha.](../../media/insights_reliability.png)

La  sección Confiabilidad entre dispositivos ofrece un resumen de estado rápido de la implementación en los últimos 14 días al notificar el porcentaje de dispositivos considerados "correctos" y el tiempo medio observado desde el último error notificado. 

 
El **gráfico Confiabilidad a** lo largo del tiempo de la derecha informa del número de dispositivos con errores críticos y el número total de errores críticos observados a lo largo del tiempo.

En **la sección De problemas** principales se detallan problemas detectados específicos que afectan al menos al 5 % de los dispositivos administrados. Entre los detalles notificados se incluyen:

- El tipo de problema
    - Se bloquea la aplicación, en la que una aplicación deja de funcionar o se detiene inesperadamente
    - La aplicación se cuelga, donde una aplicación deja de responder a la entrada
    - Errores críticos, que se producen cuando Windows ha encontrado un problema del que no se puede recuperar
- El número de dispositivos afectados por el mismo problema
- Porcentaje de dispositivos administrados que representa el número
- Recuento total de repeticiones del problema específico
- El componente de software que parece ser el origen del problema
- Categoría del problema detectado:
    - Explorador (Edge, Chrome, IE)
    - Desconocido (componentes que no son de Microsoft)
    - Controlador (audio, gráficos u otros controladores)
    - Productividad (Slack, G-Suite, Microsoft Office y sus complementos o extensiones, Teams)
    - Medios (aplicaciones de imagen, música o vídeo
    - Seguridad (componentes de seguridad de Windows)
- El estado actual de Operaciones de escritorio administrado de Microsoft investiga y corrige el problema

