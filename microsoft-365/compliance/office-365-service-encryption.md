---
title: Cifrado de servicio
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
description: 'Resumen: comprenda la resistencia de datos en Microsoft Office 365.'
ms.openlocfilehash: 89f3fbcc90cee0ad822156014ee4ac9e04fe3371
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2021
ms.locfileid: "50058553"
---
# <a name="service-encryption"></a>Cifrado de servicio

Además de usar el cifrado de nivel de volumen, Exchange Online, Microsoft Teams, SharePoint Online y OneDrive para la Empresa también usan el cifrado de servicio para cifrar los datos de los clientes. El cifrado de servicio permite dos opciones de administración de claves:

## <a name="microsoft-managed-keys"></a>Claves administradas por Microsoft
Microsoft administra todas las claves criptográficas, incluidas las claves raíz para el cifrado del servicio. Esta opción está habilitada actualmente de forma predeterminada para Exchange Online, SharePoint Online y OneDrive para la Empresa. Las claves administradas por Microsoft proporcionan cifrado de servicio predeterminado a menos que decida incorporar con la clave de cliente. Si, en una fecha posterior, decide dejar de usar la clave de cliente sin seguir la ruta de depuración de datos, los datos permanecen cifrados con las claves administradas por Microsoft. Los datos siempre se cifran en este nivel predeterminado como mínimo. 

## <a name="customer-key"></a>Clave de cliente
Las claves raíz que se usan con el cifrado de servicio se suministran y se administran mediante Azure Key Vault. Microsoft administra el resto de claves. Esta opción se denomina clave de cliente y actualmente está disponible para Exchange Online, SharePoint Online y OneDrive para la Empresa. (Anteriormente denominado cifrado avanzado con BYOK. Consulte Mejorar la transparencia y el control para los clientes de [Office 365](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) para el anuncio original).

El cifrado de servicio proporciona varias ventajas:

- Proporciona una capa de protección adicional sobre BitLocker.

- Proporciona una separación entre los administradores del sistema operativo Windows y el acceso a los datos de la aplicación almacenados o procesados por el sistema operativo.

- Incluye una opción de clave de cliente que permite que los servicios multiinquilino proporcionen administración de claves por inquilino.

- Mejora la capacidad de Microsoft 365 para satisfacer las demandas de los clientes que tienen requisitos de cumplimiento específicos relacionados con el cifrado.

Con la clave de cliente, puede generar sus propias claves criptográficas mediante un módulo de servicio de hardware (MATE) local o Azure Key Vault (AKV). Independientemente de cómo genere la clave, use AKV para controlar y administrar las claves criptográficas que usa Office 365. Una vez que las claves se almacenan en AKV, se pueden usar como la raíz de una de las cadenas de claves que cifra los archivos o datos del buzón.

Otra ventaja de la clave de cliente es el control que tiene sobre la capacidad de Microsoft para procesar los datos. Si desea quitar datos de Office 365, como si desea finalizar el servicio con Microsoft o quitar una parte de los datos almacenados en la nube, puede hacerlo y usar la clave de cliente como control técnico. La eliminación de datos garantiza que nadie, incluido Microsoft, pueda acceder o procesar los datos. La clave de cliente es además y complementaria de la Caja de seguridad del cliente que se usa para controlar el acceso a los datos por parte del personal de Microsoft.

Para obtener información sobre cómo configurar la clave de cliente para Microsoft 365 para Exchange Online, Microsoft Teams, SharePoint Online, incluidos los sitios de grupo y OneDrive para la Empresa, vea estos artículos:

- [Cifrado de servicio con clave de cliente](customer-key-overview.md)

- [Configurar la clave de cliente](customer-key-set-up.md)

- [Administrar clave de cliente](customer-key-manage.md)

- [Roll or rotate a customer key or an availability key](customer-key-availability-key-roll.md)

- [Comprender la clave de disponibilidad](customer-key-availability-key-understand.md)
