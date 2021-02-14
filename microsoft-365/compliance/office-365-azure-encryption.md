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
description: Obtenga información sobre el cifrado disponible en Azure, como El cifrado de disco de Azure
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a90f66ed7288d84785becbb4cd25c803ccf4fdbe
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198333"
---
# <a name="encryption-in-azure"></a>Cifrado en Azure

Las protecciones tecnológicas de Azure, como las comunicaciones cifradas y los procesos operativos, ayudan a mantener la seguridad de los datos. También tiene la flexibilidad de implementar características de cifrado adicionales y administrar sus propias claves criptográficas. Independientemente de la configuración del cliente, Microsoft aplica el cifrado para proteger los datos de los clientes en Azure. Microsoft también le permite controlar los datos hospedados en Azure a través de una variedad de tecnologías avanzadas para cifrar, controlar y administrar claves criptográficas, y controlar y auditar el acceso a los datos. Además, Azure Storage proporciona un conjunto completo de funcionalidades de seguridad que, en conjunto, permiten a los desarrolladores crear aplicaciones seguras.

Azure ofrece muchos mecanismos para proteger los datos a medida que se mueven de una ubicación a otra. Microsoft usa TLS para proteger los datos cuando viajan entre los servicios en la nube y los clientes. Los centros de datos de Microsoft negocian una conexión TLS con los sistemas cliente que se conectan a los servicios de Azure. El secreto directo perfecto (PFS) protege las conexiones entre los sistemas cliente de los clientes y los servicios en la nube de Microsoft mediante claves únicas. Las conexiones también usan longitudes de clave de cifrado de 2.048 bits basadas en RSA. Esta combinación dificulta la interceptación y el acceso a datos en tránsito.

