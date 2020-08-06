---
title: Crear un origen de datos (tutorial básico de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d7107c32-69ed-49a8-9b6e-32753eebf42c
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: d8d5974c3685476f5d7a5751fb71bfa98384cf36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671283"
---
# <a name="creating-a-data-source-basic-data-mining-tutorial"></a><span data-ttu-id="dae39-102">Crear un origen de datos (Tutorial básico de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="dae39-102">Creating a Data Source (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="dae39-103">Un *origen de datos* es una conexión de datos que se guarda y administra en el proyecto y se implementa en la base de datos [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dae39-103">A *data source* is a data connection that is saved and managed in your project and deployed to your [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="dae39-104">El origen de datos contiene los nombres del servidor y la base de datos donde residen los datos de origen, además de otras propiedades de conexión necesarias.</span><span class="sxs-lookup"><span data-stu-id="dae39-104">The data source contains the names of the server and database where your source data resides, in addition to any other required connection properties.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="dae39-105">El nombre de la base de datos es [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dae39-105">The name of the database is [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)].</span></span> <span data-ttu-id="dae39-106">Si aún no ha instalado esta base de datos, vea la página bases de datos de [ejemplo de Microsoft SQL](https://go.microsoft.com/fwlink/?LinkId=88417) .</span><span class="sxs-lookup"><span data-stu-id="dae39-106">If you have not already installed this database, see the [Microsoft SQL Sample Databases](https://go.microsoft.com/fwlink/?LinkId=88417) page.</span></span>  
  
### <a name="to-create-a-data-source"></a><span data-ttu-id="dae39-107">Para crear un origen de datos</span><span class="sxs-lookup"><span data-stu-id="dae39-107">To create a data source</span></span>  
  
1.  <span data-ttu-id="dae39-108">En **Explorador de soluciones**, haga clic con el botón secundario en la carpeta **orígenes de datos** y seleccione **nuevo origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="dae39-108">In **Solution Explorer**, right-click the **Data Sources** folder and select **New Data Source**.</span></span>  
  
2.  <span data-ttu-id="dae39-109">En la página inicial del **Asistente para orígenes de datos** , haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="dae39-109">On the **Welcome to the Data Source Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="dae39-110">En la página **seleccionar cómo definir la conexión** , haga clic en **nuevo** para agregar una conexión a la [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] base de datos.</span><span class="sxs-lookup"><span data-stu-id="dae39-110">On the **Select how to define the connection** page, click **New** to add a connection to the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] database.</span></span>  
  
4.  <span data-ttu-id="dae39-111">En la lista **proveedor** del **Administrador de conexiones**, seleccione **OLE DB nativo\sql Server Native Client 11,0**.</span><span class="sxs-lookup"><span data-stu-id="dae39-111">In the **Provider** list in **Connection Manager**, select **Native OLE DB\SQL Server Native Client 11.0**.</span></span>  
  
