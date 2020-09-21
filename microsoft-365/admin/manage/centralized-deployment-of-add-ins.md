---
title: Determinar si la implementación centralizada de complementos funciona para su organización
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b4527d49-4073-4b43-8274-31b7a3166f92
description: Determine si el espacio empresarial y los usuarios cumplen los requisitos, de modo que pueda usar la implementación centralizada para implementar complementos de Office.
ms.openlocfilehash: 4bd81dcf1d1ee6221a3519baac0a3b1bc63b791f
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2020
ms.locfileid: "48131739"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a>Determinar si la implementación centralizada de complementos funciona para su organización

La implementación centralizada es la forma recomendada y con más características para la mayoría de los clientes de implementar complementos de Office para los usuarios y grupos de su organización. Si es administrador, use esta guía para determinar si la organización y los usuarios cumplen los requisitos para que pueda usar la implementación centralizada.

Implementación centralizada proporciona las siguientes ventajas:
  
- Un administrador global puede asignar un complemento directamente a un usuario, a varios usuarios a través de un grupo o a todos los usuarios de la organización.
    
- Cuando se inicie la aplicación de Office pertinente, el complemento se descargará automáticamente. Si el complemento admite comandos de complemento, el complemento aparece automáticamente en la cinta de la aplicación de Office.
    
- Los complementos ya no aparecen para los usuarios si el administrador desactiva o elimina el complemento, o si se quita el usuario de Azure Active Directory o de un grupo al que está asignado el complemento.

La implementación centralizada admite tres plataformas de escritorio Windows, Mac y aplicaciones de Office en línea. La implementación centralizada también admite iOS y Android (solo complementos de Outlook Mobile).

Un complemento puede tardar hasta 24 horas en mostrarse para el cliente para todos los usuarios.
  
## <a name="requirements"></a>Requirements

