---
title: Configurar Micro Focus ArcSight para extraer Microsoft Defender para detecciones de puntos de conexión
description: Configurar Micro Focus ArcSight para recibir y extraer detecciones de Centro de seguridad de Microsoft Defender
keywords: configurar Micro Focus ArcSight, herramientas de administración de eventos y información de seguridad, arcsight
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a52f810647c387c5a5726b9d31998c34add4092e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166190"
---
# <a name="configure-micro-focus-arcsight-to-pull-defender-for-endpoint-detections"></a><span data-ttu-id="3b292-104">Configurar Micro Focus ArcSight para extraer Defender para detecciones de puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="3b292-104">Configure Micro Focus ArcSight to pull Defender for Endpoint detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3b292-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="3b292-105">**Applies to:**</span></span>
- [<span data-ttu-id="3b292-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="3b292-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3b292-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3b292-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="3b292-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="3b292-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="3b292-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="3b292-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configurearcsight-abovefoldlink) 

<span data-ttu-id="3b292-110">Tendrás que instalar y configurar algunos archivos y herramientas para usar Micro Focus ArcSight para que pueda extraer Defender para detecciones de puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="3b292-110">You'll need to install and configure some files and tools to use Micro Focus ArcSight so that it can pull Defender for Endpoint detections.</span></span>

>[!Note]
>- <span data-ttu-id="3b292-111">[Defender for Endpoint Alert](alerts.md) se compone de una o más detecciones</span><span class="sxs-lookup"><span data-stu-id="3b292-111">[Defender for Endpoint Alert](alerts.md) is composed from one or more detections</span></span>
>- <span data-ttu-id="3b292-112">[Defender para la detección de](api-portal-mapping.md) puntos de conexión se compone del evento sospechoso que se produjo en el dispositivo y sus detalles de alerta relacionados.</span><span class="sxs-lookup"><span data-stu-id="3b292-112">[Defender for Endpoint Detection](api-portal-mapping.md) is composed from the suspicious event occurred on the Device and its related Alert details.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="3b292-113">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="3b292-113">Before you begin</span></span>

<span data-ttu-id="3b292-114">La configuración de la herramienta Micro Focus ArcSight Connector requiere varios archivos de configuración para que extraiga y analice las detecciones de la aplicación Azure Active Directory (AAD).</span><span class="sxs-lookup"><span data-stu-id="3b292-114">Configuring the Micro Focus ArcSight Connector tool requires several configuration files for it to pull and parse detections from your Azure Active Directory (AAD) application.</span></span>

<span data-ttu-id="3b292-115">Esta sección le guía para obtener la información necesaria para establecer y usar correctamente los archivos de configuración necesarios.</span><span class="sxs-lookup"><span data-stu-id="3b292-115">This section guides you in getting the necessary information to set and use the required configuration files correctly.</span></span>

- <span data-ttu-id="3b292-116">Asegúrese de que ha habilitado la característica de integración siem desde **el Configuración** menú.</span><span class="sxs-lookup"><span data-stu-id="3b292-116">Make sure you have enabled the SIEM integration feature from the **Settings** menu.</span></span> <span data-ttu-id="3b292-117">Para obtener más información, vea [Enable SIEM integration in Defender for Endpoint](enable-siem-integration.md).</span><span class="sxs-lookup"><span data-stu-id="3b292-117">For more information, see [Enable SIEM integration in Defender for Endpoint](enable-siem-integration.md).</span></span>

- <span data-ttu-id="3b292-118">Tenga listo el archivo guardado para habilitar la característica de integración siem.</span><span class="sxs-lookup"><span data-stu-id="3b292-118">Have the file you saved from enabling the SIEM integration feature ready.</span></span> <span data-ttu-id="3b292-119">Deberá obtener los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="3b292-119">You'll need to get the following values:</span></span>
  - <span data-ttu-id="3b292-120">URL de actualización de tokens de OAuth 2.0</span><span class="sxs-lookup"><span data-stu-id="3b292-120">OAuth 2.0 Token refresh URL</span></span>
  - <span data-ttu-id="3b292-121">Id. de cliente de OAuth 2.0</span><span class="sxs-lookup"><span data-stu-id="3b292-121">OAuth 2.0 Client ID</span></span>
  - <span data-ttu-id="3b292-122">Secreto de cliente de OAuth 2.0</span><span class="sxs-lookup"><span data-stu-id="3b292-122">OAuth 2.0 Client secret</span></span>

