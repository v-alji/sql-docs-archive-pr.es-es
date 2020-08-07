---
title: 'Lección 2: Especificar información de conexión (Reporting Services) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 54405a3a-d7fa-4d95-8963-9aa224e5901e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c187f0abdc4b277a5f1428407b5c42ca4fd6fee6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745671"
---
# <a name="lesson-2-specifying-connection-information-reporting-services"></a><span data-ttu-id="1e745-102">Lección 2: Especificar información de conexión (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="1e745-102">Lesson 2: Specifying Connection Information (Reporting Services)</span></span>
  <span data-ttu-id="1e745-103">Después de agregar un informe al proyecto Tutorial, necesita definir un *origen de datos*, que es la información de conexión que el informe usa para tener acceso a los datos procedentes de una base de datos relacional, una base de datos multidimensional u otro recurso.</span><span class="sxs-lookup"><span data-stu-id="1e745-103">After you add a report to the Tutorial project, you need to define a *data source*, which is connection information the report uses to access data from either a relational database, multidimensional database, or other resource.</span></span>  
  
 <span data-ttu-id="1e745-104">En esta lección usará la base de datos de ejemplo [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] como origen de datos.</span><span class="sxs-lookup"><span data-stu-id="1e745-104">In this lesson, you will use the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] sample database as your data source.</span></span> <span data-ttu-id="1e745-105">En este tutorial se da por supuesto que esta base de datos se encuentra en una instancia predeterminada de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../includes/ssde-md.md)] que está instalada en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="1e745-105">This tutorial assumes that this database is located in a default instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../includes/ssde-md.md)] that is installed on your local computer.</span></span>  
  
### <a name="to-set-up-a-connection"></a><span data-ttu-id="1e745-106">Para configurar una conexión</span><span class="sxs-lookup"><span data-stu-id="1e745-106">To set up a connection</span></span>  
  
1.  <span data-ttu-id="1e745-107">En el panel **datos de informe** , haga clic en **nuevo** y, a continuación, haga clic en **origen de datos.**</span><span class="sxs-lookup"><span data-stu-id="1e745-107">In the **Report Data** pane, click **New** and then click **Data Source...**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1e745-108">Si el panel **Datos de informe** no está visible, haga clic en **Datos de informe** en el menú **Ver**.</span><span class="sxs-lookup"><span data-stu-id="1e745-108">If the **Report Data** pane is not visible, from the **View** menu, click **Report Data**.</span></span>  
  
2.  <span data-ttu-id="1e745-109">En **Nombre**, escriba [!INCLUDE[ssSampleDBUserInputNonLocal](../includes/sssampledbuserinputnonlocal-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1e745-109">In **Name**, type [!INCLUDE[ssSampleDBUserInputNonLocal](../includes/sssampledbuserinputnonlocal-md.md)].</span></span>  
  
3.  <span data-ttu-id="1e745-110">Asegúrese de que está seleccionado **Conexión incrustada** .</span><span class="sxs-lookup"><span data-stu-id="1e745-110">Make sure **Embedded connection** is selected.</span></span>  
  
4.  <span data-ttu-id="1e745-111">En **Tipo**, seleccione **Microsoft SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="1e745-111">In **Type**, select **Microsoft SQL Server**.</span></span>  
  
5.  <span data-ttu-id="1e745-112">En **Cadena de conexión**, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1e745-112">In **Connection string**, type the following:</span></span>  
  
    ```  
    Data source=localhost; initial catalog=AdventureWorks2012  
    ```  
  
     <span data-ttu-id="1e745-113">Esta cadena de conexión da por supuesto que [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], el servidor de informes y la base de datos [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] están instalados en el equipo local, y que el usuario tiene permiso para iniciar una sesión en la base de datos [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1e745-113">This connection string assumes that [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], the report server, and the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database are all installed on the local computer and that you have permission to log on to the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1e745-114">Si utiliza [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] con Advanced Services o una instancia con nombre, la cadena de conexión debe incluir información de la instancia:</span><span class="sxs-lookup"><span data-stu-id="1e745-114">If you are using [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] with Advanced Services or a named instance, the connection string must include instance information:</span></span>  
    >   
    >  `Data source=localhost\SQLEXPRESS; initial catalog=AdventureWorks2012`  
    >   
    >  <span data-ttu-id="1e745-115">Para obtener más información sobre las cadenas de conexión, vea [conexiones de datos, orígenes de datos y cadenas de conexión en Reporting Services](data-connections-data-sources-and-connection-strings-in-reporting-services.md) y [propiedades del origen de datos (cuadro de diálogo), general](data-source-properties-dialog-box-general.md).</span><span class="sxs-lookup"><span data-stu-id="1e745-115">For more information about connection strings, see [Data Connections, Data Sources, and Connection Strings in Reporting Services](data-connections-data-sources-and-connection-strings-in-reporting-services.md) and [Data Source Properties Dialog Box, General](data-source-properties-dialog-box-general.md).</span></span>  
  
6.  <span data-ttu-id="1e745-116">Haga clic en **Credenciales** en el panel izquierdo y haga clic en **Usar autenticación de Windows (seguridad integrada)**.</span><span class="sxs-lookup"><span data-stu-id="1e745-116">Click **Credentials** in the left pane and click **Use Windows Authentication (integrated security)**.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]<span data-ttu-id="1e745-117">origen [!INCLUDE[ssSampleDBnormal](../includes/sssampledbnormal-md.md)] de datos se agrega al panel **datos de informe** .</span><span class="sxs-lookup"><span data-stu-id="1e745-117">data source [!INCLUDE[ssSampleDBnormal](../includes/sssampledbnormal-md.md)] is added to the **Report Data** pane.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="1e745-118">Tarea siguiente</span><span class="sxs-lookup"><span data-stu-id="1e745-118">Next Task</span></span>  
 <span data-ttu-id="1e745-119">Ha definido correctamente una conexión a la base de datos de ejemplo [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1e745-119">You have successfully defined a connection to the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="1e745-120">A continuación, creará el informe.</span><span class="sxs-lookup"><span data-stu-id="1e745-120">Next, you will create the report.</span></span> <span data-ttu-id="1e745-121">Vea [Lección 3: Definir un conjunto de datos para el informe de tabla &#40;Reporting Services&#41;;](lesson-3-defining-a-dataset-for-the-table-report-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="1e745-121">See [Lesson 3: Defining a Dataset for the Table Report &#40;Reporting Services&#41;](lesson-3-defining-a-dataset-for-the-table-report-reporting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e745-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1e745-122">See Also</span></span>  
 [<span data-ttu-id="1e745-123">Data Connections, Data Sources, and Connection Strings in Reporting Services</span><span class="sxs-lookup"><span data-stu-id="1e745-123">Data Connections, Data Sources, and Connection Strings in Reporting Services</span></span>](data-connections-data-sources-and-connection-strings-in-reporting-services.md)  
  
  
