---
title: Crear registros DNS cuando Google (eNom) administra su dominio
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 3c490fbf-7833-4e43-be34-ed0dc3cce5e3
description: Obtenga información sobre cómo obtener acceso a eNom y crear DNS a través de la Página Google Domains.
ms.openlocfilehash: 37fa8836b7511d51ef2dcb137f36d62eebc36443
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645616"
---
# <a name="create-dns-records-when-your-domain-is-managed-by-google-enom"></a><span data-ttu-id="2df58-103">Crear registros DNS cuando Google (eNom) administra su dominio</span><span class="sxs-lookup"><span data-stu-id="2df58-103">Create DNS records when your domain is managed by Google (eNom)</span></span>

 <span data-ttu-id="2df58-104">**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.</span><span class="sxs-lookup"><span data-stu-id="2df58-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="2df58-105">Para migrar las cuentas de correo a Microsoft, debe crear un registro DNS en el registrador de dominios.</span><span class="sxs-lookup"><span data-stu-id="2df58-105">To migrate your mail accounts to Microsoft, you need to create a DNS record at your domain registrar.</span></span>
  
<span data-ttu-id="2df58-106">Si compró el dominio a través de Google al registrarse para su cuenta **de Google Apps for work** , Google administra los registros DNS, pero se registra con eNom.</span><span class="sxs-lookup"><span data-stu-id="2df58-106">If you purchased your domain through Google while signing up for your **Google Apps for Work** account, your DNS records are managed by Google but registered with eNom.</span></span> 
  
<span data-ttu-id="2df58-107">Puede tener acceso a eNom y crear DNS a través de la Página Google **Domains** .</span><span class="sxs-lookup"><span data-stu-id="2df58-107">You can access eNom, and create DNS, through the Google **Domains** page.</span></span> <span data-ttu-id="2df58-108">Solo tiene que seguir los pasos de este artículo.</span><span class="sxs-lookup"><span data-stu-id="2df58-108">Just follow the steps in this article.</span></span> 
  
## <a name="create-the-dns-record"></a><span data-ttu-id="2df58-109">Crear el registro DNS</span><span class="sxs-lookup"><span data-stu-id="2df58-109">Create the DNS record</span></span>

