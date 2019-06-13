---
title: Requisitos de la aplicación de escritorio administrada de Microsoft
description: ''
keywords: Escritorio administrado de Microsoft, Microsoft 365, Service, Documentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: ded8bcfd87a6b430dfc4be055a582b482872b104
ms.sourcegitcommit: 498340389e1c34f49f0b2da382c23c8d5334ae47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/12/2019
ms.locfileid: "34913021"
---
# <a name="microsoft-managed-desktop-app-requirements"></a>Requisitos de la aplicación de escritorio administrada de Microsoft

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreeement for MMD. do not delete.-->

<!--Application addendum -->
 
Para garantizar el rendimiento, la fiabilidad y la capacidad de servicio de los dispositivos de escritorio administrados por Microsoft, las aplicaciones de línea de negocio del cliente no deben afectar seriamente a la experiencia del usuario final ni modificar la postura de seguridad. Por lo tanto, las aplicaciones de línea de negocio que desea implementar en los dispositivos de escritorio administrados por Microsoft deben cumplir los requisitos de este tema.

## <a name="application-condition"></a>Condición de aplicación

Es importante que las aplicaciones no afecten negativamente al entorno de escritorio administrado por Microsoft. A continuación, se indican los requisitos que debe cumplir una aplicación para que se implemente una aplicación. Para cualquier aplicación o controlador, Microsoft puede renunciar a cualquier requisito ofrecido en este documento. Microsoft puede decidir quitar cualquier aplicación o controlador que tenga un impacto negativo en el rendimiento y la confiabilidad de los dispositivos de escritorio administrados por Microsoft.

## <a name="centrally-managed-apps"></a>Aplicaciones administradas centralmente

Todas las aplicaciones y los controladores instalados en los dispositivos administrados por Microsoft deben implementarse a través de Microsoft Intune, Microsoft Store o Microsoft Store para empresas; Si está disponible, los controladores también se implementan a través del servicio Windows Update. 

## <a name="prohibited-app-classes"></a>Clases de aplicaciones prohibidas

Ciertos tipos de aplicaciones no se permiten en dispositivos de escritorio administrados por Microsoft:
- software antivirus, de seguridad o de auditoría de terceros
- Versiones de Microsoft Office anteriores a Office 365 Pro Plus
- Aplicaciones que instalan o agrupan otro software de terceros

## <a name="restricted-app-behaviors"></a>Comportamientos de aplicación restringidos

Algunos comportamientos de la aplicación pueden afectar negativamente a la experiencia del usuario o pueden presentar un riesgo de seguridad para los dispositivos de escritorio administrados por Microsoft. No se permite que las aplicaciones con los siguientes comportamientos se ejecuten en el entorno de escritorio administrado por Microsoft sin una exención específica de Microsoft.

Experiencia del usuario:
- Instalar los servicios en segundo plano
- Agregarse a sí mismo a la ruta de acceso de inicio de Windows
- Aplicaciones que dependen de controladores
- exploradores Web de terceros

Seguridad:
- Elevar los privilegios del usuario final
- Actuar como una tienda de aplicaciones o tener un administrador de extensiones integrado
- Tener vulnerabilidades de seguridad conocidas
- Cifrar o restringir el acceso a los datos del usuario final
- No está firmado o está firmado con un certificado que no se acumula en una raíz de confianza


## <a name="driver-deployment"></a>Implementación de controladores

El escritorio administrado de Microsoft solo admite controladores de dispositivos que están disponibles a través de Windows Update o la bandeja de entrada instalada con el dispositivo administrado por Microsoft. 

Si una aplicación requiere un controlador o controladores específicos para ejecutarse, se considera una aplicación restringida y requiere que se implemente una exención en el escritorio administrado de Microsoft. 

