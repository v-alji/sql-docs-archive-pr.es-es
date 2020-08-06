---
title: Crear clases de proxy del servicio web Master Data Manager | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
ms.assetid: 8bdab026-a0c0-41f3-9d36-f3919c23247f
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c4f25d749f829357f6541f14073e654bade27215
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678218"
---
# <a name="create-master-data-manager-web-service-proxy-classes"></a><span data-ttu-id="ae6dc-102">Crear clases de proxy del servicio web Master Data Manager</span><span class="sxs-lookup"><span data-stu-id="ae6dc-102">Create Master Data Manager Web Service Proxy Classes</span></span>
  <span data-ttu-id="ae6dc-103">El servicio web [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] le permite usar las características de [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] mediante programación desde cualquier equipo que pueda acceder a su sitio web de [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ae6dc-103">The [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web service lets you make programmatic use of the features of [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] from any computer that can access your [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web site.</span></span> <span data-ttu-id="ae6dc-104">Antes de empezar a escribir código para acceder al servicio web, debe generar clases de proxy.</span><span class="sxs-lookup"><span data-stu-id="ae6dc-104">Before you can start writing code to access the web service, you must generate proxy classes.</span></span> <span data-ttu-id="ae6dc-105">La clase de proxy principal que utiliza para realizar operaciones del servicio web es la clase <xref:Microsoft.MasterDataServices.ServiceClient>, que implementa la interfaz <xref:Microsoft.MasterDataServices.IService>.</span><span class="sxs-lookup"><span data-stu-id="ae6dc-105">The main proxy class you use to perform web service operations is the <xref:Microsoft.MasterDataServices.ServiceClient> class, which implements the <xref:Microsoft.MasterDataServices.IService> interface.</span></span>  
  
## <a name="enable-web-service-metadata-publishing"></a><span data-ttu-id="ae6dc-106">Habilitar la publicación de metadatos del servicio web</span><span class="sxs-lookup"><span data-stu-id="ae6dc-106">Enable Web Service Metadata Publishing</span></span>  
 <span data-ttu-id="ae6dc-107">Para poder generar clases de proxy, debe habilitar la publicación de metadatos del servicio web.</span><span class="sxs-lookup"><span data-stu-id="ae6dc-107">Before you can generate proxy classes, you must enable web service metadata publishing.</span></span> <span data-ttu-id="ae6dc-108">Para ello, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="ae6dc-108">Follow these steps to do this:</span></span>  
  
1.  <span data-ttu-id="ae6dc-109">Abra el archivo Web.config de [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] en un editor de texto.</span><span class="sxs-lookup"><span data-stu-id="ae6dc-109">Open the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] Web.config file in a text editor.</span></span> <span data-ttu-id="ae6dc-110">Este archivo se encuentra en la carpeta WebApplication de la ruta de instalación de [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ae6dc-110">This file is in the WebApplication folder of the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] installation path.</span></span>  
  
2.  <span data-ttu-id="ae6dc-111">Busque la `mdsWsHttpBehavior` sección en **\<serviceBehaviors>** .</span><span class="sxs-lookup"><span data-stu-id="ae6dc-111">Find the `mdsWsHttpBehavior` section under **\<serviceBehaviors>**.</span></span> <span data-ttu-id="ae6dc-112">En el caso del **\<serviceMetadata>** elemento, establezca `httpGetEnabled` en `true` .</span><span class="sxs-lookup"><span data-stu-id="ae6dc-112">For the **\<serviceMetadata>** element, set `httpGetEnabled` to `true`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ae6dc-113">Si desea habilitar los servicios web sobre la capa de (SSL) sockets seguros, establezca `httpsGetEnabled` a `true` en la sección de `mdsWsHttpBehavior` de archivo web.config.</span><span class="sxs-lookup"><span data-stu-id="ae6dc-113">If you want to enable Web services over Secure Sockets Layer (SSL), set `httpsGetEnabled` to `true` in the `mdsWsHttpBehavior` section of the web.config file.</span></span> <span data-ttu-id="ae6dc-114">También debe cambiar `mdsWsHTTPBinding` para configurarlo para SSL y comentar la sección que no es de SSL.</span><span class="sxs-lookup"><span data-stu-id="ae6dc-114">You also need to change `mdsWsHTTPBinding` so that it is configured for SSL, as well, and comment out the non-SSL section.</span></span>  
  
3.  <span data-ttu-id="ae6dc-115">Guarde los cambios realizados en el archivo.</span><span class="sxs-lookup"><span data-stu-id="ae6dc-115">Save changes to the file.</span></span>  
  
4.  <span data-ttu-id="ae6dc-116">Pruebe la publicación de metadatos yendo a la dirección URL del servicio (por ejemplo, http://yourserver/MDS/service/service.svc).</span><span class="sxs-lookup"><span data-stu-id="ae6dc-116">Test metadata publishing by browsing to the service URL, for example: http://yourserver/MDS/service/service.svc.</span></span> <span data-ttu-id="ae6dc-117">Si la publicación de metadatos está habilitada, se muestra una página que empieza con</span><span class="sxs-lookup"><span data-stu-id="ae6dc-117">If metadata publishing is enabled, a page is displayed that begins with</span></span>   
    <span data-ttu-id="ae6dc-118">"Ha creado un servicio".</span><span class="sxs-lookup"><span data-stu-id="ae6dc-118">"You have created a service."</span></span>  
  
## <a name="creating-proxy-classes-by-using-visual-studio"></a><span data-ttu-id="ae6dc-119">Crear clases de proxy usando Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ae6dc-119">Creating Proxy Classes by Using Visual Studio</span></span>  
 <span data-ttu-id="ae6dc-120">Si tiene instalado Visual Studio 2010, la manera más sencilla de generar clases de proxy consiste en agregar una **referencia de servicio** al proyecto.</span><span class="sxs-lookup"><span data-stu-id="ae6dc-120">If you have Visual Studio 2010 installed, the simplest way to generate proxy classes is to add a **Service Reference** to your project.</span></span> <span data-ttu-id="ae6dc-121">La dirección de la referencia de servicio es la URL de la aplicación de [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)], seguida de /service/service.svc.</span><span class="sxs-lookup"><span data-stu-id="ae6dc-121">The address of the service reference is the URL of the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application, appended with /service/service.svc.</span></span> <span data-ttu-id="ae6dc-122">Por ejemplo: http://yourserver/MDS/service/service.svc.</span><span class="sxs-lookup"><span data-stu-id="ae6dc-122">For example: http://yourserver/MDS/service/service.svc.</span></span> <span data-ttu-id="ae6dc-123">Para más información, vea [Cómo: Agregar, actualizar o quitar una referencia de servicio](https://go.microsoft.com/fwlink/?LinkId=221167).</span><span class="sxs-lookup"><span data-stu-id="ae6dc-123">For more information, see [How to: Add, Update, or Remove a Service Reference](https://go.microsoft.com/fwlink/?LinkId=221167).</span></span>  
  
## <a name="creating-proxy-classes-by-using-svcutilexe"></a><span data-ttu-id="ae6dc-124">Crear clases de proxy usando Svcutil.exe</span><span class="sxs-lookup"><span data-stu-id="ae6dc-124">Creating Proxy Classes by Using Svcutil.exe</span></span>  
 <span data-ttu-id="ae6dc-125">Debe tener [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] instalado o el [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows SDK para poder tener Svcutil.exe en el equipo.</span><span class="sxs-lookup"><span data-stu-id="ae6dc-125">You must have either [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] or the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows SDK installed in order to have Svcutil.exe on your computer.</span></span> <span data-ttu-id="ae6dc-126">Si utiliza [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], debe utilizar el símbolo del sistema de [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] para ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="ae6dc-126">If you use [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], you must use the [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] command prompt to run the command.</span></span> <span data-ttu-id="ae6dc-127">Para más información, vea [Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](https://go.microsoft.com/fwlink/?LinkId=165027) y [Generación de un cliente WCF a partir de los metadatos de servicio](https://go.microsoft.com/fwlink/?LinkId=164821).</span><span class="sxs-lookup"><span data-stu-id="ae6dc-127">For more information, see [ServiceModel Metadata Utility Tool (Svcutil.exe)](https://go.microsoft.com/fwlink/?LinkId=165027) and [Generating a WCF Client from Service Metadata](https://go.microsoft.com/fwlink/?LinkId=164821).</span></span>  
  
 <span data-ttu-id="ae6dc-128">Para crear un conjunto de clases de proxy en C# usando Svcutil.exe, utilice un comando como el siguiente:</span><span class="sxs-lookup"><span data-stu-id="ae6dc-128">To create a set of C# proxy classes by using Svcutil.exe, use a command such as the following:</span></span>  
  
```  
svcutil.exe http://<server_name:port>/<virtual_path>/Service/Service.svc   
/out:<proxy_name>.cs /messageContract /tcv:Version35   
/noconfig /ct:System.Collections.ObjectModel.Collection`1   
/namespace:*,Microsoft.MasterDataServices  
```  
  
 <span data-ttu-id="ae6dc-129">Donde:</span><span class="sxs-lookup"><span data-stu-id="ae6dc-129">Where:</span></span>  
  
-   <span data-ttu-id="ae6dc-130">*servername*:*port* son el nombre de equipo y el número de puerto del equipo que hospeda [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ae6dc-130">*servername*:*port* are the computer name and port number of the computer that hosts [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span></span>  
  
-   <span data-ttu-id="ae6dc-131">*virtual_path* es la ruta de acceso virtual de [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] en Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="ae6dc-131">*virtual_path* is the virtual path of [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] in Internet Information Services (IIS).</span></span>  
  
-   <span data-ttu-id="ae6dc-132">*proxy_name* es el nombre del archivo de proxy generado.</span><span class="sxs-lookup"><span data-stu-id="ae6dc-132">*proxy_name* is the name for the generated proxy file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae6dc-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ae6dc-133">See Also</span></span>  
 [<span data-ttu-id="ae6dc-134">Operaciones de servicio web clasificadas &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="ae6dc-134">Categorized Web Service Operations &#40;Master Data Services&#41;</span></span>](categorized-web-service-operations-master-data-services.md)  
  
  
