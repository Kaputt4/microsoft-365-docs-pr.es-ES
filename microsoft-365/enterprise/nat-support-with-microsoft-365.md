---
title: Compatibilidad de NAT con Office 365
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 1/24/2017
audience: Admin
ms.topic: overview
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- BCS160
ms.assetid: 170e96ea-d65d-4e51-acac-1de56abe39b9
description: En este artículo se proporcionan detalles sobre cómo aproximar el número de clientes que puede usar por dirección IP de su organización mediante NAT.
ms.openlocfilehash: 74c202f9f1ce8550f05a107fac9237dfc86b724f
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67687183"
---
# <a name="nat-support-with-office-365"></a>Compatibilidad de NAT con Office 365

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Anteriormente, las instrucciones sugirieron que el número máximo de clientes de Exchange que debe usar por dirección IP para conectarse a Office 365 era de aproximadamente 2000 clientes por puerto de red.
  
## <a name="why-use-nat"></a>¿Por qué usar NAT?

Al usar NAT, miles de personas en una red corporativa pueden "compartir" algunas direcciones IP enrutables públicamente.
  
La mayoría de las redes corporativas usan espacio de direcciones IP privadas (RFC1918). El espacio de direcciones privadas es asignado por la Autoridad de Números Asignados por Internet (IANA) y está destinado únicamente a las redes que no enrutan directamente hacia y desde internet global.
  
Para proporcionar acceso a Internet a los dispositivos en un espacio de direcciones IP privadas, las organizaciones usan tecnologías de puerta de enlace, como firewalls y servidores proxy, que proporcionan servicios de traducción de direcciones de red (NAT) o traducción de direcciones de puerto (PAT). Estas puertas de enlace hacen que el tráfico desde dispositivos internos a Internet (incluidos los Office 365) parezca que procede de una o varias direcciones IP enrutables públicamente. Cada conexión saliente de un dispositivo interno se traduce en un puerto TCP de origen diferente en la dirección IP pública. 
  
## <a name="why-do-you-need-to-have-so-many-connections-open-to-office-365-at-the-same-time"></a>¿Por qué necesita tener tantas conexiones abiertas para Office 365 al mismo tiempo?

Outlook puede abrir ocho o más conexiones (en situaciones en las que hay complementos, calendarios compartidos, buzones, etc.). Dado que hay un máximo de 64 000 puertos disponibles en un dispositivo NAT basado en Windows, puede haber un máximo de 8000 usuarios detrás de una dirección IP antes de que se agoten los puertos. Tenga en cuenta que si los clientes usan dispositivos que no están basados en el sistema operativo Windows para NAT, el total de puertos disponibles depende del dispositivo o software NAT que se use. En este escenario, el número máximo de puertos podría ser inferior a 64 000. La disponibilidad de los puertos también se ve afectada por otros factores, como que Windows restrinja 4000 puertos para su propio uso, lo que reduce el número total de puertos disponibles a 60 000. Puede haber otras aplicaciones, como Internet Explorer, que se puedan conectar al mismo tiempo, lo que requiere puertos adicionales.
  
## <a name="calculating-maximum-supported-devices-behind-a-single-public-ip-address-with-office-365"></a>Cálculo del número máximo de dispositivos admitidos detrás de una única dirección IP pública con Office 365

Para determinar el número máximo de dispositivos detrás de una única dirección IP pública, debe supervisar el tráfico de red para determinar el consumo máximo de puertos por cliente. Además, se debe usar un factor máximo para el uso del puerto (mínimo 4). 
  
 **Use la siguiente fórmula para calcular el número de dispositivos admitidos por dirección IP:**
  
Número máximo de dispositivos admitidos detrás de una única dirección IP pública = (64 000 - puertos restringidos)/(Consumo máximo de puertos + factor máximo)
  
 **Por ejemplo, si se cumple lo siguiente:**
  
- **Puertos restringidos:** 4000 para el sistema operativo

- **Consumo máximo de puertos:** 6 por dispositivo

- **Factor máximo:** 4

A continuación, el número máximo de dispositivos admitidos detrás de una única dirección IP pública = (64 000 - 4 000)/(6 + 4) = 6000
  
Con la versión de Office 365 paquete de hospedaje, incluida en las actualizaciones de septiembre de 2011 para Microsoft Office Outlook 2007, o noviembre de 2011 para Microsoft Outlook 2010, o una actualización posterior, el número de conexiones desde Outlook (tanto Office Outlook 2007 con Service Pack 2 como Outlook 2010) a Exchange puede ser tan solo 2. Tendrá que tener en cuenta los diferentes sistemas operativos, comportamientos de usuario, etc. para determinar el número mínimo y máximo de puertos que la red necesitará en el pico.
  
Si desea admitir más dispositivos detrás de una única dirección IP pública, siga los pasos descritos para evaluar el número máximo de dispositivos que se pueden admitir:
  
Supervise el tráfico de red para determinar el consumo máximo de puertos por cliente. Debe recopilar estos datos:
  
- Desde varias ubicaciones
    
- Desde varios dispositivos
    
- En varias ocasiones
    
Use la fórmula anterior para calcular el número máximo de usuarios por dirección IP que se pueden admitir en su entorno.
  
Hay varios métodos para distribuir la carga de cliente entre direcciones IP públicas adicionales. Las estrategias disponibles dependen de las funcionalidades de la solución de puerta de enlace corporativa. La solución más sencilla es segmentar el espacio de direcciones de usuario y "asignar" estáticamente un número de direcciones IP a cada puerta de enlace. Otra alternativa que ofrecen muchos dispositivos de puerta de enlace es la capacidad de usar un grupo de direcciones IP. La ventaja del grupo de direcciones es que es mucho más dinámico y menos probable que requiera ajustes a medida que crece la base de usuarios.
  
## <a name="see-also"></a>Vea también

[Administrar puntos de conexión de Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[Preguntas frecuentes sobre extremos de Office 365](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)
