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
ms.localizationpriority: ''
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Resumen: comprender la resistencia de los datos en Microsoft Office 365.'
ms.openlocfilehash: f6967905c97f83fda2f73fc61ddf96a4a02fbec8
ms.sourcegitcommit: 23a53b5c5e372a2a7ad5e175850224d3d464f6dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2022
ms.locfileid: "67055996"
---
# <a name="service-encryption"></a>Cifrado de servicio

Además de usar el cifrado de nivel de volumen, Exchange Online, Microsoft Teams, SharePoint Online y OneDrive para la Empresa también usan El cifrado de servicio para cifrar los datos del cliente. Service Encryption permite dos opciones de administración de claves:

## <a name="microsoft-managed-keys"></a>Claves administradas por Microsoft
Microsoft administra todas las claves criptográficas, incluidas las claves raíz para el cifrado de servicios. Esta opción está habilitada actualmente de forma predeterminada para Exchange Online, SharePoint Online OneDrive para la Empresa. Las claves administradas por Microsoft proporcionan cifrado de servicio predeterminado a menos que decida incorporarlas mediante la clave de cliente. Si, en una fecha posterior, decide dejar de usar la clave de cliente sin seguir la ruta de acceso de purga de datos, los datos permanecen cifrados mediante las claves administradas por Microsoft. Los datos siempre se cifran en este nivel predeterminado como mínimo.

## <a name="customer-key"></a>Clave de cliente
Proporcione las claves raíz que se usan con el cifrado de servicio y administre estas claves mediante Azure Key Vault. Microsoft administra todas las demás claves. Esta opción se denomina Clave de cliente y está disponible actualmente para Exchange Online, SharePoint Online y OneDrive para la Empresa. (Anteriormente denominado Cifrado avanzado con BYOK. Consulte [Mejora de la transparencia y el control de los clientes Office 365](https://www.microsoft.com/en-us/microsoft-365/blog/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) para ver el anuncio original).

El cifrado de servicio proporciona varias ventajas:

- Proporciona una capa de protección agregada sobre BitLocker.

- Proporciona la separación de los administradores del sistema operativo Windows del acceso a los datos de la aplicación almacenados o procesados por el sistema operativo.

- Incluye una opción clave de cliente que permite que los servicios multiinquilino proporcionen administración de claves por inquilino.

- Mejora la capacidad de Microsoft 365 para satisfacer las demandas de los clientes que tienen requisitos de cumplimiento específicos con respecto al cifrado.

Con la clave de cliente, puede generar sus propias claves criptográficas mediante un módulo de servicio de hardware (HSM) local o Azure Key Vault (AKV). Independientemente de cómo genere la clave, use AKV para controlar y administrar las claves criptográficas usadas por Office 365. Una vez que las claves se almacenan en AKV, se pueden usar como raíz de una de las cadenas de claves que cifra los archivos o los datos del buzón.

Otra ventaja de la clave de cliente es el control que tiene sobre la capacidad de Microsoft para procesar los datos. Si desea quitar datos de Office 365, como si desea finalizar el servicio con Microsoft o quitar una parte de los datos almacenados en la nube, puede hacerlo y usar clave de cliente como control técnico. La eliminación de datos garantiza que nadie, incluido Microsoft, pueda acceder a los datos ni procesarlos. La clave de cliente es adicional y complementaria a la caja de seguridad del cliente que se usa para controlar el acceso a los datos por parte del personal de Microsoft.

Para obtener información sobre cómo configurar la clave de cliente para Microsoft 365 para Exchange Online, Microsoft Teams, SharePoint Online, incluidos los sitios de equipo y OneDrive para la Empresa, consulte estos artículos:

- [Cifrado de servicio con clave de cliente](customer-key-overview.md)

- [Configuración de la clave de cliente](customer-key-set-up.md)

- [Administrar clave de cliente](customer-key-manage.md)

- [Reversión o rotación de una clave de cliente o una clave de disponibilidad](customer-key-availability-key-roll.md)

- [Descripción de la clave de disponibilidad](customer-key-availability-key-understand.md)
