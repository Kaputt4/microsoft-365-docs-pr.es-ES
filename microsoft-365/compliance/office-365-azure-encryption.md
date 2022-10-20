---
title: Cifrado en Azure
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: ''
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- purview-compliance
- tier3
- Strat_O365_Enterprise
description: Obtenga información sobre el cifrado disponible en Azure, como Azure Disk Encryption.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b320fdf7125746e6ad7c4b4d3fa6e70d8d757ac7
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68630850"
---
# <a name="encryption-in-azure"></a>Cifrado en Azure

Las medidas de seguridad tecnológicas en Azure, como las comunicaciones cifradas y los procesos operativos, ayudan a proteger los datos. También tiene la flexibilidad de implementar características de cifrado adicionales y administrar sus propias claves criptográficas. Independientemente de la configuración del cliente, Microsoft aplica el cifrado para proteger los datos de los clientes en Azure. Microsoft también le permite controlar los datos hospedados en Azure a través de una gama de tecnologías avanzadas para cifrar, controlar y administrar claves criptográficas, y controlar y auditar el acceso a los datos. Además, Azure Storage proporciona un conjunto completo de funcionalidades de seguridad que, en conjunto, permiten a los desarrolladores crear aplicaciones seguras.

Azure ofrece muchos mecanismos para proteger los datos a medida que se mueven de una ubicación a otra. Microsoft usa TLS para proteger los datos cuando viajan entre los servicios en la nube y los clientes. Los centros de datos de Microsoft negocian una conexión TLS con sistemas cliente que se conectan a los servicios de Azure. Perfect Forward Secrecy (PFS) protege las conexiones entre los sistemas cliente de los clientes y los servicios en la nube de Microsoft mediante claves únicas. Las conexiones también usan longitudes de clave de cifrado de 2.048 bits basadas en RSA. Esta combinación dificulta que alguien intercepte y acceda a los datos que están en tránsito.

