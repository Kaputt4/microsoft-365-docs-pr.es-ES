---
title: Introducción al escáner de Microsoft Purview Information Protection
f1.keywords: ''
ms.author: libarson
author: libarson
manager: aashishr
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: normal
ms.collection:
- purview-compliance
- tier3
description: Enumera los requisitos previos para instalar e implementar el analizador de Microsoft Purview Information Protection.
ms.openlocfilehash: cf8daa62709c557d771a76889b9c277c124cadbc
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68639016"
---
# <a name="get-started-with-the-information-protection-scanner"></a>Introducción al analizador de protección de la información

Antes de instalar el escáner desde Microsoft Purview Information Protection, asegúrese de que el sistema cumple los requisitos básicos [de Azure Information Protection](/azure/information-protection/requirements).

Además, los siguientes requisitos son específicos para el analizador:

- [Requisitos de Windows Server](#windows-server-requirements)
- [Requisitos de la cuenta de servicio](#service-account-requirements)
- [Requisitos de SQL Server](#sql-server-requirements)
- [Requisitos de cliente de Azure Information Protection](#azure-information-protection-client-requirements)
- [Requisitos de configuración de etiquetas](#label-configuration-requirements)
- [Requisitos de SharePoint](#sharepoint-requirements)
- [Requisitos de Microsoft Office](#microsoft-office-requirements)
- [Requisitos de ruta de acceso de archivo](#file-path-requirements)

Si no puede cumplir todos los requisitos enumerados para el analizador porque están prohibidos por las directivas de su organización, consulte la sección [configuraciones alternativas](#deploying-the-scanner-with-alternative-configurations) .

Al implementar el analizador en producción o probar el rendimiento de varios escáneres, consulte [Requisitos de almacenamiento y planeamiento de capacidad para SQL Server](#storage-requirements-and-capacity-planning-for-sql-server).

Cuando esté listo para empezar a instalar e implementar el escáner, continúe con [Configuración e instalación del analizador de protección de la información](deploy-scanner-configure-install.md).

## <a name="windows-server-requirements"></a>Requisitos de Windows Server

Debe tener un equipo con Windows Server para ejecutar el analizador, que tiene las siguientes especificaciones del sistema:

|Especificación  |Detalles  |
|---------|---------|
|**Procesador**     |Procesadores de 4 núcleos         |
|**RAM**     |8 GB         |
|**Espacio en disco**     |10 GB de espacio libre (promedio) para los archivos temporales. </br></br>El analizador requiere suficiente espacio en disco para crear archivos temporales para cada archivo que examina, cuatro archivos por núcleo. </br></br>El espacio en disco recomendado de 10 GB permite 4 procesadores de núcleos que examinan 16 archivos que tienen un tamaño de archivo de 625 MB.
|**Sistema operativo**     |Versiones de 64 bits de: <br><br>- Windows Server 2019 </br>- Windows Server 2016 </br>- Windows Server 2012 R2 </br></br>**Nota**: Para fines de prueba o evaluación en un entorno que no es de producción, también puede usar cualquier sistema operativo Windows [compatible con el cliente de Azure Information Protection](/azure/information-protection/requirements#client-devices).
|**Conectividad de la red**     | El equipo del escáner puede ser un equipo físico o virtual con una conexión de red rápida y confiable a los almacenes de datos que se van a examinar. </br></br> Si no es posible la conectividad a Internet debido a las directivas de la organización, consulte [Implementación del analizador con configuraciones alternativas](#deploying-the-scanner-with-alternative-configurations). </br></br>De lo contrario, asegúrese de que este equipo tenga conectividad a Internet que permita las siguientes direcciones URL a través de HTTPS (puerto 443):</br><br />-  \*.aadrm.com <br />-  \*.azurerms.com<br />-  \*.informationprotection.azure.com <br /> - informationprotection.hosting.portal.azure.net <br /> - \*.aria.microsoft.com <br />-  \*.protection.outlook.com |
|**Recursos compartidos de NFS** |Para admitir exámenes en recursos compartidos de NFS, los servicios de NFS deben implementarse en la máquina del escáner. <br><br>En el equipo, vaya al cuadro de diálogo **de configuración Características de Windows (activar o desactivar características de Windows)** y seleccione los siguientes elementos: **Servicios para NFS** > **Herramientas administrativas** y **Cliente para NFS**. |
| **iFilter de Microsoft Office** |Cuando el escáner está instalado en un equipo con Windows Server, también debe instalar el iFilter de Microsoft Office para examinar .zip archivos en busca de tipos de información confidencial. <br><br>Para obtener más información, consulte el [sitio de descarga de Microsoft](https://www.microsoft.com/en-us/download/details.aspx?id=17062).|

## <a name="service-account-requirements"></a>Requisitos de la cuenta de servicio

Debe tener una cuenta de servicio para ejecutar el servicio de escáner en el equipo con Windows Server, así como autenticarse en Azure AD y descargar la directiva del analizador.

La cuenta de servicio debe ser una cuenta de Active Directory y estar sincronizada con Azure AD.

Si no puede sincronizar esta cuenta debido a las directivas de la organización, consulte [Implementación del analizador con configuraciones alternativas](#deploying-the-scanner-with-alternative-configurations).

Esta cuenta de servicio tiene los siguientes requisitos:

|Requisito  |Detalles  |
|---------|---------|
|**Iniciar sesión en la asignación de** derechos de usuario local     |Es necesario para instalar y configurar el analizador, pero no es necesario para ejecutar exámenes.  </br></br>Una vez que haya confirmado que el analizador puede detectar, clasificar y proteger archivos, puede quitar este derecho de la cuenta de servicio.  </br></br>Si no es posible conceder este derecho incluso durante un breve período de tiempo debido a las directivas de la organización, consulte [Implementación del analizador con configuraciones alternativas](#deploying-the-scanner-with-alternative-configurations).         |
|**Inicie sesión como una** asignación de derechos de usuario de servicio.     |  Este derecho se concede automáticamente a la cuenta de servicio durante la instalación del escáner y este derecho es necesario para la instalación, configuración y funcionamiento del escáner.        |
|**Permisos para los repositorios de datos**     |- **Recursos compartidos de archivos o archivos locales**: conceda permisos de **lectura**, **escritura** y **modificación** para examinar los archivos y, a continuación, aplique la clasificación y la protección según lo configurado.  <br /><br />- **SharePoint**: debe conceder permisos de **control total** para examinar los archivos y, a continuación, aplicar la clasificación y la protección a los archivos que cumplen las condiciones de la directiva de Azure Information Protection.  <br /><br />- **Modo de detección**: para ejecutar el analizador solo en modo de detección, el permiso **de lectura** es suficiente.         |
|**Para etiquetas que reprotegen o quitan la protección**     | Para asegurarse de que el analizador siempre tiene acceso a archivos cifrados, convierta esta cuenta en [superusuario](/azure/information-protection/configure-super-users) para Azure Information Protection y asegúrese de que la característica superusuario está habilitada. </br></br>Además, si ha implementado [controles de incorporación](/azure/information-protection/activate-service#configuring-onboarding-controls-for-a-phased-deployment) para una implementación por fases, asegúrese de que la cuenta de servicio está incluida en los controles de incorporación que ha configurado.|
|**Examen de nivel de dirección URL específico** |Para examinar y detectar sitios y subsitios [en una dirección URL específica](#deploying-the-scanner-with-alternative-configurations), conceda derechos de **auditor del recopilador** de sitios a la cuenta del analizador en el nivel de granja de servidores.|
|**Licencia para la protección de la información** | Se requiere para proporcionar funcionalidades de clasificación, etiquetado o protección de archivos a la cuenta de servicio del analizador. <br><br>Para obtener más información, consulte las [instrucciones de Microsoft 365 para la seguridad & cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection-sensitivity-labeling). |

## <a name="sql-server-requirements"></a>Requisitos de SQL Server

Para almacenar los datos de configuración del analizador, use un servidor SQL Server con los siguientes requisitos:

- **Una instancia local o remota.**

    Se recomienda hospedar sql server y el servicio de escáner en máquinas diferentes, a menos que trabaje con una pequeña implementación. Además, se recomienda tener una instancia de SQL dedicada que solo sirva a la base de datos del analizador y que no se comparta con otras aplicaciones.

    Si está trabajando en un servidor compartido, asegúrese de que el [número recomendado de núcleos](#windows-server-requirements) es gratuito para que la base de datos del analizador funcione.

    SQL Server 2016 es la versión mínima para las siguientes ediciones:

    - SQL Server Enterprise

    - SQL Server Standard

    - SQL Server Express (solo se recomienda para entornos de prueba)

- **Una cuenta con el rol Sysadmin para instalar el analizador.**

    El rol Sysadmin permite que el proceso de instalación cree automáticamente la base de datos de configuración del analizador y conceda el rol **de db_owner** necesario a la cuenta de servicio que ejecuta el analizador.

    Si no se le puede conceder el rol Sysadmin o las directivas de la organización requieren que las bases de datos se creen y configuren manualmente, consulte [Implementación del analizador con configuraciones alternativas](#deploying-the-scanner-with-alternative-configurations).

- **Capacidad.** Para obtener instrucciones sobre la capacidad, consulte [Requisitos de almacenamiento y planeamiento de capacidad para SQL Server](#storage-requirements-and-capacity-planning-for-sql-server).

- **[Intercalación sin distinción entre mayúsculas y minúsculas](/sql/relational-databases/collations/collation-and-unicode-support).**

> [!NOTE]
> Se admiten varias bases de datos de configuración en el mismo servidor SQL Server cuando se especifica un nombre de clúster personalizado para el analizador o cuando se usa la versión preliminar del analizador.

### <a name="storage-requirements-and-capacity-planning-for-sql-server"></a>Requisitos de almacenamiento y planeamiento de capacidad para SQL Server

La cantidad de espacio en disco necesaria para la base de datos de configuración del analizador y la especificación del equipo que ejecuta SQL Server puede variar para cada entorno, por lo que le recomendamos que realice sus propias pruebas. Use la siguiente guía como punto de partida.

Para obtener más información, consulte [Optimización del rendimiento del escáner](deploy-scanner-configure-install.md#optimize-scanner-performance).

El tamaño del disco de la base de datos de configuración del analizador variará para cada implementación. Use la siguiente ecuación como guía:

```cli
100 KB + <file count> *(1000 + 4* <average file name length>)
```

Por ejemplo, para examinar 1 millón de archivos que tienen una longitud media de nombre de archivo de 250 bytes, asigne 2 GB de espacio en disco.

Para varios escáneres:

- **Hasta 10 escáneres**, use:

    - Procesadores de 4 núcleos
    - 8 GB de RAM recomendada

- **Más de 10 escáneres** (máximo 40), utilice:
    - 8 procesos principales
    - 16 GB de RAM recomendada

## <a name="azure-information-protection-client-requirements"></a>Requisitos de cliente de Azure Information Protection

Debe tener instalada la [versión de disponibilidad general actual](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history) del cliente de Azure Information Protection en el equipo con Windows Server.

Para obtener más información, consulte la [guía del administrador de cliente de etiquetado unificado de Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide#installing-the-azure-information-protection-scanner).

> [!IMPORTANT]
> Debe instalar el cliente completo para el analizador. No instale el cliente solo con el módulo de PowerShell.
>

## <a name="label-configuration-requirements"></a>Requisitos de configuración de etiquetas

Debe tener al menos una etiqueta de confidencialidad configurada en la portal de cumplimiento Microsoft Purview para la cuenta del analizador, para aplicar la clasificación y, opcionalmente, el cifrado.

La *cuenta del analizador* es la cuenta que especificará en el parámetro **DelegatedUser** del cmdlet [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) , que se ejecuta al configurar el analizador. 

Si las etiquetas no tienen condiciones de etiquetado automático, consulte las [instrucciones para las configuraciones alternativas](#restriction-your-labels-do-not-have-auto-labeling-conditions) que se indican a continuación.

Para más información, vea:

- [Información sobre las etiquetas de confidencialidad](sensitivity-labels.md)
- [Aplicar una etiqueta de confidencialidad automáticamente al contenido](apply-sensitivity-label-automatically.md)
- [Restringir el acceso al contenido mediante el cifrado en las etiquetas de confidencialidad](encryption-sensitivity-labels.md)
- [Configuración e instalación del analizador de protección de la información](deploy-scanner-configure-install.md)

## <a name="sharepoint-requirements"></a>Requisitos de SharePoint

Para examinar las bibliotecas y carpetas de documentos de SharePoint, asegúrese de que el servidor de SharePoint cumple los siguientes requisitos:

|Requisito  |Descripción  |
|---------|---------|
|**Versiones compatibles** | Entre las versiones admitidas se incluyen: SharePoint 2019, SharePoint 2016 y SharePoint 2013. <br> No se admiten otras versiones de SharePoint para el analizador.     |
|**Control de versiones**     |  Al usar [el control de versiones](/sharepoint/governance/versioning-content-approval-and-check-out-planning), el analizador inspecciona y etiqueta la última versión publicada. <br><br>Si el analizador etiqueta un archivo y se requiere [la aprobación de contenido](/sharepoint/governance/versioning-content-approval-and-check-out-planning#plan-content-approval) , ese archivo etiquetado debe aprobarse para que esté disponible para los usuarios.       |
|**Granjas de servidores de SharePoint grandes** |En el caso de las granjas de servidores de SharePoint grandes, compruebe si necesita aumentar el umbral de vista de lista (de forma predeterminada, 5 000) para que el analizador acceda a todos los archivos. <br><br>Para obtener más información, vea [Administrar listas y bibliotecas grandes en SharePoint](https://support.office.com/article/manage-large-lists-and-libraries-in-sharepoint-b8588dae-9387-48c2-9248-c24122f07c59#__bkmkchangelimit&ID0EAABAAA=Server). |
|**Rutas de acceso de archivo largas**  |Si tiene rutas de acceso de archivo largas en SharePoint, asegúrese de que el valor [httpRuntime.maxUrlLength](/dotnet/api/system.web.configuration.httpruntimesection.maxurllength) del servidor de SharePoint sea mayor que los 260 caracteres predeterminados. <br><br>Para obtener más información, vea [Evitar tiempos de espera del analizador en SharePoint](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#avoid-scanner-timeouts-in-sharepoint). | 

## <a name="microsoft-office-requirements"></a>Requisitos de Microsoft Office

Para examinar documentos de Office, los documentos deben tener uno de los siguientes formatos:

- Microsoft Office 97-2003
- Formatos Open XML de Office para Word, Excel y PowerPoint

Para obtener más información, consulte [Tipos de archivo admitidos por el cliente de etiquetado unificado de Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide-file-types).

## <a name="file-path-requirements"></a>Requisitos de ruta de acceso de archivo

De forma predeterminada, para examinar archivos, las rutas de acceso de archivo deben tener un máximo de 260 caracteres.

Para examinar archivos con rutas de acceso de archivo de más de 260 caracteres, instale el escáner en un equipo con una de las siguientes versiones de Windows y configure el equipo según sea necesario:

|Versión de Windows  |Descripción  |
|---------|---------|
|**Windows 2016 o posterior**     |   Configuración del equipo para admitir rutas de acceso largas      |
|**Windows 10 o Windows Server 2016**     | Defina la siguiente [configuración de directiva de grupo](/archive/blogs/jeremykuhne/net-4-6-2-and-long-paths-on-windows-10):**Configuración** >  del equipo de directiva de **equipo** >  local **Plantillas** >  administrativas **Toda la configuración** > **Habilita las rutas de acceso largas de Win32**.    </br></br>Para obtener más información sobre la compatibilidad con rutas de acceso de archivos largas en estas versiones, consulte la sección [Limitación de longitud](/windows/desktop/FileIO/naming-a-file#maximum-path-length-limitation) máxima de ruta de acceso de la documentación de Windows 10 desarrollador.    |
|**Windows 10, versión 1607 o posterior**     |  Opte por la funcionalidad **de MAX_PATH** actualizada. Para obtener más información, vea [Habilitar rutas de acceso largas en Windows 10 versiones 1607 y posteriores](/windows/win32/fileio/naming-a-file#enable-long-paths-in-windows-10-version-1607-and-later).      |

## <a name="deploying-the-scanner-with-alternative-configurations"></a>Implementación del analizador con configuraciones alternativas

Los requisitos previos enumerados anteriormente son los requisitos predeterminados para la implementación del analizador y se recomiendan porque admiten la configuración del analizador más sencilla.

Los requisitos predeterminados deben ser adecuados para las pruebas iniciales, de modo que pueda comprobar las funcionalidades del escáner.

Sin embargo, en un entorno de producción, las directivas de la organización pueden ser diferentes de los requisitos predeterminados. El analizador puede dar cabida a los siguientes cambios con una configuración adicional:

- [Detección y examen de todos los sitios y subsitios en una dirección URL específica](#discover-and-scan-all-sharepoint-sites-and-subsites-under-a-specific-url)

- [Restricción: el servidor de escáner no puede tener conectividad a Internet](#restriction-the-scanner-server-cannot-have-internet-connectivity)

- [Restricción: la cuenta de servicio del analizador no se puede sincronizar con Azure Active Directory, pero el servidor tiene conectividad a Internet](#restriction-the-scanner-service-account-cannot-be-synchronized-to-azure-active-directory-but-the-server-has-internet-connectivity)

- [Restricción: no se puede conceder a la cuenta de servicio del analizador el derecho **Iniciar sesión localmente**](#restriction-the-service-account-for-the-scanner-cannot-be-granted-the-log-on-locally-right)

- [Restricción: No se le puede conceder Sysadmin o las bases de datos deben crearse y configurarse manualmente.](#restriction-you-cannot-be-granted-sysadmin-or-databases-must-be-created-and-configured-manually)

- [Restricción: las etiquetas no tienen condiciones de etiquetado automático](#restriction-your-labels-do-not-have-auto-labeling-conditions)

### <a name="discover-and-scan-all-sharepoint-sites-and-subsites-under-a-specific-url"></a>Detección y examen de todos los sitios y subsitios de SharePoint en una dirección URL específica

El analizador puede detectar y examinar todos los sitios y subsitios de SharePoint en una dirección URL específica con la siguiente configuración:

1. Inicie **administración central de SharePoint**.

1. En el sitio web **de Administración central de SharePoint** , en la sección **Administración de** aplicaciones, haga clic en **Administrar aplicaciones web**.

1. Haga clic para resaltar la aplicación web cuyo nivel de directiva de permisos desea administrar.

1. Elija la granja correspondiente y, a continuación, seleccione **Administrar niveles de directiva de permisos**.

1. Seleccione **Auditor de colección** de sitios en las opciones **Permisos de colección** de sitios, conceda **a View Application Pages** en la lista Permisos y, por último, asigne al nuevo nivel de directiva el nombre **Auditor y visor de la colección de sitios del analizador de AIP**.

1. Agregue el usuario del analizador a la nueva directiva y conceda **a La colección de sitios** en la lista Permisos.

1. Agregue una dirección URL de SharePoint que hospede sitios o subsitios que necesiten examinarse. Para obtener más información, consulte [Configuración de los valores del analizador](/azure/information-protection/deploy-scanner-configure-install#configure-the-scanner-settings).

Para obtener más información sobre cómo administrar los niveles de directiva de SharePoint, vea [Administrar directivas de permisos para una aplicación web](/sharepoint/administration/manage-permission-policies-for-a-web-application).

### <a name="restriction-the-scanner-server-cannot-have-internet-connectivity"></a>Restricción: el servidor de escáner no puede tener conectividad a Internet

Aunque el cliente de etiquetado unificado no puede aplicar el cifrado sin una conexión a Internet, el analizador todavía puede aplicar etiquetas basadas en directivas importadas.

Para admitir un equipo desconectado, use uno de los métodos siguientes:

- [Uso de Azure Portal](#use-the-azure-portal-with-a-disconnected-computer) (recomendado siempre que sea posible)

- [Usar PowerShell](#use-powershell-with-a-disconnected-computer)

#### <a name="use-the-azure-portal-with-a-disconnected-computer"></a>Uso de Azure Portal con un equipo desconectado

Para admitir un equipo desconectado de Azure Portal, siga estos pasos:

1.  Configure las etiquetas en la directiva y, a continuación, use el [procedimiento para admitir equipos desconectados](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#support-for-disconnected-computers) para habilitar la clasificación y el etiquetado sin conexión.

1. Habilite la administración sin conexión para los trabajos de contenido como se indica a continuación:

    **Habilitar la administración sin conexión para trabajos de examen de contenido**:

    1. Establezca el analizador para que funcione en modo **sin conexión** mediante el cmdlet [Set-AIPScannerConfiguration](/powershell/module/azureinformationprotection/set-aipscannerconfiguration) .

    1. Configure el analizador en el portal de cumplimiento mediante la creación de un clúster de escáner. Para obtener más información, consulte [Configuración de los valores del analizador](deploy-scanner-configure-install.md#configure-the-scanner-settings).

    1. Exporte el trabajo de contenido desde el panel Protección de la **información: trabajos de examen de contenido** mediante la opción **Exportar** .

    1. Importe la directiva mediante el cmdlet [Import-AIPScannerConfiguration](/powershell/module/azureinformationprotection/import-aipscannerconfiguration) .

    Los resultados de los trabajos de examen de contenido sin conexión se encuentran en: **%localappdata%\Microsoft\MSIP\Scanner\Reports**

#### <a name="use-powershell-with-a-disconnected-computer"></a>Uso de PowerShell con un equipo desconectado

Realice el procedimiento siguiente para admitir un equipo desconectado solo con PowerShell.

> [!IMPORTANT]
> Los administradores de [los servidores de escáner de Azure China 21Vianet](/microsoft-365/admin/services-in-china/parity-between-azure-information-protection#manage-azure-information-protection-content-scan-jobs) *deben* usar este procedimiento para administrar sus trabajos de examen de contenido.
>

**Administre los trabajos de examen de contenido solo con PowerShell**:

1. Establezca el analizador para que funcione en modo **sin conexión** mediante el cmdlet [Set-AIPScannerConfiguration](/powershell/module/azureinformationprotection/set-aipscannerconfiguration) .

1. Cree un nuevo trabajo de examen de contenido mediante el cmdlet [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) , asegurándose de usar el parámetro obligatorio `-Enforce On` .

1. Agregue los repositorios mediante el cmdlet [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) , con la ruta de acceso al repositorio que desea agregar.

    > [!TIP]
    > Para evitar que el repositorio herede la configuración del trabajo de examen de contenido, agregue el `OverrideContentScanJob On` parámetro, así como los valores de configuración adicionales.
    >
    > Para editar los detalles de un repositorio existente, use el comando [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) .
    >
 
1. Use los cmdlets [Get-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) y [Get-AIPScannerRepository](/powershell/module/azureinformationprotection/get-aipscannerrepository) para devolver información sobre la configuración actual del trabajo de examen de contenido. 

1. Use el comando [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) para actualizar los detalles de un repositorio existente.

1. Ejecute el trabajo de examen de contenido inmediatamente si es necesario mediante el cmdlet [Start-AIPScan](/powershell/module/azureinformationprotection/start-aipscan) . 

    Los resultados de los trabajos de examen de contenido sin conexión se encuentran en: **%localappdata%\Microsoft\MSIP\Scanner\Reports**

1. Si necesita quitar un repositorio o un trabajo de examen de contenido completo, use los siguientes cmdlets:

    - [Remove-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob)
    - [Remove-AIPScannerRepository](/powershell/module/azureinformationprotection/remove-aipscannerrepository)

### <a name="restriction-you-cannot-be-granted-sysadmin-or-databases-must-be-created-and-configured-manually"></a>Restricción: No se le puede conceder Sysadmin o las bases de datos deben crearse y configurarse manualmente.

Use los procedimientos siguientes para crear manualmente bases de datos y conceder el rol **de db_owner** , según sea necesario.

- [Procedimiento para la base de datos del analizador](#manually-create-a-database-and-user-for-the-scanner-and-grant-db_owner-rights)

Si se le puede conceder el rol Sysadmin *temporalmente* para instalar el analizador, puede quitar este rol cuando se complete la instalación del analizador.

Realice una de las siguientes acciones, en función de los requisitos de su organización:

|Restriction  |Descripción  |
|---------|---------|
|**Puede tener el rol Sysadmin temporalmente.**     |  Si tiene temporalmente el rol Sysadmin, la base de datos se crea automáticamente y a la cuenta de servicio del analizador se le conceden automáticamente los permisos necesarios. <br><br>Sin embargo, la cuenta de usuario que configura el analizador todavía requiere el rol **de db_owner** para la base de datos de configuración del analizador. Si solo tiene el rol Sysadmin hasta que se complete la instalación del analizador, conceda manualmente el rol **db_owner** a la cuenta de usuario.       |
|**No puede tener el rol Sysadmin en absoluto.**     |  Si no se le puede conceder el rol Sysadmin incluso temporalmente, debe pedir a un usuario con derechos sysadmin que cree manualmente una base de datos antes de instalar el analizador. <br><br>Para esta configuración, el rol **de db_owner** debe asignarse a las cuentas siguientes: <br>- Cuenta de servicio para el analizador<br>- Cuenta de usuario para la instalación del escáner<br>- Cuenta de usuario para la configuración del analizador <br><br>Normalmente, usará la misma cuenta de usuario para instalar y configurar el analizador. Si usa cuentas diferentes, ambas requieren el rol **de db_owner** para la base de datos de configuración del analizador. Cree este usuario y los derechos según sea necesario. Si especifica su propio nombre de clúster, la base de datos de configuración se denomina **AIPScannerUL_<cluster_name>**.  |

Además:

- Debe ser un administrador local en el servidor que ejecutará el analizador.
- A la cuenta de servicio que ejecutará el analizador se le deben conceder permisos de control total a las siguientes claves del Registro:

    - `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\Server`
    - `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\Server`

Si, después de configurar estos permisos, ve un error al instalar el analizador, se puede omitir el error y puede iniciar manualmente el servicio de escáner.

#### <a name="manually-create-a-database-and-user-for-the-scanner-and-grant-db_owner-rights"></a>Cree manualmente una base de datos y un usuario para el analizador y conceda derechos de db_owner

Si necesita crear manualmente la base de datos del analizador o crear un usuario y conceder **derechos de db_owner** en la base de datos, pida al administrador del sistema que realice los pasos siguientes:

1. Cree una base de datos para el analizador:

    ```sql
    **CREATE DATABASE AIPScannerUL_[clustername]**

    **ALTER DATABASE AIPScannerUL_[clustername] SET TRUSTWORTHY ON**
    ```

2. Conceda derechos al usuario que ejecuta el comando de instalación y se usa para ejecutar comandos de administración del analizador. Use el siguiente script:

    ```sql
    if not exists(select * from master.sys.server_principals where sid = SUSER_SID('domain\user')) BEGIN declare @T nvarchar(500) Set @T = 'CREATE LOGIN ' + quotename('domain\user') + ' FROM WINDOWS ' exec(@T) END
    USE DBName IF NOT EXISTS (select * from sys.database_principals where sid = SUSER_SID('domain\user')) BEGIN declare @X nvarchar(500) Set @X = 'CREATE USER ' + quotename('domain\user') + ' FROM LOGIN ' + quotename('domain\user'); exec sp_addrolemember 'db_owner', 'domain\user' exec(@X) END
    ```

3. Conceda derechos a la cuenta de servicio del analizador. Use el siguiente script:

    ```sql
    if not exists(select * from master.sys.server_principals where sid = SUSER_SID('domain\user')) BEGIN declare @T nvarchar(500) Set @T = 'CREATE LOGIN ' + quotename('domain\user') + ' FROM WINDOWS ' exec(@T) END
    ```

### <a name="restriction-the-service-account-for-the-scanner-cannot-be-granted-the-log-on-locally-right"></a>Restricción: no se puede conceder a la cuenta de servicio del analizador el derecho **Iniciar sesión localmente**

Si las directivas de su organización prohíben el derecho **Iniciar sesión localmente** para las cuentas de servicio, use el parámetro *OnBehalfOf* con Set-AIPAuthentication.

Para obtener más información, consulte [Cómo etiquetar archivos de forma no interactiva para Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection).

### <a name="restriction-the-scanner-service-account-cannot-be-synchronized-to-azure-active-directory-but-the-server-has-internet-connectivity"></a>Restricción: la cuenta de servicio del analizador no se puede sincronizar con Azure Active Directory, pero el servidor tiene conectividad a Internet

Puede tener una cuenta para ejecutar el servicio de escáner y usar otra cuenta para autenticarse en Azure Active Directory:

- **Para la cuenta de servicio del analizador**, use una cuenta local de Windows o una cuenta de Active Directory.

- **Para la cuenta de Azure Active Directory**, especifique el usuario de AAD en el cmdlet [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) , en el parámetro *DelegatedUser* . 

    Si está ejecutando el examen en cualquier usuario que no sea la cuenta del analizador, asegúrese de especificar también la cuenta del escáner en el parámetro *OnBehalfOf* . 

    Para obtener más información, consulte [Cómo etiquetar archivos de forma no interactiva para Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection).

### <a name="restriction-your-labels-do-not-have-auto-labeling-conditions"></a>Restricción: las etiquetas no tienen condiciones de etiquetado automático

Si las etiquetas no tienen condiciones de etiquetado automático, planee usar una de las siguientes opciones al configurar el escáner:

|Opción  |Descripción  |
|---------|---------|
|**Detectar todos los tipos de información**     |  En el [trabajo de examen de contenido](deploy-scanner-configure-install.md#create-a-content-scan-job), establezca la opción **Tipos de información que se van a detectar** en **Todos**. </br></br>Esta opción establece el trabajo de examen de contenido para examinar el contenido en busca de todos los tipos de información confidencial.      |
|**Uso del etiquetado recomendado**     |  En el [trabajo de examen de contenido](deploy-scanner-configure-install.md#create-a-content-scan-job), establezca la opción **Tratar el etiquetado recomendado como automático** **en Activado**.</br></br> Esta configuración configura el analizador para aplicar automáticamente todas las etiquetas recomendadas en el contenido.      |
|**Definición de una etiqueta predeterminada**     |   Defina una etiqueta predeterminada en la [directiva](sensitivity-labels.md#what-label-policies-can-do), el [trabajo de examen de contenido](deploy-scanner-configure-install.md#create-a-content-scan-job) o [el repositorio](deploy-scanner-configure-install.md#apply-a-default-label-to-all-files-in-a-data-repository). </br></br>En este caso, el escáner aplica la etiqueta predeterminada en todos los archivos encontrados.       |

## <a name="next-steps"></a>Pasos siguientes

Una vez que haya confirmado que el sistema cumple los requisitos previos del escáner, continúe con [Configuración e instalación del analizador de protección de la información](deploy-scanner-configure-install.md).

Para obtener información general sobre el analizador, consulte [Información sobre el analizador de protección de la información](deploy-scanner.md).