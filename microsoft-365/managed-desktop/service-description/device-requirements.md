---
title: Requisitos del dispositivo
description: Resumen de los requisitos mínimos de hardware y software para que los dispositivos funcionen con Microsoft Managed Desktop
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 90dee316ee5bdc99b6a2386260a3be38728e7282
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453722"
---
# <a name="device-requirements"></a>Requisitos del dispositivo

Microsoft Managed Desktop evalúa periódicamente los requisitos del dispositivo que se incluirán en el servicio. En este artículo se describen los requisitos de hardware y software que debe cumplir un dispositivo para poder trabajar con Microsoft Managed Desktop. Puedes revisar una lista de dispositivos [específicos ya](device-list.md) aprobados para su uso con el servicio en función de estos requisitos.

> [!NOTE]
> Estos requisitos pueden cambiar en cualquier momento, pero proporcionaremos un aviso de 30 días de cualquier cambio en los requisitos de hardware. Los requisitos modificados más recientemente se marcan con **\*** . 

## <a name="check-hardware-requirements"></a>Comprobar requisitos de hardware

Además de revisar las especificaciones del dispositivo, también puedes usar el control de evaluación de preparación descargable para comprobar que un dispositivo determinado cumple los requisitos necesarios. [](../get-ready/readiness-assessment-downloadable.md) Esta herramienta también comprueba la configuración de red y los puntos de conexión que también son necesarios para que el servicio funcione.

## <a name="minimum-requirements"></a>Requisitos mínimos

Para inscribirse en Microsoft Managed Desktop, un dispositivo debe cumplir o superar todos estos requisitos.

### <a name="manufacturer"></a>Fabricante

El dispositivo debe haber sido creado por uno de estos fabricantes:

- Dell
- HP
- Lenovo
- Microsoft


### <a name="installed-software"></a>Software instalado

El dispositivo debe tener preinstalado este software:

- Edición windows 10 Enterprise, Pro o Pro Workstation
- la versión de 64 bits de Microsoft Office hacer clic y ejecutar 
- Todos los controladores de dispositivo aplicables


### <a name="physical-features"></a>Características físicas

Los dispositivos deben tener estas capacidades:

- Habilitado para el arranque seguro de UEFI 
- Módulo de plataforma de confianza 2.0 
- Compatible con la seguridad basada en virtualización 
- Admite integridad de código protegida por hipervisor 

Para obtener más información sobre estas capacidades y las tecnologías relacionadas con ellas que usa el servicio, vea [Tecnologías de Escritorio administrado de Microsoft](../intro/technologies.md).

> [!NOTE]
> ARM procesadores no son compatibles.

Los dispositivos deben cumplir o superar los siguientes límites de almacenamiento y memoria:

- La unidad de arranque debe ser de cualquier tipo que no sea un disco duro. Por ejemplo, las unidades SSD, NVMe y eMMC son opciones válidas.
- La unidad de arranque debe tener una capacidad de al menos 128 GB.
- La memoria interna del dispositivo (RAM) debe ser igual o superior a 8 GB.

Si el dispositivo se hizo después del 1 de julio de 2020, también debe tener una cámara IR, un lector de huellas digitales o ambos, para admitir [Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-enhanced-sign-in-security).

## <a name="recommended-requirements"></a>Requisitos recomendados

Aunque no son requisitos absolutos, los usuarios tendrán una experiencia mucho mejor si elige dispositivos que tengan estas características:

- Un procesador intel vPro-platform o un procesador AMD Ryzen Pro
- Unidad de arranque del tipo SSD con una capacidad de al menos 256 GB
- Compatibilidad con espera moderna
- El dispositivo es de tipo PC de núcleo seguro
- Admite protección de kernel DMA
