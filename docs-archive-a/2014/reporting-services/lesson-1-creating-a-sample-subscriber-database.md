---
title: 'Lección 1: Crear una base de datos de suscriptor de ejemplo | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 47a882b7-efe5-4ee6-bef4-06118eb56903
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6ee49f0858b28c0c4b00fd391b0db7b4d2c54b16
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751809"
---
# <a name="lesson-1-creating-a-sample-subscriber-database"></a><span data-ttu-id="3d10d-102">Lección 1: Crear una base de datos de suscriptor de ejemplo</span><span class="sxs-lookup"><span data-stu-id="3d10d-102">Lesson 1: Creating a Sample Subscriber Database</span></span>
  <span data-ttu-id="3d10d-103">Antes de que pueda definir una suscripción controlada por datos, debe disponer de un origen de datos que proporcione datos de suscripción.</span><span class="sxs-lookup"><span data-stu-id="3d10d-103">Before you can define a data-driven subscription, you must have a data source that provides subscription data.</span></span> <span data-ttu-id="3d10d-104">En este paso, creará una pequeña base de datos para almacenar los datos de suscripción utilizados en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="3d10d-104">In this step, you will create a small database to store the subscription data used in this tutorial.</span></span> <span data-ttu-id="3d10d-105">Más adelante, cuando la suscripción se haya procesado, el servidor de informes recupera estos datos y los utiliza para personalizar los resultados del informe, las opciones de entrega y el formato de presentación del informe.</span><span class="sxs-lookup"><span data-stu-id="3d10d-105">Later, when the subscription is processed, the report server retrieves this data and uses it to customize report output, delivery options, and report presentation format.</span></span>  
  
 <span data-ttu-id="3d10d-106">En esta lección se supone que está usando [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] para crear una [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] base de datos.</span><span class="sxs-lookup"><span data-stu-id="3d10d-106">This lesson assumes you are using [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] to create a [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] database.</span></span>  
  
### <a name="to-create-a-sample-subscriber-database"></a><span data-ttu-id="3d10d-107">Para crear una base de datos de suscriptor de ejemplo</span><span class="sxs-lookup"><span data-stu-id="3d10d-107">To create a sample Subscriber database</span></span>  
  