1. <span data-ttu-id="2df58-110">En la [consola de administración de Google](https://www.google.com/work/apps/business), seleccione **iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="2df58-110">At the [Google Admin console](https://www.google.com/work/apps/business), select **Sign In**.</span></span>
    
    ![Google-Apps-Configure-1-1-0](../../media/37a6e9f6-319e-4c02-aa18-d8d06df7953d.png)
  
2. <span data-ttu-id="2df58-112">Escriba su nombre de dominio y, después, seleccione **ir**.</span><span class="sxs-lookup"><span data-stu-id="2df58-112">Enter your domain name, and then select **Go**.</span></span>
    
    ![Google-Apps-Configure-1-1-1](../../media/2caf8dcb-4d40-4cfa-bc40-d634e454e699.png)
  
3. <span data-ttu-id="2df58-114">En la parte inferior de la página, seleccione **más controles**.</span><span class="sxs-lookup"><span data-stu-id="2df58-114">At the bottom of the page, select **More controls**.</span></span>
    
    ![Google-Apps-Configure-1-2-0](../../media/1518ff78-035b-423e-85a3-c16d7faa0968.png)
  
4. <span data-ttu-id="2df58-116">Seleccione **Dominios**.</span><span class="sxs-lookup"><span data-stu-id="2df58-116">Select **Domains**.</span></span>
    
    ![Google-Apps-Configure-1-2-1](../../media/c2972c06-9bca-43bd-9876-2cee63043bf1.png)
  
5. <span data-ttu-id="2df58-118">En la página **dominios** , seleccione **Agregar o quitar dominios**.</span><span class="sxs-lookup"><span data-stu-id="2df58-118">On the **Domains** page, select **Add/remove domains**.</span></span>
    
    ![Google-Apps-Configure-1-2-2](../../media/07b8068f-9a05-40aa-a041-fc495c729a18.png)
  
6. <span data-ttu-id="2df58-120">En la página **dominios** , seleccione **Configuración avanzada de DNS**.</span><span class="sxs-lookup"><span data-stu-id="2df58-120">On the **Domains** page, select **Advanced DNS settings**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2df58-121">Si no ha comprado un nombre de dominio a través de Google al registrar su cuenta de **Google Apps for Work**, no tendrá **configuración avanzada de DNS** en su página **Dominios**.</span><span class="sxs-lookup"><span data-stu-id="2df58-121">If you didn't purchase a domain name through Google while signing up for your **Google Apps for Work** account, you won't have **Advanced DNS settings** on your **Domains** page.</span></span> <span data-ttu-id="2df58-122">En su lugar, debe ir directamente al sitio web de su host de su dominio para acceder a la configuración de DNS y para realizar este paso y los siguientes.</span><span class="sxs-lookup"><span data-stu-id="2df58-122">Instead, you must go directly to your domain host's web site to access your DNS settings and to perform this and the following steps.</span></span> <span data-ttu-id="2df58-123">Consulte [tener acceso a la configuración del dominio de G Suite](https://support.google.com/a/answer/54693?hl=en) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2df58-123">See [Access your G Suite domain settings](https://support.google.com/a/answer/54693?hl=en) for more information.</span></span> 
  
    ![Google-Apps-eNom-configure-1-3](../../media/b244b29c-e479-40be-b380-4ffa0f74b421.png)
  
7. <span data-ttu-id="2df58-125">En la página **Configuración avanzada de DNS** , seleccione **iniciar sesión en la consola DNS**.</span><span class="sxs-lookup"><span data-stu-id="2df58-125">On the **Advanced DNS settings** page, select **Sign in to DNS Console**.</span></span> <span data-ttu-id="2df58-126">Anote la información del **nombre de inicio de sesión** y la **contraseña**.</span><span class="sxs-lookup"><span data-stu-id="2df58-126">Note the **Sign-in name** and **Password** information.</span></span> <span data-ttu-id="2df58-127">La necesitará en el siguiente paso.</span><span class="sxs-lookup"><span data-stu-id="2df58-127">You'll need it in the next step.</span></span> 
    
    ![Google-Apps-eNom-configure-1-4](../../media/056a2767-462f-4847-acee-d01e3f773add.png)
  
8. <span data-ttu-id="2df58-129">Inicie sesión en el **Administrador de dominios** de Google con el **nombre de inicio de sesión** y la **contraseña** de la página **Configuración avanzada de DNS**.</span><span class="sxs-lookup"><span data-stu-id="2df58-129">Log in to the Google **Domain Manager** using the **Sign-in name** and **Password** from the **Advanced DNS settings** page.</span></span> 
    
    ![Google-Apps-eNom-configure-1-5](../../media/08b74652-8cdb-4560-a5fd-0899f86deee8.png)
  
9. <span data-ttu-id="2df58-131">En la **página _domain_name_*_, en la sección _ registros de*host** , seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="2df58-131">On the **_domain_name_*_ page, in the _\* Host Records*\* section, select **Edit**.</span></span>
    
    ![Google-Apps-eNom-configure-1-6](../../media/d54fec18-b9d1-4796-8397-0393c964eade.png)
  
10. <span data-ttu-id="2df58-133">En la sección **registros de host** , seleccione **Agregar nuevo**.</span><span class="sxs-lookup"><span data-stu-id="2df58-133">In the **Host Records** section, select **Add New**.</span></span>
    
    ![Google-Apps-eNom-configure-1-7](../../media/3562806a-4328-4e60-a717-0566841204cf.png)
  
11. <span data-ttu-id="2df58-135">En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="2df58-135">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="2df58-136">**HOST**</span><span class="sxs-lookup"><span data-stu-id="2df58-136">**HOST**</span></span>|<span data-ttu-id="2df58-137">**TXT VALUE**</span><span class="sxs-lookup"><span data-stu-id="2df58-137">**TXT VALUE**</span></span>|<span data-ttu-id="2df58-138">**TIPO DE REGISTRO**</span><span class="sxs-lookup"><span data-stu-id="2df58-138">**RECORD TYPE**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> ||<span data-ttu-id="2df58-139">TXT</span><span class="sxs-lookup"><span data-stu-id="2df58-139">TXT</span></span>  <br/> |

    > [!NOTE]
    > <span data-ttu-id="2df58-140">This is an example.</span><span class="sxs-lookup"><span data-stu-id="2df58-140">This is an example.</span></span> <span data-ttu-id="2df58-141">Utilice aquí su valor de **Dirección de destino**, desde la tabla.</span><span class="sxs-lookup"><span data-stu-id="2df58-141">Use your specific **Destination or Points to Address** value here, from the table.</span></span> 
  
    [<span data-ttu-id="2df58-142">¿Cómo puedo encontrar esto?</span><span class="sxs-lookup"><span data-stu-id="2df58-142">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)
  
12. <span data-ttu-id="2df58-143">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2df58-143">Select **Save**.</span></span>
    
    ![Google-Apps-eNom-configure-1-9](../../media/7a6f7b45-8f79-487b-afe4-05949c2c04e8.png)
  
13. <span data-ttu-id="2df58-145">Seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="2df58-145">Select **Save Changes**.</span></span>
    
    ![Google-Apps-Configure-1-11](../../media/7f321236-33fb-4a7d-9d03-26605e9e558c.png)
  
> [!NOTE]
>  <span data-ttu-id="2df58-p105">Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="2df58-p105">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
