---
title: Referencia de configuración configurable para escritorio administrado de Microsoft
description: Establecer categorías para las opciones configurables en el escritorio administrado de Microsoft
keywords: Escritorio administrado de Microsoft, Microsoft 365, Service, Documentation
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/14/2019
ms.openlocfilehash: 1f0301f8660fd7ff60bd347d0d7b88c629d79453
ms.sourcegitcommit: 59bc66eaa2575bad8ecb34d45b1172cda23a729b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2019
ms.locfileid: "30051101"
---
# <a name="configurable-settings-reference---microsoft-managed-desktop"></a><span data-ttu-id="c55d3-104">Referencia de opciones conFigurables-escritorio administrado por Microsoft</span><span class="sxs-lookup"><span data-stu-id="c55d3-104">Configurable settings reference - Microsoft Managed Desktop</span></span>

<span data-ttu-id="c55d3-p101">En este tema se enumeran las categorías de configuración que los clientes pueden configurar con el escritorio administrado de Microsoft. Cada categoría de configuración incluye información sobre los requisitos, procedimientos recomendados y cómo personalizar la categoría de configuración.</span><span class="sxs-lookup"><span data-stu-id="c55d3-p101">This topic lists the settings categories that customers can configure with Microsoft Managed Desktop. Each setting category includes info on requirements, best practices, and how to customize the setting category.</span></span> 

## <a name="desktop-background-picture"></a><span data-ttu-id="c55d3-107">Imagen de fondo de escritorio</span><span class="sxs-lookup"><span data-stu-id="c55d3-107">Desktop background picture</span></span>
<span data-ttu-id="c55d3-p102">Puede personalizar la imagen de fondo de escritorio de los dispositivos de escritorio administrados por Microsoft en su organización. Puede usar esto para aplicar una marca de empresa o marketing</span><span class="sxs-lookup"><span data-stu-id="c55d3-p102">You can customize the desktop background picture for Microsoft Managed Desktop devices in your organization. You might use this to apply a company brand or marketing</span></span> 

### <a name="requirements"></a><span data-ttu-id="c55d3-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c55d3-110">Requirements</span></span>

<span data-ttu-id="c55d3-111">Estos requisitos se deben cumplir para una imagen de fondo de escritorio:</span><span class="sxs-lookup"><span data-stu-id="c55d3-111">These requirements must be met for a desktop background picture:</span></span>
- <span data-ttu-id="c55d3-112">Formato de archivo de imagen:. jpg, JPEG o. png</span><span class="sxs-lookup"><span data-stu-id="c55d3-112">Picture file format - .jpg, jpeg, or .png</span></span>
- <span data-ttu-id="c55d3-113">Ubicación del archivo: host en una ubicación http seguro de confianza (https).</span><span class="sxs-lookup"><span data-stu-id="c55d3-113">File location - Host on a trusted secure http (https) location.</span></span> 
- <span data-ttu-id="c55d3-114">No permitido: no se admiten las ubicaciones http y de recursos compartidos de archivos (UNC).</span><span class="sxs-lookup"><span data-stu-id="c55d3-114">Not allowed - Http and file share (unc) locations are not supported.</span></span> 

### <a name="customize-and-deploy-desktop-background-picture"></a><span data-ttu-id="c55d3-115">Personalizar e implementar la imagen de fondo de escritorio</span><span class="sxs-lookup"><span data-stu-id="c55d3-115">Customize and deploy desktop background picture</span></span>

