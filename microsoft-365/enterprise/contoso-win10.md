---
title: Implementación de Windows 10 Enterprise para Contoso
author: kelleyvice-msft
f1.keywords:
- NOCSH
ms.author: kvice
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
ms.openlocfilehash: 9315e57fb08f0adda39f1a08107d8d96e1c2bc24
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2021
ms.locfileid: "59218627"
---
# <a name="windows-10-enterprise-deployment-for-contoso"></a>Implementación de Windows 10 Enterprise para Contoso

Antes de la implementación de Microsoft 365 para empresas, Contoso tenía equipos y dispositivos compatibles con Windows que ejecutaba una mezcla de Windows 7 (10%), Windows 8.1 (65%) y Windows 10 (25%). Contoso quería actualizar sus equipos para Windows 10 Enterprise aprovechar la seguridad avanzada y reducir la sobrecarga de TI de las implementaciones automatizadas de actualizaciones. 

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

Contoso usó la preparación de actualización en Windows Analytics para determinar el conjunto de aplicaciones instaladas y su compatibilidad con Windows 10 Enterprise.

## <a name="deployment-process"></a>Proceso de implementación

Para completar la implementación de actualizaciones locales de Windows 10 Enterprise, Contoso implementó el siguiente proceso, que incluye los procedimientos recomendados de Microsoft:

1. Habilitó la caché del mismo nivel para Configuration Manager.
2. Creó paquetes de Windows personalizados en función de imágenes del Centro de servicios de licencias por volumen.
3. Se usó Configuration Manager para implementar los Windows paquetes de distribución en puntos de distribución en toda la red y se implementaron compilaciones en los tres grupos de validación e implementación provisional.
4. Evaluó el éxito de los equipos y dispositivos en los tres anillos de validación y pruebas de implementación mediante las soluciones Estado del dispositivo y Update Compliance de Windows Analytics.
5. En función de la Windows analytics, Contoso determinó la versión de Windows 10 Enterprise implementar en el grupo de implementación general.
6. Se ejecutaron las secuencias de tareas de implementación de Configuration Manager para implementar el paquete Windows seleccionado en el grupo de implementación general.
7. Equipos y dispositivos supervisados en el grupo de implementación general mediante las soluciones de mantenimiento de dispositivos y cumplimiento de actualizaciones para solucionar problemas.

Aquí se muestra la arquitectura de implementación de actualización local y actualizaciones continuas de Contoso.

![Infraestructura de implementación Windows 10 Enterprise contoso.](../media/contoso-win10/contoso-win10-fig1.png)

Esta infraestructura consta de:

- Configuration Manager, el cual:
  - Obtiene imágenes de paquetes de Windows 10 Enterprise del Centro de servicios de licencias por volumen de Microsoft en Microsoft Network.
  - Es el punto de administración central para los paquetes de implementación.
- Puntos de distribución regionales que normalmente se encuentran en las oficinas centrales regionales de Contoso.
- Windows Equipos y dispositivos en distintas ubicaciones que reciben e instalan los paquetes de implementación para la actualización local o actualizaciones en curso basadas en la pertenencia a grupos.

## <a name="next-step"></a>Paso siguiente

Obtenga información sobre cómo Contoso está aprovechando su infraestructura de Configuration Manager para [implementar y](contoso-o365pp.md) mantener las actualizaciones Aplicaciones Microsoft 365 para empresas toda la organización. 

## <a name="see-also"></a>Consulte también

[Windows 10 Enterprise](/windows/deployment/)

[Información general de Microsoft 365 para empresas](microsoft-365-overview.md)

[Guías del laboratorio de pruebas](m365-enterprise-test-lab-guides.md)