---
title: Requisitos de la aplicación de escritorio administrado de Microsoft
description: ''
keywords: Servicio de escritorio administrado de Microsoft, Microsoft 365, documentación
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/08/2019
ms.openlocfilehash: 6b6c6f6a2e719496578ac1d15c9b94a92a2ab492
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "26871143"
---
# <a name="microsoft-managed-desktop-app-requirements"></a>Requisitos de la aplicación de escritorio administrado de Microsoft

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreeement for MMD. do not delete.-->

<!--Application addendum -->
 
Las aplicaciones de línea de negocio que se van a implementar en los dispositivos de escritorio administrado de Microsoft deben cumplir los requisitos descritos en este tema. 

## <a name="application-condition"></a>Condición de la aplicación

Es importante que las aplicaciones no impacto negativo en el entorno de escritorio administrado de Microsoft. Los siguientes son los requisitos que deben cumplir las aplicaciones en orden de Microsoft implementarlo. Para cualquier aplicación determinada o el controlador, Microsoft podrá renunciar a cualquier requisito proporcionada en este documento. Microsoft podría decidir quitar cualquier aplicación o controlador que afecta negativamente al rendimiento y la confiabilidad de los dispositivos de escritorio administrado de Microsoft.

## <a name="deployable-using-microsoft-technologies"></a>Se puede implementar mediante tecnologías de Microsoft

Microsoft Managed Desktop utiliza Intune, Store de Microsoft y Microsoft Store para la empresa para implementar aplicaciones. Por consiguiente, se deben empaquetar aplicaciones de una manera pueden implementarse por medio de la versión actual de esos servicios.

## <a name="prohibited-app-classes"></a>Clases de aplicación prohibido

No se admiten ciertos tipos de aplicación en los dispositivos de escritorio administrado de Microsoft:
- 3 º antivirus de terceros, la seguridad o software de auditoría
- 3ª exploradores web de terceros
- Versiones de Microsoft Office anteriores a Office 365 Pro Plus
- Aplicaciones que instalen o reúnen otro software de terceros 3ª

## <a name="restricted-app-behaviors"></a>Comportamientos de aplicación restringidos

Algunos comportamientos de la aplicación pueden ser perjudiciales para la experiencia del usuario o suponer un riesgo de seguridad en los dispositivos de escritorio administrado de Microsoft. Las aplicaciones no presentará los comportamientos o las características siguientes: 

Experiencia del usuario:
- Instalar los servicios de fondo o que generan prolongados procesos en segundo plano
- Agregarse a sí mismo a la ruta de acceso de inicio de Windows

Seguridad:
- Llamada sin documentar de Windows o las API de Office o tomar las dependencias en estructuras de datos internas de Windows o de Office
- Actuar como un almacén de aplicación o tiene el Administrador de extensión incorporada
- Elevar los privilegios del usuario final
- Tener vulnerabilidades de seguridad conocidas
- Firmado mediante un certificado que no resumir en una raíz de confianza
- Cifrar o restringir el acceso a los datos del usuario final
- Modificar el código del sistema operativo en tiempo de ejecución

## <a name="driver-deployment"></a>Implementación de controlador

A menos que un controlador está disponible en Windows Update o por separado está firmado por el laboratorio de calidad de Hardware de Windows (WHQL), Microsoft debe aprobar un controlador antes de que Microsoft va a implementar el controlador en los dispositivos de escritorio administrado de Microsoft.