Los datos se pueden proteger en tránsito entre una aplicación y Azure mediante el cifrado del lado [cliente,](https://docs.microsoft.com/azure/storage/storage-client-side-encryption)HTTPS o SMB 3.0. Puede habilitar el cifrado para el tráfico entre sus propias máquinas virtuales (VM) y los usuarios. Con [Azure Virtual Networks,](https://azure.microsoft.com/services/virtual-network/)puede usar el protocolo IPsec estándar del sector para cifrar el tráfico entre la puerta de enlace VPN corporativa y Azure, así como entre las máquinas virtuales ubicadas en la red virtual.

Para los datos en reposo, Azure ofrece muchas opciones de cifrado, como la compatibilidad con AES-256, lo que proporciona flexibilidad para elegir el escenario de almacenamiento de datos que mejor se adapte a sus necesidades. Los datos se pueden cifrar automáticamente cuando se escriben en Azure Storage mediante el cifrado del servicio de [almacenamiento,](https://docs.microsoft.com/azure/storage/storage-service-encryption)y el sistema operativo y los discos de datos usados por las máquinas virtuales se pueden cifrar. Para obtener más información, vea [Recomendaciones de seguridad para máquinas virtuales de Windows en Azure.](https://docs.microsoft.com/azure/security/azure-security-disk-encryption) Además, el acceso delegado a los objetos de datos en Azure Storage se puede conceder mediante [firmas de acceso compartido.](https://docs.microsoft.com/azure/storage/storage-dotnet-shared-access-signature-part-1) Azure también proporciona cifrado para los datos en reposo mediante el cifrado de datos transparente para Azure SQL base de datos [y almacén de datos.](https://docs.microsoft.com/sql/relational-databases/security/encryption/transparent-data-encryption-azure-sql)

Para obtener más información sobre el cifrado en Azure, vea [Información general](https://docs.microsoft.com/azure/security/security-azure-encryption-overview) sobre el cifrado de Azure y Azure [Data Encryption-at-Rest.](https://docs.microsoft.com/azure/security/azure-security-encryption-atrest)

## <a name="azure-disk-encryption"></a>Azure Disk Encryption

Azure Disk Encryption te permite cifrar los discos de vm de Infraestructura como servicio (IaaS) de Windows y Linux. Azure Disk Encryption aprovecha la característica BitLocker de Windows y la característica DM-Crypt de Linux para proporcionar cifrado de nivel de volumen para el sistema operativo y los discos de datos. También garantiza que todos los datos de los discos de máquina virtual se cifran en reposo en el almacenamiento de Azure. Azure Disk Encryption se integra con Azure Key Vault para ayudarle a controlar, administrar y auditar el uso de las claves y secretos de cifrado.

Para obtener más información, vea Recomendaciones [de seguridad para máquinas virtuales de Windows en Azure.](https://docs.microsoft.com/azure/virtual-machines/windows/security-recommendations)

## <a name="azure-storage-service-encryption"></a>Cifrado del servicio de almacenamiento de Azure

Con [Azure Storage Service Encryption,](https://docs.microsoft.com/azure/storage/storage-service-encryption)Azure Storage cifra automáticamente los datos antes de conservarlos en el almacenamiento y descifra los datos antes de la recuperación. Los procesos de cifrado, descifrado y administración de claves son totalmente transparentes para los usuarios. Azure Storage Service Encryption puede usarse para [Azure Blob Storage](https://azure.microsoft.com/services/storage/blobs/) y Azure [Files.](https://azure.microsoft.com/services/storage/files/) También puede usar claves de cifrado administradas por Microsoft con Azure Storage Service Encryption o puede usar sus propias claves de cifrado. (Para obtener información sobre cómo usar sus propias claves, consulte Cifrado del servicio de almacenamiento con claves administradas por [el cliente en Azure Key Vault.](https://docs.microsoft.com/azure/storage/common/storage-service-encryption-customer-managed-keys) Para obtener información sobre el uso de claves administradas por Microsoft, consulte [Cifrado del servicio de almacenamiento para datos en reposo.](https://docs.microsoft.com/azure/storage/storage-service-encryption) Además, puede automatizar el uso del cifrado. Por ejemplo, puede habilitar o deshabilitar mediante programación el cifrado del servicio de almacenamiento en una cuenta de almacenamiento mediante la API de REST del proveedor de recursos de almacenamiento de [Azure,](https://msdn.microsoft.com/library/azure/mt163683.aspx)la biblioteca cliente del proveedor de recursos de almacenamiento para [.NET,](https://msdn.microsoft.com/library/azure/mt131037.aspx) [Azure PowerShell](https://docs.microsoft.com/powershell/azureps-cmdlets-docs)o la CLI de [Azure](https://docs.microsoft.com/azure/storage/storage-azure-cli).

Algunos servicios de Microsoft 365 usan Azure para almacenar datos. Por ejemplo, SharePoint Online y OneDrive para la Empresa almacenan datos en Azure Blob Storage, y Microsoft Teams almacena datos para su servicio de chat en tablas, blobs y colas. Además, la característica Administrador de cumplimiento del Centro de cumplimiento de Microsoft 365 almacena los datos introducidos por el cliente que se almacenan en forma cifrada en [Azure Cosmos DB,](https://docs.microsoft.com/azure/cosmos-db/database-encryption-at-rest)una plataforma como servicio (PaaS), una base de datos de varios modelos distribuida globalmente. El cifrado del servicio de almacenamiento de Azure cifra los datos almacenados en Azure Blob Storage y en tablas, y El cifrado de disco de Azure cifra los datos en las colas, así como los discos de máquina virtual de Windows e IaaS para proporcionar cifrado de volumen para el sistema operativo y el disco de datos. La solución garantiza que todos los datos de los discos de la máquina virtual estén cifrados en reposo en el almacenamiento de Azure. [El cifrado en reposo en Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/database-encryption-at-rest) se implementa mediante varias tecnologías de seguridad, como sistemas de almacenamiento de claves seguras, redes cifradas y API criptográficas.

## <a name="azure-key-vault"></a>Azure Key Vault

La administración de claves seguras no es solo esencial para los procedimientos recomendados de cifrado; también es esencial para proteger los datos en la nube. [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/key-vault-whatis) le permite cifrar claves y secretos pequeños, como contraseñas que usan claves almacenadas en módulos de seguridad de hardware (MS). Azure Key Vault es la solución recomendada de Microsoft para administrar y controlar el acceso a las claves de cifrado que usan los servicios en la nube. Los permisos para obtener acceso a las claves se pueden asignar a servicios o a usuarios con cuentas de Azure Active Directory. Azure Key Vault libera a las organizaciones de la necesidad de configurar, aplicar revisiones y mantener HSMs y software de administración de claves. Con Azure Key Vault, Microsoft nunca ve las claves y las aplicaciones no tienen acceso directo a ellas; mantener el control. También puede importar o generar claves en los MS. Las organizaciones que tienen una suscripción que incluye Azure Information Protection pueden configurar su inquilino de Azure Information Protection para usar una clave administrada por el cliente [Bring Your Own Key](https://docs.microsoft.com/information-protection/plan-design/byok-price-restrictions) (BYOK)) y registrar su [uso.](https://docs.microsoft.com/information-protection/deploy-use/log-analyze-usage)
