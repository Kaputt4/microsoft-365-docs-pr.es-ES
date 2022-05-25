---
title: Kit de laboratorio de implementación de Windows y Office 365
f1.keywords:
- NOCSH
ms.author: aaroncz
author: cdmm12
manager: dougeby
ms.reviewer: alainme
ms.date: 05/11/2022
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Obtenga información sobre dónde acceder al kit de laboratorio de implementación de Windows y Office.
ms.openlocfilehash: 2324501927b39d860b8f2b06e36a85585fa8d4be
ms.sourcegitcommit: 6c2ab5e8efe74d0dc2df610e2d9d2fdda8aaf074
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65669219"
---
# <a name="windows-and-office-365-deployment-lab-kit"></a>Kit de laboratorio de implementación de Windows y Office 365

El kit de laboratorio de implementación Windows y Office 365 está diseñado para ayudarle a planear, probar y validar la implementación y administración de escritorios que ejecutan Windows 10 Enterprise o Windows 11 Empresas y Aplicaciones Microsoft 365 para empresas. Los laboratorios de la cubierta del kit usan Microsoft Endpoint Configuration Manager, OneDrive, Windows Autopilot, etc. Este kit es muy recomendable para las organizaciones que se preparan para las actualizaciones de escritorio. Como entorno aislado, el laboratorio también es ideal para explorar las actualizaciones de herramientas de implementación y probar la automatización relacionada con la implementación.

Hay dos versiones del laboratorio disponibles para descarga gratuita:  

|laboratorio de Windows 10|laboratorio de Windows 11|
|---|---|
|[Entorno de laboratorio de Win 10](https://download.microsoft.com/download/3/3/a/33a3c7d7-b393-4f78-9b90-2d5eb7fd98e8/Win10_21H1_lab.zip)|[Entorno de laboratorio de Win 11](https://download.microsoft.com/download/9/d/9/9d9e278e-a1ea-4704-85e1-cb24f3806f45/Win11_Lab_05.09.zip)|
|[Guías de laboratorio de Win 10](https://download.microsoft.com/download/2/9/9/29952cdb-b98d-4f9b-9d6e-9fb49644b0a0/Win10_21H1_Lab_05.12.zip)|[Guías de laboratorio de Win 11](https://download.microsoft.com/download/9/d/9/9d9e278e-a1ea-4704-85e1-cb24f3806f45/Win11_Lab_Guides_05.09.zip)|

## <a name="a-complete-lab-environment"></a>Un entorno de laboratorio completo

El laboratorio proporciona un entorno de laboratorio virtual aprovisionado automáticamente, incluidos los clientes de escritorio unidos a un dominio, un controlador de dominio, una puerta de enlace de Internet y una instancia de Configuration Manager totalmente configurada. Los laboratorios incluyen versiones de evaluación de los siguientes productos:

|laboratorio de Windows 10|laboratorio de Windows 11|
|---|---|
|Windows 10 Enterprise, versión 21H1|Windows 11 Enterprise|
|Microsoft Endpoint Configuration Manager, versión 2203|Microsoft Endpoint Configuration Manager, versión 2203|
|Windows Assessment and Deployment Kit para Windows 10|Kit de evaluación e implementación de Windows para Windows 11|
|Windows Server 2019|Windows Server 2022|

Los laboratorios también están diseñados para conectarse a pruebas para:

- Microsoft 365 E5
- Aplicaciones de Microsoft 365 para empresas
- Office 365 E5 con Enterprise Mobility + Security (EMS)

## <a name="step-by-step-labs"></a>Prácticas paso a paso

Las guías de laboratorio detalladas le llevarán a través de varios escenarios de implementación y administración. Se han actualizado las prácticas para las versiones más recientes de Intune y Configuration Manager Nota: Ahora hay disponible una nueva versión Windows 11 del laboratorio. Las guías de laboratorio incluyen los siguientes escenarios:

### <a name="plan-and-prepare-infrastructure"></a>Planeamiento y preparación de la infraestructura

- Cloud Management Gateway
- Asociación y administración conjunta de inquilinos
- Análisis de puntos de conexión
- Optimización de la entrega de actualizaciones

### <a name="deploy-windows"></a>Implementación de Windows

- Secuencias de tareas de implementación del sistema operativo en Configuration Manager
- Windows Autopilot

### <a name="service-windows"></a>Windows de servicio

- Mantenimiento Windows mediante directiva de grupo
- Mantenimiento Windows mediante Microsoft Intune
- Mantenimiento de Windows con Configuration Manager

### <a name="deploy-microsoft-365-apps-for-enterprise"></a>Implementación de Aplicaciones de Microsoft 365 para empresas

- Implementación administrada en la nube
- Implementación administrada localmente
- Implementación de Aplicaciones Microsoft 365 para empresas en dispositivos no unidos a AD
- Enterprise implementación administrada mediante Configuration Manager
- Enterprise implementación administrada mediante Microsoft Intune
- Mantenimiento Aplicaciones Microsoft 365 para empresas mediante Configuration Manager
- Mantenimiento Aplicaciones Microsoft 365 para empresas mediante Intune
- Implementación y administración de LOB con Microsoft Intune
- Implementación de Microsoft Teams
- Filtros de asignación

### <a name="managing-microsoft-edge"></a>Administración de Microsoft Edge

- Implementación y actualización de Edge
- Modo IE
- Configurar Enterprise página nueva pestaña

### <a name="security-and-compliance"></a>Seguridad y cumplimiento

- BitLocker
- Antivirus de Microsoft Defender
- Windows Hello para empresas
- Credential Guard de Windows Defender       
- Protección de aplicaciones de Microsoft Defender     
- Protección contra vulnerabilidades de seguridad de Windows Defender             
- Control de aplicaciones de Windows Defender   
- Microsoft Defender para punto de conexión 


> [!NOTE]
> Use una conexión a Internet de banda ancha para descargar este contenido y espere aproximadamente 30 minutos para el aprovisionamiento automático. El entorno de laboratorio requiere un mínimo de 16 GB de memoria disponible y 150 GB de espacio libre en disco. Para un rendimiento óptimo, se recomiendan 32 GB de memoria disponible y 300 GB de espacio libre. El software de evaluación de estos laboratorios expira entre 90 y 120 días después de la activación. Las nuevas versiones de los laboratorios se publicarán en agosto de 2022. 

## <a name="additional-guidance"></a>Instrucciones adicionales

- [Windows documentación y recursos de implementación de cliente](/windows/deployment)
- [Vídeos de la serie de implementación de escritorios de Microsoft Mechanics](https://www.aka.ms/watchhowtoshift)
- [Implementación de sistema operativo de Microsoft Endpoint Configuration Manager](/mem/configmgr/osd/understand/introduction-to-operating-system-deployment)
- [Guía de implementación de Aplicaciones de Microsoft 365](/deployoffice/deployment-guide-microsoft-365-apps)
- [Introducción a Intune](/intune/get-started-evaluation)

## <a name="related-resources"></a>Recursos relacionados

- [Presentación de Microsoft Office 365](https://www.microsoft.com/microsoft-365/default.aspx)
- [Microsoft 365 para empresas](https://products.office.com/business/office)
- [Presentación de Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
- [Windows para empresas](https://www.microsoft.com/windows/business)