La implementación centralizada de complementos requiere que los usuarios usen las aplicaciones de Microsoft 365 para empresas (y que hayan iniciado sesión en Office con su identificador de organización) y tengan Exchange Online y los buzones activos de Exchange Online. El directorio de suscripción debe estar en el o ser federado en Azure Active Directory.
Puede ver los requisitos específicos para Office y Exchange, o usar el[Comprobador de compatibilidad de implementación centralizada](#centralized-deployment-compatibility-checker).

La implementación centralizada no es compatible con lo siguiente:
  
- Complementos que tengan como objetivo Word, Excel o PowerPoint en Office 2013 
- Un servicio de directorio local
- Implementación de complementos en un buzón de correo local de Exchange
- Implementación de complemento a SharePoint  
- Aplicaciones de Teams
- Implementación complementos de modelo de objetos componentes (COM) o de Visual Studio Tools para Office (VSTO)
- Implementaciones de Microsoft 365 que no incluyen Exchange, como Microsoft 365 apps for Business

### <a name="office-requirements"></a>Requisitos de Office

- Para los complementos de Word, Excel y PowerPoint, los usuarios deben usar una de las siguientes opciones:
  - En un dispositivo Windows, versión 1704 o posterior de Microsoft 365 apps for Enterprise.
  - En un equipo Mac, versión 15,34 o posterior.

- Para Outlook, los usuarios deben usar una de las siguientes opciones: 
  - Versión 1701 o posterior de las aplicaciones de Microsoft 365 para empresas.
  - La versión 1808 o posterior de Office Professional Plus 2019 u Office Standard 2019.
  - Versión 16.0.4494.1000 o posterior de Office Professional Plus 2016 (MSI) u Office Standard 2016 (MSI)\*
  - Versión 15.0.4937.1000 o posterior de Office Professional Plus 2013 (MSI) u Office Standard 2013 (MSI)\*
  - Versión 16.0.9318.1000 o posterior de Office 2016 para Mac 
- Versión 2.75.0 o posterior de Outlook Mobile para iOS 
- Versión 2.2.145 o posterior de Outlook Mobile para Android 
    
    * Las versiones MSI de Outlook muestran complementos instalados por el administrador en la cinta de Outlook correspondiente, no en la sección "mis complementos".
    

#### <a name="find-out-if-microsoft-365-apps-for-enterprise-is-installed"></a>Averiguar si Microsoft 365 apps for Enterprise está instalado

Para usar las aplicaciones de Microsoft 365 para empresas, un usuario debe tener una cuenta de Microsoft 365 y debe tener una licencia asignada. Para obtener más información, vea [información general de las aplicaciones de Microsoft 365 para empresas](https://go.microsoft.com/fwlink/p/?linkid=846328).

La forma más sencilla de detectar si un usuario tiene Microsoft 365 apps for Enterprise instalado y lo ha usado recientemente es usar el informe de activaciones de Microsoft Office, que está disponible en el centro de administración de Microsoft 365. El informe proporciona una lista de todos los usuarios que han activado Microsoft 365 apps for Enterprise en los últimos 7 días, 30 días, 90 días o 180 días. Con fines de implementación centralizada, las activaciones de escritorio para Windows o Mac son las columnas importantes del informe. Puede exportar el informe a Excel. Para obtener más información acerca del informe, vea [informes de microsoft 365 en el centro de administración: activaciones de Microsoft Office](../activity-reports/microsoft-office-activations.md).
  
Si no desea usar el informe de activaciones, puede pedir a un usuario que abra una aplicación de Office, como Word en su equipo y, a continuación, elija cuenta de **archivo** \> **Account**. En **información del producto**, verá que el **producto de suscripción** y **Microsoft 365 para empresas**, o Microsoft 365 empresa Premium, son similares a lo que se muestra en la siguiente imagen.

![Información de producto en una aplicación de Office](../../media/product-information-microsoft-365-enterprise.png)
  
Para obtener ayuda con Microsoft 365 apps for Enterprise, vea [Troubleshooting Tips for microsoft 365 apps for Enterprise](https://go.microsoft.com/fwlink/p/?linkid=846339).


### <a name="exchange-online-requirements"></a>Requisitos de Exchange Online

Microsoft Exchange almacena los manifiestos de complementos dentro del espacio empresarial de la organización. El administrador que implementa los complementos y los usuarios que reciben esos complementos deben estar en una versión de Exchange online que admita la autenticación de OAuth.
  
Póngase en contacto con el administrador de Exchange de su organización para averiguar qué configuración está en uso. La conectividad de OAuth por usuario puede comprobarse usando el cmdlet de PowerShell [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351). 


### <a name="centralized-deployment-compatibility-checker"></a>Comprobador de compatibilidad de implementación centralizada

Con el comprobador de compatibilidad de implementación centralizada, puede comprobar si los usuarios de su espacio empresarial están configurados para usar la implementación centralizada para Word, Excel y PowerPoint. El Comprobador de compatibilidad no es necesario para la compatibilidad con Outlook. Descargue el Comprobador de compatibilidad [aquí](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).
  
#### <a name="run-the-compatibility-checker"></a>Ejecutar el comprobador de compatibilidad
  
1. Inicie una ventana de PowerShell.exe elevado.
    
2. Ejecute el siguiente comando:

   ```powershell
   Import-Module O365CompatibilityChecker
   ```
    
3. Ejecute el comando **Invoke-CompatabilityCheck** :

   ```powershell
   Invoke-CompatibilityCheck
   ```
   Este comando le pedirá que  *_TenantDomain_* (por ejemplo, *TailspinToysIncorporated. de Microsoft. </span> com*) y  *_TenantAdmin_* (use las credenciales de administrador global) y, a continuación, solicite el consentimiento.
    
   > [!NOTE]
   > Según el número de usuarios de su espacio empresarial, el comprobador puede tardar minutos u horas en realizar la comprobación. 
  
Cuando la herramienta completa el proceso, genera un archivo de salida en formato delimitado por comas (.csv). El archivo se guarda en **C:\windows\system32** de forma predeterminada. El archivo de salida contiene la información siguiente:
  
- Nombre de usuario
    
- Id. de usuario (dirección de correo electrónico del usuario)
    
- Preparado para la Implementación centralizada: si los elementos restantes son ciertos
    
- Plan de Office: el plan de Office para el que se tiene licencia
    
- Office activado: si Office está activado
    
- Buzón compatible: si están en un buzón habilitado para OAuth


  
## <a name="user-and-group-assignments"></a>Asignaciones de usuario y de grupo

La característica de implementación centralizada es compatible actualmente con la mayoría de los grupos compatibles con Azure Active Directory, incluidos los grupos de Microsoft 365, las listas de distribución y los grupos de seguridad.
  
> [!NOTE]
> Los grupos de seguridad no habilitados para correo no son compatibles en estos momentos. 
  
La implementación centralizada admite asignaciones a usuarios individuales, grupos y a todos los miembros del espacio empresarial. La implementación centralizada es compatible con usuarios en grupos de nivel superior o grupos sin grupo primario, pero no con usuarios en grupos anidados o grupos que forman parte de otros primarios.
   
Eche un vistazo al siguiente ejemplo, en el que Sandra, Sheila y el grupo del departamento de ventas están asignados a un complemento. Como el departamento de ventas de la Costa Occidental es un grupo anidado, Bert y Fred no están asignados a un complemento.
  
![Diagrama del Departamento de ventas](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

   
### <a name="find-out-if-a-group-contains-nested-groups"></a>Averiguar si un grupo contiene grupos anidados

La forma más sencilla de detectar si un grupo contiene grupos anidados es ver la tarjeta de contacto del grupo en Outlook. Si escribe el nombre de grupo en el campo **para** de un correo electrónico y, a continuación, selecciona el nombre del grupo cuando se resuelve, mostrará si contiene usuarios o grupos anidados. En el ejemplo siguiente, la pestaña **Miembros** de la tarjeta de contacto de Outlook del grupo de pruebas no muestra usuarios, solo dos subgrupos. 
  
![Pestaña miembros de la tarjeta de contacto de Outlook](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)
  
Puede realizar la consulta opuesta para comprobar si un grupo es miembro de cualquier otro. En el ejemplo siguiente, puede ver en la pestaña **Miembros** de la tarjeta de contacto de Outlook que el Subgrupo 1 es miembro del grupo de pruebas. 
  
![Ficha pertenencia de la tarjeta de contacto de Outlook](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)
  
De forma alternativa, puede usar la API de Graph Azure Active Directory para ejecutar consultas para encontrar una lista de grupos dentro de un grupo. Para obtener más información, vea [Operaciones en grupos | Referencia de API de Graph](https://go.microsoft.com/fwlink/p/?linkid=846342).
  
### <a name="contacting-microsoft-for-support"></a>Ponerse en contacto con Microsoft para obtener soporte técnico

Si usted o sus usuarios experimentan problemas al cargar el complemento mientras usan aplicaciones de Office para la web (Word, Excel, etc.), que se implementaron de forma centralizada, es posible que deba ponerse en contacto con el soporte técnico de Microsoft ([obtenga información](../contact-support-for-business-products.md)). Proporcione la siguiente información sobre el entorno de Microsoft 365 en la incidencia de soporte técnico.
  
|**Plataforma**|**Información de depuración**|
|:-----|:-----|
|Office  <br/> | Registros Charles/Fiddler  <br/>  Id. del espacio empresarial ( [más información](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id.aspx))      <br/>  CorrelationID. Vea el origen de una de las páginas de Office y busque el valor del identificador de correlación y envíelo a soporte técnico:  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|Clientes enriquecidos (Windows y Mac)  <br/> | Registros Charles/Fiddler  <br/>  Números de compilación de la aplicación cliente (preferiblemente como una captura de pantalla de **archivo/cuenta**)  <br/> |
   

