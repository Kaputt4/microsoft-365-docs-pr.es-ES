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
description: 'Resumen: comprender la resistencia de datos en Microsoft Office 365.'
ms.openlocfilehash: 89f3fbcc90cee0ad822156014ee4ac9e04fe3371
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2021
ms.locfileid: "50058553"
---
# <a name="service-encryption"></a>Cifrado de servicio

Además de usar el cifrado a nivel de volumen, Exchange Online, Microsoft Teams, SharePoint Online y OneDrive para la Empresa también usan cifrado de servicio para cifrar los datos de los clientes. Cifrado de servicio permite dos opciones de administración de claves:

## <a name="microsoft-managed-keys"></a>Claves administradas por Microsoft
Microsoft administra todas las claves criptográficas, incluidas las claves raíz del cifrado de servicio. Esta opción está habilitada de forma predeterminada para Exchange Online, SharePoint Online, OneDrive para la Empresa. Las claves administradas por Microsoft proporcionan cifrado de servicio predeterminado a menos que decida incorporarse con la clave de cliente. Si, en una fecha posterior, decide dejar de usar la clave de cliente sin seguir la ruta de depuración de datos, los datos permanecerán cifrados con las claves administradas por Microsoft. Los datos siempre están cifrados en este nivel predeterminado como mínimo. 

## <a name="customer-key"></a>Clave de cliente
Proporciona claves raíz usadas con el cifrado de servicio y administra estas claves con Azure Key Vault. Microsoft administra todas las demás claves. Esta opción se denomina Clave de cliente y actualmente está disponible para Exchange Online, SharePoint Online y OneDrive para la Empresa. (Anteriormente denominado Cifrado avanzado con BYOK. Vea [Mejorar la transparencia y el control para Office 365 clientes para](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) el anuncio original).

El cifrado de servicio proporciona varias ventajas:

- Proporciona una capa de protección adicional en la parte superior de BitLocker.

- Proporciona la separación Windows administradores del sistema operativo del acceso a los datos de la aplicación almacenados o procesados por el sistema operativo.

- Incluye una opción de clave de cliente que permite a los servicios multiinquilino proporcionar administración de claves por inquilino.

- Mejora la capacidad de los Microsoft 365 satisfacer las demandas de los clientes que tienen requisitos de cumplimiento específicos con respecto al cifrado.

Con la clave de cliente, puede generar sus propias claves criptográficas mediante un módulo de servicio de hardware (HSM) local o Azure Key Vault (AKV). Independientemente de cómo genere la clave, use AKV para controlar y administrar las claves criptográficas usadas por Office 365. Una vez que las claves se almacenan en AKV, se pueden usar como la raíz de uno de los llaveros que cifra los datos o archivos del buzón.

Otra ventaja de la clave de cliente es el control que tiene sobre la capacidad de Microsoft para procesar los datos. Si desea quitar datos de Office 365, como si desea finalizar el servicio con Microsoft o quitar una parte de los datos almacenados en la nube, puede hacerlo y usar la clave de cliente como control técnico. La eliminación de datos garantiza que nadie, incluido Microsoft, pueda acceder o procesar los datos. La clave de cliente es adicional y complementaria a la caja de seguridad del cliente que se usa para controlar el acceso a los datos por parte del personal de Microsoft.

Para obtener información sobre cómo configurar la clave de cliente para Microsoft 365 para Exchange Online, Microsoft Teams, SharePoint Online, incluidos los sitios de grupo y OneDrive para la Empresa, vea estos artículos:

- [Cifrado de servicio con clave de cliente](customer-key-overview.md)

- [Configurar clave de cliente](customer-key-set-up.md)

- [Administrar clave de cliente](customer-key-manage.md)

- [Revertir o girar una clave de cliente o una clave de disponibilidad](customer-key-availability-key-roll.md)

- [Comprender la clave de disponibilidad](customer-key-availability-key-understand.md)
