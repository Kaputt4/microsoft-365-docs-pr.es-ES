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
ms.sourcegitcommit: cebbdd393dcfd93ff43a1ab66ad70115853f83e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739816"
---
# <a name="reliability-insights"></a>Información sobre la confiabilidad

Esta vista le proporciona un resumen de estado de los dispositivos administrados. Para ver los datos de confiabilidad, seleccione la **pestaña** Confiabilidad.


![Panel de confiabilidad: confiabilidad en todos los dispositivos en la parte superior izquierda, confiabilidad con el gráfico de tiempo en la parte superior derecha, tabla de problemas superior en la parte inferior. Botones de ayuda y comentarios en la parte inferior derecha.](../../media/insights_reliability.png)

La  sección Confiabilidad entre dispositivos ofrece un resumen de estado rápido de la implementación en los últimos 14 días al informar del porcentaje de dispositivos considerados "correctos" y el tiempo medio observado desde el último error notificado. 

 
El **gráfico Confiabilidad con el tiempo** de la derecha informa del número de dispositivos con errores críticos y el número total de errores críticos observados con el tiempo.

En **la sección Principales problemas** se detallan los problemas detectados específicos que afectan al menos al 5 % de los dispositivos administrados. Entre los detalles notificados se incluyen:

- Tipo de problema
    - Se bloquea la aplicación, en la que una aplicación deja de funcionar o se detiene inesperadamente
    - La aplicación se cuelga, donde una aplicación deja de responder a la entrada
    - Errores críticos, que se producen Windows se ha encontrado con un problema del que no puede recuperarse
- El número de dispositivos afectados por el mismo problema
- Porcentaje de dispositivos administrados que representa el número
- Recuento total de repeticiones del problema específico
- El componente de software que parece ser el origen del problema
- Categoría del problema detectado:
    - Explorador (Edge, Chrome, IE)
    - Desconocido (componentes que no son de Microsoft)
    - Controlador (audio, gráficos u otros controladores)
    - Productividad (Slack, G-Suites, Microsoft Office y sus complementos o extensiones, Teams)
    - Medios (aplicaciones de imagen, música o vídeo
    - Seguridad (Windows de seguridad)
- El estado actual como Escritorio administrado de Microsoft operations investiga y corrige el problema