- <span data-ttu-id="3b292-123">Tenga los siguientes archivos de configuración listos:</span><span class="sxs-lookup"><span data-stu-id="3b292-123">Have the following configuration files ready:</span></span>
  - <span data-ttu-id="3b292-124">WDATP-connector.properties</span><span class="sxs-lookup"><span data-stu-id="3b292-124">WDATP-connector.properties</span></span>
  - <span data-ttu-id="3b292-125">WDATP-connector.jsonparser.properties</span><span class="sxs-lookup"><span data-stu-id="3b292-125">WDATP-connector.jsonparser.properties</span></span>

    <span data-ttu-id="3b292-126">Habría guardado un archivo .zip que contiene estos dos archivos al elegir Micro Focus ArcSight como el tipo SIEM que usa en su organización.</span><span class="sxs-lookup"><span data-stu-id="3b292-126">You would have saved a .zip file which contains these two files when you chose Micro Focus ArcSight as the SIEM type you use in your organization.</span></span>

- <span data-ttu-id="3b292-127">Asegúrese de generar los siguientes tokens y tenerlos listos:</span><span class="sxs-lookup"><span data-stu-id="3b292-127">Make sure you generate the following tokens and have them ready:</span></span>
  - <span data-ttu-id="3b292-128">Token de acceso</span><span class="sxs-lookup"><span data-stu-id="3b292-128">Access token</span></span>
  - <span data-ttu-id="3b292-129">Token de actualización</span><span class="sxs-lookup"><span data-stu-id="3b292-129">Refresh token</span></span>

  <span data-ttu-id="3b292-130">Puede generar estos tokens desde la sección de configuración **de integración siem** del portal.</span><span class="sxs-lookup"><span data-stu-id="3b292-130">You can generate these tokens from the **SIEM integration** setup section of the portal.</span></span>

## <a name="install-and-configure-micro-focus-arcsight-flexconnector"></a><span data-ttu-id="3b292-131">Instalar y configurar Micro Focus ArcSight FlexConnector</span><span class="sxs-lookup"><span data-stu-id="3b292-131">Install and configure Micro Focus ArcSight FlexConnector</span></span>

