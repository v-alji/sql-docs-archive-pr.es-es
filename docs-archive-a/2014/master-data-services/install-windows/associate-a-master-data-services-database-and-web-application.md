---
title: Asociar una base de datos y una aplicación web de Master Data Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: ccb25672-f71d-4135-b548-f50eb45d8fa5
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 01afde6aea5065a51cb9e7ae5dc4151e9f1e9fc7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744733"
---
# <a name="associate-a-master-data-services-database-and-web-application"></a><span data-ttu-id="228f4-102">Asociar una base de datos y una aplicación web de Master Data Services</span><span class="sxs-lookup"><span data-stu-id="228f4-102">Associate a Master Data Services Database and Web Application</span></span>
  <span data-ttu-id="228f4-103">Asocie una aplicación web de [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] a una base de datos de [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] para especificar la base de datos que se utilizará en las operaciones web.</span><span class="sxs-lookup"><span data-stu-id="228f4-103">Associate your [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application with a [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database to specify the database to use for web operations.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="228f4-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="228f4-104">Prerequisites</span></span>  
  
-   [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)] <span data-ttu-id="228f4-105">en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="228f4-105">must be installed on the local computer.</span></span> <span data-ttu-id="228f4-106">Para obtener más información, vea [Instalar Master Data Services](install-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="228f4-106">For more information, see [Install Master Data Services](install-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="228f4-107">Debe existir una aplicación web de [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] local.</span><span class="sxs-lookup"><span data-stu-id="228f4-107">A local [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application must exist.</span></span> <span data-ttu-id="228f4-108">Para obtener más información, vea [Crear una aplicación web de Master Data Manager &#40;Master Data Services&#41;](create-a-master-data-manager-web-application-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="228f4-108">For more information, see [Create a Master Data Manager Web Application &#40;Master Data Services&#41;](create-a-master-data-manager-web-application-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="228f4-109">Debe existir una base de datos de [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] local o remota.</span><span class="sxs-lookup"><span data-stu-id="228f4-109">Either a local or remote [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database must exist.</span></span> <span data-ttu-id="228f4-110">Para obtener más información, vea [Crea una base de datos de Master Data Services](create-a-master-data-services-database.md).</span><span class="sxs-lookup"><span data-stu-id="228f4-110">For more information, see [Create a Master Data Services Database](create-a-master-data-services-database.md).</span></span>  
  
### <a name="to-associate-a-master-data-services-database-and-web-application"></a><span data-ttu-id="228f4-111">Para asociar una base de datos y una aplicación web de Master Data Services</span><span class="sxs-lookup"><span data-stu-id="228f4-111">To associate a Master Data Services database and web application</span></span>  
  
1.  <span data-ttu-id="228f4-112">Abra [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="228f4-112">Open [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span></span>  
  
2.  <span data-ttu-id="228f4-113">En el panel izquierdo, haga clic en **Configuración web**.</span><span class="sxs-lookup"><span data-stu-id="228f4-113">In the left pane, click **Web Configuration**.</span></span>  
  
3.  <span data-ttu-id="228f4-114">En la página **Configuración web** , debajo de **Aplicación web**, en la lista **Sitio web** , seleccione el sitio web que contiene su aplicación web de [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="228f4-114">On the **Web Configuration** page, under **Web application**, from the **Website** list, select the website that contains your [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application.</span></span>  
  
4.  <span data-ttu-id="228f4-115">En el cuadro **Aplicación web** , seleccione la aplicación web que hospeda [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="228f4-115">In the **Web application** box, select the web application that hosts [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span></span>  
  
5.  <span data-ttu-id="228f4-116">Debajo de **Asociar una aplicación con una base de datos**, haga clic en **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="228f4-116">Under **Associate Application with Database**, click **Select**.</span></span> <span data-ttu-id="228f4-117">Se abre el cuadro de diálogo **Conectar con base de datos** .</span><span class="sxs-lookup"><span data-stu-id="228f4-117">The **Connect to Database** dialog box opens.</span></span>  
  
6.  <span data-ttu-id="228f4-118">Especifique la información de conexión para la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que hospeda la base de datos [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] y haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="228f4-118">Specify connection information for the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that hosts the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database, and click **Connect**.</span></span>  
  
7.  <span data-ttu-id="228f4-119">En la lista **Base de datos de Master Data Services** , seleccione la base de datos que desee asociar a la aplicación web y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="228f4-119">From the **Master Data Services database** list, select the database you want to associate the web application with and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="228f4-120">En **Asociar una aplicación con una base de datos**, compruebe que la información de las bases de datos y las instancias son correctas y, a continuación, haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="228f4-120">Under **Associate Application with Database**, verify that the instance and database information are correct, and then click **Apply**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="228f4-121">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="228f4-121">Next Steps</span></span>  
  
-   <span data-ttu-id="228f4-122">El acceso mediante programación a los servicio web de [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] se habilita automáticamente cuando se crea la aplicación web.</span><span class="sxs-lookup"><span data-stu-id="228f4-122">Programmatic access to [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] web services is automatically enabled when the web application is created.</span></span> <span data-ttu-id="228f4-123">Para que los desarrolladores tengan acceso a los metadatos del servicio para generar fácilmente clases de proxy para el acceso mediante programación, se debe habilitar la publicación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="228f4-123">To let developers access the service metadata to easily generate proxy classes for programmatic access, enable metadata publishing.</span></span> <span data-ttu-id="228f4-124">Para más información, consulte [Crear clases de proxy del servicio web Master Data Manager](../develop/create-master-data-manager-web-service-proxy-classes.md).</span><span class="sxs-lookup"><span data-stu-id="228f4-124">For more information, see [Create Master Data Manager Web Service Proxy Classes](../develop/create-master-data-manager-web-service-proxy-classes.md).</span></span>  
  
-   <span data-ttu-id="228f4-125">Agregue usuarios y grupos a [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="228f4-125">Add users and groups to [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span></span> <span data-ttu-id="228f4-126">Si no se ha concedido el acceso a [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)]a ningún usuario ni grupo, debe abrir [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] utilizando las credenciales de administrador del sistema de [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="228f4-126">If no users or groups have been granted access to [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)], you must open [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] using the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] system administrator credentials.</span></span> <span data-ttu-id="228f4-127">Para obtener más información, vea [Administradores &#40;Master Data Services&#41;](../administrators-master-data-services.md) y [Usuarios y grupos &#40;Master Data Services&#41;](../users-and-groups-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="228f4-127">For more information, see [Administrators &#40;Master Data Services&#41;](../administrators-master-data-services.md) and [Users and Groups &#40;Master Data Services&#41;](../users-and-groups-master-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="228f4-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="228f4-128">See Also</span></span>  
 <span data-ttu-id="228f4-129">[Instalar Master Data Services](install-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="228f4-129">[Install Master Data Services](install-master-data-services.md) </span></span>  
 [<span data-ttu-id="228f4-130">Página Configuración web &#40;Administrador de configuración de Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="228f4-130">Web Configuration Page &#40;Master Data Services Configuration Manager&#41;</span></span>](../web-configuration-page-master-data-services-configuration-manager.md)  
  
  
