---
title: Determinar si la implementación centralizada de complementos funciona para su organización
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier2
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b4527d49-4073-4b43-8274-31b7a3166f92
description: Determine si el inquilino y los usuarios cumplen los requisitos, de modo que pueda usar la implementación centralizada para implementar complementos de Office.
ms.openlocfilehash: aac5d5d617818528e454facad56ede72fc1bb083
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68727463"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a>Determinar si la implementación centralizada de complementos funciona para su organización

La implementación centralizada es la manera recomendada y más rica en características para que la mayoría de los clientes implementen complementos de Office en usuarios y grupos de su organización. Si es administrador, use esta guía para determinar si su organización y los usuarios cumplen los requisitos para que pueda usar la implementación centralizada.

Implementación centralizada proporciona las siguientes ventajas:

- Un administrador puede implementar y asignar un complemento directamente a un usuario, a varios usuarios a través de un grupo o a todos los usuarios de la organización (consulte Administración sección de requisitos para obtener información).
- Cuando se inicia la aplicación de Office correspondiente, el complemento se descarga automáticamente. Si el complemento admite comandos de complemento, el complemento aparece automáticamente en la cinta de opciones dentro de la aplicación de Office.
- Los complementos ya no aparecen para los usuarios si el administrador desactiva o elimina el complemento, o si el usuario se quita de Azure Active Directory o de un grupo al que está asignado el complemento.

La implementación centralizada admite tres plataformas de escritorio aplicaciones de Windows, Mac y Office en línea. La implementación centralizada también admite iOS y Android (solo complementos de Outlook Mobile).

Un complemento puede tardar hasta 24 horas en aparecer para el cliente para todos los usuarios.

## <a name="before-you-begin"></a>Antes de empezar