Los datos se pueden proteger en tránsito entre una aplicación y Azure mediante [el cifrado del lado cliente](/azure/storage/storage-client-side-encryption), HTTPS o SMB 3.0. Puede habilitar el cifrado para el tráfico entre sus propias máquinas virtuales (VM) y los usuarios. Con [Azure Virtual Networks](https://azure.microsoft.com/services/virtual-network/), puede usar el protocolo IPsec estándar del sector para cifrar el tráfico entre la puerta de enlace de VPN corporativa y Azure, así como entre las máquinas virtuales ubicadas en la red virtual.

En el caso de los datos en reposo, Azure ofrece muchas opciones de cifrado, como la compatibilidad con AES-256, lo que le ofrece la flexibilidad de elegir el escenario de almacenamiento de datos que mejor se adapte a sus necesidades. Los datos se pueden cifrar automáticamente cuando se escriben en Azure Storage mediante [Storage Service Encryption](/azure/storage/storage-service-encryption), y el sistema operativo y los discos de datos usados por las máquinas virtuales se pueden cifrar. Para obtener más información, consulte [Recomendaciones de seguridad para máquinas virtuales Windows en Azure](/azure/virtual-machines/security-recommendations). Además, el acceso delegado a los objetos de datos de Azure Storage se puede conceder mediante [firmas de acceso compartido](/azure/storage/storage-dotnet-shared-access-signature-part-1). Azure también proporciona cifrado de datos en reposo mediante [cifrado de datos transparente para Azure SQL Database y Data Warehouse](/sql/relational-databases/security/encryption/transparent-data-encryption-azure-sql).

Para obtener más información sobre el cifrado en Azure, consulte [Introducción al cifrado de Azure](/azure/security/security-azure-encryption-overview) y [Azure Data Encryption-at-Rest](/azure/security/azure-security-encryption-atrest).

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="azure-disk-encryption"></a>Azure Disk Encryption

Azure Disk Encryption le permite cifrar los discos de máquina virtual de infraestructura como servicio (IaaS) de Windows y Linux. Azure Disk Encryption aprovecha la característica BitLocker de Windows y la característica de DM-Crypt de Linux para proporcionar cifrado de nivel de volumen para el sistema operativo y los discos de datos. También garantiza que todos los datos de los discos de máquina virtual se cifran en reposo en el almacenamiento de Azure. Azure Disk Encryption se integra con Azure कि भल्ट para ayudarle a controlar, administrar y auditar el uso de las claves de cifrado y los secretos.

Para obtener más información, consulte [Recomendaciones de seguridad para máquinas virtuales Windows en Azure](/azure/virtual-machines/windows/security-recommendations).

## <a name="azure-storage-service-encryption"></a>Cifrado del servicio Azure Storage

Con [Azure Storage Service Encryption](/azure/storage/storage-service-encryption), Azure Storage cifra automáticamente los datos antes de guardarlos en el almacenamiento y descifra los datos antes de la recuperación. Los procesos de cifrado, descifrado y administración de claves son totalmente transparentes para los usuarios. Azure Storage Service Encryption se puede usar para [Azure Blob Storage](https://azure.microsoft.com/services/storage/blobs/) y [Azure Files](https://azure.microsoft.com/services/storage/files/). También puede usar claves de cifrado administradas por Microsoft con Azure Storage Service Encryption o puede usar sus propias claves de cifrado. (Para obtener información sobre el uso de sus propias claves, consulte [Storage Service Encryption using customer managed keys in Azure कि भल्ट (Cifrado del servicio de almacenamiento mediante claves administradas por el cliente en Azure कि भल्ट](/azure/storage/common/storage-service-encryption-customer-managed-keys)). Para obtener información sobre el uso de claves administradas por Microsoft, consulte [Storage Service Encryption for Data at Rest](/azure/storage/storage-service-encryption)).) Además, puede automatizar el uso del cifrado. Por ejemplo, puede habilitar o deshabilitar mediante programación Storage Service Encryption en una cuenta de almacenamiento mediante la [API REST del proveedor de recursos de Azure Storage](/rest/api/storagerp/), la [biblioteca cliente del proveedor de recursos de almacenamiento para .NET](/dotnet/api/overview/azure/storage), [Azure PowerShell](/powershell/azureps-cmdlets-docs) o la [CLI de Azure](/azure/storage/storage-azure-cli).

Algunos servicios de Microsoft 365 usan Azure para almacenar datos. Por ejemplo, SharePoint Online y OneDrive para la Empresa almacenan datos en Azure Blob Storage y Microsoft Teams almacena datos para su servicio de chat en tablas, blobs y colas. Además, la característica Administrador de cumplimiento de la portal de cumplimiento Microsoft Purview almacena los datos especificados por el cliente que se almacenan en forma cifrada en [Azure Cosmos DB](/azure/cosmos-db/database-encryption-at-rest), una base de datos multimodelo de plataforma como servicio (PaaS), distribuida globalmente. Azure Storage Service Encryption cifra los datos almacenados en Azure Blob Storage y en tablas, y Azure Disk Encryption cifra los datos en las colas, así como los discos de máquina virtual De IaaS y Windows para proporcionar cifrado de volumen para el sistema operativo y el disco de datos. La solución garantiza que todos los datos de los discos de máquina virtual se cifran en reposo en el almacenamiento de Azure. [El cifrado en reposo en Azure Cosmos DB](/azure/cosmos-db/database-encryption-at-rest) se implementa mediante varias tecnologías de seguridad, incluidos sistemas de almacenamiento de claves seguros, redes cifradas y API criptográficas.

## <a name="azure-key-vault"></a>Azure Key Vault

La administración segura de claves no es solo el núcleo de los procedimientos recomendados de cifrado; también es esencial para proteger los datos en la nube. [Azure कि भल्ट](/azure/key-vault/key-vault-whatis) permite cifrar claves y secretos pequeños, como contraseñas que usan claves almacenadas en módulos de seguridad de hardware (HSM). Azure कि भल्ट es la solución recomendada de Microsoft para administrar y controlar el acceso a las claves de cifrado que usan los servicios en la nube. Los permisos para acceder a las claves se pueden asignar a servicios o a usuarios con cuentas de Azure Active Directory. Azure कि भल्ट alivia a las organizaciones de la necesidad de configurar, aplicar revisiones y mantener HSM y software de administración de claves. Con Azure कि भल्ट, Microsoft nunca ve que las claves y las aplicaciones no tienen acceso directo a ellas; mantiene el control. También puede importar o generar claves en HSM. Las organizaciones que tienen una suscripción que incluye Azure Information Protection pueden configurar su inquilino de Azure Information Protection para usar una clave administrada por el cliente [Bring Your Own Key](/information-protection/plan-design/byok-price-restrictions) (BYOK)) y [registrar su uso](/information-protection/deploy-use/log-analyze-usage).
