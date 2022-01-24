---
title: Escritorio administrado de Microsoft y Windows 11
description: Cómo y cuándo Windows 11 está disponible en el servicio
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.openlocfilehash: b7a4366281172254a893c20dfd7519e2e8ef36d1
ms.sourcegitcommit: 6f3bc00a5cf25c48c61eb3835ac069e9f41dc4db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2022
ms.locfileid: "62170968"
---
# <a name="microsoft-managed-desktop-and-windows-11"></a>Escritorio administrado de Microsoft y Windows 11

Después del anuncio de Windows 11, es posible que haya comenzado a planear Windows 11 migraciones como parte de sus esfuerzos para mantener los dispositivos Windows 10 actualizados. En este artículo se describen consideraciones importantes y cómo Microsoft Managed Desktop admitirá transiciones suaves en los entornos. Para obtener información sobre Windows 11 en sí, [vea Windows 11 overview](/windows/whats-new/windows-11).

Para ver los pasos específicos que deben seguirse para instalar Windows 11 en los dispositivos de Escritorio administrado de Microsoft, vea Vista previa y prueba [de Windows 11 con Microsoft Managed Desktop](../working-with-managed-desktop/test-win11-mmd.md).

## <a name="timeline-for-windows-10-and-windows-11"></a>Escala de tiempo Windows 10 y Windows 11

Windows 11 se puso a disposición general el 4 de octubre de 2021. Está listo para la implementación de consumidores y empresas y es una plataforma totalmente compatible. Comenzaremos a programar implementaciones para todos los dispositivos de Escritorio administrado de Microsoft a partir de enero de 2023, pero proporcionaremos compatibilidad completa para aquellos que deseen implementar Windows 11 antes. Consultaremos y aconsejaremos a los administradores que desarrollen e implementen planes de migración para cada inquilino en función de la preparación técnica y las consideraciones empresariales.

Microsoft Managed Desktop sigue siendo compatible con Windows 10 en paralelo hasta que llega al final del soporte técnico empresarial. Consulte [Windows 10 de lanzamiento para](/windows/release-health/release-information) obtener información sobre el ciclo de vida.



## <a name="assessing-pre-release-versions-of-windows-11"></a>Evaluación de versiones anteriores a la Windows 11

Más del 95 % de los dispositivos de Escritorio administrado de Microsoft son aptos para Windows 11, por lo que es posible que quieras probar la actualización en dispositivos de prueba antes de la implementación de producción. Para obtener más información Windows 11 requisitos del sistema, [vea Windows 11 requirements](/windows/whats-new/windows-11-requirements). 

Para dispositivos de Escritorio administrado de Microsoft, puedes agregar dispositivos al [grupo de dispositivos Windows 11 pruebas.](/microsoft-365/managed-desktop/working-with-managed-desktop/test-win11-mmd?view=o365-worldwide#add-devices-to-the-windows-11-test-group) Este grupo recibe la compilación Windows disponibilidad general 11 junto con una configuración de línea base de Escritorio administrado de Microsoft. Una vez agregado al grupo de dispositivos, permita de uno a dos días que un dispositivo resalte la nueva configuración y se le Windows 11.

Para los dispositivos que no están administrados [](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/endpoint-manager-simplifies-upgrades-to-windows-11/ba-p/2771886) por Microsoft Managed Desktop, puede leer instrucciones Endpoint Manager para obtener información sobre cómo implementar Windows 11 usted mismo. Si tienes dispositivos que Windows 11 y versiones posteriores, inscríbalos en Microsoft Managed Desktop; no volverán a Windows 10.

## <a name="support-for-pre-release-windows-11-devices"></a>Compatibilidad con versiones anteriores Windows 11 dispositivos

Para aquellos que optaron por realizar Windows 11 pruebas antes de la disponibilidad general, es posible que los dispositivos tengan compilaciones de vista previa instaladas. Los dispositivos de Escritorio administrado de Microsoft en este estado no se ofrecerán Windows compilación de disponibilidad general 11, pero seguirán siendo compatibles con la resolución de problemas encontrados. Además, Microsoft Managed Desktop supervisa todos los dispositivos administrados en busca de amenazas de seguridad y responderá a cualquier alerta independientemente de si el dispositivo ejecuta una compilación Windows versión preliminar 11. 

Dado que nos comprometemos a ayudarle a migrar a Windows 11 mientras permanece productivo, le recomendamos que informe de los defectos que encuentre con la plataforma. Priorizamos defectos que bloquearán la productividad del usuario tras la implementación general de Windows 11 y defectos que bloquean la productividad del usuario en Windows 10 dispositivos.

## <a name="testing-application-compatibility"></a>Probar la compatibilidad de aplicaciones

La compatibilidad de aplicaciones es una de las preocupaciones más comunes en cualquier migración de plataforma debido a la posibilidad de interrupciones de productividad. We're using several proactive and reactive measures to help you feel confident about smooth app transitions to Windows 11.

### <a name="proactive-measures"></a>Medidas proactivas

**Aplicaciones comunes:** Microsoft prueba exhaustivamente las aplicaciones y conjuntos de aplicaciones empresariales más comunes implementados en compilaciones de Windows 11. Trabajamos con editores de software externos y equipos de productos internos para resolver los problemas detectados durante las pruebas. Para obtener más información sobre nuestro esfuerzo de pruebas de compatibilidad proactiva, consulte el [blog Compatibilidad de aplicaciones](https://blogs.windows.com/windowsexperience/2019/01/15/application-compatibility-in-the-windows-ecosystem/).

Aplicaciones de línea de **negocio:** [Test Base](https://www.microsoft.com/en-us/testbase) es un recurso que los editores de aplicaciones y los administradores de TI pueden usar para enviar aplicaciones y casos de prueba para que Microsoft se ejecute en una máquina virtual que ejecute Windows 11 compilaciones en un entorno seguro de Azure. Los resultados, las perspectivas de prueba y el análisis de regresión de cada ejecución de prueba están disponibles en un Azure Portal privado. Microsoft Managed Desktop te ayudará a priorizar las aplicaciones de línea de negocio para la validación en función de los datos de confiabilidad y uso de la aplicación. Para obtener más información acerca de Test Base, vea [Test Base for Microsoft 365](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/test-base-for-microsoft-365-microsoft-ignite-2021-updates/ba-p/2185566).

### <a name="reactive-measures"></a>Medidas reactivas
Si encuentras problemas de compatibilidad de aplicaciones en entornos de prueba o producción, puedes recibir soporte técnico sin costo abriendo una [solicitud de servicio](/microsoft-365/managed-desktop/working-with-managed-desktop/test-win11-mmd?view=o365-worldwide#report-issues). Para Windows 11, esto incluye cualquier funcionalidad con aplicaciones de Office, Microsoft Edge, Teams y línea de negocio que se ejecuten en las compilaciones más recientes del sistema operativo. Microsoft App Assure interactúa directamente con los editores de aplicaciones para priorizar y resolver problemas de compatibilidad de aplicaciones cuando sea necesario.