1.  <span data-ttu-id="3d10d-108">Inicie [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] y abra una conexión a un [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3d10d-108">Start [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], and open a connection to a [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3d10d-109">Haga clic con el botón derecho en Bases de datos y seleccione **Nueva base de datos...** .</span><span class="sxs-lookup"><span data-stu-id="3d10d-109">Right-click on Databases, select **New Database...**.</span></span>  
  
3.  <span data-ttu-id="3d10d-110">En el cuadro de diálogo nueva base de datos, en nombre de la base de datos, escriba *Subscribers*.</span><span class="sxs-lookup"><span data-stu-id="3d10d-110">In the New Database dialog box, in Database Name, type *Subscribers*.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
4.  <span data-ttu-id="3d10d-111">Haga clic en el botón **Nueva consulta** de la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="3d10d-111">Click the **New Query** button on the toolbar.</span></span>  
  
5.  <span data-ttu-id="3d10d-112">Copie las siguientes instrucciones [!INCLUDE[tsql](../includes/tsql-md.md)] en la consulta vacía:</span><span class="sxs-lookup"><span data-stu-id="3d10d-112">Copy the following [!INCLUDE[tsql](../includes/tsql-md.md)] statements into the empty query:</span></span>  
  
    ```  
    Use Subscribers  
    CREATE TABLE [dbo].[OrderInfo] (  
        [SubscriptionID] [int] NOT NULL PRIMARY KEY ,  
        [Order] [nvarchar] (20) NOT NULL,  
        [FileType] [bit],  
        [Format] [nvarchar] (20) NOT NULL ,  
    ) ON [PRIMARY]  
    GO  
  
    INSERT INTO [dbo].[OrderInfo] (SubscriptionID, [Order], FileType, Format)   
    VALUES ('1', 'so43659', '1', 'IMAGE')  
    INSERT INTO [dbo].[OrderInfo] (SubscriptionID, [Order], FileType, Format)   
    VALUES ('2', 'so43664', '1', 'MHTML')  
    INSERT INTO [dbo].[OrderInfo] (SubscriptionID, [Order], FileType, Format)   
    VALUES ('3', 'so43668', '1', 'PDF')  
    INSERT INTO [dbo].[OrderInfo] (SubscriptionID, [Order], FileType, Format)   
    VALUES ('4', 'so71949', '1', 'Excel')  
    GO  
    ```  
  
6.  <span data-ttu-id="3d10d-113">Haga clic en **! en Ejecutar** en la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="3d10d-113">Click **! Execute** on the toolbar.</span></span>  
  
7.  <span data-ttu-id="3d10d-114">Use una instrucción SELECT para comprobar que tiene tres filas de datos.</span><span class="sxs-lookup"><span data-stu-id="3d10d-114">Use a SELECT statement to verify that you have three rows of data.</span></span> <span data-ttu-id="3d10d-115">Por ejemplo: `select * from OrderInfo`</span><span class="sxs-lookup"><span data-stu-id="3d10d-115">For example: `select * from OrderInfo`</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="3d10d-116">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="3d10d-116">Next Steps</span></span>  
 <span data-ttu-id="3d10d-117">Ha creado correctamente los datos de suscripción que controlarán la distribución de informes y cambiarán los resultados del informe para cada suscriptor.</span><span class="sxs-lookup"><span data-stu-id="3d10d-117">You have successfully created the subscription data that will drive report distribution and vary the report output for each subscriber.</span></span> <span data-ttu-id="3d10d-118">A continuación, modificará las propiedades del origen de datos del informe que distribuirá a los suscriptores.</span><span class="sxs-lookup"><span data-stu-id="3d10d-118">Next, you will modify the data source properties of the report you will distribute to subscribers.</span></span> <span data-ttu-id="3d10d-119">Las propiedades del origen de datos se modifican con el fin de preparar el informe para la entrega de la suscripción controlada por datos.</span><span class="sxs-lookup"><span data-stu-id="3d10d-119">Modifying the data source properties is done to prepare the report for data-driven subscription delivery.</span></span> <span data-ttu-id="3d10d-120">Además, modificará el diseño de informe para que incluya un parámetro usará la suscripción con los datos del suscriptor.</span><span class="sxs-lookup"><span data-stu-id="3d10d-120">You will also modify the report design to include a parameter that the subscription will use with the subscriber data.</span></span> <span data-ttu-id="3d10d-121">[Lección 2: modificar las propiedades del origen de datos del informe](lesson-2-modifying-the-report-data-source-properties.md).</span><span class="sxs-lookup"><span data-stu-id="3d10d-121">[Lesson 2: Modifying the Report Data Source Properties](lesson-2-modifying-the-report-data-source-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d10d-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3d10d-122">See Also</span></span>  
 <span data-ttu-id="3d10d-123">[Crear una suscripción controlada por datos &#40;Tutorial de SSRS&#41;](create-a-data-driven-subscription-ssrs-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="3d10d-123">[Create a Data-Driven Subscription &#40;SSRS Tutorial&#41;](create-a-data-driven-subscription-ssrs-tutorial.md) </span></span>  
 <span data-ttu-id="3d10d-124">[Crear una base de datos](../relational-databases/databases/create-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="3d10d-124">[Create a Database](../relational-databases/databases/create-a-database.md) </span></span>  
 [<span data-ttu-id="3d10d-125">Crear un informe de tabla básico &#40;Tutorial de SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="3d10d-125">Create a Basic Table Report &#40;SSRS Tutorial&#41;</span></span>](create-a-basic-table-report-ssrs-tutorial.md)  
  
  