5.  <span data-ttu-id="dae39-112">En el cuadro **nombre del servidor** , escriba o seleccione el nombre del servidor en el que ha instalado [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dae39-112">In the **Server name** box, type or select the name of the server on which you installed [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)].</span></span>  
  
     <span data-ttu-id="dae39-113">Por ejemplo, escriba **localhost** si la base de datos está hospedada en el servidor local.</span><span class="sxs-lookup"><span data-stu-id="dae39-113">For example, type **localhost** if the database is hosted on the local server.</span></span>  
  
6.  <span data-ttu-id="dae39-114">En el grupo **iniciar sesión en el servidor** , seleccione **usar autenticación de Windows**.</span><span class="sxs-lookup"><span data-stu-id="dae39-114">In the **Log onto the server** group, select **Use Windows Authentication**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="dae39-115">Siempre que sea posible, los implementadores deberían utilizar la autenticación de Windows, ya que proporciona un método de autenticación más seguro que la autenticación de SOL Server.</span><span class="sxs-lookup"><span data-stu-id="dae39-115">Whenever possible, implementers should use Windows Authentication, as it provides a more secure authentication method than SQL Server Authentication.</span></span> <span data-ttu-id="dae39-116">Sin embargo, la autenticación de SQL Server se proporciona por motivos de compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="dae39-116">However, SQL Server Authentication is provided for backward compatibility.</span></span> <span data-ttu-id="dae39-117">Para obtener más información acerca de los métodos de autenticación, consulte [configuración de motor de base de datos: aprovisionamiento de cuentas](../../2014/sql-server/install/database-engine-configuration-account-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="dae39-117">For more information about authentication methods, see [Database Engine Configuration - Account Provisioning](../../2014/sql-server/install/database-engine-configuration-account-provisioning.md).</span></span>  
  
7.  <span data-ttu-id="dae39-118">En la lista **Seleccione o escriba un nombre de base de datos** , seleccione [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="dae39-118">In the **Select or enter a database name** list, select [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="dae39-119">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="dae39-119">Click **Next**.</span></span>  
  
9. <span data-ttu-id="dae39-120">En la página **información de suplantación** , haga clic en **usar la cuenta de servicio**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="dae39-120">On the **Impersonation Information** page, click **Use the service account**, and then click **Next**.</span></span>  
  
     <span data-ttu-id="dae39-121">En la página **finalización del asistente** , observe que, de forma predeterminada, el origen de datos se denomina Adventure Works DW 2012.</span><span class="sxs-lookup"><span data-stu-id="dae39-121">On the **Completing the Wizard** page, notice that, by default, the data source is named Adventure Works DW 2012.</span></span>  
  
10. <span data-ttu-id="dae39-122">Haga clic en **Finalizar**</span><span class="sxs-lookup"><span data-stu-id="dae39-122">Click **Finish**.</span></span>  
  
     <span data-ttu-id="dae39-123">El nuevo origen de datos, Adventure Works DW 2012, aparece en la carpeta **orígenes de datos** de explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="dae39-123">The new data source, Adventure Works DW 2012, appears in the **Data Sources** folder in Solution Explorer.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="dae39-124">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="dae39-124">Next Task in Lesson</span></span>  
 [<span data-ttu-id="dae39-125">Crear una vista del origen de datos &#40;tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="dae39-125">Creating a Data Source View &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-data-source-view-basic-data-mining-tutorial.md)  
  
## <a name="previous-task-in-lesson"></a><span data-ttu-id="dae39-126">Tarea anterior de la lección</span><span class="sxs-lookup"><span data-stu-id="dae39-126">Previous Task in Lesson</span></span>  
 [<span data-ttu-id="dae39-127">Crear un proyecto de Analysis Services &#40;tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="dae39-127">Creating an Analysis Services Project &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-an-analysis-services-project-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="dae39-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dae39-128">See Also</span></span>  
 <span data-ttu-id="dae39-129">[Crear un origen de datos &#40;&#41;de SSAS multidimensional](https://docs.microsoft.com/analysis-services/multidimensional-models/create-a-data-source-ssas-multidimensional) </span><span class="sxs-lookup"><span data-stu-id="dae39-129">[Create a Data Source &#40;SSAS Multidimensional&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/create-a-data-source-ssas-multidimensional) </span></span>  
 <span data-ttu-id="dae39-130">[Definir un origen de datos](../analysis-services/lesson-1-2-defining-a-data-source.md) </span><span class="sxs-lookup"><span data-stu-id="dae39-130">[Defining a Data Source](../analysis-services/lesson-1-2-defining-a-data-source.md) </span></span>  
 [<span data-ttu-id="dae39-131">Establezca las opciones de suplantación &#40;SSAS - multidimensional&#41;</span><span class="sxs-lookup"><span data-stu-id="dae39-131">Set Impersonation Options &#40;SSAS - Multidimensional&#41;</span></span>](https://docs.microsoft.com/analysis-services/multidimensional-models/set-impersonation-options-ssas-multidimensional)  
  
  
