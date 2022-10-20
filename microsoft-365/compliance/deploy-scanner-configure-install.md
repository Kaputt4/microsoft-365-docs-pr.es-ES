---
title: Instalación y configuración del analizador de Microsoft Purview Information Protection
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
description: Obtenga información sobre cómo instalar y configurar el analizador de Microsoft Purview Information Protection para detectar, clasificar y proteger archivos en almacenes de datos.
ms.openlocfilehash: 69d8d337f78fab74f35955ad15bd2d2e013a436c
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68623965"
---
# <a name="configuring-and-installing-the-information-protection-scanner"></a>Configuración e instalación del analizador de protección de la información

> [!NOTE]
> El analizador de Microsoft Purview Information Protection se denominaba anteriormente analizador de etiquetado unificado de Azure Information Protection o escáner local. La configuración se ha movido de Azure Portal al portal de cumplimiento Microsoft Purview.

En este artículo se describe cómo configurar e instalar el analizador de Microsoft Purview Information Protection, anteriormente denominado analizador de etiquetado unificado de Azure Information Protection, o el analizador local.

> [!TIP]
> Aunque la mayoría de los clientes realizarán estos procedimientos en el portal de administración, es posible que tenga que trabajar solo en PowerShell.
>
> Por ejemplo, si trabaja en un entorno sin acceso al portal de administración, como [los servidores de escáner de Azure China 21Vianet](/microsoft-365/admin/services-in-china/parity-between-azure-information-protection#manage-azure-information-protection-content-scan-jobs), siga las instrucciones de [Uso de PowerShell para configurar el analizador](#use-powershell-to-configure-the-scanner).
>

## <a name="overview"></a>Información general

Antes de empezar, compruebe que el sistema cumple los [requisitos previos necesarios](deploy-scanner-prereqs.md).

A continuación, siga estos pasos para configurar e instalar el analizador:

1. [Configuración de la configuración del analizador](#configure-the-scanner-settings)

2. [Instalación del analizador](#install-the-scanner)

3. [Obtención de un token de Azure AD para el analizador](#get-an-azure-ad-token-for-the-scanner)

4. [Configuración del analizador para aplicar la clasificación y la protección](#configure-the-scanner-to-apply-classification-and-protection)

A continuación, realice los siguientes procedimientos de configuración según sea necesario para el sistema:

|Procedure  |Descripción  |
|---------|---------|
|[Cambiar los tipos de archivo que se van a proteger](#change-which-file-types-to-protect) |Es posible que desee examinar, clasificar o proteger tipos de archivo diferentes a los predeterminados. Para obtener más información, consulte [El proceso de examen](deploy-scanner.md#the-scanning-process). |
|[Actualización del escáner](#upgrade-your-scanner) | Actualice el escáner para usar las características y mejoras más recientes.|
|[Edición de la configuración del repositorio de datos de forma masiva](#edit-data-repository-settings-in-bulk)| Use las opciones de importación y exportación para realizar cambios de forma masiva en varios repositorios de datos.|
|[Uso del escáner con configuraciones alternativas](#use-the-scanner-with-alternative-configurations)| Uso del analizador sin configurar etiquetas con ninguna condición |
|[Optimizar el rendimiento](#optimize-scanner-performance)| Guía para optimizar el rendimiento del escáner|

Si no tiene acceso a las páginas del analizador en el portal de cumplimiento, configure los valores de analizador solo en PowerShell. Para obtener más información, consulte [Uso de PowerShell para configurar el analizador](#use-powershell-to-configure-the-scanner) y [los cmdlets de PowerShell admitidos](#supported-powershell-cmdlets).


## <a name="configure-the-scanner-settings"></a>Configuración de la configuración del analizador

Antes de instalar el escáner o actualizarlo desde una versión de disponibilidad general anterior, configure o compruebe la configuración del analizador.

**Para configurar el escáner en el portal de cumplimiento Microsoft Purview:**

1. Inicie sesión en el [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com) con uno de los siguientes roles:

    - **Administrador de cumplimiento**
    - **Administrador de datos de cumplimiento**
    - **Administrador de seguridad**
    - **Administrador global**

    A continuación, vaya al panel **Configuración** .

    En el panel **Configuración** , seleccione **Analizador de protección de la información**.

2. [Cree un clúster de escáner](#create-a-scanner-cluster). Este clúster define el analizador y se usa para identificar la instancia del analizador, como durante la instalación, las actualizaciones y otros procesos.

3. [Cree un trabajo de examen de contenido](#create-a-content-scan-job) para definir los repositorios que desea examinar.

### <a name="create-a-scanner-cluster"></a>Creación de un clúster de escáner

**Para crear un clúster de escáner en el portal de cumplimiento Microsoft Purview:**

1. En las pestañas de la página **Analizador de information protection** , seleccione **Clústeres**.

2. En la pestaña **Clústeres** , seleccione **El** ![icono Agregar agregar](../media/i-add.png "icono de agregar").

3. En el panel **Nuevo clúster** , escriba un nombre significativo para el analizador y una descripción opcional.

    El nombre del clúster se usa para identificar las configuraciones y repositorios del analizador. Por ejemplo, puede escribir **Europa** para identificar las ubicaciones geográficas de los repositorios de datos que desea examinar.

    Usará este nombre más adelante para identificar dónde desea instalar o actualizar el escáner.

4. Seleccione **Guardar** para guardar los cambios.

### <a name="create-a-content-scan-job"></a>Creación de un trabajo de examen de contenido

Profundiza en el contenido para examinar repositorios específicos en busca de contenido confidencial.

**Para crear el trabajo de examen de contenido en el portal de cumplimiento Microsoft Purview:**

1. En las pestañas de la página **Analizador de protección** de la información, seleccione **Trabajos de examen de contenido**.

2. En el panel **Trabajos de examen de contenido** , seleccione **Agregar** ![icono agregar](../media/i-add.png "icono guardar").

3. Para esta configuración inicial, configure los siguientes valores y, a continuación, seleccione **Guardar**.

    |Configuración  |Descripción  |
    |---------|---------|
    |**Configuración del trabajo de examen de contenido**     |    - **Programación**: mantenga el valor predeterminado de **Manual** <br />- **Tipos de información que se van a detectar**: cambiar **solo a directiva**
    |**Directiva DLP** | Si usa una directiva de prevención de pérdida de datos, establezca **Habilitar reglas DLP** **en Activado**. Para obtener más información, consulte [Uso de una directiva DLP](#use-a-dlp-policy). |
    |**Directiva de confidencialidad**     | - **Aplicar directiva de etiquetado de confidencialidad**: Seleccione **Desactivado** <br />- **Archivos de etiqueta basados en contenido**: mantenga el valor predeterminado de **Activado** <br />- **Etiqueta predeterminada**: mantenga el valor predeterminado de **Policy default (Valor predeterminado de directiva).** <br />- **Volver a etiquetar archivos**: mantenga el valor predeterminado **desactivado**        |
    |**Configuración de los valores de archivo**     | - **Conservar "Fecha de modificación", "Última modificación" y "Modificado por"**: Mantener el valor predeterminado de **Activado** <br />- **Tipos de archivo que se van a examinar**: mantenga los tipos de archivo predeterminados para **Excluir**. <br />- **Propietario predeterminado**: mantenga el valor predeterminado de **Cuenta de escáner**  <br /> - **Establecer propietario del repositorio**: use esta opción solo cuando [use una directiva DLP](#use-a-dlp-policy). |
    | | |


4. Abra el trabajo de examen de contenido que se guardó y seleccione la pestaña **Repositorios** para especificar los almacenes de datos que se van a examinar. 

    Especifique rutas de acceso UNC y direcciones URL de SharePoint Server para carpetas y bibliotecas de documentos locales de SharePoint.

    > [!NOTE]
    > SharePoint Server 2019, SharePoint Server 2016 y SharePoint Server 2013 son compatibles con SharePoint. SharePoint Server 2010 también se admite cuando se ha [ampliado la compatibilidad con esta versión de SharePoint](https://support.microsoft.com/lifecycle/search?alpha=SharePoint%20Server%202010).
    >
    Para agregar el primer almacén de datos, mientras que en la pestaña **Repositorios** :

    1. En el panel **Repositorios** , seleccione **Agregar**:

    2. En el panel **Repositorio** , especifique la ruta de acceso del repositorio de datos y, a continuación, seleccione **Guardar**.


        - Para un recurso compartido de red, use `\\Server\Folder`.
        - Para una biblioteca de SharePoint, use `http://sharepoint.contoso.com/Shared%20Documents/Folder`.
        - Para una ruta de acceso local: `C:\Folder`
        - Para una ruta de acceso UNC: `\\Server\Folder`

    > [!NOTE]
    > No se admiten caracteres comodín y no se admiten ubicaciones webDav.
    >

    Si agrega una ruta de acceso de SharePoint para **documentos compartidos**:
    - Especifique **Documentos compartidos** en la ruta de acceso cuando desee examinar todos los documentos y todas las carpetas de Documentos compartidos.
    Por ejemplo: `http://sp2013/SharedDocuments`
    - Especifique **Documentos** en la ruta de acceso cuando desee examinar todos los documentos y todas las carpetas de una subcarpeta en Documentos compartidos.
    Por ejemplo: `http://sp2013/Documents/SalesReports`
    - O bien, especifique solo el **FQDN** de SharePoint, por ejemplo `http://sp2013` , para [detectar y examinar todos los sitios y subsitios de SharePoint en una dirección URL y](deploy-scanner-prereqs.md#discover-and-scan-all-sharepoint-sites-and-subsites-under-a-specific-url) subtítulos específicos en esta dirección URL. Conceda derechos al **auditor del recopilador** de sitios del escáner para habilitarlo.
    >


    Para la configuración restante de este panel, no las cambie para esta configuración inicial, pero guárdelas como **el trabajo de examen de contenido predeterminado**. La configuración predeterminada significa que el repositorio de datos hereda la configuración del trabajo de examen de contenido.

    Use la sintaxis siguiente al agregar rutas de acceso de SharePoint:

    |Path  |Sintaxis  |
    |---------|---------|
    |**Ruta de acceso raíz**     | `http://<SharePoint server name>` <br /><br />Examina todos los sitios, incluidas las colecciones de sitios permitidas para el usuario del analizador. <br />Requiere [permisos adicionales](deploy-scanner-prereqs.md#discover-and-scan-all-sharepoint-sites-and-subsites-under-a-specific-url) para detectar automáticamente el contenido raíz.        |
    |**Subsitio o colección de SharePoint específico**     | Uno de los siguientes: <br />- `http://<SharePoint server name>/<subsite name>` <br />- `http://SharePoint server name>/<site collection name>/<site name>` <br /><br />Requiere [permisos adicionales](deploy-scanner-prereqs.md#discover-and-scan-all-sharepoint-sites-and-subsites-under-a-specific-url) para detectar automáticamente el contenido de la colección de sitios.         |
    |**Biblioteca específica de SharePoint**     | Uno de los siguientes: <br />- `http://<SharePoint server name>/<library name>` <br />- `http://SharePoint server name>/.../<library name>`       |
    |**Carpeta específica de SharePoint**     | `http://<SharePoint server name>/.../<folder name>`        |
    | | |

5. Repita los pasos anteriores para agregar tantos repositorios como sea necesario.

Ya está listo para instalar el escáner con el trabajo de escáner de contenido que ha creado. Continúe con [Instalar el escáner](#install-the-scanner).

## <a name="install-the-scanner"></a>Instalación del analizador

Después de [configurar el analizador](#configure-the-scanner-settings), realice los pasos siguientes para instalar el analizador. Este procedimiento se realiza completamente en PowerShell.

1. Inicie sesión en el equipo con Windows Server que ejecutará el analizador. Use una cuenta que tenga derechos de administrador local y que tenga permisos para escribir en la base de datos maestra de SQL Server.

    > [!IMPORTANT]
    > Debe tener instalado el cliente de etiquetado unificado de AIP en el equipo antes de instalar el escáner.
    >
    > Para obtener más información, consulte [Requisitos previos para instalar e implementar el analizador de protección de la información](deploy-scanner-prereqs.md).
    >

2. Abra una sesión de Windows PowerShell con la opción **Ejecutar como administrador**.

3. Ejecute el cmdlet [Install-AIPScanner](/powershell/module/azureinformationprotection/Install-AIPScanner) y especifique la instancia de SQL Server en la que crear una base de datos para el analizador de Azure Information Protection y el nombre del clúster del analizador que [especificó en la sección anterior](#create-a-scanner-cluster):

    ```PowerShell
    Install-AIPScanner -SqlServerInstance <name> -Cluster <cluster name>
    ```

    Ejemplos, con el nombre del clúster del analizador de **Europa**:

    - Para una instancia predeterminada: `Install-AIPScanner -SqlServerInstance SQLSERVER1 -Cluster Europe`

    - Para una instancia con nombre: `Install-AIPScanner -SqlServerInstance SQLSERVER1\AIPSCANNER -Cluster Europe`

    - Para SQL Server Express:`Install-AIPScanner -SqlServerInstance SQLSERVER1\SQLEXPRESS -Cluster Europe`

    Cuando se le solicite, proporcione las credenciales de Active Directory para la cuenta de servicio del analizador.

    Use la sintaxis siguiente: `\<domain\user name>`. Por ejemplo: `contoso\scanneraccount`

4. Compruebe que el servicio ya está instalado mediante **servicios de herramientas** >  administrativas.

    El servicio instalado se denomina **Analizador de Azure Information Protection** y está configurado para ejecutarse mediante la cuenta de servicio del analizador que creó.

Ahora que ha instalado el analizador, debe [obtener un token de Azure AD para que la](#get-an-azure-ad-token-for-the-scanner) cuenta de servicio del analizador se autentique, de modo que el analizador pueda ejecutarse desatendida.

## <a name="get-an-azure-ad-token-for-the-scanner"></a>Obtención de un token de Azure AD para el analizador

Un token de Azure AD permite al analizador autenticarse en el servicio Azure Information Protection, lo que permite que el analizador se ejecute de forma no interactiva.

Para obtener más información, consulte [Cómo etiquetar archivos de forma no interactiva para Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection).

**Para obtener un token de Azure AD**:

1. Abra [Azure Portal](https://portal.azure.com/) para crear una aplicación de Azure AD para especificar un token de acceso para la autenticación.

2. Desde el equipo con Windows Server, si a la cuenta de servicio del analizador se le ha concedido el derecho **Iniciar sesión localmente** para la instalación, inicie sesión con esta cuenta e inicie una sesión de PowerShell.

    Ejecute [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) y especifique los valores que copió del paso anterior:

    ```PowerShell
    Set-AIPAuthentication -AppId <ID of the registered app> -AppSecret <client secret sting> -TenantId <your tenant ID> -DelegatedUser <Azure AD account>
    ```

    Por ejemplo:

    ```PowerShell
    $pscreds = Get-Credential CONTOSO\scanner
    Set-AIPAuthentication -AppId "77c3c1c3-abf9-404e-8b2b-4652836c8c66" -AppSecret "OAkk+rnuYc/u+]ah2kNxVbtrDGbS47L4" -DelegatedUser scanner@contoso.com -TenantId "9c11c87a-ac8b-46a3-8d5c-f4d0b72ee29a" -OnBehalfOf $pscreds
    Acquired application access token on behalf of CONTOSO\scanner.
    ```

    > [!TIP]
    > Si no se puede conceder a la cuenta de servicio del analizador el derecho **Iniciar sesión localmente** para la instalación, use el parámetro *OnBehalfOf* con [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication), tal como se describe en [Cómo etiquetar archivos de forma no interactiva para Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection).
    >

El analizador ahora tiene un token para autenticarse en Azure AD. Este token es válido durante un año, dos años o nunca, según la configuración del secreto de cliente de la **aplicación web /API** en Azure AD. Cuando expire el token, debe repetir este procedimiento.

Siga usando uno de los pasos siguientes, en función de si usa el portal de cumplimiento para configurar el analizador o solo PowerShell:

# <a name="admin-portal-only"></a>[solo Administración portal](#tab/azure-portal-only)

Ya está listo para ejecutar el primer examen en modo de detección. Para obtener más información, consulte [Ejecución de un ciclo de detección y visualización de informes para el analizador](deploy-scanner-manage.md#run-a-discovery-cycle-and-view-reports-for-the-scanner).

Una vez que haya ejecutado el examen de detección inicial, continúe con [Configuración del analizador para aplicar la clasificación y la protección](#configure-the-scanner-to-apply-classification-and-protection).

# <a name="powershell-only"></a>[Solo PowerShell](#tab/powershell-only)

Si va a configurar e instalar el analizador mediante PowerShell en lugar de las páginas del analizador en el portal de cumplimiento, continúe con el paso 5 en [Uso de PowerShell para configurar el analizador](#powershell).

Luego:

- [Ejecutar un ciclo de detección y ver informes del escáner](deploy-scanner-manage.md#run-a-discovery-cycle-and-view-reports-for-the-scanner)
- [Uso de PowerShell para configurar el analizador para aplicar la clasificación y la protección](#use-powershell-to-configure-the-scanner-to-apply-classification-and-protection)
- [Uso de PowerShell para configurar una directiva DLP con el analizador](#use-powershell-to-configure-a-dlp-policy-with-the-scanner)

---

> [!NOTE]
> Para obtener más información, consulte [Cómo etiquetar archivos de forma no interactiva para Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection).



## <a name="configure-the-scanner-to-apply-classification-and-protection"></a>Configuración del analizador para aplicar la clasificación y la protección

La configuración predeterminada configura el analizador para que se ejecute una vez y en modo de solo informes. Para cambiar esta configuración, edite el trabajo de examen de contenido.

> [!TIP]
> Si solo está trabajando en PowerShell, consulte [Configuración del analizador para aplicar la clasificación y la protección: solo PowerShell](#use-powershell-to-configure-the-scanner-to-apply-classification-and-protection).
>

**Para configurar el analizador para aplicar la clasificación y la protección en el portal de cumplimiento Microsoft Purview**:

1. En la portal de cumplimiento Microsoft Purview, en la pestaña **Trabajos de examen de contenido**, seleccione un trabajo de examen de contenido específico para editarlo.

2. Seleccione el trabajo de examen de contenido, cambie lo siguiente y, a continuación, seleccione **Guardar**:

   - En la sección **Trabajo de examen de contenido** : cambie la **programación** a **Always**
   - En la sección **Aplicar directiva de etiquetado de confidencialidad**: cambie el botón de radio a **Activado**.

3. Asegúrese de que un nodo para el trabajo de examen de contenido esté en línea y, a continuación, vuelva a iniciar el trabajo de examen de contenido seleccionando **Examinar ahora**. El botón **Examinar ahora** solo aparece cuando un nodo del trabajo de examen de contenido seleccionado está en línea. 

El escáner está programado para ejecutarse continuamente. Cuando el escáner funciona a través de todos los archivos configurados, inicia automáticamente un nuevo ciclo para que se detecten los archivos nuevos y modificados.

## <a name="use-a-dlp-policy"></a>Uso de una directiva DLP

El uso de una directiva de prevención de pérdida de datos permite al analizador detectar posibles fugas de datos mediante la coincidencia de reglas DLP con archivos almacenados en recursos compartidos de archivos y SharePoint Server.

- **Habilite las reglas DLP en el trabajo de examen de contenido** para reducir la exposición de los archivos que coincidan con las directivas DLP. Cuando se habilitan las reglas DLP, el analizador puede reducir el acceso de archivos solo a los propietarios de datos o reducir la exposición a grupos de toda la red, como **Todos**, **Usuarios autenticados** o **Usuarios de dominio**.

- **En el portal de cumplimiento Microsoft Purview**, determine si solo está probando la directiva DLP o si desea que se apliquen las reglas y los permisos de archivo cambien según esas reglas. Para obtener más información, vea [Activar una directiva DLP](create-test-tune-dlp-policy.md#turn-on-a-dlp-policy).

Las directivas DLP se configuran en el portal de cumplimiento de Microsoft Purview. Para obtener más información sobre las licencias DLP, consulte [Introducción al analizador local de prevención de pérdida de datos](dlp-on-premises-scanner-get-started.md).

> [!TIP]
> El examen de los archivos, incluso al probar la directiva DLP, también crea informes de permisos de archivo. Consulte estos informes para investigar exposiciones de archivos específicas o explorar la exposición de un usuario específico a los archivos escaneados.
>
> Para usar solo PowerShell, consulte [Uso de una directiva DLP con el analizador: solo PowerShell](#use-powershell-to-configure-a-dlp-policy-with-the-scanner).
>

**Para usar una directiva DLP con el analizador en el portal de cumplimiento Microsoft Purview**:

1. En el portal de cumplimiento Microsoft Purview, vaya a la pestaña **Trabajos de examen de contenido** y seleccione un trabajo de examen de contenido específico. Para obtener más información, consulte [Creación de un trabajo de examen de contenido](#create-a-content-scan-job).

2. En **Habilitar reglas de directiva DLP**, establezca el botón de radio **en Activado**.
    
    > [!IMPORTANT]
    > No establezca **Habilitar reglas DLP** en **Activado** a menos que tenga una directiva DLP configurada en Microsoft 365.
    >
    >Activar esta característica sin una directiva DLP hará que el analizador genere errores.

3. (Opcional) Establezca el **propietario del repositorio** **en Activado** y defina un usuario específico como propietario del repositorio.
    
    Esta opción permite al analizador reducir la exposición de los archivos que se encuentran en este repositorio, que coinciden con la directiva DLP, con el propietario del repositorio definido.

### <a name="dlp-policies-and-make-private-actions"></a>Directivas DLP y *realizar acciones privadas*

Si usa una directiva DLP con una acción *privada make* y también planea usar el analizador para etiquetar automáticamente los archivos, se recomienda definir también la configuración avanzada [**UseCopyAndPreserveNTFSOwner**](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#preserve-ntfs-owners-during-labeling-public-preview) del cliente de etiquetado unificado.

Esta configuración garantiza que los propietarios originales conserven el acceso a sus archivos.

Para obtener más información, vea [Crear un trabajo de examen de contenido](#create-a-content-scan-job) y  [Aplicar una etiqueta de confidencialidad al contenido automáticamente](apply-sensitivity-label-automatically.md).

## <a name="change-which-file-types-to-protect"></a>Cambiar los tipos de archivo que se van a proteger

De forma predeterminada, el escáner solo protege los tipos de archivo de Office y los archivos PDF.

Use comandos de PowerShell para cambiar este comportamiento según sea necesario, como configurar el analizador para proteger todos los tipos de archivo, tal como lo hace el cliente, o para proteger tipos de archivo adicionales específicos.

Para una directiva de etiquetas que se aplique a las etiquetas de descarga de la cuenta de usuario para el analizador, especifique una configuración avanzada de PowerShell denominada **PFileSupportedExtensions**.

Para un analizador que tiene acceso a Internet, esta cuenta de usuario es la cuenta que se especifica para el parámetro *DelegatedUser* con el comando Set-AIPAuthentication.

**Ejemplo 1**: Comando de PowerShell para que el analizador proteja todos los tipos de archivo, donde la directiva de etiquetas se denomina "Scanner":

```PowerShell
Set-LabelPolicy -Identity Scanner -AdvancedSettings @{PFileSupportedExtensions="*"}
```

**Ejemplo 2**: Comando de PowerShell para que el analizador proteja .xml archivos y archivos .tiff, además de archivos Office y PDF, donde la directiva de etiquetas se denomina "Scanner":

```PowerShell
Set-LabelPolicy -Identity Scanner -AdvancedSettings @{PFileSupportedExtensions=ConvertTo-Json(".xml", ".tiff")}
```

Para obtener más información, vea [Cambiar los tipos de archivo que se van a proteger](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#change-which-file-types-to-protect).

## <a name="upgrade-your-scanner"></a>Actualización del escáner

Si ha instalado previamente el escáner y quiere actualizarlo, siga las instrucciones que se describen en [Actualización del analizador de protección de la información](/previous-versions/azure/information-protection/rms-client/client-admin-guide#upgrading-the-azure-information-protection-scanner).

A continuación, [configure](deploy-scanner-configure-install.md) y [use el escáner](deploy-scanner-manage.md) como de costumbre, omitiendo los pasos para instalar el escáner.

## <a name="edit-data-repository-settings-in-bulk"></a>Edición de la configuración del repositorio de datos de forma masiva

Use los botones **Exportar** e **Importar** para realizar cambios en el analizador en varios repositorios.

De este modo, no es necesario realizar los mismos cambios varias veces, manualmente, en Azure Portal o portal de cumplimiento Microsoft Purview.

Por ejemplo, si tiene un nuevo tipo de archivo en varios repositorios de datos de SharePoint, es posible que desee actualizar la configuración de esos repositorios de forma masiva.

**Para realizar cambios de forma masiva en los repositorios de la portal de cumplimiento Microsoft Purview:**

1. En el portal de cumplimiento Microsoft Purview, seleccione un trabajo de examen de contenido específico y vaya a la pestaña **Repositorios** del panel. Seleccione la opción **Exportar** .

2. Edite manualmente el archivo exportado para realizar el cambio.

3. Use la opción **Importar** de la misma página para importar las actualizaciones en los repositorios.

## <a name="use-the-scanner-with-alternative-configurations"></a>Uso del escáner con configuraciones alternativas

Por lo general, el escáner busca las condiciones especificadas para las etiquetas con el fin de clasificar y proteger el contenido según sea necesario.

En los escenarios siguientes, el analizador también puede examinar el contenido y administrar etiquetas, sin ninguna condición configurada:

- [Aplicar una etiqueta predeterminada a todos los archivos de un repositorio de datos](#apply-a-default-label-to-all-files-in-a-data-repository)
- [Eliminación de etiquetas existentes de todos los archivos de un repositorio de datos](#remove-existing-labels-from-all-files-in-a-data-repository)
- [Identificar todas las condiciones personalizadas y los tipos de información confidencial conocidos](#identify-all-custom-conditions-and-known-sensitive-information-types)

### <a name="apply-a-default-label-to-all-files-in-a-data-repository"></a>Aplicar una etiqueta predeterminada a todos los archivos de un repositorio de datos

En esta configuración, todos los archivos sin etiquetar en el repositorio se etiquetan con la etiqueta predeterminada especificada para el repositorio o el trabajo de examen de contenido. Los archivos se etiquetan sin inspección.

Configure las siguientes opciones:

|Configuración  |Descripción  |
|---------|---------|
|**Etiquetar archivos basados en contenido**    |Establecer en **Desactivado**         |
|**Etiqueta predeterminada**     | Establezca **en Personalizado** y, a continuación, seleccione la etiqueta que se va a usar.       |
|**Aplicar la etiqueta predeterminada**     | Seleccione esta opción para aplicar la etiqueta predeterminada a todos los archivos, incluso si ya están etiquetados activando **Volver a etiquetar archivos** y **Aplicar etiqueta predeterminada** .        |

### <a name="remove-existing-labels-from-all-files-in-a-data-repository"></a>Eliminación de etiquetas existentes de todos los archivos de un repositorio de datos

En esta configuración, se quitan todas las etiquetas existentes, incluida la protección, si se aplicó protección con la etiqueta. Se conserva la protección aplicada independientemente de una etiqueta.

Configure las siguientes opciones:

|Configuración  |Descripción  |
|---------|---------|
|**Etiquetar archivos basados en contenido**    |Establecer en **Desactivado**         |
|**Etiqueta predeterminada**     | Establecer en **Ninguno**  |
|**Volver a etiquetar archivos** | Establézcalo **en Activado**, con la **etiqueta Aplicar predeterminada** establecida en **Activado**|

### <a name="identify-all-custom-conditions-and-known-sensitive-information-types"></a>Identificar todas las condiciones personalizadas y los tipos de información confidencial conocidos

Esta configuración le permite encontrar información confidencial que es posible que no se dé cuenta de que tenía, a costa de las tasas de análisis del escáner.

Establezca los **tipos de información que se detectarán en** **Todos**.

Para identificar las condiciones y los tipos de información para el etiquetado, el analizador usa los tipos de información confidencial personalizados especificados y la lista de tipos de información confidencial integrados que están disponibles para seleccionar, tal como se define en el centro de administración de etiquetado.

## <a name="optimize-scanner-performance"></a>Optimización del rendimiento del escáner

> [!NOTE]
> Si quiere mejorar la capacidad de respuesta del equipo del escáner en lugar del rendimiento del escáner, use una configuración de cliente avanzada para [limitar el número de subprocesos que usa el escáner](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#limit-the-number-of-threads-used-by-the-scanner).

Use las siguientes opciones e instrucciones para ayudarle a optimizar el rendimiento del escáner:

|Opción  |Descripción  |
|---------|---------|
|**Tener una conexión de red confiable y de alta velocidad entre el equipo del escáner y el almacén de datos escaneados**     |  Por ejemplo, coloque el equipo del escáner en la misma LAN, o preferiblemente, en el mismo segmento de red que el almacén de datos digitalizado. <br /><br />La calidad de la conexión de red afecta al rendimiento del escáner porque, para inspeccionar los archivos, el escáner transfiere el contenido de los archivos al equipo que ejecuta el servicio de escáner. <br /><br />La reducción o eliminación de los saltos de red necesarios para que los datos viajen también reduce la carga en la red.      |
|**Asegúrese de que el equipo del escáner tiene recursos de procesador disponibles**     | Inspeccionar el contenido del archivo y cifrar y descifrar archivos son acciones intensivas del procesador. <br /><br />Supervise los ciclos de análisis típicos de los almacenes de datos especificados para identificar si la falta de recursos del procesador afecta negativamente al rendimiento del escáner.        |
|**Instalación de varias instancias del analizador** | El analizador admite varias bases de datos de configuración en la misma instancia de SQL Server al especificar un nombre de clúster personalizado para el analizador. <br /><br />**Sugerencia**: Varios escáneres también pueden compartir el mismo clúster, lo que da lugar a tiempos de examen más rápidos. Si tiene previsto instalar el analizador en varias máquinas con la misma instancia de base de datos y desea que los escáneres se ejecuten en paralelo, debe instalar todos los analizadores con el mismo nombre de clúster.|
|**Comprobación del uso alternativo de la configuración** |El analizador se ejecuta más rápidamente cuando se usa la [configuración alternativa](#use-the-scanner-with-alternative-configurations) para aplicar una etiqueta predeterminada a todos los archivos porque el analizador no inspecciona el contenido del archivo. <br/><br />El analizador se ejecuta más lentamente cuando se usa la [configuración alternativa](#use-the-scanner-with-alternative-configurations) para identificar todas las condiciones personalizadas y los tipos de información confidencial conocidos.|

### <a name="additional-factors-that-affect-performance"></a>Factores adicionales que afectan al rendimiento

Entre los factores adicionales que afectan al rendimiento del escáner se incluyen:

|Factor  |Descripción  |
|---------|---------|
|**Tiempos de carga y respuesta**     |Los tiempos de carga y respuesta actuales de los almacenes de datos que contienen los archivos que se van a examinar también afectarán al rendimiento del escáner.         |
|**Modo de escáner** (detección/aplicación)    | El modo de detección suele tener una tasa de examen más alta que el modo de aplicación. <br /><br />La detección requiere una única acción de lectura de archivos, mientras que el modo de aplicación requiere acciones de lectura y escritura.        |
|**Cambios en la directiva**     |El rendimiento del escáner puede verse afectado si ha realizado cambios en el etiquetado automático en la directiva de etiquetas. <br /><br />El primer ciclo de examen, cuando el escáner debe inspeccionar todos los archivos, tardará más tiempo que los ciclos de examen posteriores que, de forma predeterminada, inspeccionarán solo los archivos nuevos y modificados. <br /><br />Si cambia las condiciones o la configuración de etiquetado automático, todos los archivos se examinan de nuevo. Para obtener más información, vea [Volver a examinar archivos](deploy-scanner-manage.md#rescanning-files).|
|**Construcciones regex**    | El rendimiento del escáner se ve afectado por la forma en que se construyen las expresiones regex para condiciones personalizadas. <br /><br /> Para evitar el consumo excesivo de memoria y el riesgo de tiempos de espera (15 minutos por archivo), revise las expresiones regex para obtener una coincidencia eficaz de patrones. <br /><br />Por ejemplo: <br />- Evitar [cuantificadores expansivos](/dotnet/standard/base-types/quantifiers-in-regular-expressions) <br />- Usar grupos que no son de captura, como `(?:expression)` en lugar de `(expression)`    |
|**Nivel de registro**     |  Las opciones de nivel de registro incluyen **Depuración**, **Información**, **Error** y **Desactivado** para los informes del analizador.<br /><br />- **La desactivación** da como resultado el mejor rendimiento <br />- **La depuración** ralentiza considerablemente el analizador y solo se debe usar para solucionar problemas. <br /><br />Para obtener más información, vea el parámetro *ReportLevel* para el cmdlet [Set-AIPScannerConfiguration](/powershell/module/azureinformationprotection/Set-AIPScannerConfiguration) .       |
|**Archivos que se examinan**     |- Con la excepción de los archivos de Excel, los archivos de Office se examinan más rápidamente que los archivos PDF. <br /><br />- Los archivos no protegidos son más rápidos de examinar que los archivos protegidos. <br /><br />- Los archivos grandes obviamente tardan más tiempo en examinarse que los archivos pequeños.         |

## <a name="use-powershell-to-configure-the-scanner"></a>Uso de PowerShell para configurar el analizador

En esta sección se describen los pasos necesarios para configurar e instalar el analizador cuando no tiene acceso a las páginas del analizador en el portal de cumplimiento Microsoft Purview y solo debe usar PowerShell.

> [!IMPORTANT]
> - Algunos pasos requieren PowerShell si puede acceder a las páginas del analizador en el portal de cumplimiento y son idénticos. Para ver estos pasos, consulte las instrucciones anteriores de este artículo, como se indica.
>
> - Si está trabajando con el escáner para Azure China 21Vianet, se requieren pasos adicionales además de las instrucciones que se detallan aquí. Para obtener más información, consulte [Compatibilidad de Azure Information Protection con Office 365 operados por 21Vianet](/microsoft-365/admin/services-in-china/parity-between-azure-information-protection).

Para obtener más información, consulte [Cmdlets de PowerShell admitidos](#supported-powershell-cmdlets).

**Para configurar e instalar el escáner**:

1. Comience con PowerShell cerrado. Si ha instalado previamente el cliente y el escáner de AIP, asegúrese de que el servicio **AIPScanner** está detenido.

2. Abra una sesión de Windows PowerShell con la opción **Ejecutar como administrador**.

3. Ejecute el comando [Install-AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner) para instalar el analizador en la instancia de SQL Server, con el parámetro **Cluster** para definir el nombre del clúster.

    Este paso es idéntico tanto si puede acceder a las páginas del analizador en el portal de cumplimiento como si no. Para obtener más información, consulte las instrucciones anteriores de este artículo: [Instalación del escáner](#install-the-scanner).

4. Obtenga un token de Azure para usarlo con el analizador y, a continuación, vuelva a autenticarlo. 

    Este paso es idéntico tanto si puede acceder a las páginas del analizador en el portal de cumplimiento como si no. Para obtener más información, consulte las instrucciones anteriores de este artículo: [Obtención de un token de Azure AD para el analizador](#get-an-azure-ad-token-for-the-scanner).

5. <a name="powershell"></a>Ejecute el cmdlet [Set-AIPScannerConfiguration](/powershell/module/azureinformationprotection/set-aipscannerconfiguration) para establecer que el analizador funcione en modo sin conexión. Ejecutar:

    ```powershell
    Set-AIPScannerConfiguration -OnlineConfiguration Off
    ```

6. Ejecute el cmdlet [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) para crear un trabajo de examen de contenido predeterminado.

    El único parámetro necesario en el cmdlet **Set-AIPScannerContentScanJob** es **Enforce**. Sin embargo, es posible que quiera definir otras opciones para el trabajo de examen de contenido en este momento. Por ejemplo:

    ```powershell
    Set-AIPScannerContentScanJob -Schedule Manual -DiscoverInformationTypes PolicyOnly -Enforce Off -DefaultLabelType PolicyDefault -RelabelFiles Off -PreserveFileDetails On -IncludeFileTypes '' -ExcludeFileTypes '.msg,.tmp' -DefaultOwner <account running the scanner>
    ```

    La sintaxis anterior configura los siguientes valores mientras continúa la configuración:

    - Mantiene la programación de ejecución del escáner *en el manual*
    - Establece los tipos de información que se detectarán en función de la directiva de etiqueta de confidencialidad.
    - *No* aplica una directiva de etiqueta de confidencialidad
    - Etiqueta automáticamente los archivos en función del contenido, con la etiqueta predeterminada definida para la directiva de etiqueta de confidencialidad.
    - *No permite* volver a etiquetar archivos
    - Conserva los detalles del archivo durante el examen y el etiquetado automático, incluida *la fecha de modificación*, *última modificación* y *modificación por* valores
    - Establece el analizador para excluir los archivos .msg y .tmp al ejecutar
    - Establece el propietario predeterminado en la cuenta que desea usar al ejecutar el analizador.

7. Use el cmdlet [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) para definir los repositorios que desea examinar en el trabajo de examen de contenido. Por ejemplo, ejecute:

    ```powershell
    Add-AIPScannerRepository -OverrideContentScanJob Off -Path 'c:\repoToScan'
    ```

    Use una de las siguientes sintaxis, en función del tipo de repositorio que agregue:

    - Para un recurso compartido de red, use `\\Server\Folder`.
    - Para una biblioteca de SharePoint, use `http://sharepoint.contoso.com/Shared%20Documents/Folder`.
    - Para una ruta de acceso local: `C:\Folder`
    - Para una ruta de acceso UNC: `\\Server\Folder`

    > [!NOTE]
    > No se admiten caracteres comodín y no se admiten ubicaciones webDav.
    >
    > Para modificar el repositorio más adelante, use el cmdlet [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) en su lugar. 

    Si agrega una ruta de acceso de SharePoint para **documentos compartidos**:
    - Especifique **Documentos compartidos** en la ruta de acceso cuando desee examinar todos los documentos y todas las carpetas de Documentos compartidos.
    Por ejemplo: `http://sp2013/SharedDocuments`
    - Especifique **Documentos** en la ruta de acceso cuando desee examinar todos los documentos y todas las carpetas de una subcarpeta en Documentos compartidos.
    Por ejemplo: `http://sp2013/Documents/SalesReports`
    - O bien, especifique solo el **FQDN** de SharePoint, por ejemplo `http://sp2013` , para [detectar y examinar todos los sitios y subsitios de SharePoint en una dirección URL y](deploy-scanner-prereqs.md#discover-and-scan-all-sharepoint-sites-and-subsites-under-a-specific-url) subtítulos específicos en esta dirección URL. Conceda derechos al **auditor del recopilador** de sitios del escáner para habilitarlo.


    Use la sintaxis siguiente al agregar rutas de acceso de SharePoint:

    |Path  |Sintaxis  |
    |---------|---------|
    |**Ruta de acceso raíz**     | `http://<SharePoint server name>` <br /><br />Examina todos los sitios, incluidas las colecciones de sitios permitidas para el usuario del analizador. <br />Requiere [permisos adicionales](/previous-versions/azure/information-protection/quickstart-findsensitiveinfo#permission-users-to-scan-sharepoint-repositories) para detectar automáticamente el contenido raíz.        |
    |**Subsitio o colección de SharePoint específico**     | Uno de los siguientes: <br />- `http://<SharePoint server name>/<subsite name>` <br />- `http://SharePoint server name>/<site collection name>/<site name>` <br /><br />Requiere [permisos adicionales](/previous-versions/azure/information-protection/quickstart-findsensitiveinfo#permission-users-to-scan-sharepoint-repositories) para detectar automáticamente el contenido de la colección de sitios.         |
    |**Biblioteca específica de SharePoint**     | Uno de los siguientes: <br />- `http://<SharePoint server name>/<library name>` <br />- `http://SharePoint server name>/.../<library name>`       |
    |**Carpeta específica de SharePoint**     | `http://<SharePoint server name>/.../<folder name>`        |

Continúe con los pasos siguientes según sea necesario:

- [Configuración para clientes en China](/microsoft-365/admin/services-in-china/parity-between-azure-information-protection)
- [Ejecutar un ciclo de detección y ver informes del escáner](deploy-scanner-manage.md#run-a-discovery-cycle-and-view-reports-for-the-scanner)
- [Uso de PowerShell para configurar el analizador para aplicar la clasificación y la protección](#use-powershell-to-configure-the-scanner-to-apply-classification-and-protection)
- [Uso de PowerShell para configurar una directiva DLP con el analizador](#use-powershell-to-configure-a-dlp-policy-with-the-scanner)

### <a name="use-powershell-to-configure-the-scanner-to-apply-classification-and-protection"></a>Uso de PowerShell para configurar el analizador para aplicar la clasificación y la protección

1. Ejecute el cmdlet [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) para actualizar el trabajo de examen de contenido y establecer la programación en siempre y aplicar la directiva de confidencialidad.

    ```powershell
    Set-AIPScannerContentScanJob -Schedule Always -Enforce On
    ```

    > [!TIP]
    > Es posible que desee cambiar otras opciones de configuración en este panel, como si se cambian los atributos de archivo y si el analizador puede volver a etiquetar los archivos. Para obtener más información sobre la configuración disponible, consulte la documentación completa de [PowerShell](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob).

2. Ejecute el cmdlet [Start-AIPScan](/powershell/module/azureinformationprotection/start-aipscan) para ejecutar el trabajo de examen de contenido:

    ```PowerShell
    Start-AIPScan
    ```

El escáner está programado para ejecutarse continuamente. Cuando el escáner funciona a través de todos los archivos configurados, inicia automáticamente un nuevo ciclo para que se detecten los archivos nuevos y modificados.

### <a name="use-powershell-to-configure-a-dlp-policy-with-the-scanner"></a>Uso de PowerShell para configurar una directiva DLP con el analizador

Vuelva a ejecutar el cmdlet [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) con el parámetro **-EnableDLP** establecido en **Activado** y con un propietario de repositorio específico definido.

Por ejemplo:

```powershell
Set-AIPScannerContentScanJob -EnableDLP On -RepositoryOwner 'domain\user'
```

## <a name="supported-powershell-cmdlets"></a>Cmdlets de PowerShell admitidos

En esta sección se enumeran los cmdlets de PowerShell admitidos para el analizador de protección de la información e instrucciones para configurar e instalar el analizador solo con PowerShell.

Entre los cmdlets admitidos para el analizador se incluyen:

- [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository)

- [Export-AIPLogs](/powershell/module/azureinformationprotection/Export-AIPLogs)

- [Get-AIPScannerConfiguration](/powershell/module/azureinformationprotection/Get-AIPScannerConfiguration)

- [Get-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob)

- [Get-AIPScannerRepository](/powershell/module/azureinformationprotection/get-aipscannerrepository)

- [Get-AIPScannerStatus](/powershell/module/azureinformationprotection/Get-AIPScannerStatus)

- [Get-MIPNetworkDiscoveryConfiguration](/powershell/module/azureinformationprotection/Get-MIPNetworkDiscoveryConfiguration)

- [Get-MIPNetworkDiscoveryJobs](/powershell/module/azureinformationprotection/Get-MIPNetworkDiscoveryJobs)

- [Get-MIPNetworkDiscoveryStatus](/powershell/module/azureinformationprotection/Get-MIPNetworkDiscoveryStatus)

- Get-MIPScannerContentScanJob

- [Get-AIPScannerRepository](/powershell/module/azureinformationprotection/get-aipscannerrepository)

- [Import-AIPScannerConfiguration](/powershell/module/azureinformationprotection/Import-AIPScannerConfiguration)

- [Set-MIPNetworkDiscovery](/powershell/module/azureinformationprotection/set-mipnetworkdiscovery)

- [Import-MIPNetworkDiscoveryConfiguration](/powershell/module/azureinformationprotection/Import-MIPNetworkDiscoveryConfiguration)

- [Install-AIPScanner](/powershell/module/azureinformationprotection/Install-AIPScanner)

- [Install-MIPNetworkDiscovery](/powershell/module/azureinformationprotection/Install-MIPNetworkDiscovery)

- Remove-MIPScannerContentScanJob

- [Remove-AIPScannerRepository](/powershell/module/azureinformationprotection/remove-aipscannerrepository)

- [Set-AIPScanner](/powershell/module/azureinformationprotection/Set-AIPScanner)

- [Set-AIPScannerConfiguration](/powershell/module/azureinformationprotection/Set-AIPScannerConfiguration)

- [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob)

- [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository)

- [Set-MIPNetworkDiscoveryConfiguration](/powershell/module/azureinformationprotection/Set-MIPNetworkDiscoveryConfiguration)

- Set-MIPScannerContentScanJob

- [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository)

- [Start-AIPScan](/powershell/module/azureinformationprotection/Start-AIPScan)

- [Start-AIPScanDiagnostics](/powershell/module/azureinformationprotection/Start-AIPScannerDiagnostics)

- [Start-MIPNetworkDiscovery](/powershell/module/azureinformationprotection/Start-MIPNetworkDiscovery)

- [Stop-AIPScan](/powershell/module/azureinformationprotection/Stop-AIPScan)

- [Remove-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob)

- [Remove-AIPScannerRepository](/powershell/module/azureinformationprotection/remove-aipscannerrepository)

- [Uninstall-AIPScanner](/powershell/module/azureinformationprotection/Uninstall-AIPScanner)

- [Uninstall-MIPNetworkDiscovery](/powershell/module/azureinformationprotection/Uninstall-MIPNetworkDiscovery)

- [Update-AIPScanner](/powershell/module/azureinformationprotection/Update-AIPScanner)


## <a name="next-steps"></a>Pasos siguientes

Una vez que haya instalado y configurado el escáner, empiece a [examinar los archivos](deploy-scanner-manage.md).