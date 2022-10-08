---
title: Implementación de Windows 10 Enterprise para Contoso
author: kelleyvice-msft
f1.keywords:
- NOCSH
ms.author: kvice
manager: scotv
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Entienda cómo Contoso usó Configuration Manager de Microsoft Endpoint para implementar las actualizaciones locales de Windows 10 Enterprise.
ms.openlocfilehash: 2d71bb45aff9a61e80470ee834dbfe645298a218
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68171419"
---
# <a name="windows-10-enterprise-deployment-for-contoso"></a>Implementación de Windows 10 Enterprise para Contoso

Antes de la amplia implementación de Microsoft 365 para empresas, Contoso tenía equipos y dispositivos compatibles con Windows que ejecutaban una combinación de Windows 7 (10%), Windows 8.1 (65%) y Windows 10 (25%). Contoso quería actualizar sus equipos para Windows 10 Enterprise aprovechar la seguridad avanzada y reducir la sobrecarga de TI de las implementaciones automatizadas de actualizaciones. 

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
 
Contoso has an existing Configuration Manager (Current Branch) infrastructure. Configuration Manager scales for large environments and provides extensive control over installation, updates, and settings. It also has built-in features to make it easier and more efficient to deploy and manage Windows 10 Enterprise.

## <a name="planning-process"></a>Proceso de planeación

Contoso usó upgrade readiness en Windows Analytics para determinar el conjunto de aplicaciones instaladas y su compatibilidad con Windows 10 Enterprise.

## <a name="deployment-process"></a>Proceso de implementación

Para completar la implementación de actualizaciones locales de Windows 10 Enterprise, Contoso implementó el siguiente proceso, que incluye los procedimientos recomendados de Microsoft:

1. Habilitó la caché del mismo nivel para Configuration Manager.
2. Creó paquetes de Windows personalizados en función de imágenes del Centro de servicios de licencias por volumen.
3. Se usa Configuration Manager para implementar los paquetes de Windows en puntos de distribución en su red y compilaciones implementadas en los tres grupos de ensayo de validación e implementación.
4. Evaluó el éxito de los equipos y dispositivos en los tres anillos de validación y pruebas de implementación mediante las soluciones Estado del dispositivo y Update Compliance de Windows Analytics.
5. En función de la información de Windows Analytics, Contoso determinó la versión de Windows 10 Enterprise que se va a implementar en el amplio grupo de implementación.
6. Ejecutó las secuencias de tareas de implementación Configuration Manager para implementar el paquete de Windows seleccionado en el amplio grupo de implementación.
7. Equipos y dispositivos supervisados en el amplio grupo de implementación mediante las soluciones Estado de los dispositivos y Cumplimiento de actualizaciones para solucionar problemas.

Aquí se muestra la arquitectura de implementación de actualización local y actualizaciones continuas de Contoso.

![Infraestructura de implementación Windows 10 Enterprise de Contoso.](../media/contoso-win10/contoso-win10-fig1.png)

Esta infraestructura consta de:

- Configuration Manager, el cual:
  - Obtiene imágenes de paquetes de Windows 10 Enterprise del Centro de servicios de licencias por volumen de Microsoft en Microsoft Network.
  - Es el punto de administración central para los paquetes de implementación.
- Puntos de distribución regionales que normalmente se encuentran en las oficinas centrales regionales de Contoso.
- Equipos y dispositivos Windows en varias ubicaciones que reciben e instalan los paquetes de implementación para la actualización local o las actualizaciones en curso basadas en la pertenencia a grupos.

## <a name="next-step"></a>Paso siguiente

Obtenga información sobre cómo Contoso aprovecha su infraestructura de Configuration Manager para [implementar y mantener Aplicaciones Microsoft 365 para empresas actuales](contoso-o365pp.md) en toda su organización. 

## <a name="see-also"></a>Vea también

[Windows 10 Enterprise](/windows/deployment/)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Guías del laboratorio de pruebas](m365-enterprise-test-lab-guides.md)