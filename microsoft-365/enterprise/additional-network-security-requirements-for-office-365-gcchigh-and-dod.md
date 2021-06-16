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
ms.openlocfilehash: f4c03d364e84d89a1b12e4d858ab46eb3be6ae5e
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926564"
---
# <a name="additional-network-security-requirements-for-office-365-gcc-high-and-dod"></a>Requisitos de seguridad de conexión de red adicionales para Office 365 GCC High y DOD

*Este artículo se aplica a Office 365 GCC, Office 365 DOD, Microsoft 365 GCC High y Microsoft 365 DOD.*

Office 365 GCC High y DOD son entornos de nube seguros para satisfacer las necesidades del Gobierno de Los Estados Unidos y sus proveedores y contratistas.  Estos entornos en la nube tienen restricciones de red adicionales a las que los puntos de conexión externos a los servicios pueden tener acceso.

GCC Los clientes altos y dod que planean usar identidades federadas o coexistencia híbrida pueden requerir que Microsoft permita el acceso entrante y/o saliente a las implementaciones locales existentes.  Algunos ejemplos de estas actividades son:

* Uso de identidades federadas (con servicios de federación de Active Directory o STS compatibles similares)
* Coexistencia híbrida con una implementación Exchange Server o Skype Empresarial local
* Migración de contenido de usuario existente desde un sistema local

Para permitir que el servicio se comunique con  los puntos de conexión locales, debe enviar un correo electrónico a Office 365 ingeniería para los cambios de red.

> [!WARNING]
> Todas las solicitudes tienen **un** SLA de tres semanas y no se pueden acelerar debido a los controles de seguridad y cumplimiento requeridos y las canalizaciones de implementación.  Esto incluye solicitudes de red de incorporación iniciales, así como cualquier cambio después de migrar al servicio.  Asegúrese de que los equipos de red son conscientes de esta escala de tiempo e incluirla en sus ciclos de planeación.

Envíe un correo electrónico [a Office 365 Administración Pública Allow-List solicitudes](mailto:o365gwlt@microsoft.com) con la siguiente información:

* **To**: [Office 365 Administración Pública Allow-List Requests](mailto:o365gwlt@microsoft.com)
* **From**: A tenant administrator: the send email **must** match a Global Administrator contact in your tenant
* **Asunto de correo** electrónico: Office 365 GCC solicitud de red alta : contoso.onmicrosoft.us (reemplace por el nombre del inquilino)

El cuerpo del mensaje debe incluir los siguientes datos:

* Nombre Microsoft Online Services inquilino (por ejemplo, contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)
* Una lista de distribución de correo electrónico con la que Microsoft se comunicará para las comunicaciones en marcha relacionadas con los cambios de red o el seguimiento de subredes no válidas
* Indica si planeas usar la Microsoft Teams híbrida con las implementaciones locales
* Dirección URL accesible externamente del sistema de identidad federada (por ejemplo, sts.contoso.com) e intervalo de direcciones IP en la notación CIDR (por ejemplo, . 10.1.1.0/28)
* Dirección URL de lista de revocación de certificados PKI local e intervalo de direcciones IP en notación CIDR
* Dirección URL y intervalo de direcciones IP accesibles externamente para Exchange Server implementación local en notación CIDR
* Dirección URL y intervalo de direcciones IP accesibles externamente para Skype Empresarial implementación local en notación CIDR

Por motivos de seguridad y cumplimiento, tenga en cuenta las siguientes restricciones en su solicitud:

* Hay una limitación de cuatro subredes por inquilino
* Las subredes deben estar en notación CIDR (por ejemplo, 10.1.1.0/28)
* Los intervalos de subred no pueden ser mayores que /24
* No **podemos dar** cabida a solicitudes para permitir el acceso a servicios comerciales en la nube (Office 365 comerciales, Google G-Suite, Amazon Web Services, etc.)

Una vez que Microsoft ha recibido y aprobado la solicitud, hay un SLA de tres semanas para la implementación y no se puede acelerar.  Recibirá un acuse de recibo inicial cuando hayamos recibido su solicitud y un acuse de recibo final una vez que se haya completado.
