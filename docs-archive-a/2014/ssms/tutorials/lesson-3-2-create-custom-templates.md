---
title: Crear plantillas personalizadas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- tql
- templates [Transact-SQL], creating
- templates [Transact-SQL]
ms.assetid: 41098e78-b482-410e-bfe8-2ac10769ac4a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 771547b9c47672d2c075b5e7215d78744fe5f18e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746659"
---
# <a name="create-custom-templates"></a><span data-ttu-id="b5119-102">Crear plantillas personalizadas</span><span class="sxs-lookup"><span data-stu-id="b5119-102">Create Custom Templates</span></span>
  [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="b5119-103">incorpora plantillas para muchas tareas comunes, pero el auténtico valor reside en la posibilidad de crear una plantilla personalizada para un script complejo que tenga que crear con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="b5119-103">comes with templates for many common tasks, but the real power of templates lies in the ability to create a custom template for a complex script that you must create frequently.</span></span> <span data-ttu-id="b5119-104">En esta práctica, creará un script sencillo con unos pocos parámetros; pero las plantillas también son útiles para scripts largos y repetitivos.</span><span class="sxs-lookup"><span data-stu-id="b5119-104">In this practice you will create a simple script with few parameters, but templates are useful for long, repetitive scripts, too.</span></span>  
  
## <a name="using-custom-templates"></a><span data-ttu-id="b5119-105">Usar plantillas personalizadas</span><span class="sxs-lookup"><span data-stu-id="b5119-105">Using Custom Templates</span></span>  
  
#### <a name="to-create-a-custom-template"></a><span data-ttu-id="b5119-106">Para crear una plantilla personalizada</span><span class="sxs-lookup"><span data-stu-id="b5119-106">To create a custom template</span></span>  
  
1.  <span data-ttu-id="b5119-107">En el Explorador de plantillas, expanda **Plantillas de SQL Server**, haga clic con el botón derecho en **Procedimiento almacenado**, seleccione **Nueva**y, después, haga clic en **Carpeta**.</span><span class="sxs-lookup"><span data-stu-id="b5119-107">In Template Explorer, expand **SQL Server Templates**, right-click **Stored Procedure**, point to **New**, and then click **Folder**.</span></span>  
  
2.  <span data-ttu-id="b5119-108">Escriba **Custom** como nombre de la nueva carpeta de plantillas y, después, pulse ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="b5119-108">Type **Custom** as the name of your new template folder, and then press ENTER.</span></span>  
  
3.  <span data-ttu-id="b5119-109">Haga clic con el botón derecho en **Custom**, seleccione **Nueva**y después haga clic en **Plantilla**.</span><span class="sxs-lookup"><span data-stu-id="b5119-109">Right-click **Custom**, point to **New**, and then click **Template**.</span></span>  
  
4.  <span data-ttu-id="b5119-110">Escriba **WorkOrdersProc** como nombre de la plantilla nueva y, después, pulse **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="b5119-110">Type **WorkOrdersProc** as the name of your new template, and then press **Enter**.</span></span>  
  
5.  <span data-ttu-id="b5119-111">Haga clic con el botón derecho en **WorkOrdersProc**y, después, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="b5119-111">Right-click **WorkOrdersProc**, and then click **Edit**.</span></span>  
  
6.  <span data-ttu-id="b5119-112">En el cuadro de diálogo **Conectar al motor de base de datos** compruebe la información de conexión y, después, haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="b5119-112">In the **Connect to Database Engine** dialog box, verify the connection information and then click **Connect**.</span></span>  
  
7.  <span data-ttu-id="b5119-113">En el Editor de consultas, escriba el siguiente script para crear un procedimiento almacenado que busque pedidos de una pieza concreta, en este caso, una cuchilla (Blade).</span><span class="sxs-lookup"><span data-stu-id="b5119-113">In Query Editor, type the following script to create a stored procedure that looks up orders for a particular part, in this case the Blade.</span></span> <span data-ttu-id="b5119-114">Puede copiar y pegar el código de la ventana del tutorial.</span><span class="sxs-lookup"><span data-stu-id="b5119-114">(You can copy and paste the code from the Tutorial window.)</span></span>  
  
    ```  
    USE AdventureWorks20012;  
    GO  
    IF EXISTS (  
    SELECT *   
       FROM INFORMATION_SCHEMA.ROUTINES   
       WHERE SPECIFIC_NAME = 'WorkOrdersForBlade')  
       DROP PROCEDURE dbo.WorkOrdersForBlade;  
    GO  
    CREATE PROCEDURE dbo.WorkOrdersForBlade  
    AS  
    SELECT Name, WorkOrderID   
    FROM Production.WorkOrder AS WO  
    JOIN Production.Product AS Prod  
    ON WO.ProductID = Prod.ProductID  
    WHERE Name = 'Blade';  
    GO  
    ```  
  
8.  <span data-ttu-id="b5119-115">Pulse F5 para ejecutar este script y crear el procedimiento **WorkOrdersForBlade** .</span><span class="sxs-lookup"><span data-stu-id="b5119-115">Press F5 to execute this script, creating the **WorkOrdersForBlade** procedure.</span></span>  
  
9. <span data-ttu-id="b5119-116">En el Explorador de objetos, haga clic con el botón derecho en el servidor y, después, en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="b5119-116">In Object Explorer, right-click your server, and then click **New Query**.</span></span> <span data-ttu-id="b5119-117">Se abrirá una ventana nueva del Editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="b5119-117">A new Query Editor window opens.</span></span>  
  
10. <span data-ttu-id="b5119-118">En el Editor de consultas, escriba **EXECUTE dbo.WorkOrdersForBlade**y, después, pulse F5 para ejecutar la consulta.</span><span class="sxs-lookup"><span data-stu-id="b5119-118">In Query Editor, type **EXECUTE dbo.WorkOrdersForBlade**, and then press F5 to execute the query.</span></span> <span data-ttu-id="b5119-119">Confirme que el panel **Resultados** devuelve una lista de los pedidos de trabajo relativos a cuchillas.</span><span class="sxs-lookup"><span data-stu-id="b5119-119">Confirm that the **Results** pane returns a list of work orders for blades.</span></span>  
  
11. <span data-ttu-id="b5119-120">Edite el script de la plantilla (el script del paso 7) y reemplace el nombre del producto hoja por el parámetro <strong> *<* PRODUCT_NAME</strong>, `nvarchar(50)` , <strong> *>* nombre</strong>, en cuatro lugares.</span><span class="sxs-lookup"><span data-stu-id="b5119-120">Edit the template script (the script in step 7), replacing the product name Blade with the parameter <strong>*<* product_name</strong>, `nvarchar(50)`, <strong>name*>*</strong>, in four places.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b5119-121">Los parámetros requieren tres elementos: el nombre del parámetro que desea reemplazar, el tipo de datos del parámetro y un valor predeterminado para el parámetro.</span><span class="sxs-lookup"><span data-stu-id="b5119-121">Parameters require three elements: the name of the parameter that you want to replace, the data type of the parameter, and a default value for the parameter.</span></span>  
  
12. <span data-ttu-id="b5119-122">Ahora, el script debe tener el aspecto siguiente:</span><span class="sxs-lookup"><span data-stu-id="b5119-122">Now the script should look like:</span></span>  
  
    ```  
    USE AdventureWorks20012;  
    GO  
    IF EXISTS (  
    SELECT *   
       FROM INFORMATION_SCHEMA.ROUTINES   
       WHERE SPECIFIC_NAME = 'WorkOrdersFor<product_name, nvarchar(50), name>')  
       DROP PROCEDURE dbo.WorkOrdersFor<product_name, nvarchar(50), name>;  
    GO  
    CREATE PROCEDURE dbo.WorkOrdersFor<product_name, nvarchar(50), name>  
    AS  
    SELECT Name, WorkOrderID   
    FROM Production.WorkOrder AS WO  
    JOIN Production.Product AS Prod  
    ON WO.ProductID = Prod.ProductID  
    WHERE Name = '<product_name, nvarchar(50), name>';  
    GO  
    ```  
  
13. <span data-ttu-id="b5119-123">En el menú **Archivo** , haga clic en **Guardar WorkOrdersProc.sql** para guardar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="b5119-123">On the **File** menu, click **Save WorkOrdersProc.sql** to save your template.</span></span>  
  
#### <a name="to-test-the-custom-template"></a><span data-ttu-id="b5119-124">Para probar la plantilla personalizada</span><span class="sxs-lookup"><span data-stu-id="b5119-124">To test the custom template</span></span>  
  
1.  <span data-ttu-id="b5119-125">En el Explorador de plantillas, expanda **Procedimiento almacenado**y **Custom**y, después, haga doble clic en **WorkOrderProc**.</span><span class="sxs-lookup"><span data-stu-id="b5119-125">In Template Explorer, expand **Stored Procedure**, expand **Custom**, and then double-click **WorkOrderProc**.</span></span>  
  
2.  <span data-ttu-id="b5119-126">En el cuadro de diálogo **Conectarse al motor de base de datos** , rellene la información de conexión y luego haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="b5119-126">In the **Connect to Database Engine** dialog box, complete the connection information and then click **Connect**.</span></span> <span data-ttu-id="b5119-127">Se abrirá una ventana nueva del Editor de consultas, que incluye el contenido de la plantilla **WorkOrderProc** .</span><span class="sxs-lookup"><span data-stu-id="b5119-127">A new Query Editor window opens, containing the contents of the **WorkOrderProc** template.</span></span>  
  
3.  <span data-ttu-id="b5119-128">En el menú **Consulta** , haga clic en **Especificar valores para parámetros de plantilla**.</span><span class="sxs-lookup"><span data-stu-id="b5119-128">On the **Query** menu, click **Specify Values for Template Parameters**.</span></span>  
  
4.  <span data-ttu-id="b5119-129">En el cuadro de diálogo **reemplazar parámetros de plantilla** , para el `product_name` valor, escriba **Freewheel** (sobrescribiendo el contenido predeterminado) y, a continuación, haga clic en **Aceptar** para cerrar el cuadro de diálogo **reemplazar parámetros de plantilla** y modificar el script en el editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="b5119-129">In the **Replace Template Parameters** dialog box, for the `product_name` value, type **FreeWheel** (overwriting the default contents), and then click **OK** to close the **Replace Template Parameters** dialog box and modify the script in the Query Editor.</span></span>  
  
5.  <span data-ttu-id="b5119-130">Presione F5 para ejecutar la consulta y crear el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="b5119-130">Press F5 to execute the query, creating the procedure.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="b5119-131">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="b5119-131">Next Task in Lesson</span></span>  
 [<span data-ttu-id="b5119-132">Guardar scripts como proyectos o soluciones</span><span class="sxs-lookup"><span data-stu-id="b5119-132">Save Scripts as Projects or Solutions</span></span>](lesson-3-3-save-scripts-as-projects-or-solutions.md)  
  
  
