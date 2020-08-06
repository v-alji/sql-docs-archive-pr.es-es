---
title: Crear una aplicación web de Master Data Manager (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 241d46d7-8008-47f6-bebd-0dfff1cc856a
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: fd81188b499850397aa8ffd2e40cfcb91c648288
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669714"
---
# <a name="create-a-master-data-manager-web-application-master-data-services"></a><span data-ttu-id="18109-102">Crear una aplicación web de Master Data Manager (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="18109-102">Create a Master Data Manager Web Application (Master Data Services)</span></span>
  <span data-ttu-id="18109-103">La aplicación web de [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] proporciona una interfaz a los usuarios para trabajar con datos maestros y a los administradores para configurar y administrar MDS.</span><span class="sxs-lookup"><span data-stu-id="18109-103">The [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application provides an interface for users to work with master data and for administrators to configure and administer MDS.</span></span>  
  
 <span data-ttu-id="18109-104">Una aplicación web debe estar siempre en un sitio web.</span><span class="sxs-lookup"><span data-stu-id="18109-104">A web application must always be contained by a website.</span></span> <span data-ttu-id="18109-105">Para crear una aplicación web, debe:</span><span class="sxs-lookup"><span data-stu-id="18109-105">To create a web application, you must either:</span></span>  
  
-   <span data-ttu-id="18109-106">Usar el sitio web predeterminado y volver a crear después la aplicación web,</span><span class="sxs-lookup"><span data-stu-id="18109-106">Use the Default website and then create the web application,</span></span>  
  
-   <span data-ttu-id="18109-107">Utilizar un sitio web existente y luego crear la aplicación web, o</span><span class="sxs-lookup"><span data-stu-id="18109-107">Use an existing website and then create the web application, or</span></span>  
  
-   <span data-ttu-id="18109-108">Crear un nuevo sitio web que cree automáticamente una aplicación web.</span><span class="sxs-lookup"><span data-stu-id="18109-108">Create a new website, which automatically creates a web application.</span></span>  
  
 <span data-ttu-id="18109-109">Después de crear la aplicación web, debe asociarla a la base de datos de [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="18109-109">After you create the web application, you associate it with the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="18109-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="18109-110">Prerequisites</span></span>  
  
-   <span data-ttu-id="18109-111">Para obtener información sobre los requisitos del equipo que hospeda la aplicación web, vea [Requisitos de la aplicación web &#40;Master Data Services&#41;](web-application-requirements-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="18109-111">For information about the requirements for the computer that hosts the web application, see [Web Application Requirements &#40;Master Data Services&#41;](web-application-requirements-master-data-services.md).</span></span>  
  
## <a name="to-create-a-master-data-manager-web-application-in-a-new-website"></a><span data-ttu-id="18109-112">Para crear una aplicación web de Master Data Manager en un sitio web nuevo</span><span class="sxs-lookup"><span data-stu-id="18109-112">To create a Master Data Manager web application in a new website</span></span>  
 <span data-ttu-id="18109-113">Cuando se crea un sitio web nuevo, la aplicación web raíz es la aplicación web de [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="18109-113">When you create a new website, the root web application is the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application.</span></span> <span data-ttu-id="18109-114">La aplicación web se agrega también a un nuevo grupo de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="18109-114">The web application is also added to a new application pool.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="18109-115">Si sigue este procedimiento, no podrá especificar una ruta de acceso virtual ni un alias de la aplicación web de [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="18109-115">If you follow this procedure, you cannot specify a virtual path and alias of the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application.</span></span> <span data-ttu-id="18109-116">Si desea especificar una ruta de acceso virtual y un alias para [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)], debe crear una aplicación web en un sitio web existente que aún no se haya configurado como una aplicación web de [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="18109-116">If you want to specify a virtual path and alias for [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)], you must create a web application in an existing website that is not already configured as a [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application.</span></span>  
  
 <span data-ttu-id="18109-117">Además, [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)] solo admite crear sitios con enlaces HTTP.</span><span class="sxs-lookup"><span data-stu-id="18109-117">Additionally, [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)] supports creating sites with HTTP bindings only.</span></span> <span data-ttu-id="18109-118">Para agregar un enlace HTTPS, cree un sitio y una aplicación nuevos en [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)] y después vea [Proteger una aplicación web Master Data Services](secure-a-master-data-manager-web-application.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="18109-118">To add an HTTPS binding, create a new site and application in [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)] and then see [Secure a Master Data Manager Web Application](secure-a-master-data-manager-web-application.md) for more information.</span></span>  
  
#### <a name="to-create-a-master-data-manager-web-application-in-a-new-website"></a><span data-ttu-id="18109-119">Para crear una aplicación web de Master Data Manager en un sitio web nuevo</span><span class="sxs-lookup"><span data-stu-id="18109-119">To create a Master Data Manager web application in a new website</span></span>  
  
1.  <span data-ttu-id="18109-120">Abra [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="18109-120">Open [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span></span>  
  
2.  <span data-ttu-id="18109-121">En el panel izquierdo, haga clic en **Configuración web**.</span><span class="sxs-lookup"><span data-stu-id="18109-121">In the left pane, click **Web Configuration**.</span></span>  
  
3.  <span data-ttu-id="18109-122">En la página **Configuración web** , en la lista Sitio web, seleccione **Crear sitio web**.</span><span class="sxs-lookup"><span data-stu-id="18109-122">On the **Web Configuration** page, in the Website list, select **Create new website**.</span></span>  
  
4.  <span data-ttu-id="18109-123">En el cuadro de diálogo **Crear sitio web** , especifique la información para un sitio web nuevo.</span><span class="sxs-lookup"><span data-stu-id="18109-123">On the **Create Website** dialog box, specify information for a new website.</span></span> <span data-ttu-id="18109-124">Para obtener más información sobre las opciones de la interfaz de usuario (IU) en el cuadro de diálogo, vea [Cuadro de diálogo Crear sitio web &#40;Administrador de configuración de Master Data Services&#41;](../create-website-dialog-box-master-data-services-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="18109-124">For more information about the user interface (UI) options in the dialog box, see [Create Website Dialog Box &#40;Master Data Services Configuration Manager&#41;](../create-website-dialog-box-master-data-services-configuration-manager.md).</span></span>  
  
5.  <span data-ttu-id="18109-125">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="18109-125">Click **OK**.</span></span>  
  
## <a name="to-create-a-master-data-manager-web-application-in-an-existing-website"></a><span data-ttu-id="18109-126">Para crear una aplicación web de Master Data Manager en un sitio web existente</span><span class="sxs-lookup"><span data-stu-id="18109-126">To create a Master Data Manager web application in an existing website</span></span>  
 <span data-ttu-id="18109-127">Al crear una aplicación web en un sitio web existente , puede elegir la ruta de acceso virtual y el alias de la aplicación web.</span><span class="sxs-lookup"><span data-stu-id="18109-127">When you create a web application in an existing website, you can choose the virtual path and alias of the web application.</span></span> <span data-ttu-id="18109-128">La aplicación web se agrega a un nuevo grupo de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="18109-128">The web application is added to a new application pool.</span></span>  
  
#### <a name="to-create-a-master-data-manager-web-application-in-an-existing-website"></a><span data-ttu-id="18109-129">Para crear una aplicación web de Master Data Manager en un sitio web existente</span><span class="sxs-lookup"><span data-stu-id="18109-129">To create a Master Data Manager web application in an existing website</span></span>  
  
1.  <span data-ttu-id="18109-130">Abra [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="18109-130">Open [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span></span>  
  
2.  <span data-ttu-id="18109-131">En el panel izquierdo, haga clic en **Configuración web**.</span><span class="sxs-lookup"><span data-stu-id="18109-131">In the left pane, click **Web Configuration**.</span></span>  
  
3.  <span data-ttu-id="18109-132">En la página **Configuración web** , en la lista desplegable **Sitio web** , seleccione el sitio web en el que desea crear la aplicación web de [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="18109-132">On the **Web Configuration** page, from the **Website** list, select the website in which you want to create the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application.</span></span>  
  
4.  <span data-ttu-id="18109-133">Haga clic en **Crear aplicación**.</span><span class="sxs-lookup"><span data-stu-id="18109-133">Click **Create Application**.</span></span>  
  
5.  <span data-ttu-id="18109-134">En el cuadro de diálogo **Crear aplicación web** , especifique la información para una aplicación web nueva.</span><span class="sxs-lookup"><span data-stu-id="18109-134">On the **Create Web Application** dialog box, specify information for a new web application.</span></span> <span data-ttu-id="18109-135">Para obtener más información sobre las opciones de la interfaz de usuario (IU) en el cuadro de diálogo, vea [Cuadro de diálogo Crear aplicación web &#40;Administrador de configuración de Master Data Services&#41;](../create-web-application-dialog-box-master-data-services-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="18109-135">For more information about the user interface (UI) options in the dialog box, see [Create Web Application Dialog Box &#40;Master Data Services Configuration Manager&#41;](../create-web-application-dialog-box-master-data-services-configuration-manager.md).</span></span>  
  
6.  <span data-ttu-id="18109-136">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="18109-136">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="18109-137">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="18109-137">Next Steps</span></span>  
  
-   <span data-ttu-id="18109-138">Asocie la aplicación web a una base de datos de [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="18109-138">Associate the web application with a [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="18109-139">Para obtener más información, vea [Asociar una base de datos y una aplicación web de Master Data Services](associate-a-master-data-services-database-and-web-application.md).</span><span class="sxs-lookup"><span data-stu-id="18109-139">For more information, see [Associate a Master Data Services Database and Web Application](associate-a-master-data-services-database-and-web-application.md).</span></span>  
  
-   <span data-ttu-id="18109-140">También puede configurar el sitio web en el que se hospeda la aplicación web de [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] de forma que use un enlace HTTPS para cifrar el contenido con Capa de sockets seguros (SSL).</span><span class="sxs-lookup"><span data-stu-id="18109-140">Optionally, configure the website that hosts the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application to use an HTTPS binding if you want to encrypt content by using Secure Sockets Layer (SSL).</span></span> <span data-ttu-id="18109-141">Debe utilizar una herramienta de Internet Information Services (IIS), por ejemplo Administrador de IIS, para configurar el certificado de servidor para el servidor web y para configurar un enlace HTTPS y los parámetros de SSL para el sitio.</span><span class="sxs-lookup"><span data-stu-id="18109-141">You must use an Internet Information Services (IIS) tool, such as IIS Manager, to configure the server certificate for the web server, and to configure an HTTPS binding and the SSL settings for the site.</span></span> <span data-ttu-id="18109-142">Para más información, consulte [Secure a Master Data Manager Web Application](secure-a-master-data-manager-web-application.md).</span><span class="sxs-lookup"><span data-stu-id="18109-142">For more information, see [Secure a Master Data Manager Web Application](secure-a-master-data-manager-web-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18109-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="18109-143">See Also</span></span>  
 [<span data-ttu-id="18109-144">Instalar Master Data Services</span><span class="sxs-lookup"><span data-stu-id="18109-144">Install Master Data Services</span></span>](install-master-data-services.md)  
  
  
