---
title: Proporcionar una consulta de origen (Asistente para importación y exportación de SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.providesourcequery.f1
ms.assetid: c8cbd07e-b9c3-422f-94b8-d6fc8cf31cf5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b21100f51c279e9ba764c8f82565af9d6e391ef3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674919"
---
# <a name="provide-a-source-query-sql-server-import-and-export-wizard"></a><span data-ttu-id="bf34a-102">Proporcionar una consulta de origen (Asistente para importación y exportación de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="bf34a-102">Provide a Source Query (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="bf34a-103">Use la página **proporcionar una consulta de origen** para escribir la instrucción SQL que generará los datos que se van a copiar del origen de datos al destino.</span><span class="sxs-lookup"><span data-stu-id="bf34a-103">Use the **Provide a Source Query** page to type the SQL statement that will generate the data to copy from the data source to the destination.</span></span>  
  
 <span data-ttu-id="bf34a-104">Para obtener más información acerca de este asistente, vea [Asistente para importación y exportación de SQL Server](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="bf34a-104">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="bf34a-105">Para obtener información sobre las opciones para iniciar el asistente, así como los permisos necesarios para ejecutar el asistente correctamente, vea [ejecutar el Asistente para importación y exportación de SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="bf34a-105">To learn about the options for starting the wizard, as well as the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="bf34a-106">La finalidad del Asistente para importación y exportación de SQL Server es copiar datos desde un origen a un destino.</span><span class="sxs-lookup"><span data-stu-id="bf34a-106">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="bf34a-107">El asistente también puede crear una base de datos y tablas de destino.</span><span class="sxs-lookup"><span data-stu-id="bf34a-107">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="bf34a-108">Sin embargo, si tiene que copiar diversas bases de datos o tablas, u otros tipos de objetos de bases de datos, debe utilizar el Asistente para copiar bases de datos.</span><span class="sxs-lookup"><span data-stu-id="bf34a-108">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="bf34a-109">Para más información, consulte [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="bf34a-109">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="bf34a-110">Opciones</span><span class="sxs-lookup"><span data-stu-id="bf34a-110">Options</span></span>  
 <span data-ttu-id="bf34a-111">**Instrucción SQL**</span><span class="sxs-lookup"><span data-stu-id="bf34a-111">**SQL statement**</span></span>  
 <span data-ttu-id="bf34a-112">Escriba una instrucción de consulta para recuperar las filas de datos seleccionadas de la base de datos de origen.</span><span class="sxs-lookup"><span data-stu-id="bf34a-112">Type a query statement to retrieve selected rows of data from the source database.</span></span> <span data-ttu-id="bf34a-113">Por ejemplo, la siguiente instrucción de consulta recupera **SalesPersonID**, **SalesQuota**y **SalesYTD** de la base de datos AdventureWorks para los vendedores con un porcentaje de comisión superior al 1,5%.</span><span class="sxs-lookup"><span data-stu-id="bf34a-113">For example, the following query statement retrieves the **SalesPersonID**, **SalesQuota**, and **SalesYTD** from the AdventureWorks database for sales persons whose commission percentage is more than 1.5 percent.</span></span>  
  
```  
SELECT SalesPersonID, SalesQuota, SalesYTD  
FROM Sales.SalesPerson  
WHERE CommissionPct > 0.015  
```  
  
 <span data-ttu-id="bf34a-114">**Parse**</span><span class="sxs-lookup"><span data-stu-id="bf34a-114">**Parse**</span></span>  
 <span data-ttu-id="bf34a-115">Comprueba la sintaxis de la instrucción SQL en el cuadro de texto **Instrucción SQL**.</span><span class="sxs-lookup"><span data-stu-id="bf34a-115">Checks the syntax of the SQL statement in the **SQL statement** text box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bf34a-116">Si el tiempo necesario para comprobar la sintaxis de la instrucción supera el valor de tiempo de espera de 30 segundos, el análisis se detiene y se genera un error.</span><span class="sxs-lookup"><span data-stu-id="bf34a-116">If the time that is required to check the syntax of the statement exceeds the time-out value of 30 seconds, parsing stops and generates an error.</span></span> <span data-ttu-id="bf34a-117">No podrá pasar esta página del asistente hasta que el análisis se realice correctamente.</span><span class="sxs-lookup"><span data-stu-id="bf34a-117">You will not be able to move past this page of the wizard until parsing succeeds.</span></span> <span data-ttu-id="bf34a-118">Una solución es crear una vista de base de datos basada en la consulta y consultar la vista del asistente, en lugar de escribir directamente el texto de la consulta.</span><span class="sxs-lookup"><span data-stu-id="bf34a-118">One solution is to create a database view based on the query, and to query the view from the wizard, instead of entering the query text directly.</span></span>  
  
 <span data-ttu-id="bf34a-119">**Browse**</span><span class="sxs-lookup"><span data-stu-id="bf34a-119">**Browse**</span></span>  
 <span data-ttu-id="bf34a-120">Seleccione un archivo que contenga una instrucción SQL mediante el cuadro de diálogo **abrir** .</span><span class="sxs-lookup"><span data-stu-id="bf34a-120">Select a file containing a SQL statement by using the **Open** dialog box.</span></span> <span data-ttu-id="bf34a-121">Al seleccionar un archivo se copiará el texto del archivo en el cuadro de texto **Instrucción de consulta** .</span><span class="sxs-lookup"><span data-stu-id="bf34a-121">Selecting a file copies the text from the file into the **Query statement** text box.</span></span>  
  
  
