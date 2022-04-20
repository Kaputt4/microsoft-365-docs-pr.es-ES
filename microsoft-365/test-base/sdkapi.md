---
title: Prueba del SDK de & de la API base
description: Prueba del SDK de & de la API base
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: troubleshooting
ms.date: 07/06/2021
ms.service: virtual-desktop
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 14bfa8711d5cff46b8cce02950c087844384b9f9
ms.sourcegitcommit: e911dd506ea066795e418daf7b84c1e11381a21c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64953790"
---
# <a name="manage-your-resource-with-sdk--apis"></a>Administración del recurso con LAS API de & del SDK

La automatización es un aspecto clave del desarrollo ágil y DevOps. ¿Desea administrar Test Base para Microsoft 365 recursos, obtener resultados de pruebas mediante programación e integrarlos con nuestras herramientas de CI? ¡Las API base de prueba y el SDK pueden ayudarle a lograr todas estas y más!

Estas API o SDK permiten a los profesionales de TI y a los desarrolladores de aplicaciones:

- Administre las cuentas base de prueba, incluida la creación, actualización y eliminación.
- Administre paquetes de aplicación, incluidos los paquetes de creación, actualización, eliminación y descarga.
- Obtenga el resumen de la prueba, los resultados detallados de las pruebas y los resultados del análisis. El resultado del análisis incluye análisis de regresión de CPU, análisis de uso de CPU, análisis de regresión de memoria y análisis de uso de memoria.
- Descargue los resultados de las pruebas y la grabación de vídeo de ejecución de pruebas.

Consulte el esquema paso a paso siguiente para averiguar cómo acceder a esta nueva funcionalidad en Base de pruebas para Microsoft 365 servicio.

## <a name="a-step-by-step-example-of-test-base-account-creation-by-using-python-sdk"></a>Ejemplo paso a paso de creación de cuentas base de prueba mediante el SDK de Python

1. Requisitos previos:

   - Instale los siguientes componentes necesarios:

     - [Cuenta de Azure con una suscripción activa](https://azure.microsoft.com/free/?utm_source=campaign&utm_campaign=python-dev-center&mktingSource=environment-setup) si no tiene una suscripción
     - [Python 2.7+ o 3.6+](https://www.python.org/downloads)
     - [Interfaz de Azure Command-Line (CLI)](/cli/azure/install-azure-cli)

   - Instalación de paquetes de biblioteca mediante pip install desde la consola

     ```console
     pip install azure-identity
     pip install azure-mgmt-testbase
     ```

   - Autenticación en el entorno de desarrollo

     Al depurar y ejecutar código localmente, es habitual que los desarrolladores usen sus propias cuentas para autenticar las llamadas a los servicios de Azure. El paquete azure-identity admite la autenticación a través de la CLI de Azure para simplificar el desarrollo local. Para iniciar sesión en la CLI de Azure, ejecute `az login`. En un sistema con un explorador web predeterminado, la CLI de Azure iniciará el explorador para autenticar a un usuario.

     Consulte [Autenticación de aplicaciones de Python con servicios de Azure| Microsoft Docs](/azure/developer/python/azure-sdk-authenticate) y <https://pypi.org/project/azure-identity/> para otros métodos de autenticación admitidos.

   - Cree un grupo de recursos con el nombre deseado que se usará en los pasos siguientes.

2. El fragmento de código siguiente trata el flujo para crear una cuenta base de prueba, incluido

   - Solicitud de credenciales a través de la CLI de Azure para la interacción con Azure
   - Inicializar el cliente del SDK base de prueba con la credencial y el identificador de suscripción para operaciones posteriores
   - Invocar begin_create desde test_base_accounts modelo para crear una cuenta base de prueba

   Copie el código en el entorno de desarrollo de Python y reemplace "subscription-id" por el identificador de suscripción de Azure y "resource-group-name" por el grupo de recursos que creó anteriormente.

   ```python
   from azure.identity import AzureCliCredential
   from azure.mgmt.testbase import TestBase
   from azure.mgmt.testbase.models import TestBaseAccountResource
   from azure.mgmt.testbase.models import TestBaseAccountSKU

   # requesting token from Azure CLI for request
   # For other authentication approaches, please see: https://pypi.org/project/azure-identity/
   credential = AzureCliCredential()
   subscription_id = "<subscription-id>"
   resource_group = "<resource-group-name>"
   testBaseAccount_name = "contoso-testbaseAccount"
   testBaseAccount_location = "global"
   sku_name = "S0"
   sku_tier = "Standard"
   sku_locations = {"global"}
  
   # Create client
   testBase_client = TestBase(credential, subscription_id)
  
   # Create sku for test base account
   sku = TestBaseAccountSKU(name=sku_name, tier=sku_tier, locations=sku_locations)
  
   # Create test base account
   parameters = TestBaseAccountResource(location=testBaseAccount_location, sku=sku)
   testBaseAccount = testBase_client.test_base_accounts.begin_create(resource_group, testBaseAccount_name, parameters).result()
   print("Create test base account:\n{}".format(testBaseAccount))
   ```

## <a name="learn-more"></a>Más información

Consulte los vínculos siguientes para obtener más información sobre la API de & SDK.

**Suscripción de Azure**:

- [Cuenta de Azure con una suscripción activa](https://azure.microsoft.com/free/?utm_source=campaign&utm_campaign=python-dev-center&mktingSource=environment-setup)

**SDK de Python**:

- [Prueba de la documentación base del SDK de Python](/python/api/overview/azure/mgmt-testbase-readme)
- [Prueba del ejemplo base del SDK de Python](https://aka.ms/testbase-sample-py)
- [Patrón de uso general de Azure del SDK de Python](/azure/developer/python/azure-sdk-overview#provision-and-manage-azure-resources-with-management-libraries)

**API REST**:

- [Documentación de la API REST](https://aka.ms/testbase-api)
