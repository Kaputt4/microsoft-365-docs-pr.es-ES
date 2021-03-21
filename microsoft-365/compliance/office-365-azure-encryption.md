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
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: Obtenga información sobre el cifrado disponible en Azure, como Azure Disk Encryption
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ee4eb2bec814d7e06d418518bb9be272f1bd5aaa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926258"
---
# <a name="encryption-in-azure"></a>Cifrado en Azure

Las protecciones tecnológicas en Azure, como las comunicaciones cifradas y los procesos operativos, ayudan a mantener los datos seguros. También tiene la flexibilidad de implementar características de cifrado adicionales y administrar sus propias claves criptográficas. Independientemente de la configuración del cliente, Microsoft aplica el cifrado para proteger los datos de los clientes en Azure. Microsoft también le permite controlar los datos hospedados en Azure a través de una amplia variedad de tecnologías avanzadas para cifrar, controlar y administrar claves criptográficas y controlar y auditar el acceso a los datos. Además, Azure Storage proporciona un conjunto completo de funcionalidades de seguridad que, en conjunto, permiten a los desarrolladores crear aplicaciones seguras.

Azure ofrece muchos mecanismos para proteger los datos a medida que se mueve de una ubicación a otra. Microsoft usa TLS para proteger los datos cuando se desplazan entre los servicios en la nube y los clientes. Los centros de datos de Microsoft negocian una conexión TLS con sistemas cliente que se conectan a los servicios de Azure. Perfect Forward Secrecy (PFS) protege las conexiones entre los sistemas cliente de los clientes y los servicios en la nube de Microsoft mediante claves únicas. Las conexiones también usan longitudes de clave de cifrado basadas en RSA de 2.048 bits. Esta combinación hace que sea difícil para alguien interceptar y acceder a los datos que están en tránsito.

