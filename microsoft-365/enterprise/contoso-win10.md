---
title: Implementación de Windows 10 Enterprise para Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Entienda cómo Contoso usó Configuration Manager de Microsoft Endpoint para implementar las actualizaciones locales de Windows 10 Enterprise.
ms.openlocfilehash: 0543f24665048d0679bc1b099fdd0a2d431c1e54
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754256"
---
# <a name="windows-10-enterprise-deployment-for-contoso"></a>Implementación de Windows 10 Enterprise para Contoso

Antes de la amplia implementación de Microsoft 365 para empresas, Contoso tenía equipos y dispositivos compatibles con Windows que ejecutaba una combinación de Windows 7 (10%), Windows 8.1 (65%) y Windows 10 (25%). Contoso quería actualizar sus equipos para Windows 10 Enterprise aprovechar las ventajas de la seguridad avanzada y reducir la sobrecarga de TI de las implementaciones automatizadas de actualizaciones. 

Después de evaluar la infraestructura y las necesidades empresariales, Contoso identificó estos requisitos de implementación principales:

- Se debería ejecutar Windows 10 Enterprise en el mayor número posible de equipos y dispositivos.
- La implementación de las actualizaciones locales aprovecha la infraestructura existente de Configuration Manager.
- Control sobre qué versiones de Windows 10 Enterprise se implementan y actualizan a través de anillos.
- Los equipos y dispositivos se deberían mantener actualizados con los mínimos costos administrativos de TI y el menor impacto en los usuarios finales.

Actualizado se define como la versión compatible de Windows 10 Enterprise que satisface las necesidades empresariales de Contoso, lo que puede diferir de tener equipos compatibles con Windows con la versión más reciente de Windows 10 Enterprise.

## <a name="deployment-tools"></a>Herramientas de implementación

Antes y durante las actualizaciones locales de Windows 10 Enterprise, Contoso usó las siguientes soluciones de Windows Analytics:

- Upgrade Readiness  

  Recopila datos del sistema, aplicaciones y controladores para el análisis y, después, identifica los problemas de compatibilidad que pueden bloquear una actualización y sugiere correcciones de los problemas que Microsoft conoce.

- Update Compliance  

  Le muestra el estado de sus dispositivos con respecto a las actualizaciones de Windows, para que pueda asegurarse de que tienen instaladas las actualizaciones más recientes según corresponda.

- Estado del dispositivo  

  Identifica los dispositivos que se bloquean con frecuencia y que quizás deban volver a crearse o reemplazarse, y los controladores de dispositivos que estén causando bloqueos en los mismos, y ofrece sugerencias de versiones alternativas de dichos controladores que pueden reducir el número de bloqueos. Proporciona una notificación de las configuraciones incorrectas de Windows Information Protection que envía avisos a los usuarios finales.
 
Contoso tiene una infraestructura existente de Configuration Manager (Rama actual). Configuration Manager se escala en entornos de gran tamaño y proporciona un amplio control sobre la instalación, las actualizaciones y la configuración. También incluye características integradas para que sea más fácil y eficaz implementar y administrar Windows 10 Enterprise.

## <a name="planning-process"></a>Proceso de planeación

Contoso usó upgrade readiness en Windows Analytics para determinar el conjunto de aplicaciones instaladas y su compatibilidad con Windows 10 Enterprise.

## <a name="deployment-process"></a>Proceso de implementación

Para completar la implementación de actualizaciones locales de Windows 10 Enterprise, Contoso implementó el siguiente proceso, que incluye los procedimientos recomendados de Microsoft:

1. Habilitó la caché del mismo nivel para Configuration Manager.
2. Creó paquetes de Windows personalizados en función de imágenes del Centro de servicios de licencias por volumen.
3. Se usó Configuration Manager para implementar los paquetes de Windows en puntos de distribución en su red e implementó compilaciones en los tres grupos de validación e implementación provisional.
4. Evaluó el éxito de los equipos y dispositivos en los tres anillos de validación y pruebas de implementación mediante las soluciones Estado del dispositivo y Update Compliance de Windows Analytics.
5. En función de la información de Windows Analytics, Contoso determinó la versión de Windows 10 Enterprise para implementarla en el grupo de implementación general.
6. Ejecutó las secuencias de tareas de implementación de Configuration Manager para implementar el paquete de Windows seleccionado en el grupo de implementación general.
7. Monitored PCs and devices in the broad deployment group using the Device Health and Update Compliance solutions to address issues.

Aquí se muestra la arquitectura de implementación de actualización local y actualizaciones continuas de Contoso.

![Infraestructura de implementación de Windows 10 Enterprise de Contoso](../media/contoso-win10/contoso-win10-fig1.png)

Esta infraestructura consta de:

- Configuration Manager, el cual:
  - Obtiene imágenes de paquetes de Windows 10 Enterprise del Centro de servicios de licencias por volumen de Microsoft en Microsoft Network.
  - Es el punto de administración central para los paquetes de implementación.
- Puntos de distribución regionales que normalmente se encuentran en las oficinas centrales regionales de Contoso.
- Equipos y dispositivos Windows en varias ubicaciones que reciben e instalan los paquetes de implementación para la actualización local o actualizaciones continuas basadas en la pertenencia a grupos.

## <a name="next-step"></a>Paso siguiente

Obtenga información sobre cómo Contoso aprovecha su infraestructura de Configuration Manager para implementar y mantener las aplicaciones actuales de [Microsoft 365](contoso-o365pp.md) para empresas en toda la organización. 

## <a name="see-also"></a>Vea también

[Windows 10 Enterprise](https://docs.microsoft.com/windows/deployment/)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Guías del laboratorio de pruebas](m365-enterprise-test-lab-guides.md)
