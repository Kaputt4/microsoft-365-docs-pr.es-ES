---
title: SDK de prueba de API & base
description: SDK de prueba de API & base
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
ms.openlocfilehash: f7e5edeeac79b417bcb41f8607c46fc8894ea4fc
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/19/2021
ms.locfileid: "61110384"
---
# <a name="manage-your-resource-with-sdk--apis"></a>Administrar el recurso con LAS API & SDK
La automatización es un aspecto clave del desarrollo DevOps y ágil. ¿Está buscando administrar Test Base para obtener Microsoft 365, obtener resultados de pruebas mediante programación e integrarlos con nuestras herramientas de CI? Probar API base/SDK puede ayudarle a lograr todas estas y más cosas. 

Estas API/SDK permiten a los profesionales de TI y desarrolladores de aplicaciones: 
- Administrar cuentas base de prueba, incluidas las de creación, actualización y offboard. 
- Administrar paquetes de aplicación, incluidos crear, actualizar, eliminar y descargar paquetes. 
- Obtenga el resumen de la prueba, los resultados detallados de la prueba y los resultados del análisis. El resultado del análisis incluye análisis de regresión de CPU, análisis de utilización de CPU, análisis de regresión de memoria y análisis de uso de memoria. 
- Descargue los resultados de la prueba y la grabación de vídeo de ejecución de pruebas.  

Consulte el esquema paso a paso siguiente para averiguar cómo obtener acceso a esta nueva funcionalidad en Test Base for Microsoft 365 service.

## <a name="a-step-by-step-example-of-test-base-account-creation-by-using-python-sdk"></a>Un ejemplo paso a paso de la creación de cuentas base de prueba mediante el SDK de Python

1. Requisitos previos: 

- Instale los siguientes componentes necesarios: 

    [Cuenta de Azure con una suscripción activa](https://azure.microsoft.com/free/?utm_source=campaign&utm_campaign=python-dev-center&mktingSource=environment-setup) si no tiene una suscripción<br>
    [Python 2.7+ o 3.6+](https://www.python.org/downloads)<br>
    [Interfaz Command-Line Azure (CLI)](/cli/azure/install-azure-cli) <br>

- Instalar paquetes de biblioteca mediante la instalación de pip desde la consola 

```
pip install azure-identity 
pip install azure-mgmt-testbase
```

- Autenticación en entorno de desarrollo 

Al depurar y ejecutar código localmente, es habitual que los desarrolladores usen sus propias cuentas para autenticar llamadas a servicios de Azure. El paquete azure-identity admite la autenticación a través de la CLI de Azure para simplificar el desarrollo local. Para iniciar sesión en la CLI de Azure, ejecute ```az login ``` . En un sistema con un explorador web predeterminado, la CLI de Azure iniciará el explorador para autenticar a un usuario. 

Consulte [Cómo autenticar aplicaciones de Python con servicios de Azure| Microsoft Docs y](/azure/developer/python/azure-sdk-authenticate)  para [https://pypi.org/project/azure-identity/](https://pypi.org/project/azure-identity/) otros métodos de autenticación compatibles. 

 - Cree un grupo de recursos con el nombre deseado que se usará en los pasos siguientes. 

2. Debajo del fragmento de código se describe el flujo para crear una cuenta base de prueba, incluida la 

- Solicitar credenciales a través de la CLI de Azure para la interacción con Azure 
- Inicializar el cliente del SDK de Base de prueba con la credencial y el identificador de suscripción para operaciones posteriores 
- Invocar begin_create desde test_base_accounts modelo para crear una cuenta base de prueba 

Copie el código en el entorno de desarrollo de Python y reemplace "subscription-id" por su id. de suscripción de Azure y "resource-group-name" por el grupo de recursos que creó anteriormente. 

 
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

Consulte los vínculos siguientes para obtener más información acerca de la API & SDK. 

**Suscripción a Azure** 

- [Cuenta de Azure con una suscripción activa](https://azure.microsoft.com/free/?utm_source=campaign&utm_campaign=python-dev-center&mktingSource=environment-setup)

**SDK de Python** 

- [Documentación del SDK de Python base de prueba](/python/api/overview/azure/mgmt-testbase-readme)
- [Ejemplo de SDK de Python base de prueba](https://aka.ms/testbase-sample-py)
- [Patrón de uso general de Azure del SDK de Python](/azure/developer/python/azure-sdk-overview#provision-and-manage-azure-resources-with-management-libraries)

**API de REST**  

- [Documentación de la API de REST](https://aka.ms/testbase-api)  
