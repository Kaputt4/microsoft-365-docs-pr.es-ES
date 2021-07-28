---
title: Escritorio administrado de Microsoft y Windows 11
description: Cómo y cuándo Windows 11 está disponible en el servicio
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 7a99ca8d5f56fd5614dc27e3a28efe905ba30e46
ms.sourcegitcommit: 60cc1b2828b1e191f30ca439b97e5a38f48c5169
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2021
ms.locfileid: "53543010"
---
# <a name="microsoft-managed-desktop-and-windows-11"></a>Escritorio administrado de Microsoft y Windows 11

Después del anuncio de Windows 11, es posible que haya comenzado a planear Windows 11 migraciones como parte de sus esfuerzos para mantener los dispositivos Windows 10 actualizados. En este artículo se describen consideraciones importantes y Escritorio administrado de Microsoft admitir transiciones suaves en los entornos. Para obtener información sobre Windows 11 en sí, [vea Windows 11 overview](/windows/whats-new/windows-11).

Para ver los pasos específicos que deben seguirse para instalar Windows 11 en los dispositivos Escritorio administrado de Microsoft, vea Vista previa y prueba [Windows 11 con Escritorio administrado de Microsoft](../working-with-managed-desktop/test-win11-mmd.md).

## <a name="timeline-for-windows-11"></a>Escala de tiempo Windows 11

Windows 11 versiones preliminares están disponibles a partir del 28 de junio de 2021 a través del programa [Windows Insider](/windows-insider/). Esperamos que las compilaciones de versiones estén disponibles por lo general al final del año calendario 2021.

Puedes instalar compilaciones de vista previa en dispositivos independientemente de si Escritorio administrado de Microsoft o no. Seguiremos dando soporte técnico a Windows 10 en paralelo hasta que llegue al final del soporte técnico empresarial. Consulte la [Windows 10 de lanzamiento para](/windows/release-health/release-information) obtener información sobre el ciclo de vida.

Cuando Windows 11 esté disponible, haremos más pruebas de validación. Esperamos que enero de 2022 sea el más pronto que Windows 11 se ofrecerá a Escritorio administrado de Microsoft de producción a través de nuestros grupos de implementación estándar.

Consultaremos y aconsejaremos a los administradores que desarrollen e implementen planes de migración para cada inquilino en función de la preparación técnica y las consideraciones empresariales.

## <a name="assessing-pre-release-versions-of-windows-11"></a>Evaluación de versiones anteriores a la Windows 11

Más del 95 % de los dispositivos Escritorio administrado de Microsoft son aptos para Windows 11, por lo que es posible que quieras obtener una vista previa de la actualización en dispositivos de prueba antes de la implementación de producción. Para obtener más información Windows 11 requisitos del sistema, [vea Windows 11 requirements](/windows/whats-new/windows-11-requirements). Puedes solicitar detalles sobre el estado de elegibilidad de tus dispositivos desde Escritorio administrado de Microsoft.

Para Escritorio administrado de Microsoft dispositivos, puedes solicitar agregar dispositivos de prueba al grupo de dispositivos **Modern Workplace- Windows 11 Pre-Release Test Devices.** Este grupo recibe Windows 11 compilaciones de vista previa junto con una Escritorio administrado de Microsoft de línea base. Escritorio administrado de Microsoft no administra la cadencia de lanzamiento de Windows 11 compilaciones de vista previa, por lo que los miembros de este grupo de dispositivos pueden recibir actualizaciones con más frecuencia que Windows 10 grupos de dispositivos.

Para los dispositivos que no están administrados por Escritorio administrado de Microsoft, puede unirse al programa [de Windows Insider](/windows-insider/) para descargar compilaciones de vista previa y obtener instrucciones sobre cómo implementar Windows 11 usted mismo. Si tienes dispositivos que ejecutan Windows 11 compilaciones previas a la versión y posteriormente los inscribes en Escritorio administrado de Microsoft, no volverán a Windows 10.

## <a name="support-for-pre-release-windows-11-devices"></a>Compatibilidad con versiones anteriores Windows 11 dispositivos

Se espera que las compilaciones de versión previa de cualquier plataforma contengan defectos y problemas de compatibilidad de aplicaciones que se puedan identificar y resolver antes de la disponibilidad general. Como resultado, consideramos que los dispositivos que ejecutan compilaciones previas a la versión de Windows 11 son dispositivos de prueba, pero los supervisamos junto con el resto del entorno en busca de amenazas de seguridad y están sujetos a la misma respuesta de alerta de seguridad que otros dispositivos Escritorio administrado de Microsoft.

Dado que nos comprometemos a ayudarle a migrar a Windows 11 mientras permanece productivo, le recomendamos que informe de los defectos que encuentre con las compilaciones de versiones anteriores. Priorizamos defectos que bloquearán la productividad del usuario tras la implementación general de Windows 11 y defectos que bloquean la productividad del usuario en Windows 10 dispositivos.

## <a name="testing-application-compatibility"></a>Probar la compatibilidad de aplicaciones

La compatibilidad de aplicaciones es una de las preocupaciones más comunes en cualquier migración de plataforma debido a la posibilidad de interrupciones de productividad. We're using several proactive and reactive measures to help you feel confident about smooth app transitions to Windows 11.

### <a name="proactive-measures"></a>Medidas proactivas

**Aplicaciones comunes:** Microsoft está probando exhaustivamente las aplicaciones y conjuntos de aplicaciones empresariales más comunes implementados en compilaciones de Windows 11. Trabajamos con editores de software externos y equipos de productos internos para resolver los problemas detectados durante las pruebas. Para obtener más información sobre nuestro esfuerzo de pruebas de compatibilidad proactiva, consulte el [blog Compatibilidad de aplicaciones](https://blogs.windows.com/windowsexperience/2019/01/15/application-compatibility-in-the-windows-ecosystem/).

Aplicaciones de línea de **negocio:** [Test Base](https://www.microsoft.com/en-us/testbase) es un recurso que los editores de aplicaciones y los administradores de TI pueden usar para enviar aplicaciones y casos de prueba para que Microsoft se ejecute en una máquina virtual que ejecute Windows 11 compilaciones en un entorno seguro de Azure. Los resultados, las perspectivas de prueba y el análisis de regresión de cada ejecución de prueba están disponibles en un Azure Portal privado. Escritorio administrado de Microsoft te ayudará a priorizar las aplicaciones de línea de negocio para la validación en función de los datos de confiabilidad y uso de la aplicación. Para obtener más información acerca de Test Base, vea [Test Base for Microsoft 365](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/test-base-for-microsoft-365-microsoft-ignite-2021-updates/ba-p/2185566).

### <a name="reactive-measures"></a>Medidas reactivas
Si encuentras problemas de compatibilidad de aplicaciones en entornos de prueba o producción, puedes recibir soporte sin costo si participas en [App Assure](/fasttrack/products-and-capabilities#app-assure) o FastTrack, según corresponda. Para Windows 11, esto incluye cualquier funcionalidad con aplicaciones de Office, Microsoft Edge, Teams y línea de negocio que se ejecuten en las compilaciones más recientes del sistema operativo. App Assure interactúa directamente con los editores de aplicaciones para priorizar y resolver problemas de compatibilidad de aplicaciones.

