---
title: Cifrado de servicio de Office 365
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.date: 10/3/2019
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Resumen: comprenda la resistencia de los datos en Microsoft Office 365.'
ms.openlocfilehash: ec7f794a62a910fadaece890cf73451644d44109
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42071117"
---
# <a name="office-365-service-encryption"></a>Cifrado de servicio de Office 365

Además de usar el cifrado de nivel de volumen, Exchange Online, Skype empresarial, SharePoint Online y OneDrive para la empresa también usan el cifrado de servicio para cifrar los datos de los clientes. El cifrado del servicio permite dos opciones de administración de claves:

- Microsoft administra todas las claves de cifrado. (Esta opción está disponible actualmente en SharePoint Online, OneDrive para la empresa y Skype empresarial).

- El cliente suministra claves raíz que se usan con el cifrado de servicio y el cliente administra estas claves mediante Azure Key Vault. Microsoft administra todas las demás claves. Esta opción se denomina clave de cliente y actualmente está disponible para Exchange Online, SharePoint Online y OneDrive para la empresa. (Anteriormente denominado cifrado avanzado con BYOK. Consulte [mejorar la transparencia y el control para clientes de Office 365](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) para el anuncio original).

El cifrado de servicio ofrece varias ventajas. Por ejemplo, clave de cliente:

- Proporciona características de protección y administración de derechos sobre la protección de cifrado de alta seguridad.

- Incluye una opción de clave de cliente que permite que los servicios multiinquilinos proporcionen administración de claves por espacio empresarial.

- Proporciona la separación de los administradores del sistema operativo Windows del acceso a los datos de clientes almacenados o procesados por el sistema operativo.

- Mejora la capacidad de Office 365 para satisfacer las demandas de los clientes que tienen requisitos de cumplimiento relacionados con el cifrado.

## <a name="customer-key"></a>Clave del cliente

Mediante la clave de cliente, puede generar sus propias claves criptográficas mediante un módulo de servicio de hardware (HSM) local o Azure Key Vault (AKV). Independientemente de cómo genere la clave, use AKV para controlar y administrar las claves criptográficas que usa Office 365. Una vez que las claves se almacenan en AKV, se pueden usar como la raíz de una de las llaves que cifran los archivos o datos de buzones de correo.

Otra ventaja de la clave de cliente es el control que tiene sobre la posibilidad de que Microsoft procese sus datos. Si desea quitar datos de Office 365, por ejemplo, si desea finalizar el servicio con Microsoft o quitar una parte de los datos almacenados en la nube, puede hacerlo y usar la clave de cliente como control técnico. Esto garantiza que nadie, incluido Microsoft, puede tener acceso a los datos o procesarlos. La clave de cliente es adicional y complemental a la caja de caja del cliente que se usa para controlar el acceso a los datos por parte del personal de Microsoft.

Para obtener información sobre cómo configurar la clave de cliente de Office 365 para Exchange Online, Skype empresarial, SharePoint Online, incluidos los sitios de grupo y OneDrive para la empresa, consulte estos artículos:

- [Cifrado de servicios con clave de cliente en Office 365](customer-key-overview.md)

- [Configurar la clave de cliente de Office 365](customer-key-set-up.md)

- [Administrar la clave de cliente de Office 365](customer-key-manage.md)

- [Rollo o rotación de una clave de cliente o una clave de disponibilidad](customer-key-availability-key-roll.md)

- [Descripción de la clave de disponibilidad](customer-key-availability-key-understand.md)
 
