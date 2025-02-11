---
title: Requisitos de seguridad de red adicionales para Office 365 GCC High y DoD
ms.author: dzazzo
author: dzazzo
manager: dzazzo
ms.date: 05/19/2020
audience: ITPro
ms.topic: conceptual
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
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
ms.openlocfilehash: 90dae84ac9fb5144aaf6e3049dedfa8c27dd227b
ms.sourcegitcommit: 62368e5a48e569c8e475b07d194d7d8ff7d167ab
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2022
ms.locfileid: "67556290"
---
# <a name="additional-network-security-requirements-for-office-365-gcc-high-and-dod"></a>Requisitos de seguridad de conexión de red adicionales para Office 365 GCC High y DOD

*Este artículo se aplica a Office 365 GCC High, Office 365 DOD, Microsoft 365 GCC High y Microsoft 365 DOD.*

Office 365 GCC High y DOD son entornos en la nube seguros para satisfacer las necesidades del Estados Unidos Government y sus proveedores y contratistas.  Estos entornos en la nube tienen restricciones de red adicionales a las que se permite el acceso a los puntos de conexión externos a los servicios.

Los clientes de GCC High y DOD que planean usar identidades federadas o coexistencia híbrida pueden requerir que Microsoft permita el acceso entrante o saliente a las implementaciones locales existentes.  Algunos ejemplos de estas actividades son:

* Uso de identidades federadas (con Servicios de federación de Active Directory (AD FS) o STS compatible similar)
* Coexistencia híbrida con una implementación de Exchange Server o Skype Empresarial local
* Migración del contenido de usuario existente desde un sistema local

Para permitir que el servicio se comunique con los puntos de conexión locales, **debe** enviar un correo electrónico a Office 365 ingeniería para los cambios de red.

> [!WARNING]
> Todas las solicitudes tienen un acuerdo **de nivel de servicio de tres semanas** y no se pueden acelerar debido a los controles de seguridad y cumplimiento necesarios y a las canalizaciones de implementación.  Esto incluye las solicitudes de red de incorporación iniciales, así como los cambios después de haber migrado al servicio.  Asegúrese de que los equipos de red son conscientes de esta escala de tiempo e incluyéndola en sus ciclos de planeación.

Envíe un correo electrónico a [Office 365 Administración Pública Allow-List Solicitudes](mailto:o365gwlt@microsoft.com) con la siguiente información:

* **Para**: [solicitudes de Office 365 Administración Pública Allow-List](mailto:o365gwlt@microsoft.com)
* **Desde**: Un administrador de inquilinos: el correo electrónico **de envío debe** coincidir con un contacto de administrador global en el inquilino.
* **Email asunto**: Office 365 solicitud de alta red de GCC: contoso.onmicrosoft.us (reemplace por el nombre del inquilino)

El cuerpo del mensaje debe incluir los siguientes datos:

* Nombre del inquilino de Microsoft Online Services (por ejemplo, contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)
* Una lista de distribución de correo electrónico con la que Microsoft se comunicará para las comunicaciones continuas relacionadas con los cambios de red o el seguimiento de subredes no válidas
* Indique si tiene previsto usar la coexistencia híbrida de Microsoft Teams con las implementaciones locales.
* Dirección URL accesible externamente del sistema de identidad federada (por ejemplo, sts.contoso.com) y intervalo de direcciones IP en notación CIDR (por ejemplo, ). 10.1.1.0/28)
* Dirección URL de lista de revocación de certificados PKI local e intervalo de direcciones IP en notación CIDR
* Dirección URL y intervalo de direcciones IP accesibles externamente para Exchange Server implementación local en notación CIDR
* Dirección URL y intervalo de direcciones IP accesibles externamente para Skype Empresarial implementación local en notación CIDR

Por motivos de seguridad y cumplimiento, tenga en cuenta las siguientes restricciones en su solicitud:

* Hay una limitación de cuatro subredes por inquilino
* Las subredes deben estar en notación CIDR (por ejemplo, 10.1.1.0/28)
* Los intervalos de subred no pueden ser mayores que /24
* **No podemos** dar cabida a solicitudes para permitir el acceso a servicios en la nube comerciales (Office 365 comerciales, Google G-Suite, Amazon Web Services, etc.)

Una vez que Microsoft ha recibido y aprobado la solicitud, hay un Acuerdo de Nivel de Servicio de tres semanas para la implementación y no se puede acelerar.  Recibirá una confirmación inicial cuando hayamos recibido su solicitud y una confirmación final una vez que se haya completado.