<span data-ttu-id="c55d3-116">**Para agregar una imagen de fondo de escritorio personalizada**</span><span class="sxs-lookup"><span data-stu-id="c55d3-116">**To add a custom desktop background picture**</span></span>
1. <span data-ttu-id="c55d3-117">Iniciar sesión en el [portal de administración de escritorio administrado de Microsoft](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="c55d3-117">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="c55d3-118">En **configuración**, seleccione **configurable**.</span><span class="sxs-lookup"><span data-stu-id="c55d3-118">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="c55d3-119">En área de trabajo **configurable** , seleccione **imagen de fondo de escritorio**.</span><span class="sxs-lookup"><span data-stu-id="c55d3-119">In **Configurable** workspace, select **Desktop background picture**.</span></span> 
4. <span data-ttu-id="c55d3-120">Escriba la ubicación de la imagen que desea usar.</span><span class="sxs-lookup"><span data-stu-id="c55d3-120">Enter the location of the picture you want to use.</span></span> 
5. <span data-ttu-id="c55d3-121">Seleccione **Stage Deployment** para guardar los cambios e implementarlos en el anillo de prueba.</span><span class="sxs-lookup"><span data-stu-id="c55d3-121">Select **Stage deployment** to save your changes and deploy them to the Test ring.</span></span> 

## <a name="browser-start-pages"></a><span data-ttu-id="c55d3-122">Páginas de inicio del explorador</span><span class="sxs-lookup"><span data-stu-id="c55d3-122">Browser start pages</span></span>
<span data-ttu-id="c55d3-p103">Las páginas de inicio del explorador se abren en pestañas individuales cuando los usuarios inician Microsoft Edge. Si desea que los usuarios puedan abrir fácilmente un conjunto de sitios que usan con frecuencia, agregue una página de inicio de explorador para cada sitio.</span><span class="sxs-lookup"><span data-stu-id="c55d3-p103">Browser start pages open in individual tabs when your users start Microsoft Edge. If you want to make it easy for your users to open a set of sites that they use frequently, add a browser start page for each site.</span></span> 

### <a name="requirements"></a><span data-ttu-id="c55d3-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c55d3-125">Requirements</span></span>

<span data-ttu-id="c55d3-p104">Debe proporcionar el nombre de dominio completo (FQDN) para los sitios de intranet o Internet en las páginas de inicio del explorador. Si se configuran los sitios internos, informe a los usuarios de que solo se permite el acceso a estos sitios cuando está conectado a la red interna en la oficina o cuando está conectado con una conexión VPN.</span><span class="sxs-lookup"><span data-stu-id="c55d3-p104">You must provide the fully qualified domain name (FQDN) for intranet or Internet sites for your browser start pages. If internal sites are configured, let users know that access to these sites is only allowed when connected to the internal network when in the office, or when connected with a VPN connection.</span></span> 

### <a name="customize-and-deploy-browser-start-pages"></a><span data-ttu-id="c55d3-128">Personalización e implementación de páginas de inicio del explorador</span><span class="sxs-lookup"><span data-stu-id="c55d3-128">Customize and deploy browser start pages</span></span>

<span data-ttu-id="c55d3-129">**Para agregar una página de inicio del explorador**</span><span class="sxs-lookup"><span data-stu-id="c55d3-129">**To add a browser start page**</span></span>
1. <span data-ttu-id="c55d3-130">Iniciar sesión en el [portal de administración de escritorio administrado de Microsoft](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="c55d3-130">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="c55d3-131">En **configuración**, seleccione **configurable**.</span><span class="sxs-lookup"><span data-stu-id="c55d3-131">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="c55d3-132">En área de trabajo **configurable** , seleccione **páginas de inicio del explorador**.</span><span class="sxs-lookup"><span data-stu-id="c55d3-132">In **Configurable** workspace, select **Browser start pages**.</span></span> 
4. <span data-ttu-id="c55d3-133">Seleccione **Agregar página de inicio**.</span><span class="sxs-lookup"><span data-stu-id="c55d3-133">Select **Add start page**.</span></span>
5. <span data-ttu-id="c55d3-134">En **Agregar página de inicio del explorador**, escriba la dirección URL del sitio que desea usar y, a continuación, seleccione **Agregar página de inicio**.</span><span class="sxs-lookup"><span data-stu-id="c55d3-134">On **Add browser start page**, enter the URL for the site you want to use, and then select **Add start page**.</span></span> 
6. <span data-ttu-id="c55d3-135">Repita los pasos 1-5 para páginas de inicio adicionales del explorador.</span><span class="sxs-lookup"><span data-stu-id="c55d3-135">Repeat steps 1-5 for additional browser start pages.</span></span> 
7. <span data-ttu-id="c55d3-136">Seleccione **Stage Deployment** para guardar los cambios e implementarlos en el anillo de prueba.</span><span class="sxs-lookup"><span data-stu-id="c55d3-136">Select **Stage deployment** to save your changes and deploy them to the Test ring.</span></span>

## <a name="enterprise-mode-site-list-location"></a><span data-ttu-id="c55d3-137">Ubicación de la lista de sitios del modo de empresa</span><span class="sxs-lookup"><span data-stu-id="c55d3-137">Enterprise mode site list location</span></span>

<span data-ttu-id="c55d3-p105">Si tienes sitios web y aplicaciones específicos en los que conoces problemas de compatibilidad con Microsoft Edge, puedes usar la lista de sitios del modo de empresa para que los sitios web se abran automáticamente con Internet Explorer 11. Además, si sabe que los sitios de la intranet no van a funcionar correctamente con Microsoft Edge, puede configurar todos los sitios de intranet para que se abran automáticamente con Internet Explorer 11. El uso del modo de empresa significa que puede seguir usando Microsoft Edge como explorador predeterminado, a la vez que garantiza que las aplicaciones sigan funcionando en Internet Explorer 11. Para obtener más información sobre las listas de sitios del modo de empresa, vea el modo [de empresa y las listas de sitios del modo](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode)de empresa.</span><span class="sxs-lookup"><span data-stu-id="c55d3-p105">If you have specific websites and apps that you know have compatibility problems with Microsoft Edge, you can use the Enterprise Mode site list so that the websites automatically open using Internet Explorer 11. Also, if you know that your intranet sites aren't going to work correctly with Microsoft Edge, you can set all intranet sites to open using Internet Explorer 11 automatically. Using Enterprise Mode means that you can continue to use Microsoft Edge as your default browser, while also ensuring that your apps continue working on Internet Explorer 11. For more information on enterprise mode site lists,see [Enterprise Mode and Enterprise Mode Site Lists](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode).</span></span> 

<span data-ttu-id="c55d3-142">Puede especificar una ubicación de https://o la ubicación de un recurso compartido interno donde haya hospedado la lista de sitios del modo de empresa.</span><span class="sxs-lookup"><span data-stu-id="c55d3-142">You can specify an https:// location, or the location for an internal share where you’ve hosted your enterprise mode site list.</span></span> 

### <a name="requirements"></a><span data-ttu-id="c55d3-143">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c55d3-143">Requirements</span></span>

<span data-ttu-id="c55d3-144">Estos requisitos deben cumplirse para el archivo de lista de sitios del modo de empresa:</span><span class="sxs-lookup"><span data-stu-id="c55d3-144">These requirements must be met for the enterprise mode site list file:</span></span>
- <span data-ttu-id="c55d3-145">Formato de archivo: archivo XML que cumple [los requisitos de archivo](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)</span><span class="sxs-lookup"><span data-stu-id="c55d3-145">File format - XML file that meets [file requirements](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)</span></span>
- <span data-ttu-id="c55d3-146">Ubicación del archivo: archivo de host en una ubicación https interna.</span><span class="sxs-lookup"><span data-stu-id="c55d3-146">File location - Host file on an internal https location.</span></span> 
- <span data-ttu-id="c55d3-147">No permitido: no se permite el hospedaje en un recurso compartido de archivos interno, como *//ShareName*</span><span class="sxs-lookup"><span data-stu-id="c55d3-147">Not allowed - Hosting on an internal file share, like *//sharename*, is not allowed</span></span>

### <a name="best-practices"></a><span data-ttu-id="c55d3-148">Procedimientos recomendados</span><span class="sxs-lookup"><span data-stu-id="c55d3-148">Best practices</span></span>

<span data-ttu-id="c55d3-149">Se ofrecen estos procedimientos recomendados para ayudar a los clientes a tomar decisiones para modernizar su infraestructura de TI:</span><span class="sxs-lookup"><span data-stu-id="c55d3-149">These best practices are offered to help customers make decisions to modernize their IT infrastructure:</span></span>
- <span data-ttu-id="c55d3-p106">**Elegir un número limitado de sitios** : Microsoft Managed Desktop usa Microsoft Edge como explorador preferido para mejorar la seguridad general de la organización y la facilidad de uso para los usuarios. La mayoría de los sitios de esta lista son para las aplicaciones web heredadas que necesitan una versión anterior de un explorador que no incluirá tantas características de seguridad.</span><span class="sxs-lookup"><span data-stu-id="c55d3-p106">**Choose a limited number of sites** – Microsoft Managed Desktop uses Microsoft Edge as the preferred browser to improve overall security for your organization and usability for your users. Most sites in this list are for legacy web apps that need an older version of a browser that will not include as many security features.</span></span> 
- <span data-ttu-id="c55d3-p107">**Considere** la posibilidad de usar un sitio alternativo o una aplicación web diferente que no requiera un explorador más antiguo. O bien, considere la posibilidad de actualizar el sitio para que pueda usar los exploradores más recientes. Los exploradores más modernos usan la tecnología más reciente y ayudan a mejorar la seguridad.</span><span class="sxs-lookup"><span data-stu-id="c55d3-p107">**Consider an alternate** – Consider a different site, or web app that doesn’t require an older browser. Or, consider updating the site so that it can use newer browsers. Newer browsers use the latest technology and help improve security.</span></span>

### <a name="customize-and-deploy-enterprise-site-mode-list-location"></a><span data-ttu-id="c55d3-155">Personalización e implementación de la ubicación de la lista del modo de sitio de empresa</span><span class="sxs-lookup"><span data-stu-id="c55d3-155">Customize and deploy Enterprise site mode list location</span></span>

<span data-ttu-id="c55d3-156">**Para agregar una ubicación de la lista en el modo de sitio de empresa**</span><span class="sxs-lookup"><span data-stu-id="c55d3-156">**To add an enterprise site mode list location**</span></span>

1.  <span data-ttu-id="c55d3-157">Iniciar sesión en el [portal de administración de escritorio administrado de Microsoft](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="c55d3-157">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2.  <span data-ttu-id="c55d3-158">En **configuración**, seleccione **configurable**.</span><span class="sxs-lookup"><span data-stu-id="c55d3-158">Under **Settings**, select **Configurable**.</span></span>
3.  <span data-ttu-id="c55d3-159">En área de trabajo **configurable** , seleccione ubicación de la **lista de sitios del modo de empresa**.</span><span class="sxs-lookup"><span data-stu-id="c55d3-159">In **Configurable** workspace, select **Enterprise mode site list location**.</span></span> 
4.  <span data-ttu-id="c55d3-160">Escriba la ubicación https de la lista de sitios.</span><span class="sxs-lookup"><span data-stu-id="c55d3-160">Enter the https location for your site list.</span></span> 
5.  <span data-ttu-id="c55d3-161">Seleccione **Stage Deployment** para guardar los cambios e implementarlos en el anillo de prueba.</span><span class="sxs-lookup"><span data-stu-id="c55d3-161">Select **Stage deployment** to save your changes and deploy them to the Test ring.</span></span>

## <a name="trusted-sites"></a><span data-ttu-id="c55d3-162">Sitios de confianza</span><span class="sxs-lookup"><span data-stu-id="c55d3-162">Trusted sites</span></span>

<span data-ttu-id="c55d3-p108">Los sitios de confianza permiten personalizar las zonas de seguridad o dónde se puede usar un sitio para sitios diferentes. Las zonas de seguridad incluyen:</span><span class="sxs-lookup"><span data-stu-id="c55d3-p108">Trusted sites allow you to customize security zones, or where a site can be used, for different sites. Security zones include:</span></span> 
- <span data-ttu-id="c55d3-165">Zona 1: zona de Intranet local</span><span class="sxs-lookup"><span data-stu-id="c55d3-165">Zone 1 – Local Intranet zone</span></span>
- <span data-ttu-id="c55d3-166">Zona 2: zona de sitios de confianza</span><span class="sxs-lookup"><span data-stu-id="c55d3-166">Zone 2 – Trusted sites zone</span></span>
- <span data-ttu-id="c55d3-167">Zona 3: zona de Internet</span><span class="sxs-lookup"><span data-stu-id="c55d3-167">Zone 3 – Internet zone</span></span>
- <span data-ttu-id="c55d3-168">Zona 4: zona de sitios restringidos</span><span class="sxs-lookup"><span data-stu-id="c55d3-168">Zone 4 – Restricted Sites zone</span></span>

### <a name="requirements"></a><span data-ttu-id="c55d3-169">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c55d3-169">Requirements</span></span>

<span data-ttu-id="c55d3-170">Proporcione el nombre de dominio completo (FQDN) para los sitios de intranet o de Internet para cada sitio de confianza.</span><span class="sxs-lookup"><span data-stu-id="c55d3-170">Provide the fully qualified domain name (FQDN) for intranet or Internet sites for each trusted site.</span></span> 

### <a name="customize-and-deploy-trusted-sites"></a><span data-ttu-id="c55d3-171">Personalización e implementación de sitios de confianza</span><span class="sxs-lookup"><span data-stu-id="c55d3-171">Customize and deploy trusted sites</span></span>

<span data-ttu-id="c55d3-172">**Para agregar un sitio de confianza**</span><span class="sxs-lookup"><span data-stu-id="c55d3-172">**To add a trusted site**</span></span>

1. <span data-ttu-id="c55d3-173">Iniciar sesión en el [portal de administración de escritorio administrado de Microsoft](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="c55d3-173">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="c55d3-174">En **configuración**, seleccione **configurable**.</span><span class="sxs-lookup"><span data-stu-id="c55d3-174">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="c55d3-175">En área de trabajo **configurable** , seleccione **sitios de confianza**y, a continuación, seleccione **Agregar sitio de confianza**.</span><span class="sxs-lookup"><span data-stu-id="c55d3-175">In **Configurable** workspace, select **Trusted sites**, and then select **Add trusted site**.</span></span> 
4. <span data-ttu-id="c55d3-176">En **Agregar sitio de confianza**, escriba la dirección URL, elija una zona de seguridad y, a continuación, seleccione **Agregar sitio de confianza**.</span><span class="sxs-lookup"><span data-stu-id="c55d3-176">On **Add trusted site**, enter the URL, choose a security zone, and then select **Add trusted site**.</span></span> 
5. <span data-ttu-id="c55d3-177">Repita los pasos 1-4 para cada sitio de confianza que desee agregar.</span><span class="sxs-lookup"><span data-stu-id="c55d3-177">Repeat steps 1-4 for each trusted site you want to add.</span></span> 
6. <span data-ttu-id="c55d3-178">Seleccione **Stage Deployment** para guardar los cambios e implementarlos en el anillo de prueba.</span><span class="sxs-lookup"><span data-stu-id="c55d3-178">Select **Stage deployment** to save your changes and deploy them to the Test ring.</span></span>

<span data-ttu-id="c55d3-179">**Para quitar un sitio de confianza**</span><span class="sxs-lookup"><span data-stu-id="c55d3-179">**To remove a trusted site**</span></span>

1. <span data-ttu-id="c55d3-180">Iniciar sesión en el [portal de administración de escritorio administrado de Microsoft](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="c55d3-180">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="c55d3-181">En **configuración**, seleccione **configurable**.</span><span class="sxs-lookup"><span data-stu-id="c55d3-181">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="c55d3-182">En área de trabajo **configurable** , seleccione **sitios de confianza**.</span><span class="sxs-lookup"><span data-stu-id="c55d3-182">In **Configurable** workspace, select **Trusted sites**.</span></span> 
4. <span data-ttu-id="c55d3-183">Seleccione el sitio que desea eliminar y, a continuación, seleccione **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="c55d3-183">Select the site that you want to delete, and then select **Delete**.</span></span> 
5. <span data-ttu-id="c55d3-184">Repita los pasos 1-4 para cada sitio de confianza que desee eliminar.</span><span class="sxs-lookup"><span data-stu-id="c55d3-184">Repeat steps 1-4 for each trusted site you want to delete.</span></span> 
6. <span data-ttu-id="c55d3-185">Seleccione **Stage Deployment** para guardar los cambios e implementarlos en el anillo de prueba.</span><span class="sxs-lookup"><span data-stu-id="c55d3-185">Select **Stage deployment** to save your changes and deploy them to the Test ring.</span></span>

## <a name="proxy"></a><span data-ttu-id="c55d3-186">Proxy</span><span class="sxs-lookup"><span data-stu-id="c55d3-186">Proxy</span></span>
<span data-ttu-id="c55d3-p109">Puede administrar la configuración del proxy de red de su organización. Agregue el servidor proxy y el número de puerto y, a continuación, agregue las excepciones de sitio proxy. Microsoft manAged Desktop incluye un conjunto de excepciones de proxy predeterminadas necesarias para que funcione el servicio. La lista de exclusión predeterminada solo puede ser modificada por el servicio de escritorio administrado de Microsoft.  Para obtener más información, consulte [configuración de red para escritorio administrado de Microsoft](../get-ready/network.md).</span><span class="sxs-lookup"><span data-stu-id="c55d3-p109">You can manage network proxy settings for your organization. Add your proxy server and port number, and then add your proxy site exceptions. Microsoft Managed Desktop includes a set of default proxy exceptions that are required for the service to operate. The default exclusion list may only be modified by the Microsoft Managed Desktop service.  For more information, see [Network configuration for Microsoft Managed Desktop](../get-ready/network.md).</span></span> 

<span data-ttu-id="c55d3-192">Las excepciones de sitio de proxy que agregue en el portal de escritorio administrado de Microsoft se agregan a las excepciones predeterminadas de proxy incluidas en el servicio de escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c55d3-192">The proxy site exceptions that you add in the Microsoft Managed Desktop portal are added to the default proxy exceptions included with Microsoft Managed Desktop service.</span></span> 

> [!NOTE]
> <span data-ttu-id="c55d3-p110">La actualización de la lista de excepciones de proxy predeterminada siempre tiene prioridad sobre las implementaciones de clientes. Esto significa que la implementación preconfigurada se pondrá en pausa si hay una implementación para la lista de excepciones de proxy predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c55d3-p110">Updating the default proxy exception list is always prioritized over customer deployments. This means that your staged deployment will be paused if there is a deployment for the default proxy exception list.</span></span>  

### <a name="requirements"></a><span data-ttu-id="c55d3-195">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c55d3-195">Requirements</span></span>

<span data-ttu-id="c55d3-196">Estos requisitos se deben cumplir con las excepciones de servidor proxy y de sitio proxy:</span><span class="sxs-lookup"><span data-stu-id="c55d3-196">These requirements must be met for proxy server and proxy site exceptions:</span></span>
- <span data-ttu-id="c55d3-197">Debe ser una dirección de servidor y un número de Puerto válidos</span><span class="sxs-lookup"><span data-stu-id="c55d3-197">Must be a valid server address and port number</span></span>
- <span data-ttu-id="c55d3-198">Las direcciones URL deben ser un sitio http válido</span><span class="sxs-lookup"><span data-stu-id="c55d3-198">URLs must be a valid http site</span></span> 

### <a name="customize-and-deploy-proxies"></a><span data-ttu-id="c55d3-199">Personalización e implementación de servidores proxy</span><span class="sxs-lookup"><span data-stu-id="c55d3-199">Customize and deploy proxies</span></span>

<span data-ttu-id="c55d3-200">**Para agregar una excepción de sitio de proxy individual**</span><span class="sxs-lookup"><span data-stu-id="c55d3-200">**To add an individual proxy site exception**</span></span>

1. <span data-ttu-id="c55d3-201">Iniciar sesión en el [portal de administración de escritorio administrado de Microsoft](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="c55d3-201">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="c55d3-202">En **configuración**, seleccione **configurable**.</span><span class="sxs-lookup"><span data-stu-id="c55d3-202">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="c55d3-203">En área de trabajo **configurable** , seleccione **proxy**.</span><span class="sxs-lookup"><span data-stu-id="c55d3-203">In **Configurable** workspace, select **Proxy**.</span></span> 
4. <span data-ttu-id="c55d3-204">Escriba la **Dirección** y el **número de Puerto** del servidor proxy y, a continuación, seleccione **Agregar excepción de proxy**.</span><span class="sxs-lookup"><span data-stu-id="c55d3-204">Enter the **Address** and **Port number** for you proxy server, and then select **Add proxy exception**.</span></span> 
5. <span data-ttu-id="c55d3-205">Escriba la dirección URL de un sitio http válido y, a continuación, seleccione **Agregar excepción de proxy**.</span><span class="sxs-lookup"><span data-stu-id="c55d3-205">Enter the URL of a valid http site, and then select **Add proxy exception**.</span></span> 
6. <span data-ttu-id="c55d3-206">Repita los pasos 1-5 para cada sitio de confianza que desee agregar.</span><span class="sxs-lookup"><span data-stu-id="c55d3-206">Repeat steps 1-5 for each trusted site you want to add.</span></span> 
7. <span data-ttu-id="c55d3-207">Seleccione **Stage Deployment** para guardar los cambios e implementarlos en el anillo de prueba.</span><span class="sxs-lookup"><span data-stu-id="c55d3-207">Select **Stage deployment** to save your changes and deploy them to the Test ring.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c55d3-208">Otros recursos</span><span class="sxs-lookup"><span data-stu-id="c55d3-208">Additional resources</span></span>
- [<span data-ttu-id="c55d3-209">Información general de configuración configurable</span><span class="sxs-lookup"><span data-stu-id="c55d3-209">Configurable settings overview</span></span>](config-setting-overview.md) 
- [<span data-ttu-id="c55d3-210">Implementar opciones configurables</span><span class="sxs-lookup"><span data-stu-id="c55d3-210">Deploy configurable settings</span></span>](config-setting-deploy.md)