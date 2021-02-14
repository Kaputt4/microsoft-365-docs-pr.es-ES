---
title: Requisitos de seguridad de red adicionales para Office 365 GCC High y DoD
ms.author: dzazzo
author: dzazzo
manager: dzazzo
ms.date: 05/19/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: Adm_O365
search.appverid:
- OGA150m
- OGC150
- OGD150
- MOE150
ms.assetid: ''
description: 'Resumen: Office 365 GCC High y DoD tienen requisitos de seguridad de red adicionales'
hideEdit: true
ms.openlocfilehash: 4817edfcea638324e26eb855d1ea33936be1bfb4
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693915"
---
# <a name="additional-network-security-requirements-for-office-365-gcc-high-and-dod"></a>Requisitos de seguridad de conexión de red adicionales para Office 365 GCC High y DOD

*Este artículo se aplica a Office 365 GCC High, Office 365 DOD, Microsoft 365 GCC High y Microsoft 365 DOD.*

Office 365 GCC High y DOD son entornos de nube seguros para satisfacer las necesidades del Gobierno de los Estados Unidos y sus proveedores y contratistas.  Estos entornos de nube tienen restricciones de red adicionales a los puntos de conexión externos a los que los servicios tienen permiso de acceso.

Los clientes de GCC High y DOD que planean usar identidades federadas o coexistencia híbrida pueden requerir que Microsoft permita el acceso entrante y/o saliente a las implementaciones locales existentes.  Algunos ejemplos de estas actividades son:

* Uso de identidades federadas (con servicios de federación de Active Directory o STS admitidos similares)
* Coexistencia híbrida con una implementación local Exchange Server o Skype Empresarial
* Migración de contenido de usuario existente desde un sistema local

Para permitir que el servicio se comunique con  los puntos de conexión locales, debe enviar un correo electrónico a los ingenieros de Office 365 para realizar cambios en la red.

> [!WARNING]
> Todas las solicitudes tienen **un** SLA de tres semanas y no se pueden acelerar debido a los controles de seguridad y cumplimiento necesarios y a las canalizaciones de implementación.  Esto incluye las solicitudes de red de incorporación iniciales, así como cualquier cambio después de migrar al servicio.  Asegúrese de que los equipos de red son conscientes de esta escala de tiempo e inscluyéndola en sus ciclos de planeación.

Envíe un correo electrónico a la lista [blanca de Office 365 Government Network](mailto:o365gwlt@microsoft.com) con la siguiente información:

* **Para:** Lista blanca de red de Office [365 Administración Pública](mailto:o365gwlt@microsoft.com)
* **Desde**: Un administrador de inquilinos: el correo electrónico de **envío debe coincidir** con un contacto de administrador global en su espacio empresarial
* **Asunto del correo** electrónico: Solicitud de red alta GCC de Office 365: contoso.onmicrosoft.us (reemplace esto por el nombre de su espacio empresarial)

El cuerpo del mensaje debe incluir los siguientes datos:

* Su Microsoft Online Services inquilino (es decir, contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)
* Una lista de distribución de correo electrónico con la que Microsoft se comunicará para comunicaciones en marcha relacionadas con cambios en la red o seguimiento de subredes no válidas
* Indicar si tiene previsto usar la coexistencia híbrida de Microsoft Teams con las implementaciones locales
* Dirección URL de acceso externo del sistema de identidad federada (por ejemplo, sts.contoso.com) e intervalo de direcciones IP en notación CIDR (por ejemplo, 10.1.1.0/28)
* Dirección URL de lista de revocación de certificados PKI locales e intervalo de direcciones IP en notación CIDR
* Dirección URL de acceso externo e intervalo de direcciones IP para Exchange Server implementación local en notación CIDR
* Url de acceso externo e intervalo de direcciones IP para la implementación local de Skype Empresarial en notación CIDR

Por motivos de seguridad y cumplimiento, tenga en cuenta las siguientes restricciones en su solicitud:

* Hay una limitación de cuatro subredes por inquilino
* Las subredes deben estar en notación CIDR (por ejemplo, 10.1.1.0/28)
* Los intervalos de subredes no pueden ser superiores a /24
* No **podemos dar** cabida a solicitudes para permitir el acceso a los servicios en la nube comerciales (comercial Office 365, Google G-Suite, Amazon Web Services, etc.)

Una vez que Microsoft ha recibido y aprobado la solicitud, hay un SLA de tres semanas para la implementación y no se puede acelerar.  Recibirá un acuse de recibo inicial cuando hayamos recibido su solicitud y una confirmación final una vez que se haya completado.