Los datos se pueden proteger en tránsito entre una aplicación y Azure mediante el cifrado del lado [cliente,](/azure/storage/storage-client-side-encryption)HTTPS o SMB 3.0. Puede habilitar el cifrado para el tráfico entre sus propias máquinas virtuales (VM) y los usuarios. Con [Azure Virtual Networks,](https://azure.microsoft.com/services/virtual-network/)puede usar el protocolo IPsec estándar del sector para cifrar el tráfico entre la puerta de enlace VPN corporativa y Azure, así como entre las máquinas virtuales ubicadas en la red virtual.

Para los datos en reposo, Azure ofrece muchas opciones de cifrado, como la compatibilidad con AES-256, lo que le ofrece la flexibilidad para elegir el escenario de almacenamiento de datos que mejor se adapte a sus necesidades. Los datos se pueden cifrar automáticamente cuando se escriben en Azure Storage mediante el cifrado del servicio de almacenamiento [y](/azure/storage/storage-service-encryption)los discos de datos y del sistema operativo usados por las máquinas virtuales se pueden cifrar. Para obtener más información, vea [Security recommendations for Windows virtual machines in Azure](/azure/security/azure-security-disk-encryption). Además, se puede conceder acceso delegado a objetos de datos en Azure Storage mediante [firmas de acceso compartido.](/azure/storage/storage-dotnet-shared-access-signature-part-1) Azure también proporciona cifrado para los datos en reposo mediante el cifrado de datos transparente para Azure SQL Base de datos [y almacén de datos](/sql/relational-databases/security/encryption/transparent-data-encryption-azure-sql).

Para obtener más información sobre el cifrado en Azure, vea [Azure encryption overview](/azure/security/security-azure-encryption-overview) y Azure Data [Encryption-at-Rest](/azure/security/azure-security-encryption-atrest).

## <a name="azure-disk-encryption"></a>Cifrado de disco de Azure

Azure Disk Encryption permite cifrar los discos de vm de Infraestructura de Windows y Linux como servicio (IaaS). Azure Disk Encryption aprovecha la característica BitLocker de Windows y la característica DM-Crypt de Linux para proporcionar cifrado de nivel de volumen para el sistema operativo y los discos de datos. También garantiza que todos los datos de los discos de máquina virtual se cifran en reposo en el almacenamiento de Azure. Azure Disk Encryption se integra con Azure Key Vault para ayudarle a controlar, administrar y auditar el uso de las claves y secretos de cifrado.

Para obtener más información, vea [Security recommendations for Windows virtual machines in Azure](/azure/virtual-machines/windows/security-recommendations).

## <a name="azure-storage-service-encryption"></a>Cifrado de servicio de Azure Storage

Con [el cifrado de servicio de Azure Storage,](/azure/storage/storage-service-encryption)Azure Storage cifra automáticamente los datos antes de conservarlos en el almacenamiento y descifra los datos antes de la recuperación. Los procesos de cifrado, descifrado y administración de claves son totalmente transparentes para los usuarios. Azure Storage Service Encryption se puede usar para [Azure Blob Storage](https://azure.microsoft.com/services/storage/blobs/) y Azure [Files.](https://azure.microsoft.com/services/storage/files/) También puede usar claves de cifrado administradas por Microsoft con Azure Storage Service Encryption o puede usar sus propias claves de cifrado. (Para obtener información sobre cómo usar sus propias claves, vea [Storage Service Encryption using customer managed keys in Azure Key Vault](/azure/storage/common/storage-service-encryption-customer-managed-keys). Para obtener información sobre el uso de claves administradas por Microsoft, vea [Storage Service Encryption for Data at Rest](/azure/storage/storage-service-encryption).) Además, puede automatizar el uso del cifrado. Por ejemplo, puede habilitar o deshabilitar mediante programación el cifrado de servicio de almacenamiento en una cuenta de almacenamiento mediante la API rest del proveedor de recursos de almacenamiento de [Azure,](/rest/api/storagerp/)la biblioteca de cliente del proveedor de recursos de almacenamiento para [.NET,](/dotnet/api/overview/azure/storage) [Azure PowerShell](/powershell/azureps-cmdlets-docs)o la CLI de [Azure](/azure/storage/storage-azure-cli).

Algunos servicios de Microsoft 365 usan Azure para almacenar datos. Por ejemplo, SharePoint Online y OneDrive para la Empresa almacenan datos en Azure Blob Storage y Microsoft Teams almacena datos para su servicio de chat en tablas, blobs y colas. Además, la característica Administrador de cumplimiento del Centro de cumplimiento de Microsoft 365 almacena los datos introducidos por el cliente que se almacenan en forma cifrada en [Azure Cosmos DB](/azure/cosmos-db/database-encryption-at-rest), una plataforma como servicio (PaaS), una base de datos multi model distribuida globalmente. Azure Storage Service Encryption cifra los datos almacenados en Azure Blob Storage y en tablas, y Azure Disk Encryption cifra los datos en colas, así como los discos de máquina virtual windows e IaaS para proporcionar cifrado de volumen para el sistema operativo y el disco de datos. La solución garantiza que todos los datos de los discos de la máquina virtual se cifran en reposo en el almacenamiento de Azure. [El cifrado en reposo en Azure Cosmos DB](/azure/cosmos-db/database-encryption-at-rest) se implementa mediante varias tecnologías de seguridad, incluidos sistemas de almacenamiento de claves seguros, redes cifradas y API criptográficas.

## <a name="azure-key-vault"></a>Azure Key Vault

La administración de claves seguras no es solo fundamental para los procedimientos recomendados de cifrado; también es esencial para proteger los datos en la nube. [Azure Key Vault](/azure/key-vault/key-vault-whatis) le permite cifrar claves y pequeños secretos como contraseñas que usan claves almacenadas en módulos de seguridad de hardware (HSM). Azure Key Vault es la solución recomendada por Microsoft para administrar y controlar el acceso a las claves de cifrado usadas por los servicios en la nube. Los permisos para obtener acceso a las claves se pueden asignar a servicios o a usuarios con cuentas de Azure Active Directory. Azure Key Vault libera a las organizaciones de la necesidad de configurar, aplicar revisiones y mantener los HSM y el software de administración de claves. Con Azure Key Vault, Microsoft nunca ve las claves y las aplicaciones no tienen acceso directo a ellas; mantener el control. También puede importar o generar claves en HSM. Las organizaciones que tienen una suscripción que incluye Azure Information Protection pueden configurar su inquilino de Azure Information Protection para usar una clave administrada por el cliente [Bring Your Own Key](/information-protection/plan-design/byok-price-restrictions) (BYOK)) y registrar su [uso.](/information-protection/deploy-use/log-analyze-usage)