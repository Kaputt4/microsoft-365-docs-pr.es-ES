---
title: Información sobre la confiabilidad
description: ''
keywords: Escritorio administrado de Microsoft, Microsoft 365, Service, Documentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: f830e01d54aef9065727971533633f8e63bc1214
ms.sourcegitcommit: e292e9f0181d722a11398fbd012bb84589aef052
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2019
ms.locfileid: "39257038"
---
# <a name="reliability-insights"></a>Información sobre la confiabilidad

Esta vista le proporciona un resumen de estado de los dispositivos administrados. Para ver los datos de confiabilidad, seleccione la ficha **confiabilidad** .


![Panel confiabilidad](images/insights_reliability.png)

La sección **confiabilidad en todos los dispositivos** ofrece un resumen rápido del estado de la implementación en los últimos 14 días mediante la generación de informes sobre el porcentaje de dispositivos considerados "correctos" y el tiempo medio observado desde el último error notificado. 

 
El gráfico **confiabilidad sobre el tiempo** de la derecha informa sobre el número de dispositivos con errores críticos y el número total de errores críticos observados a lo largo del tiempo.

En la sección **problemas principales** se explican los problemas específicos detectados que afectan al menos el 5% de los dispositivos administrados. Los detalles que se indican incluyen:

- El tipo de problema
    - Bloqueos de aplicación, en los que una aplicación deja de funcionar o se detiene inesperadamente
    - La aplicación se bloquea, donde una aplicación deja de responder a la entrada
    - Errores críticos, que se producen cuando Windows ha encontrado un problema del que no se puede recuperar
- El número de dispositivos afectados por el mismo problema
- El porcentaje de dispositivos administrados que representa el número
- Número total de repeticiones del problema específico
- Componente de software que parece ser el origen del problema
- El estado actual de Microsoft Managed Desktop Operations investiga y corrige el problema