La implementación centralizada de complementos requiere que los usuarios usen licencias de Microsoft 365 Business (Business Basic, Business Standard, Business Premium), licencias de Office 365 Enterprise (E1/E3/E5/F3) o licencias de Microsoft 365 Enterprise (E3/E5/F3) (y inicien sesión en Office con su identificador de organización), Office 365 Educación licencias (A1/A3/A5) o licencias de Microsoft 365 Educación (A3/A5) y tienen buzones de Exchange Online activos y Exchange Online. El directorio de suscripción debe estar en Azure Active Directory o estar federado en él.
Puede ver los requisitos específicos de Office y Exchange a continuación, o usar el [Comprobador de compatibilidad de implementación centralizada](#centralized-deployment-compatibility-checker).

La implementación centralizada no es compatible con lo siguiente:

- Complementos que tienen como destino la versión msi de Office (excepto Outlook 2016)
- Un servicio de directorio local
- Implementación de complementos en un buzón local de Exchange
- Implementación de complemento a SharePoint
- Aplicaciones de Teams
- Implementación de complementos de modelo de objetos componentes (COM) o Visual Studio Tools para Office (VSTO).
- Implementaciones de Microsoft 365 que no incluyen Exchange Online como SKU: Aplicaciones Microsoft 365 para empresas y Aplicaciones Microsoft 365 para empresas.

### <a name="office-requirements"></a>Requisitos de Office

- Para los complementos de Word, Excel y PowerPoint, los usuarios deben usar uno de los siguientes elementos:
  - En un dispositivo Windows, versión 1704 o posterior de licencias de Microsoft 365 Business (Business Basic, Business Standard, Business Premium), licencias de Office 365 Enterprise (E1/E3/E5/F3) o licencias de Microsoft 365 Enterprise (E3/E5/F3).
  - En un Equipo Mac, versión 15.34 o posterior.

- Para Outlook, los usuarios deben usar uno de los siguientes elementos:
  - Versión 1701 o posterior de licencias empresariales de Microsoft 365 (Business Basic, Business Standard, Business Premium), licencias de Office 365 Enterprise (E1/E3/E5/F3) o licencias de Microsoft 365 Enterprise (E3/E5/F3).
  - Versión 1808 o posterior de Office Profesional Plus 2019 o Office Standard 2019.
  - Versión 16.0.4494.1000 o posterior de Office Profesional Plus 2016 (MSI) o Office Standard 2016 (MSI)\*
  - Versión 15.0.4937.1000 o posterior de Office Profesional Plus 2013 (MSI) o Office Standard 2013 (MSI)\*
  - Versión 16.0.9318.1000 o posterior de Office 2016 para Mac
- Versión 2.75.0 o posterior de Outlook mobile para iOS
- Versión 2.2.145 o posterior de Outlook mobile para Android

    *Las versiones MSI de Outlook muestran complementos instalados por el administrador en la cinta de opciones de Outlook adecuada, no en la sección "Mis complementos".

### <a name="exchange-online-requirements"></a>requisitos de Exchange Online

Microsoft Exchange almacena los manifiestos de complemento dentro del inquilino de la organización. Los administradores que implementan complementos y los usuarios que reciben esos complementos deben estar en una versión de Exchange Online que admita la autenticación de OAuth.

Check with your organization's Exchange admin to find out which configuration is in use. OAuth connectivity per user can be verified by using the [Test-OAuthConnectivity](/powershell/module/exchange/test-oauthconnectivity) PowerShell cmdlet.

### <a name="admin-requirements"></a>Requisitos de administrador

Para implementar un complemento a través de la implementación centralizada, debe ser un administrador global o un administrador de Exchange en la organización.

> [!NOTE]
> Un administrador de Exchange puede implementar un complemento si se agrega el rol **Administrador** de aplicaciones o si la propiedad **Registros** de aplicaciones está establecida en true en el Centro de administración de Azure Active Directory, como se muestra en la siguiente imagen:
>
> ![imagen](https://user-images.githubusercontent.com/89943918/144516704-8874a10d-b540-41f3-ae9d-c07a8d7e143f.png)

### <a name="centralized-deployment-compatibility-checker"></a>Comprobador de compatibilidad de implementación centralizada

Con el Comprobador de compatibilidad de implementación centralizada, puede comprobar si los usuarios del inquilino están configurados para usar la implementación centralizada para Word, Excel y PowerPoint. El Comprobador de compatibilidad no es necesario para la compatibilidad con Outlook. Descargue e instale el [comprobador de compatibilidad](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).

#### <a name="run-the-compatibility-checker"></a>Ejecución del comprobador de compatibilidad

1. Inicie una ventana de PowerShell.exe con privilegios elevados.

2. Ejecute el comando siguiente:

   ```powershell
   Import-Module O365CompatibilityChecker
   ```

3. Ejecute el comando **Invoke-CompatibilityCheck** :

   ```powershell
   Invoke-CompatibilityCheck
   ```

   Este comando le pide las credenciales _TenantDomain_ (por ejemplo, _TailspinToysIncorporated.onmicrosoft.com_) y _TenantAdmin_ (use sus credenciales de administrador global) y, a continuación, solicita consentimiento.

   > [!NOTE]
   > Según el número de usuarios de su espacio empresarial, el comprobador puede tardar minutos u horas en realizar la comprobación.

Cuando la herramienta completa el proceso, genera un archivo de salida en formato delimitado por comas (.csv). El archivo se guarda **en el directorio de trabajo actual** de forma predeterminada. El archivo de salida contiene la información siguiente:

- Nombre de usuario
- Id. de usuario (dirección de correo electrónico del usuario)
- Preparado para la Implementación centralizada: si los elementos restantes son ciertos
- Plan de Office: el plan de Office para el que tienen licencia
- Office activado: si Office está activado
- Buzón compatible: si están en un buzón habilitado para OAuth

Si los informes de Microsoft 365 muestran nombres de usuario anónimos en lugar de nombres de usuario reales, corrija este problema cambiando la configuración de informes en Centro de administración de Microsoft 365. Para obtener pasos detallados, consulte [Informes de Microsoft 365 que muestran nombres de usuario anónimos en lugar de nombres de usuario reales](/office365/troubleshoot/miscellaneous/reports-show-anonymous-user-name).

> [!NOTE]
> No se admite la autenticación multifactor cuando se usa el módulo de PowerShell de implementación central. El módulo solo funciona con la autenticación básica.

## <a name="user-and-group-assignments"></a>Asignaciones de usuario y de grupo

La característica Implementación centralizada admite actualmente la mayoría de los grupos admitidos por Azure Active Directory, incluidos los grupos de Microsoft 365, las listas de distribución, los grupos dinámicos y los grupos de seguridad.

> [!NOTE]
> Los grupos de seguridad no habilitados para correo no son compatibles en estos momentos.

La implementación centralizada admite asignaciones a usuarios individuales, grupos y todos los usuarios del inquilino. La implementación centralizada es compatible con usuarios en grupos de nivel superior o grupos sin grupo primario, pero no con usuarios en grupos anidados o grupos que forman parte de otros primarios.

Take a look at the following example where Sandra, Sheila, and the Sales Department group are assigned to an add-in. Because the West Coast Sales Department is a nested group, Bert and Fred aren't assigned to an add-in.

![MicrosoftTeams-image](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

### <a name="find-out-if-a-group-contains-nested-groups"></a>Averiguar si un grupo contiene grupos anidados

La forma más sencilla de detectar si un grupo contiene grupos anidados es ver la tarjeta de contacto del grupo en Outlook. Si escribe el nombre del grupo en el campo **Para** de un correo electrónico y, a continuación, selecciona el nombre del grupo cuando se resuelve, se mostrará si contiene usuarios o grupos anidados. En el ejemplo siguiente, la pestaña **Miembros** de la tarjeta de contacto de Outlook del grupo de pruebas no muestra usuarios, solo dos subgrupos.

![Pestaña Miembros de la tarjeta de contacto de Outlook.](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)

You can do the opposite query by resolving the group to see if it's a member of any group. In the example below, you can see under the **Membership** tab of the Outlook contact card that Sub Group 1 is a member of the Test Group.

![Pestaña Pertenencia de la tarjeta de contacto de Outlook.](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)

De forma alternativa, puede usar la API de Graph Azure Active Directory para ejecutar consultas para encontrar una lista de grupos dentro de un grupo. Para obtener más información, vea [Operaciones en grupos| Graph API referencia](/previous-versions/azure/ad/graph/api/groups-operations).

### <a name="contacting-microsoft-for-support"></a>Ponerse en contacto con Microsoft para obtener soporte técnico

Si usted o los usuarios tienen problemas para cargar el complemento mientras usan aplicaciones de Office para la web (Word, Excel, etc.), que se implementaron de forma centralizada, es posible que tenga que ponerse en contacto con el soporte técnico de Microsoft ([obtenga información sobre cómo](../../business-video/get-help-support.md) hacerlo. Proporcione la siguiente información sobre el entorno de Microsoft 365 en la incidencia de soporte técnico.

|Plataforma|Información de depuración|
|---|---|
|Oficina|Registros Charles/Fiddler <br/> Identificador de inquilino ([obtenga información sobre cómo](/onedrive/find-your-office-365-tenant-id)) <br/> CorrelationID. Vea el origen de una de las páginas de office, busque el valor de Identificador de correlación y envíelo para admitirlo:  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">` <br/> `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`|
|Clientes enriquecidos (Windows y Mac)|Registros Charles/Fiddler <br/> Números de compilación de la aplicación cliente (preferiblemente como captura de pantalla de **archivo o cuenta**)|

## <a name="related-content"></a>Contenido relacionado

[Implementar complementos en el centro de administración](../manage/manage-deployment-of-add-ins.md) (artículo)\
[Administrar complementos en el Centro de administración](manage-addins-in-the-admin-center.md) (artículo)\
[Preguntas más frecuentes sobre la implementación centralizada](../manage/centralized-deployment-faq.yml) (artículo)\
[Actualice los usuarios de Microsoft 365 para empresas al cliente de Office más reciente](../setup/upgrade-users-to-latest-office-client.md) (artículo)
