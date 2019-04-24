---
title: Requisitos de la aplicación de escritorio administrada de Microsoft
description: ''
keywords: Escritorio administrado de Microsoft, Microsoft 365, Service, Documentation
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/08/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: de6cc7d77e023a9d41961e5fbcce060f1bb659ae
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278340"
---
# <a name="microsoft-managed-desktop-app-requirements"></a>Requisitos de la aplicación de escritorio administrada de Microsoft

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreeement for MMD. do not delete.-->

<!--Application addendum -->
 
Las aplicaciones de línea de negocio que desea implementar en los dispositivos de escritorio administrados por Microsoft deben cumplir los requisitos de este tema. 

## <a name="application-condition"></a>Condición de aplicación

Es importante que las aplicaciones no afecten negativamente al entorno de escritorio administrado por Microsoft. A continuación, se indican los requisitos que debe cumplir una aplicación para que Microsoft la implemente. Para cualquier aplicación o controlador, Microsoft puede renunciar a cualquier requisito ofrecido en este documento. Microsoft puede decidir quitar cualquier aplicación o controlador que tenga un impacto negativo en el rendimiento y la confiabilidad de los dispositivos de escritorio administrados por Microsoft.

## <a name="deployable-using-microsoft-technologies"></a>Implementable con tecnologías de Microsoft

Microsoft manAged Desktop usa Intune, Microsoft Store y Microsoft Store for Business para implementar aplicaciones. Por lo tanto, las aplicaciones deben empaquetarse de una manera que pueda ser implementada por la versión actual de dichos servicios.

## <a name="prohibited-app-classes"></a>Clases de aplicaciones prohibidas

Ciertos tipos de aplicaciones no se permiten en dispositivos de escritorio administrados por Microsoft:
- software antivirus, de seguridad o de auditoría de terceros
- exploradores Web de terceros
- Versiones de Microsoft Office anteriores a Office 365 Pro Plus
- Aplicaciones que instalan o agrupan otro software de terceros

## <a name="restricted-app-behaviors"></a>Comportamientos de aplicación restringidos

Algunos comportamientos de la aplicación pueden perjudicar la experiencia del usuario o presentar un riesgo de seguridad a los dispositivos de escritorio administrados por Microsoft. Las aplicaciones no deben presentar los siguientes comportamientos o características: 

Experiencia del usuario:
- Instalar servicios en segundo plano o generar procesos en segundo plano de ejecución prolongada
- Agregarse a sí mismo a la ruta de acceso de inicio de Windows

Seguridad:
- Llamar a las API de Windows o de Office no documentadas o realizar dependencias en estructuras de datos internas de Windows u Office
- Actuar como una tienda de aplicaciones o tener un administrador de extensiones integrado
- Elevar los privilegios del usuario final
- Tener vulnerabilidades de seguridad conocidas
- Firmado con un certificado que no se acumula en una raíz de confianza
- Cifrar o restringir el acceso a los datos del usuario final
- Modificar código del sistema operativo en tiempo de ejecución

## <a name="driver-deployment"></a>Implementación de controladores

A menos que un controlador esté disponible en Windows Update o que esté firmado por separado por el laboratorio de calidad de hardware de Windows (WHQL), Microsoft debe aprobar un controlador antes de que Microsoft implemente el controlador en los dispositivos de escritorio administrados por Microsoft.