<span data-ttu-id="3b292-132">En los pasos siguientes se supone que ha completado todos los pasos necesarios en [Antes de comenzar](#before-you-begin).</span><span class="sxs-lookup"><span data-stu-id="3b292-132">The following steps assume that you have completed all the required steps in [Before you begin](#before-you-begin).</span></span>

1. <span data-ttu-id="3b292-133">Instale el último instalador de FlexConnector Windows de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="3b292-133">Install the latest 32-bit Windows FlexConnector installer.</span></span> <span data-ttu-id="3b292-134">Puedes encontrarlo en el Centro de software de HPE.</span><span class="sxs-lookup"><span data-stu-id="3b292-134">You can find this in the HPE Software center.</span></span> <span data-ttu-id="3b292-135">La herramienta suele instalarse en la siguiente ubicación predeterminada: `C:\Program Files\ArcSightFlexConnectors\current\bin` .</span><span class="sxs-lookup"><span data-stu-id="3b292-135">The tool is typically installed in the following default location: `C:\Program Files\ArcSightFlexConnectors\current\bin`.</span></span></br></br><span data-ttu-id="3b292-136">Puede elegir dónde guardar la herramienta, por ejemplo C: folder_location \\ \current\bin donde *folder_location* representa la ubicación de instalación.</span><span class="sxs-lookup"><span data-stu-id="3b292-136">You can choose where to save the tool, for example C:\\*folder_location*\current\bin where *folder_location* represents the installation location.</span></span>

2. <span data-ttu-id="3b292-137">Siga el asistente de instalación a través de las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="3b292-137">Follow the installation wizard through the following tasks:</span></span>
   - <span data-ttu-id="3b292-138">Introducción</span><span class="sxs-lookup"><span data-stu-id="3b292-138">Introduction</span></span>
   - <span data-ttu-id="3b292-139">Elegir instalar carpeta</span><span class="sxs-lookup"><span data-stu-id="3b292-139">Choose Install Folder</span></span>
   - <span data-ttu-id="3b292-140">Elegir instalar conjunto</span><span class="sxs-lookup"><span data-stu-id="3b292-140">Choose Install Set</span></span>
   - <span data-ttu-id="3b292-141">Elegir carpeta de acceso directo</span><span class="sxs-lookup"><span data-stu-id="3b292-141">Choose Shortcut Folder</span></span>
   - <span data-ttu-id="3b292-142">Resumen previo a la instalación</span><span class="sxs-lookup"><span data-stu-id="3b292-142">Pre-Installation Summary</span></span>
   - <span data-ttu-id="3b292-143">Instalación...</span><span class="sxs-lookup"><span data-stu-id="3b292-143">Installing...</span></span>

   <span data-ttu-id="3b292-144">Puede mantener los valores predeterminados para cada una de estas tareas o modificar la selección para que se adapte a sus requisitos.</span><span class="sxs-lookup"><span data-stu-id="3b292-144">You can keep the default values for each of these tasks or modify the selection to suit your requirements.</span></span>

3. <span data-ttu-id="3b292-145">Abra el Explorador de archivos y busque los dos archivos de configuración que guardó al habilitar la característica de integración siem.</span><span class="sxs-lookup"><span data-stu-id="3b292-145">Open File Explorer and locate the two configuration files you saved when you enabled the SIEM integration feature.</span></span> <span data-ttu-id="3b292-146">Ponga los dos archivos en la ubicación de instalación de FlexConnector, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3b292-146">Put the two files in the FlexConnector installation location, for example:</span></span>

   - <span data-ttu-id="3b292-147">WDATP-connector.jsonparser.properties: C: \\ *folder_location*\current\user\agent\flexagent</span><span class="sxs-lookup"><span data-stu-id="3b292-147">WDATP-connector.jsonparser.properties: C:\\*folder_location*\current\user\agent\flexagent</span></span>\

   - <span data-ttu-id="3b292-148">WDATP-connector.properties: C: \\ *folder_location*\current\user\agent\flexagent</span><span class="sxs-lookup"><span data-stu-id="3b292-148">WDATP-connector.properties: C:\\*folder_location*\current\user\agent\flexagent</span></span>\

   > [!NOTE]
   > 
   > <span data-ttu-id="3b292-149">Debe colocar los archivos de configuración en esta ubicación, donde *folder_location* representa la ubicación donde instaló la herramienta.</span><span class="sxs-lookup"><span data-stu-id="3b292-149">You must put the configuration files in this location, where *folder_location* represents the location where you installed the tool.</span></span>

4. <span data-ttu-id="3b292-150">Una vez completada la instalación del conector principal, se abrirá la ventana Configuración del conector.</span><span class="sxs-lookup"><span data-stu-id="3b292-150">After the installation of the core connector completes, the Connector Setup window opens.</span></span> <span data-ttu-id="3b292-151">En la ventana Configuración del conector, seleccione **Agregar un conector**.</span><span class="sxs-lookup"><span data-stu-id="3b292-151">In the Connector Setup window, select **Add a Connector**.</span></span>

5. <span data-ttu-id="3b292-152">Seleccione Tipo: **ArcSight FlexConnector REST** y haga clic **en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3b292-152">Select Type: **ArcSight FlexConnector REST** and click **Next**.</span></span>

6. <span data-ttu-id="3b292-153">Escriba la siguiente información en el formulario de detalles del parámetro.</span><span class="sxs-lookup"><span data-stu-id="3b292-153">Type the following information in the parameter details form.</span></span> <span data-ttu-id="3b292-154">Todos los demás valores del formulario son opcionales y se pueden dejar en blanco.</span><span class="sxs-lookup"><span data-stu-id="3b292-154">All other values in the form are optional and can be left blank.</span></span>

   <table>
    <tbody style="vertical-align:top;">
    <tr>
    <th><span data-ttu-id="3b292-155">Campo</span><span class="sxs-lookup"><span data-stu-id="3b292-155">Field</span></span></th>
    <th><span data-ttu-id="3b292-156">Valor</span><span class="sxs-lookup"><span data-stu-id="3b292-156">Value</span></span></th>
    </tr>
    <tr>
    <td><span data-ttu-id="3b292-157">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="3b292-157">Configuration File</span></span></td>
    <td><span data-ttu-id="3b292-158">Escriba el nombre del archivo de propiedad de cliente.</span><span class="sxs-lookup"><span data-stu-id="3b292-158">Type in the name of the client property file.</span></span> <span data-ttu-id="3b292-159">El nombre debe coincidir con el archivo proporcionado en el .zip que descargó.</span><span class="sxs-lookup"><span data-stu-id="3b292-159">The name must match the file provided in the .zip that you downloaded.</span></span>
<span data-ttu-id="3b292-160">Por ejemplo, si el archivo de configuración del directorio flexagent se denomina &quot; &quot;WDATP-Connector.js&quot; onparser.properties , debe escribir &quot; &quot; WDATP-Connector &quot; como el nombre del archivo de propiedad del cliente.</span><span class="sxs-lookup"><span data-stu-id="3b292-160">For example, if the configuration file in &quot;flexagent&quot; directory is named &quot;WDATP-Connector.jsonparser.properties&quot;, you must type &quot;WDATP-Connector&quot; as the name of the client property file.</span></span></td>
    </tr>
    <td><span data-ttu-id="3b292-161">Dirección URL de eventos</span><span class="sxs-lookup"><span data-stu-id="3b292-161">Events URL</span></span></td>
    <td><span data-ttu-id="3b292-162">En función de la ubicación del centro de datos, seleccione la dirección URL de la UE o estados unidos:</span><span class="sxs-lookup"><span data-stu-id="3b292-162">Depending on the location of your datacenter, select either the EU or the US URL:</span></span> </br></br> <span data-ttu-id="3b292-163"><b>Para la</b>UE : https:// <i></i> wdatp-alertexporter-eu.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span><span class="sxs-lookup"><span data-stu-id="3b292-163"><b>For EU</b>:  https://<i></i>wdatp-alertexporter-eu.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span></span> <br>
   </br><span data-ttu-id="3b292-164"><b>Para ESTADOS UNIDOS:</b> https:// <i></i> wdatp-alertexporter-us.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span><span class="sxs-lookup"><span data-stu-id="3b292-164"><b>For US:</b> https://<i></i>wdatp-alertexporter-us.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span></span> <br> <br> <span data-ttu-id="3b292-165"><b>Para Reino</b>Unido : https:// <i></i> wdatp-alertexporter-uk.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span><span class="sxs-lookup"><span data-stu-id="3b292-165"><b>For UK</b>:  https://<i></i>wdatp-alertexporter-uk.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span></span></td>
    <tr>
    <td><span data-ttu-id="3b292-166">Tipo de autenticación</span><span class="sxs-lookup"><span data-stu-id="3b292-166">Authentication Type</span></span></td>
    <td><span data-ttu-id="3b292-167">OAuth 2</span><span class="sxs-lookup"><span data-stu-id="3b292-167">OAuth 2</span></span></td>
    </tr>
    <td><span data-ttu-id="3b292-168">Archivo de propiedades de cliente de OAuth 2</span><span class="sxs-lookup"><span data-stu-id="3b292-168">OAuth 2 Client Properties file</span></span></td>
    <td><span data-ttu-id="3b292-169">Vaya a la ubicación del <em>archivo wdatp-connector.properties.</em></span><span class="sxs-lookup"><span data-stu-id="3b292-169">Browse to the location of the <em>wdatp-connector.properties</em> file.</span></span> <span data-ttu-id="3b292-170">El nombre debe coincidir con el archivo proporcionado en el .zip que descargó.</span><span class="sxs-lookup"><span data-stu-id="3b292-170">The name must match the file provided in the .zip that you downloaded.</span></span></td>
    <tr>
    <td><span data-ttu-id="3b292-171">Token de actualización</span><span class="sxs-lookup"><span data-stu-id="3b292-171">Refresh Token</span></span></td>
    <td><span data-ttu-id="3b292-172">Puede obtener un token de actualización de dos maneras: generando un token de actualización desde la página de configuración de <b>SIEM</b> o usando la herramienta restutil.</span><span class="sxs-lookup"><span data-stu-id="3b292-172">You can obtain a refresh token in two ways: by generating a refresh token from the <b>SIEM settings</b> page or using the restutil tool.</span></span> <br><br> <span data-ttu-id="3b292-173">Para obtener más información sobre cómo <b></b> generar un token de actualización desde la configuración de preferencias, vea <a href="enable-siem-integration.md" data-raw-source="[Enable SIEM integration in Defender for Endpoint](enable-siem-integration.md)">Enable SIEM integration in Defender for Endpoint</a>.</span><span class="sxs-lookup"><span data-stu-id="3b292-173">For more information on generating a refresh token from the <b>Preferences setup</b> , see <a href="enable-siem-integration.md" data-raw-source="[Enable SIEM integration in Defender for Endpoint](enable-siem-integration.md)">Enable SIEM integration in Defender for Endpoint</a>.</span></span> </br> </br><span data-ttu-id="3b292-174"><b>Obtenga el token de actualización con la herramienta restutil:</b> </span><span class="sxs-lookup"><span data-stu-id="3b292-174"><b>Get your refresh token using the restutil tool:</b> </span></span></br> <span data-ttu-id="3b292-175">a.</span><span class="sxs-lookup"><span data-stu-id="3b292-175">a.</span></span> <span data-ttu-id="3b292-176">Abra un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="3b292-176">Open a command prompt.</span></span> <span data-ttu-id="3b292-177">Vaya a C:\<em>folder_location</em>\current\bin donde <em>folder_location</em> representa la ubicación donde instaló la herramienta.</span><span class="sxs-lookup"><span data-stu-id="3b292-177">Navigate to C:\<em>folder_location</em>\current\bin where <em>folder_location</em> represents the location where you installed the tool.</span></span> </br></br> <span data-ttu-id="3b292-178">b.</span><span class="sxs-lookup"><span data-stu-id="3b292-178">b.</span></span> <span data-ttu-id="3b292-179">Tipo: <code>arcsight restutil token -config</code> desde el directorio bin. Por ejemplo: <b>arcsight restutil boxtoken -proxy proxy.location.hp.com:8080</b> Se abrirá una ventana del explorador web.</span><span class="sxs-lookup"><span data-stu-id="3b292-179">Type: <code>arcsight restutil token -config</code> from the bin directory.For example: <b>arcsight restutil boxtoken -proxy proxy.location.hp.com:8080</b> A Web browser window will open.</span></span> </br> </br><span data-ttu-id="3b292-180">c.</span><span class="sxs-lookup"><span data-stu-id="3b292-180">c.</span></span> <span data-ttu-id="3b292-181">Escriba sus credenciales y, a continuación, haga clic en el campo de contraseña para permitir que la página redirija.</span><span class="sxs-lookup"><span data-stu-id="3b292-181">Type in your credentials then click on the password field to let the page redirect.</span></span> <span data-ttu-id="3b292-182">En el símbolo del sistema de inicio de sesión, escriba sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="3b292-182">In the login prompt, enter your credentials.</span></span> </br> </br><span data-ttu-id="3b292-183">d.</span><span class="sxs-lookup"><span data-stu-id="3b292-183">d.</span></span> <span data-ttu-id="3b292-184">Se muestra un token de actualización en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="3b292-184">A refresh token is shown in the command prompt.</span></span> </br></br> <span data-ttu-id="3b292-185">e.</span><span class="sxs-lookup"><span data-stu-id="3b292-185">e.</span></span> <span data-ttu-id="3b292-186">Cópielo y péguelo en el <b>campo Actualizar token.</b></span><span class="sxs-lookup"><span data-stu-id="3b292-186">Copy and paste it into the <b>Refresh Token</b> field.</span></span>
    </td>
    </tr>
    </tr>
    </table><br/>
    
7. <span data-ttu-id="3b292-187">El conector abre una ventana del explorador.</span><span class="sxs-lookup"><span data-stu-id="3b292-187">A browser window is opened by the connector.</span></span> <span data-ttu-id="3b292-188">Inicie sesión con las credenciales de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3b292-188">Login with your application credentials.</span></span> <span data-ttu-id="3b292-189">Después de iniciar sesión, se le pedirá que le dé permiso a su cliente de OAuth2.</span><span class="sxs-lookup"><span data-stu-id="3b292-189">After you log in, you'll be asked to give permission to your OAuth2 Client.</span></span> <span data-ttu-id="3b292-190">Debe conceder permiso al cliente de OAuth 2 para que la configuración del conector pueda autenticarse.</span><span class="sxs-lookup"><span data-stu-id="3b292-190">You must give permission to your OAuth 2 Client so that the connector configuration can authenticate.</span></span>

   <span data-ttu-id="3b292-191">Si la <code>redirect_uri</code> dirección URL es https, se le redirigirá a una dirección URL en el host local.</span><span class="sxs-lookup"><span data-stu-id="3b292-191">If the <code>redirect_uri</code> is a https URL, you'll be redirected to a URL on the local host.</span></span> <span data-ttu-id="3b292-192">Verá una página que solicita que confíe en el certificado proporcionado por el conector que se ejecuta en el host local.</span><span class="sxs-lookup"><span data-stu-id="3b292-192">You'll see a page that requests for you to trust the certificate supplied by the connector running on the local host.</span></span> <span data-ttu-id="3b292-193">Deberá confiar en este certificado si el redirect_uri es https.</span><span class="sxs-lookup"><span data-stu-id="3b292-193">You'll need to trust this certificate if the redirect_uri is a https.</span></span>
   
   <span data-ttu-id="3b292-194">Sin embargo, si especifica una dirección URL http para el redirect_uri, no es necesario proporcionar consentimiento para confiar en el certificado.</span><span class="sxs-lookup"><span data-stu-id="3b292-194">If however you specify a http URL for the redirect_uri, you do not need to provide consent in trusting the certificate.</span></span>

8. <span data-ttu-id="3b292-195">Continúe con la configuración del conector volviendo a la ventana Configuración del conector de Micro Focus ArcSight.</span><span class="sxs-lookup"><span data-stu-id="3b292-195">Continue with the connector setup by returning to the Micro Focus ArcSight Connector Setup window.</span></span>

9. <span data-ttu-id="3b292-196">Seleccione el **Administrador de ArcSight (cifrado)** como destino y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3b292-196">Select the **ArcSight Manager (encrypted)** as the destination and click **Next**.</span></span>

10. <span data-ttu-id="3b292-197">Escriba el IP/nombre de host de destino en **Nombre de host** del administrador y sus credenciales en el formulario de parámetros.</span><span class="sxs-lookup"><span data-stu-id="3b292-197">Type in the destination IP/hostname in **Manager Hostname** and your credentials in the parameters form.</span></span> <span data-ttu-id="3b292-198">Todos los demás valores del formulario deben conservarse con los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="3b292-198">All other values in the form should be retained with the default values.</span></span> <span data-ttu-id="3b292-199">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3b292-199">Click **Next**.</span></span>

11. <span data-ttu-id="3b292-200">Escriba un nombre para el conector en el formulario de detalles del conector.</span><span class="sxs-lookup"><span data-stu-id="3b292-200">Type in a name for the connector in the connector details form.</span></span> <span data-ttu-id="3b292-201">Todos los demás valores del formulario son opcionales y se pueden dejar en blanco.</span><span class="sxs-lookup"><span data-stu-id="3b292-201">All other values in the form are optional and can be left blank.</span></span> <span data-ttu-id="3b292-202">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3b292-202">Click **Next**.</span></span>

12. <span data-ttu-id="3b292-203">Se muestra la ventana de certificado de importación del Administrador de ESM.</span><span class="sxs-lookup"><span data-stu-id="3b292-203">The ESM Manager import certificate window is shown.</span></span> <span data-ttu-id="3b292-204">Seleccione **Importar el certificado al conector del destino y** haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3b292-204">Select **Import the certificate to connector from destination** and click **Next**.</span></span> <span data-ttu-id="3b292-205">Se **muestra la ventana Agregar resumen** del conector y se importa el certificado.</span><span class="sxs-lookup"><span data-stu-id="3b292-205">The **Add connector Summary** window is displayed and the certificate is imported.</span></span>

13. <span data-ttu-id="3b292-206">Compruebe que los detalles de la **ventana Agregar resumen** del conector son correctos y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3b292-206">Verify that the details in the **Add connector Summary** window is correct, then click **Next**.</span></span>

14. <span data-ttu-id="3b292-207">Seleccione **Instalar como servicio y** haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3b292-207">Select **Install as a service** and click **Next**.</span></span>

15. <span data-ttu-id="3b292-208">Escriba un nombre en el **campo Nombre interno del** servicio.</span><span class="sxs-lookup"><span data-stu-id="3b292-208">Type a name in the **Service Internal Name** field.</span></span> <span data-ttu-id="3b292-209">Todos los demás valores del formulario se pueden conservar con los valores predeterminados o dejar en blanco .</span><span class="sxs-lookup"><span data-stu-id="3b292-209">All other values in the form can be retained with the default values or left blank .</span></span> <span data-ttu-id="3b292-210">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3b292-210">Click **Next**.</span></span>

16. <span data-ttu-id="3b292-211">Escriba los parámetros de servicio y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3b292-211">Type in the service parameters and click **Next**.</span></span> <span data-ttu-id="3b292-212">Se muestra una ventana **con el Resumen del** servicio de instalación.</span><span class="sxs-lookup"><span data-stu-id="3b292-212">A window with the **Install Service Summary** is shown.</span></span> <span data-ttu-id="3b292-213">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3b292-213">Click **Next**.</span></span>

17. <span data-ttu-id="3b292-214">Para finalizar la instalación, seleccione **Salir** y **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3b292-214">Finish the installation by selecting **Exit** and **Next**.</span></span>

## <a name="install-and-configure-the-micro-focus-arcsight-console"></a><span data-ttu-id="3b292-215">Instalar y configurar la consola de Micro Focus ArcSight</span><span class="sxs-lookup"><span data-stu-id="3b292-215">Install and configure the Micro Focus ArcSight console</span></span>

1. <span data-ttu-id="3b292-216">Siga el asistente de instalación a través de las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="3b292-216">Follow the installation wizard through the following tasks:</span></span>
   - <span data-ttu-id="3b292-217">Introducción</span><span class="sxs-lookup"><span data-stu-id="3b292-217">Introduction</span></span>
   - <span data-ttu-id="3b292-218">Contrato de licencia</span><span class="sxs-lookup"><span data-stu-id="3b292-218">License Agreement</span></span>
   - <span data-ttu-id="3b292-219">Aviso especial</span><span class="sxs-lookup"><span data-stu-id="3b292-219">Special Notice</span></span>
   - <span data-ttu-id="3b292-220">Elegir directorio de instalación de ArcSight</span><span class="sxs-lookup"><span data-stu-id="3b292-220">Choose ArcSight installation directory</span></span>
   - <span data-ttu-id="3b292-221">Elegir carpeta de acceso directo</span><span class="sxs-lookup"><span data-stu-id="3b292-221">Choose Shortcut Folder</span></span>
   - <span data-ttu-id="3b292-222">Resumen previo a la instalación</span><span class="sxs-lookup"><span data-stu-id="3b292-222">Pre-Installation Summary</span></span>

2. <span data-ttu-id="3b292-223">Haga clic en **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="3b292-223">Click **Install**.</span></span> <span data-ttu-id="3b292-224">Una vez completada la instalación, se abrirá el Asistente para configuración de consola de ArcSight.</span><span class="sxs-lookup"><span data-stu-id="3b292-224">After the installation completes, the ArcSight Console Configuration Wizard opens.</span></span>

3. <span data-ttu-id="3b292-225">Escriba localhost en **Nombre de host del administrador** y 8443 en Puerto **del** administrador y, a continuación, haga clic **en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3b292-225">Type localhost in **Manager Host Name** and 8443 in **Manager Port** then click **Next**.</span></span>

4. <span data-ttu-id="3b292-226">Seleccione **Usar conexión directa y,** a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3b292-226">Select **Use direct connection**, then click **Next**.</span></span>

5. <span data-ttu-id="3b292-227">Seleccione **Autenticación basada en contraseña** y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3b292-227">Select **Password Based Authentication**, then click **Next**.</span></span>

6. <span data-ttu-id="3b292-228">Seleccione **Esta es una instalación de un solo usuario. (Recomendado)** y, a continuación, haga clic **en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3b292-228">Select **This is a single user installation. (Recommended)**, then click **Next**.</span></span>

7. <span data-ttu-id="3b292-229">Haga **clic en** Listo para salir del instalador.</span><span class="sxs-lookup"><span data-stu-id="3b292-229">Click **Done** to quit the installer.</span></span>

8. <span data-ttu-id="3b292-230">Inicie sesión en la consola de Micro Focus ArcSight.</span><span class="sxs-lookup"><span data-stu-id="3b292-230">Login to the Micro Focus ArcSight console.</span></span>

9. <span data-ttu-id="3b292-231">Vaya a **Active channel set** New  >  **Condition**  >  **Device**  >  **Device Product**.</span><span class="sxs-lookup"><span data-stu-id="3b292-231">Navigate to **Active channel set** > **New Condition** > **Device** > **Device Product**.</span></span>

10. <span data-ttu-id="3b292-232">Set **Device Product = ATP de Microsoft Defender**.</span><span class="sxs-lookup"><span data-stu-id="3b292-232">Set **Device Product = Microsoft Defender ATP**.</span></span> <span data-ttu-id="3b292-233">Cuando haya comprobado que los eventos fluyen a la herramienta, detenga el proceso de nuevo y vaya a Windows Services e inicie el REST de ArcSight FlexConnector.</span><span class="sxs-lookup"><span data-stu-id="3b292-233">When you've verified that events are flowing to the tool, stop the process again and go to Windows Services and start the ArcSight FlexConnector REST.</span></span>

<span data-ttu-id="3b292-234">Ahora puede ejecutar consultas en la consola de Micro Focus ArcSight.</span><span class="sxs-lookup"><span data-stu-id="3b292-234">You can now run queries in the Micro Focus ArcSight console.</span></span>

<span data-ttu-id="3b292-235">Defender para detecciones de puntos de conexión aparecerá como eventos discretos, con "Microsoft" como proveedor y "Windows Defender ATP" como el nombre del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3b292-235">Defender for Endpoint detections will appear as discrete events, with "Microsoft” as the vendor and “Windows Defender ATP” as the device name.</span></span>


## <a name="troubleshooting-micro-focus-arcsight-connection"></a><span data-ttu-id="3b292-236">Solución de problemas de conexión de Micro Focus ArcSight</span><span class="sxs-lookup"><span data-stu-id="3b292-236">Troubleshooting Micro Focus ArcSight connection</span></span>

<span data-ttu-id="3b292-237">**Problema:** No se pudo actualizar el token.</span><span class="sxs-lookup"><span data-stu-id="3b292-237">**Problem:** Failed to refresh the token.</span></span> <span data-ttu-id="3b292-238">Puede encontrar el registro ubicado en C: \\ *folder_location*\current\logs donde *folder_location* representa la ubicación donde instaló la herramienta.</span><span class="sxs-lookup"><span data-stu-id="3b292-238">You can find the log located in C:\\*folder_location*\current\logs where *folder_location* represents the location where you installed the tool.</span></span> <span data-ttu-id="3b292-239">Abra _agent.log_ y busque `ERROR/FATAL/WARN` .</span><span class="sxs-lookup"><span data-stu-id="3b292-239">Open _agent.log_ and look for `ERROR/FATAL/WARN`.</span></span>

<span data-ttu-id="3b292-240">**Síntoma:** Obtiene el siguiente mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="3b292-240">**Symptom:** You get the following error message:</span></span>

`Failed to refresh the token. Set reauthenticate to true: com.arcsight.common.al.e: Failed to refresh access token: status=HTTP/1.1 400 Bad Request FATAL EXCEPTION: Could not refresh the access token`

<span data-ttu-id="3b292-241">**Solución:**</span><span class="sxs-lookup"><span data-stu-id="3b292-241">**Solution:**</span></span>

1. <span data-ttu-id="3b292-242">Detenga el proceso haciendo clic en Ctrl + C en la ventana Conector.</span><span class="sxs-lookup"><span data-stu-id="3b292-242">Stop the process by clicking Ctrl + C on the Connector window.</span></span> <span data-ttu-id="3b292-243">Haga **clic en Y** cuando se le pregunte "¿Finalizar el trabajo por lotes Y/N?".</span><span class="sxs-lookup"><span data-stu-id="3b292-243">Click **Y** when asked "Terminate batch job Y/N?".</span></span>

2. <span data-ttu-id="3b292-244">Navegue hasta la carpeta donde ha almacenado el archivo WDATP-connector.properties y edúzcalo para agregar el siguiente valor: `reauthenticate=true` .</span><span class="sxs-lookup"><span data-stu-id="3b292-244">Navigate to the folder where you stored the WDATP-connector.properties file and edit it to add the following value: `reauthenticate=true`.</span></span>

3. <span data-ttu-id="3b292-245">Reinicie el conector ejecutando el siguiente comando: `arcsight.bat connectors` .</span><span class="sxs-lookup"><span data-stu-id="3b292-245">Restart the connector by running the following command: `arcsight.bat connectors`.</span></span>

   <span data-ttu-id="3b292-246">Aparece una ventana del explorador.</span><span class="sxs-lookup"><span data-stu-id="3b292-246">A browser window appears.</span></span> <span data-ttu-id="3b292-247">Permitir que se ejecute, debe desaparecer y el conector debería estar en ejecución.</span><span class="sxs-lookup"><span data-stu-id="3b292-247">Allow it to run, it should disappear, and the connector should now be running.</span></span>

> [!NOTE]
> <span data-ttu-id="3b292-248">Compruebe que el conector se está ejecutando deteniendo el proceso de nuevo.</span><span class="sxs-lookup"><span data-stu-id="3b292-248">Verify that the connector is running by stopping the process again.</span></span> <span data-ttu-id="3b292-249">A continuación, vuelva a iniciar el conector y no debería aparecer ninguna ventana del explorador.</span><span class="sxs-lookup"><span data-stu-id="3b292-249">Then start the connector again, and no browser window should appear.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3b292-250">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="3b292-250">Related topics</span></span>
- [<span data-ttu-id="3b292-251">Habilitar la integración de SIEM en Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3b292-251">Enable SIEM integration in Defender for Endpoint</span></span>](enable-siem-integration.md)
- [<span data-ttu-id="3b292-252">Extraer detecciones a las herramientas SIEM</span><span class="sxs-lookup"><span data-stu-id="3b292-252">Pull detections to your SIEM tools</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-siem)
- [<span data-ttu-id="3b292-253">Pull Defender for Endpoint detections using REST API</span><span class="sxs-lookup"><span data-stu-id="3b292-253">Pull Defender for Endpoint detections using REST API</span></span>](pull-alerts-using-rest-api.md)
- [<span data-ttu-id="3b292-254">Solucionar problemas de integración de la herramienta SIEM</span><span class="sxs-lookup"><span data-stu-id="3b292-254">Troubleshoot SIEM tool integration issues</span></span>](troubleshoot-siem.md)
