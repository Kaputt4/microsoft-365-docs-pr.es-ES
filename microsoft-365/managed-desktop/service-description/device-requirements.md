---
title: Requisitos del dispositivo
description: Resumen de los requisitos mínimos de hardware y software para que los dispositivos funcionen con Escritorio administrado de Microsoft
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: fcd7f192ba0846e3bf3051cde927095088f32d26
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245797"
---
# <a name="device-requirements"></a>Requisitos del dispositivo

Escritorio administrado de Microsoft evalúa periódicamente los requisitos del dispositivo para incluirse en el servicio. En este artículo se describen los requisitos de hardware y software que debe cumplir un dispositivo para poder trabajar con Escritorio administrado de Microsoft. Puedes revisar una lista de dispositivos específicos ya aprobados para su uso con el servicio en función de estos requisitos. Filtrar por Escritorio administrado de Microsoft en el sitio [De Windows 10 Pro de dispositivos](https://www.microsoft.com/windowsforbusiness/view-all-devices) empresariales

> [!NOTE]
> Estos requisitos pueden cambiar en cualquier momento, pero proporcionaremos un aviso de 30 días de cualquier cambio en los requisitos de hardware. Los requisitos modificados más recientemente se marcan con **\*** . 

## <a name="check-hardware-requirements"></a>Comprobar requisitos de hardware

Además de revisar las especificaciones del dispositivo, también puedes usar el control de evaluación de preparación descargable para comprobar que un dispositivo determinado cumple los requisitos necesarios. [](../get-ready/readiness-assessment-downloadable.md) Esta herramienta también comprueba la configuración de red y los puntos de conexión que también son necesarios para que el servicio funcione.

## <a name="minimum-requirements"></a>Requisitos mínimos

Para inscribirse en Escritorio administrado de Microsoft, un dispositivo debe cumplir o superar todos estos requisitos.

### <a name="manufacturer"></a>Fabricante

El dispositivo debe haber sido creado por uno de estos fabricantes:

- Dell
- HP
- Lenovo
- Microsoft


### <a name="installed-software"></a>Software instalado

El dispositivo debe tener preinstalado este software:

- Windows 10 Enterprise, Pro o Pro workstation edition
- la versión de 64 bits de Aplicaciones Microsoft 365 para empresas 
- Todos los controladores de dispositivo aplicables


### <a name="physical-features"></a>Características físicas

Los dispositivos deben tener estas capacidades:

- Habilitado para el arranque seguro de UEFI 
- Módulo de plataforma de confianza 2.0 
- Compatible con la seguridad basada en virtualización 
- [Integridad de código protegida por hipervisor](/windows-hardware/drivers/bringup/device-guard-and-credential-guard) compatible con el BIOS

Para obtener más información sobre estas capacidades y las tecnologías relacionadas con ellas que usa el servicio, [vea Escritorio administrado de Microsoft technologies](../intro/technologies.md).

> [!NOTE]
> ARM procesadores no son compatibles.

Los dispositivos deben cumplir o superar los siguientes límites de almacenamiento y memoria:

- La unidad de arranque debe ser de cualquier tipo que no sea un disco duro. Por ejemplo, las unidades SSD, NVMe y eMMC son opciones válidas.
- La unidad de arranque debe tener una capacidad de al menos 128 GB.
- La memoria interna del dispositivo (RAM) debe ser igual o superior a 8 GB.

Si el dispositivo se hizo después del 1 de julio de 2020, también debe tener una cámara IR, un lector de huellas digitales o ambos, para admitir Windows [Hello](/windows-hardware/design/device-experiences/windows-hello-enhanced-sign-in-security).

## <a name="recommended-features"></a>Características recomendadas

Los usuarios tendrán una experiencia mucho mejor si eliges dispositivos que tengan estas características:

- Un procesador intel vPro-platform o un procesador amd ryzen Pro procesador
- Unidad de arranque del tipo SSD con una capacidad de al menos 256 GB
- Memoria de dispositivo interna (RAM) de al menos 16 GB
- Compatibilidad con espera moderna
- El dispositivo es de tipo PC de núcleo seguro
- Admite protección de kernel DMA
